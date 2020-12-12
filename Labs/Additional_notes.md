# Additional Notes

Idea to further refine the knowledge.

* SES is a cloud-based email sending service designed to send notification and transactional emails. One should use SNS instead of SES (Simple Email Service) when **you want to monitor your EC2 instances.**
* When failing over, Amazon RDS simply flips the canonical name record (CNAME) (**not ipaddress**) for your DB instance to point at the standby, which is in turn promoted to become the new primary.

### CloudWatch Agent

* The CloudWatch Logs agent is comprised of the following components:
  * A plug-in to the AWS CLI that pushes log data to CloudWatch Logs.
  * A script (daemon) that initiates the process to push data to CloudWatch Logs.
  * A cron job that ensures that the daemon is always running.

### Kinesis

* The time period from when a record is added to when it is no longer accessible is called the retention period. A Kinesis data stream stores records from 24 hours by default to a maximum of 168 hours

### AWS MQ

If you’re using messaging with **existing applications** and want to move your messaging service to the cloud quickly and easily, it is recommended that you consider Amazon MQ. It supports industry-standard APIs and protocols so you can switch from any standards-based message broker to Amazon MQ without rewriting the messaging code in your applications.

If you are building **brand new applications** in the cloud, then it is highly recommended that you consider Amazon SQS and Amazon SNS

SQS does not support an extensive list of industry-standard messaging APIs and protocol, unlike Amazon MQ. Moreover, using Amazon SQS requires you to do **additional changes** in the messaging code of applications to make it compatible.

### AWS EMR

Amazon EMR is a managed cluster platform that simplifies running big data frameworks, such as Apache Hadoop and Apache Spark, on AWS to process and analyze vast amounts of data. By using these frameworks and related open-source projects such as Apache Hive and Apache Pig, you can process data for analytics purposes and business intelligence workloads. Additionally, you can use Amazon EMR to transform and move large amounts of data into and out of other AWS data stores and databases such as Amazon Simple Storage Service (Amazon S3) and Amazon DynamoDB.

### Expedited retrievals

Expedited retrievals allow you to quickly access your data when occasional urgent requests for a subset of archives are required. For all below the largest archives (250 MB+)**, data accessed using Expedited retrievals are typically made available within 1–5 minutes. Provisioned Capacity ensures that retrieval capacity for Expedited retrievals is available when you need it.

### Provisioned Capacity

Provisioned capacity ensures that your retrieval capacity for expedited retrievals is available when you need it. Each unit of capacity provides that at least **three** expedited retrievals can be performed every five minutes and provides up to 150 MB/s of retrieval throughput. 

You should purchase provisioned retrieval capacity if your workload requires **highly reliable and predictable access to a subset of your data in minutes**. Without provisioned capacity Expedited retrievals are accepted, except for rare situations of unusually high demand. However, if you require access to Expedited retrievals under all circumstances, you must purchase provisioned retrieval capacity.

AWS Glue is a fully managed extract, transform, and load (ETL) service that makes it easy for customers to prepare and load their data for analytics

Detailed monitoring just provides a higher frequency of metrics (1-minute frequency).

### Cognito
You can add multi-factor authentication (MFA) to a user pool to protect the identity of your users. MFA adds a second authentication method that doesn’t rely solely on user name and password. You can choose to use SMS text messages, or time-based one-time (TOTP) passwords as second factors in signing in your users. You can also use adaptive authentication with its risk-based model to predict when you might need another authentication factor. It’s part of the user pool advanced security features, which also include protections against compromised credentials.

### CORS

Cross-origin resource sharing (CORS) defines a way for client web applications that are loaded in one domain to interact with resources in a different domain. With CORS support, you can build rich client-side web applications with Amazon S3 and selectively allow cross-origin access to your Amazon S3 resources.

CORS allows client web applications that are loaded in one domain to interact with resources in a different domain.

### AWS Reserved Instance Marketplace

The Reserved Instance Marketplace is a platform that supports the sale of third-party and AWS customers’ unused Standard Reserved Instances, which vary in terms of length and pricing options. For example, you may want to sell Reserved Instances after moving instances to a new AWS region, changing to a new instance type, ending projects before the term expiration, when your business needs change, or if you have unneeded capacity.

### AWS Cost Explorer

AWS Cost Explorer is a tool that enables you to view and analyze your costs and usage. You can explore your usage and costs using the main graph, the Cost Explorer cost and usage reports, or the Cost Explorer RI reports. It has an easy-to-use interface that lets you visualize, understand, and manage your AWS costs and usage over time.

### AWS Budgets

AWS Budgets is gives you the ability to set custom budgets that alert you when your costs or usage exceed (or are forecasted to exceed) your budgeted amount. You can also use AWS Budgets to set reservation utilization or coverage targets and receive alerts when your utilization drops below the threshold you define.

### Amazon Inspector

Amazon Inspector is an automated security assessment service that helps improve the security and compliance of applications deployed on AWS. Amazon Inspector automatically assesses applications for exposure, vulnerabilities, and deviations from best practices.


### AWS Trusted Advisor

AWS Trusted Advisor is an online tool that provides you real-time guidance to help you provision your resources following **AWS best practices**. It inspects your AWS environment and makes recommendations for saving money, improving system performance and reliability, or closing security gaps.

Whether establishing new workflows, developing applications, or as part of ongoing improvement, take advantage of the recommendations provided by Trusted Advisor on a regular basis to help keep your solutions provisioned optimally.

Trusted Advisor includes an ever-expanding list of checks in the following five categories:

**Cost Optimization** – recommendations that can potentially save you money by highlighting unused resources and opportunities to reduce your bill.

**Security** – identification of security settings that could make your AWS solution less secure.

**Fault Tolerance** – recommendations that help increase the resiliency of your AWS solution by highlighting redundancy shortfalls, current service limits, and over-utilized resources.

**Performance** – recommendations that can help to improve the speed and responsiveness of your applications.

**Service Limits** – recommendations that will tell you when service usage is more than 80% of the service limit.


Although you can configure automatic key rotation with SSE-S3, these two do not provide you with an audit trail that shows when your CMK was used and by whom, unlike Server-Side Encryption with AWS KMS-Managed Keys (SSE-KMS).