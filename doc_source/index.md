# Amazon EMR Management Guide

-----
*****Copyright &copy; Amazon Web Services, Inc. and/or its affiliates. All rights reserved.*****

-----
Amazon's trademarks and trade dress may not be used in 
     connection with any product or service that is not Amazon's, 
     in any manner that is likely to cause confusion among customers, 
     or in any manner that disparages or discredits Amazon. All other 
     trademarks not owned by Amazon are the property of their respective
     owners, who may or may not be affiliated with, connected to, or 
     sponsored by Amazon.

-----
## Contents
+ [What is Amazon EMR?](emr-what-is-emr.md)
   + [Overview of Amazon EMR](emr-overview.md)
   + [Benefits of using Amazon EMR](emr-overview-benefits.md)
   + [Overview of Amazon EMR architecture](emr-overview-arch.md)
+ [Setting up Amazon EMR](emr-setting-up.md)
+ [Tutorial: Getting started with Amazon EMR](emr-gs.md)
+ [Amazon EMR Studio](emr-studio.md)
   + [How Amazon EMR Studio works](how-emr-studio-works.md)
   + [Considerations and limitations](emr-studio-considerations.md)
   + [Set up and manage an Amazon EMR Studio](emr-studio-set-up.md)
      + [Enable AWS Single Sign-On for Amazon EMR Studio](emr-studio-enable-sso.md)
      + [Set up Amazon EMR on EKS for your Studio](emr-studio-create-eks-cluster.md)
      + [EMR Studio security and access control](emr-studio-security.md)
         + [Create an EMR Studio service role](emr-studio-service-role.md)
         + [Create an EMR Studio user role with session policies](emr-studio-user-role.md)
         + [Define security groups to control EMR Studio network traffic](emr-studio-security-groups.md)
         + [Establish access and permissions for Git-based repositories](emr-studio-enable-git.md)
      + [Add required permissions to create and manage an EMR Studio](emr-studio-admin-permissions.md)
      + [Create an EMR Studio](emr-studio-create-studio.md)
      + [Manage users and groups assigned to your Amazon EMR Studio](emr-studio-manage-users.md)
      + [Manage and monitor an Amazon EMR Studio](emr-studio-manage-studio.md)
      + [Create AWS CloudFormation templates for Amazon EMR Studio](emr-studio-cluster-templates.md)
      + [Optimize Spark jobs in EMR Studio](emr-studio-spark-optimization.md)
   + [Work in an Amazon EMR Studio](work-with-an-emr-studio.md)
      + [Workspaces in Amazon EMR Studio](emr-studio-configure-workspace.md)
      + [Attach a cluster to your Workspace](emr-studio-create-use-clusters.md)
      + [Link Git-based repositories to an EMR Studio Workspace](emr-studio-git-repo.md)
      + [Diagnose applications and jobs with EMR Studio](emr-studio-debug.md)
      + [Install and use kernels and libraries](emr-studio-install-libraries-and-kernels.md)
      + [Enhance kernels with magic commands](emr-studio-magics.md)
+ [EMR Notebooks](emr-managed-notebooks.md)
   + [Considerations when using EMR Notebooks](emr-managed-notebooks-considerations.md)
   + [Creating a Notebook](emr-managed-notebooks-create.md)
   + [Working with EMR Notebooks](emr-managed-notebooks-working-with.md)
   + [Sample commands to execute EMR Notebooks programmatically](emr-managed-notebooks-headless.md)
      + [Notebook execution CLI command samples](emr-managed-notebooks-headless-cli.md)
      + [Notebook execution Python samples](emr-managed-notebooks-headless-python.md)
      + [Notebook execution Ruby samples](emr-managed-notebooks-headless-ruby.md)
   + [Enabling user impersonation to monitor Spark user and job activity](emr-managed-notebooks-spark-monitor.md)
   + [EMR notebooks security and access control](emr-managed-notebooks-security.md)
   + [Installing and using kernels and libraries](emr-managed-notebooks-installing-libraries-and-kernels.md)
   + [Associating Git-based repositories with EMR Notebooks](emr-git-repo.md)
      + [Prerequisites and considerations](emr-managed-notebooks-git-considerations.md)
      + [Add a Git-based repository to Amazon EMR](emr-git-repo-add.md)
      + [Update or delete a Git-based repository](emr-git-repo-delete.md)
      + [Link or unlink a Git-based repository](emr-git-repo-link.md)
      + [Create a new Notebook with an associated Git repository](emr-git-repo-create-notebook.md)
      + [Use Git repositories in a Notebook](emr-git-repo-open.md)
