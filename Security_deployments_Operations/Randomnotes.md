# AWS Solution Architect Associate Exam -Notes

Revised On: 05.12.2020

Date: 05th Nov, 2020

Reference: [AWS Course from Adrian Cantrill](https://learn.cantrill.io/)

## Notes on Secrets Manager

* API Keys and Passwords are the key words for the exam
* Application integrations
  * RDS

> :bellhop_bell: do not need Lamda function, when there is Integration.

* Automatic rotation of keys using **Lambda**, or rotation of the secrets

> :bellhop_bell: Lamda function needs execution Role

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
  * **Standard**
    * Protects Cloudfront and Route53
    * :magnet: Provides L3 and L4 Protections
  * **Advanced**
    * Protects over and above CF and Route53
      * EC2
      * Elastic LB (remember it is only L3 and L4)
      * Global Accelerator
    * comes with premium cost :money_mouth_face: but then you also get
      * Financial Insurance
      * 24 x 7 :stopwatch: support from DDoS Protection team

### AWS WAF

* Layer 7 FW which protects against
  * SQL Injection
  * Cross site scripting
  * Provides Geo Blocks
  * Controlled through Web Access Control (WACL)
  * Applied to ELB, **API GW** (:magnet:) and CloudFront

> Remember ELB, API GW and CloudFront are protecting perimeter/Global Perimeter.
> CloudFront and ELB gets protection from both Shield and WAF. At CloudFront, you apply Web ACL at the distribution.

:anchor: Cloudfront and ELB (but in advanced) get protected by both WAF and Shield. Refer to lessons from Adrian. He explains it quite well.

## Cloud HSM

* The most important :magnet: to remember it is dedicated service in cloud. It is dedicated to you and no one can use it.
* This also means, you have to manage this end-to-end except the Hardware and software maintenance is done by AWS
* BUT HA still needs to be considered. So one should deploy multiple CloudHSM in different availability zone. (_But who deploys it? unclear at this Stage_)
* Access is available via ENI which is injected in to the Private VPC
* CloudHSM is managed via CloudHSM Client. This utility needs to be installed on the EC2 instances
* Some keywords for the exam
  * FIPS 140-2 **Level 3**
  * Cloud HSM can be accessed via
    * PKCS#11
    * CryptoNG Extension from Microsoft
    * Java Cryptographic Extensions from Java

### Considerations

* No native integration with AWS. In other words, AWS API cannot be used here.
* But you can use Client Side encryption in this case.
* Here one can use CloudHSM do SSL offload for ELB (i guess bridging mode) as Privatekey and infrastructure is managed by you
* CloudHSM can protect Private keys :key: of your CA. *Now, if you worked in this domain, this is the standard way how traditionally CA's private keys are protected.*
* Oracle can use CloudHSM for encrypting data using TDE
* Transparent Data Encryption (TDE) is primarily used to encrypt stored data on your DB instances. Kind of data at rest encryption but at DB level (?) 

Revised On: 21.11.2020 | Next Revision: 24.11.2020
-----------------------| -------------------------
