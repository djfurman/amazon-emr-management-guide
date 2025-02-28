# Understand node types: master, core, and task nodes<a name="emr-master-core-task-nodes"></a>

Use this section to understand how Amazon EMR uses each of these node types and as a foundation for cluster capacity planning\.

## Master node<a name="emr-plan-master"></a>

The master node manages the cluster and typically runs master components of distributed applications\. For example, the master node runs the YARN ResourceManager service to manage resources for applications\. It also runs the HDFS NameNode service, tracks the status of jobs submitted to the cluster, and monitors the health of the instance groups\.

To monitor the progress of a cluster and interact directly with applications, you can connect to the master node over SSH as the Hadoop user\. For more information, see [Connect to the master node using SSH](emr-connect-master-node-ssh.md)\. Connecting to the master node allows you to access directories and files, such as Hadoop log files, directly\. For more information, see [View log files](emr-manage-view-web-log-files.md)\. You can also view user interfaces that applications publish as websites running on the master node\. For more information, see [View web interfaces hosted on Amazon EMR clusters](emr-web-interfaces.md)\. 

**Note**  
With Amazon EMR 5\.23\.0 and later, you can launch a cluster with three master nodes to support high availability of applications like YARN Resource Manager, HDFS Name Node, Spark, Hive, and Ganglia\. The master node is no longer a potential single point of failure with this feature\. If one of the master nodes fails, Amazon EMR automatically fails over to a standby master node and replaces the failed master node with a new one with the same configuration and bootstrap actions\. For more information, see [Plan and Configure Master Nodes](https://docs.aws.amazon.com/emr/latest/ManagementGuide/emr-plan-ha.html)\.

## Core nodes<a name="emr-plan-core"></a>

Core nodes are managed by the master node\. Core nodes run the Data Node daemon to coordinate data storage as part of the Hadoop Distributed File System \(HDFS\)\. They also run the Task Tracker daemon and perform other parallel computation tasks on data that installed applications require\. For example, a core node runs YARN NodeManager daemons, Hadoop MapReduce tasks, and Spark executors\.

There is only one core instance group or instance fleet per cluster, but there can be multiple nodes running on multiple EC2 instances in the instance group or instance fleet\. With instance groups, you can add and remove EC2 instances while the cluster is running\. You can also set up automatic scaling to add instances based on the value of a metric\. For more information about adding and removing EC2 instances with the instance groups configuration, see [Scaling cluster resources](emr-scale-on-demand.md)\.

With instance fleets, you can effectively add and remove instances by modifying the instance fleet's *target capacities* for On\-Demand and Spot accordingly\. For more information about target capacities, see [Instance fleet options](emr-instance-fleet.md#emr-instance-fleet-options)\.

**Warning**  
Removing HDFS daemons from a running core node or terminating core nodes risks data loss\. Use caution when configuring core nodes to use Spot Instances\. For more information, see [When should you use Spot Instances?](emr-plan-instances-guidelines.md#emr-plan-spot-instances)\.

## Task nodes<a name="emr-plan-task"></a>

You can use task nodes to add power to perform parallel computation tasks on data, such as Hadoop MapReduce tasks and Spark executors\. Task nodes don't run the Data Node daemon, nor do they store data in HDFS\. As with core nodes, you can add task nodes to a cluster by adding EC2 instances to an existing uniform instance group or by modifying target capacities for a task instance fleet\.

With the uniform instance group configuration, you can have up to a total of 48 task instance groups\. The ability to add instance groups in this way allows you to mix EC2 instance types and pricing options, such as On\-Demand Instances and Spot Instances\. This gives you flexibility to respond to workload requirements in a cost\-effective way\.

With the instance fleet configuration, the ability to mix instance types and purchasing options is built in, so there is only one task instance fleet\.

Because Spot Instances are often used to run task nodes, Amazon EMR has default functionality for scheduling YARN jobs so that running jobs do not fail when task nodes running on Spot Instances are terminated\. Amazon EMR does this by allowing application master processes to run only on core nodes\. The application master process controls running jobs and needs to stay alive for the life of the job\.

Amazon EMR release version 5\.19\.0 and later uses the built\-in [YARN node labels](https://hadoop.apache.org/docs/current/hadoop-yarn/hadoop-yarn-site/NodeLabel.html) feature to achieve this\. \(Earlier versions used a code patch\)\. Properties in the `yarn-site` and `capacity-scheduler` configuration classifications are configured by default so that the YARN capacity\-scheduler and fair\-scheduler take advantage of node labels\. Amazon EMR automatically labels core nodes with the `CORE` label, and sets properties so that application masters are scheduled only on nodes with the CORE label\. Manually modifying related properties in the yarn\-site and capacity\-scheduler configuration classifications, or directly in associated XML files, could break this feature or modify this functionality\.

Beginning with Amazon EMR 6\.x release series, the YARN node labels feature is disabled by default\. The application master processes can run on both core and task nodes by default\. You can enable the YARN node labels feature by configuring following properties: 
+ `yarn.node-labels.enabled: true`
+ `yarn.node-labels.am.default-node-label-expression: 'CORE'`

For information about specific properties, see [Amazon EMR settings to prevent job failure because of task node Spot Instance termination](emr-plan-instances-guidelines.md#emr-plan-spot-YARN)\.