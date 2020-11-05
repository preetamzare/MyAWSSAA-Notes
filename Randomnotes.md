## AWS Solution Architect Associate Exam

                                                        Date: 05th Nov, 2020

### Notes on Secrets Manager

* API Keys and Passwords are the key words for the exam
* Application integrations
  * RDS

> do not need lamda function
* Automatic rotation of keys using **Lambda**, or rotation of the secrets

> Note Lamda function needs execution Role

* Integrates with IAM and uses IAM Permissions
* can be accessed via
  * Console
  * CLI
  * SDK
  * API

## Notes on AWS Shield and WAF

Both these products are configured together to protect against advanced attacks.

### AWS Shield
* AWS Shield comes into 2 Versions
  * Standard
    * Protects Cloud front and Route53
    * Provides L3 and L4 Protections
  * Advanced
    * Protects over and above CF and Route53
      * EC2
      * Elastic LB
      * Global Accelerator
    * comes with premium cost but then also gets
      * Financial Insurance
      * 24 x 7 support from DDoS Protection team

### AWS WAF

* Layer 7 FW which protects against
  * SQL Injection
  * Cross site scripting
  * Provides Geo Blocks
  * Controlled through Web Access Control (WACL)
  * Applied to ELB, API GW and CloudFront

  > Remember ELB, API GW and CloudFront are protecting perimeter/Global Perimeter.
  > CloudFront and ELB gets protection from both Shield and WAF. At CloudFront, you apply WACL at the distribution

## Cloud HSM

* The most important to remember it is dedicated service in cloud. It is dedicated to you and no one can use it.
* This also means, you have to manage this end to end except the Hardware and software maintenance is done by AWS
* BUT HA still needs to be considered. So one should deploy multiple CloudHSM in different availability zone
* Access is available via ENI which is injected in to the Private VPC
* CloudHSM is access via CloudHSM Client. It needs to be installed on the EC2 instances
* Some keywords for the exam
  * FIPS 140-2 **Level 3**
  * Cloud HSM can be accessed via
    * PKCS#11
    * CryptoNG Extension from Microsoft
    * Java Cryptographic Extensions from Java

### Drawbags

* No native integration with AWS. In other words, AWS API cannot be used here.
* But here you can use Client Side encryption
* Here one use CloudHSM do SSL offload as Privatekey and infrastructure is managed by you
* CloudHSM can protect Private keys of your CA. Now, this is how traditionally CA's private keys are protected
* Oracle can use CloudHSM for encrypting data using TDE 