+ [Plan and configure clusters](emr-plan.md)
   + [Launch a cluster with Quick Options](emr-launch-with-quick-options.md)
   + [Configure cluster location and data storage](emr-cluster-location-data-storage.md)
      + [Choose an AWS Region](emr-plan-region.md)
      + [Work with storage and file systems](emr-plan-file-systems.md)
      + [Prepare input data](emr-plan-input.md)
         + [Types of input Amazon EMR can accept](emr-plan-input-accept.md)
         + [How to get data into Amazon EMR](emr-plan-get-data-in.md)
            + [Upload data to Amazon S3](emr-plan-upload-s3.md)
            + [Import files with distributed cache](emr-plan-input-distributed-cache.md)
            + [How to process compressed files](HowtoProcessGzippedFiles.md)
            + [Import DynamoDB data into Hive](emr-plan-input-dynamodb.md)
            + [Connect to data with AWS Direct Connect](emr-plan-input-directconnect.md)
            + [Upload large amounts of data with AWS Snowball](emr-plan-input-snowball.md)
      + [Configure an output location](emr-plan-output.md)
         + [What formats can Amazon EMR return?](emr-plan-output-formats.md)
         + [How to write data to an Amazon S3 bucket you don't own](emr-s3-acls.md)
         + [Compress the output of your cluster](emr-plan-output-compression.md)
   + [Plan and configure master nodes](emr-plan-ha.md)
      + [Supported applications and features](emr-plan-ha-applications.md)
      + [Launch an EMR Cluster with multiple master nodes](emr-plan-ha-launch.md)
      + [EMR integration with EC2 placement groups](emr-plan-ha-placementgroup.md)
      + [Considerations and best practices](emr-plan-ha-considerations.md)
   + [EMR clusters on AWS Outposts](emr-plan-outposts.md)
   + [EMR clusters on AWS Local Zones](emr-plan-localzones.md)
   + [Configure Docker](emr-plan-docker.md)
   + [Use EMR File System (EMRFS)](emr-fs.md)
      + [Consistent view](emr-plan-consistent-view.md)
         + [Enable consistent view](enable-consistent-view.md)
         + [Understanding how EMRFS consistent view tracks objects in Amazon S3](emrfs-files-tracked.md)
         + [Retry logic](emrfs-retry-logic.md)
         + [EMRFS consistent view metadata](emrfs-metadata.md)
         + [Configure consistency notifications for CloudWatch and Amazon SQS](emrfs-configure-sqs-cw.md)
         + [Configure consistent view](emrfs-configure-consistent-view.md)
         + [EMRFS CLI Command Reference](emrfs-cli-reference.md)
      + [Authorizing access to EMRFS data in Amazon S3](emr-plan-credentialsprovider.md)
      + [Managing the default AWS Security Token Service endpoint](emr-emrfs-sts-endpoint.md)
      + [Specifying Amazon S3 encryption using EMRFS properties](emr-emrfs-encryption.md)
         + [Amazon S3 client-side encryption](emr-emrfs-encryption-cse.md)
   + [Control cluster termination](emr-plan-termination.md)
      + [Configuring a cluster to auto-terminate or continue](emr-plan-longrunning-transient.md)
      + [Using termination protection](UsingEMR_TerminationProtection.md)
   + [Working with Amazon Linux AMIs in Amazon EMR](emr-ami.md)
      + [Using the default Amazon Linux AMI for Amazon EMR](emr-default-ami.md)
      + [Using a custom AMI](emr-custom-ami.md)
      + [Specifying a custom AMI](emr-specify-custom-ami.md)
      + [Specifying the Amazon EBS root device volume size](emr-custom-ami-boot-volume-size.md)
   + [Configure cluster software](emr-plan-software.md)
      + [Create bootstrap actions to install additional software](emr-plan-bootstrap.md)
   + [Configure cluster hardware and networking](emr-plan-instances.md)
      + [Understand node types: master, core, and task nodes](emr-master-core-task-nodes.md)
      + [Configure EC2 instances](emr-plan-ec2-instances.md)
         + [Supported instance types](emr-supported-instance-types.md)
         + [Instance purchasing options](emr-instance-purchasing-options.md)
         + [Instance storage](emr-plan-storage.md)
      + [Configure networking](emr-plan-vpc-subnet.md)
         + [Amazon VPC options](emr-clusters-in-a-vpc.md)
         + [Set up a VPC to host clusters](emr-vpc-host-job-flows.md)
         + [Launch clusters into a VPC](emr-vpc-launching-job-flows.md)
         + [Minimum Amazon S3 policy for private subnet](private-subnet-iampolicy.md)
      + [Create a cluster with instance fleets or uniform instance groups](emr-instance-group-configuration.md)
         + [Configure instance fleets](emr-instance-fleet.md)
         + [Use capacity reservations with instance fleets](on-demand-capacity-reservations.md)
         + [Configure uniform instance groups](emr-uniform-instance-group.md)
         + [Cluster configuration guidelines and best practices](emr-plan-instances-guidelines.md)
   + [Configure cluster logging and debugging](emr-plan-debugging.md)
   + [Tag clusters](emr-plan-tags.md)
      + [Tag restrictions](emr-plan-tags-restrictions.md)
      + [Tag resources for billing](emr-plan-tags-billing.md)
      + [Add tags to a new cluster](emr-plan-tags-add-new.md)
      + [Adding tags to an existing cluster](emr-plan-tags-add.md)
      + [View tags on a cluster](emr-plan-tags-view.md)
      + [Remove tags from a cluster](emr-plan-tags-delete.md)
   + [Drivers and third-party application integration](emr-plan-third-party.md)
      + [Use business intelligence tools with Amazon EMR](emr-bi-tools.md)
+ [Security in Amazon EMR](emr-security.md)
   + [Use security configurations to set up cluster security](emr-security-configurations.md)
      + [Create a security configuration](emr-create-security-configuration.md)
      + [Specify a security configuration for a cluster](emr-specify-security-configuration.md)
   + [Data protection in Amazon EMR](data-protection.md)
      + [Encrypt data at rest and in transit](emr-data-encryption.md)
         + [Encryption options](emr-data-encryption-options.md)
         + [Create keys and certificates for data encryption](emr-encryption-enable.md)
   + [AWS Identity and Access Management for Amazon EMR](emr-plan-access-iam.md)
      + [How Amazon EMR works with IAM](security_iam_emr-with-iam.md)
      + [Configure IAM service roles for Amazon EMR permissions to AWS services and resources](emr-iam-roles.md)
         + [IAM service roles used by Amazon EMR](emr-iam-service-roles.md)
            + [Service role for Amazon EMR (EMR role)](emr-iam-role.md)
            + [Service role for cluster EC2 instances (EC2 instance profile)](emr-iam-role-for-ec2.md)
            + [Service role for automatic scaling in EMR (Auto Scaling role)](emr-iam-role-automatic-scaling.md)
            + [Service role for EMR Notebooks](emr-managed-notebooks-service-role.md)
            + [Using the service-linked role for Amazon EMR](using-service-linked-roles.md)
         + [Customize IAM roles](emr-iam-roles-custom.md)
         + [Configure IAM roles for EMRFS requests to Amazon S3](emr-emrfs-iam-roles.md)
         + [Use resource-based policies for Amazon EMR access to AWS Glue Data Catalog](emr-iam-roles-glue.md)
         + [Use IAM roles with applications that call AWS services directly](emr-iam-roles-calling.md)
         + [Allow users and groups to create and modify roles](emr-iam-roles-create-permissions.md)
      + [Amazon EMR identity-based policy examples](security_iam_id-based-policy-examples.md)
         + [Policy best practices for Amazon EMR](security_iam_emr-with-iam-policy-best-practices.md)
         + [Allow users to view their own permissions](security_iam_id-based-policy-examples-view-own-permissions.md)
         + [Amazon EMR managed policies](emr-managed-iam-policies.md)
            + [IAM managed policy for full access (v2 managed default policy)](emr-managed-policy-fullaccess-v2.md)
            + [IAM managed policy for full access (on path to deprecation)](emr-managed-policy-fullaccess.md)
            + [IAM managed policy for read-only access (v2 managed default policy)](emr-managed-policy-readonly-v2.md)
            + [IAM managed policy for read-only access (on path to deprecation)](emr-managed-policy-readonly.md)
         + [IAM policies for tag-based access to clusters and EMR notebooks](emr-fine-grained-cluster-access.md)
         + [Denying the ModifyInstanceGroup action](emr-cluster-deny-modifyinstancegroup.md)
   + [Authenticate to Amazon EMR cluster nodes](emr-authenticate-cluster-connections.md)
      + [Use an Amazon EC2 key pair for SSH credentials](emr-plan-access-ssh.md)
      + [Use Kerberos authentication](emr-kerberos.md)
         + [Supported applications](emr-kerberos-principals.md)
         + [Kerberos architecture options](emr-kerberos-options.md)
         + [Configuring Kerberos on Amazon EMR](emr-kerberos-configure.md)
            + [Security configuration and cluster settings for Kerberos on Amazon EMR](emr-kerberos-configure-settings.md)
               + [Configuration examples](emr-kerberos-config-examples.md)
            + [Configuring a cluster for Kerberos-authenticated HDFS users and SSH connections](emr-kerberos-configuration-users.md)
         + [Using SSH to connect to Kerberized clusters](emr-kerberos-connect-ssh.md)
         + [Tutorial: Configure a cluster-dedicated KDC](emr-kerberos-cluster-kdc.md)
         + [Tutorial: Configure a cross-realm trust with an Active Directory domain](emr-kerberos-cross-realm.md)
   + [Integrate Amazon EMR with AWS Lake Formation](emr-lake-formation.md)
      + [Overview of Amazon EMR integration with Lake Formation](emr-lf-conceptual.md)
         + [IAM roles for Lake Formation](emr-lf-iam-role.md)
         + [Terms and concepts](emr-lf-terms.md)
         + [Amazon EMR components](emr-lf-components.md)
         + [Architecture of SAML-enabled single sign-on and fine-grained access control](emr-lf-architecture.md)
      + [Applications, features, and limitations](emr-lf-scope.md)
      + [Before you begin](emr-lf-prerequisites.md)
         + [Configure a trust relationship between your IdP and Lake Formation](emr-lf-federation.md)
         + [Configure third-party providers for SAML](emr-lf-idp.md)
         + [Create a customized Amazon EC2 instance profile](emr-lf-create-instance-profile.md)
         + [Configure EMR security](emr-lf-security.md)
      + [Launch an Amazon EMR cluster with Lake Formation](emr-lf-launch.md)
         + [Launch an Amazon EMR cluster with Lake Formation](emr-lf-launch-cluster.md)
         + [Set up EMR Notebooks to access Lake Formation data](emr-lf-notebook.md)
         + [Set up cross-account access](emr-lf-cross-account-access.md)
   + [Integrate Amazon EMR with Apache Ranger](emr-ranger.md)
      + [Apache Ranger](emr-ranger-overview.md)
         + [Architecture of Amazon EMR integration with Apache Ranger](emr-ranger-architecture.md)
         + [Amazon EMR components](emr-ranger-components.md)
      + [Application support and limitations](emr-ranger-app-support.md)
      + [Set up Amazon EMR for Apache Ranger](emr-ranger-begin.md)
         + [Set up Ranger Admin server](emr-ranger-admin.md)
            + [TLS certificates](emr-ranger-admin-tls.md)
            + [Service definition installation](emr-ranger-admin-servicedef-install.md)
            + [Network traffic rules](emr-ranger-network.md)
         + [IAM roles for native integration with Apache Ranger](emr-ranger-iam.md)
            + [EC2 instance profile](emr-ranger-iam-ec2.md)
            + [IAM role for Apache Ranger](emr-ranger-iam-ranger.md)
            + [IAM role for other AWS services](emr-ranger-iam-other-AWS.md)
            + [Validate your permissions](emr-ranger-iam-validate.md)
         + [Create the EMR security configuration](emr-ranger-security-config.md)
         + [Store TLS certificates in AWS Secrets Manager](emr-ranger-tls-certificates.md)
         + [Start an EMR cluster](emr-ranger-start-emr-cluster.md)
         + [Considerations and issues](emr-ranger-security-considerations.md)
      + [Apache Ranger plugins](emr-ranger-plugins.md)
      + [Apache Ranger troubleshooting](emr-ranger-troubleshooting.md)
         + [EMR Cluster failed to provision](emr-ranger-troubleshooting-cluster-failed.md)
         + [Queries are unexpectedly failing](emr-ranger-troubleshooting-queries-failed.md)
   + [Control network traffic with security groups](emr-security-groups.md)
      + [Working with Amazon EMR-managed security groups](emr-man-sec-groups.md)
      + [Working with additional security groups](emr-additional-sec-groups.md)
      + [Specifying Amazon EMR-managed and additional security groups](emr-sg-specify.md)
      + [Specifying EC2 security groups for EMR Notebooks](emr-managed-notebooks-security-groups.md)
      + [Using Amazon EMR block public access](emr-block-public-access.md)
   + [Compliance validation for Amazon EMR](emr-compliance.md)
   + [Resilience in Amazon EMR](disaster-recovery-resiliency.md)
   + [Infrastructure security in Amazon EMR](infrastructure-security.md)
      + [Connect to Amazon EMR using an interface VPC endpoint](interface-vpc-endpoint.md)
+ [Manage clusters](emr-manage.md)
   + [View and monitor a cluster](emr-manage-view.md)
      + [View cluster status and details](emr-manage-view-clusters.md)
      + [Enhanced step debugging](emr-enhanced-step-debugging.md)
      + [View application history](emr-cluster-application-history.md)
         + [View persistent application user interfaces](app-history-spark-UI.md)
         + [View a high-level application history](app-history-summary.md)
      + [View log files](emr-manage-view-web-log-files.md)
      + [View cluster instances in Amazon EC2](UsingEMR_Tagging.md)
      + [CloudWatch events and metrics](emr-manage-cluster-cloudwatch.md)
         + [Monitor CloudWatch events](emr-manage-cloudwatch-events.md)
         + [Monitor metrics with CloudWatch](UsingEMR_ViewingMetrics.md)
      + [View cluster application metrics with Ganglia](ViewingGangliaMetrics.md)
      + [Logging Amazon EMR API calls in AWS CloudTrail](logging_emr_api_calls.md)
   + [Connect to the cluster](emr-connect-master-node.md)
      + [Before you connect: Authorize inbound traffic](emr-connect-ssh-prereqs.md)
      + [Connect to the master node using SSH](emr-connect-master-node-ssh.md)
      + [View web interfaces hosted on Amazon EMR clusters](emr-web-interfaces.md)
         + [Option 1: Set up an SSH tunnel to the master node using local port forwarding](emr-ssh-tunnel-local.md)
         + [Option 2, part 1: Set up an SSH tunnel to the master node using dynamic port forwarding](emr-ssh-tunnel.md)
         + [Option 2, part 2: Configure proxy settings to view websites hosted on the master node](emr-connect-master-node-proxy.md)
   + [Terminate a cluster](UsingEMR_TerminateJobFlow.md)
   + [Scaling cluster resources](emr-scale-on-demand.md)
      + [Using EMR managed scaling in Amazon EMR](emr-managed-scaling.md)
         + [Understanding node allocation strategy and scenarios](managed-scaling-allocation-strategy.md)
         + [Understanding managed scaling metrics](managed-scaling-metrics.md)
         + [Use the AWS Management Console to configure managed scaling](managed-scaling-console.md)
         + [Updated console options for cluster scaling](managed-scaling-console-updates.md)
         + [Using the AWS CLI to configure managed scaling](managed-scaling-cli.md)
         + [Using AWS SDK for Java to configure managed scaling](managed-scaling-sdk.md)
      + [Using automatic scaling with a custom policy for instance groups](emr-automatic-scaling.md)
      + [Manually resizing a running cluster](emr-manage-resize.md)
      + [Cluster scale-down](emr-scaledown-behavior.md)
   + [Cloning a cluster using the console](clone-console.md)
   + [Submit work to a cluster](AddingStepstoaJobFlow.md)
      + [Work with steps using the AWS CLI and console](emr-work-with-steps.md)
         + [Adding steps to a cluster using the console](emr-add-steps-console.md)
         + [Adding steps to a cluster using the AWS CLI](add-step-cli.md)
         + [Considerations for running multiple steps in parallel](emr-concurrent-steps.md)
         + [Viewing steps](emr-view-steps.md)
         + [Canceling steps](emr-cancel-steps.md)
      + [Submit Hadoop jobs interactively](interactive-jobs.md)
      + [Add more than 256 steps to a cluster](AddMoreThan256Steps.md)
   + [Automate recurring clusters with AWS Data Pipeline](emr-manage-recurring.md)
+ [Troubleshoot a cluster](emr-troubleshoot.md)
   + [What tools are available for troubleshooting?](emr-troubleshoot-tools.md)
   + [Viewing and restarting Amazon EMR and application processes (daemons)](emr-process-restart-stop-view.md)
   + [Troubleshoot a failed cluster](emr-troubleshoot-failed.md)
      + [Step 1: Gather data about the issue](emr-troubleshoot-failed-1.md)
      + [Step 2: Check the environment](emr-troubleshoot-failed-2.md)
      + [Step 3: Look at the last state change](emr-troubleshoot-failed-3.md)
      + [Step 4: Examine the log files](emr-troubleshoot-failed-4.md)
      + [Step 5: Test the cluster step by step](emr-troubleshoot-failed-5-test-steps.md)
   + [Troubleshoot a slow cluster](emr-troubleshoot-slow.md)
      + [Step 1: Gather data about the issue](emr-troubleshoot-slow-1.md)
      + [Step 2: Check the environment](emr-troubleshoot-slow-2.md)
      + [Step 3: Examine the log files](emr-troubleshoot-slow-3.md)
      + [Step 4: Check cluster and instance health](emr-troubleshoot-slow-4.md)
      + [Step 5: Check for suspended groups](emr-troubleshoot-slow-5.md)
      + [Step 6: Review configuration settings](emr-troubleshoot-slow-6.md)
      + [Step 7: Examine input data](emr-troubleshoot-slow-7.md)
   + [Common errors in Amazon EMR](emr-troubleshoot-errors.md)
      + [Input and output errors](emr-troubleshoot-errors-io.md)
      + [Permissions errors](emr-troubleshoot-error-permissions.md)
      + [Resource errors](emr-troubleshoot-error-resource.md)
         + [Cluster terminates with NO_SLAVE_LEFT and core nodes FAILED_BY_MASTER](emr-cluster-NO_SLAVE_LEFT-FAILED_BY_MASTER.md)
         + [Cannot replicate block, only managed to replicate to zero nodes.](enough-hdfs-space.md)
         + [EC2 QUOTA EXCEEDED](emr-EC2.md)
         + [Too many fetch-failures](emr-troubleshoot-error-resource-1.md)
         + [File could only be replicated to 0 nodes instead of 1](emr-troubleshoot-error-resource-2.md)
         + [Blacklisted nodes](emr-troubleshoot-error-resource-3.md)
         + [Throttling errors](emr-throttling-error.md)
         + [Instance type not supported](emr-INSTANCE_TYPE_NOT_SUPPORTED-error.md)
         + [EC2 is out of capacity](emr-EC2_INSUFFICIENT_CAPACITY-error.md)
      + [Streaming cluster errors](emr-troubleshoot-error-streaming.md)
      + [Custom JAR cluster errors](emr-troubleshoot-error-custom-jar.md)
      + [Hive cluster errors](emr-troubleshoot-error-hive.md)
      + [VPC errors](emr-troubleshoot-error-vpc.md)
      + [AWS GovCloud (US-West) errors](emr-troubleshoot-error-govcloud.md)
   + [Troubleshoot a Lake Formation cluster](emr-troubleshoot-lf.md)
+ [Write applications that launch and manage clusters](making_api_requests.md)
   + [End-to-end Amazon EMR Java source code sample](emr-common-programming-sample.md)
   + [Common concepts for API calls](emr-common-programming-concepts.md)
   + [Use SDKs to call Amazon EMR APIs](call-emr-using-sdks.md)
      + [Using the AWS SDK for Java to create an Amazon EMR cluster](calling-emr-with-java-sdk.md)
   + [Manage Amazon EMR Service Quotas](emr-service-limits-manage.md)
      + [What are Amazon EMR Service Quotas](emr-service-limits-what-are.md)
      + [How to manage Amazon EMR Service Quotas](emr-service-limits-strategy.md)
      + [When to set up EMR events in CloudWatch](emr-service-limits-cloudwatch-events.md)
+ [AWS glossary](glossary.md)