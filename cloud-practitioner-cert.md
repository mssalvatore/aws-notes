# AWS Cloud Practitioner Exam Notes

## Benefits of cloud computing

* Trade upfront expense for variable expense
* Stop spending monkey to run and maintain data centers
* Stop guessing capacity
* Benefit from massive economies of scale
* Increase speed and agility
* Go global in minutes

### Key Values

* Pay for what you need.


## Glossary
### Availability Zone (AZ)
One of many physical data centers within a region.

A distinct location within a Region that's insulated from failures in other
Availability Zones, and provides inexpensive, low-latency network connectivity
to other Availability Zones in the same Region.
https://docs.aws.amazon.com/general/latest/gr/glos-chap.html

An Availability Zone is a single data center or a group of data centers within
a Region. Availability Zones are located tens of miles apart from each other.

### [EC2 Auto Scaling](#amazon-ec2-auto-scaling)

### EC2

Amazon Elastic Compute Cloud - A web service for launching and managing
Linux/UNIX and Windows Server instances in Amazon's data centers.

### EC2 Instance Family
The hardware an EC2 instance runs on

### Internet Gateway (IGW)
Attach to VPC to allow internet traffic into the VPC.

### What is cloud computing?`

The on-demand delivery of IT resources over the internet with pay-as-you-go
pricing.

### Undifferentiated heavy-lifting of IT

Stuff that doesn't provide you a competitive advantage but IT needs to do:
    Example: Your ability to setup a MySQL database doesn't make you better or
             differentiate you from your competitors. The way you build your
             tables or the data you store does.

## Three cloud computing deployment models

### Cloud-based
* Run all parts of the application in the cloud.
* Migrate existing applications to the cloud.
* Design and build new applications in the cloud.

### On-prem / Private cloud
* Deploy resources by using virtualization and resource management tools.
* Increase resource utilization by using application management and
  virtualization technologies.

On-premises deployment is also known as a *private cloud* deployment. In this
model, resources are deployed on premises by using virtualization and resource
management tools.

### Hybrid

* Connect cloud-based resources to on-premises infrastructure.
* Integrate cloud-based resources with legacy IT applications.

In a hybrid deployment, cloud-based resources are connected to on-premises
infrastructure.

## Cloud Computing Models
### Infrastructure as a Service (IaaS)
* Basic building blocks for cloud IT
    * Networking
    * Computers
    * Data storage
### Platform as a Service (PaaS)

Platform as a Service (PaaS) removes the need for your organization to manage
the underlying infrastructure (usually hardware and operating systems) and
allows you to focus on the deployment and management of your applications. This
helps you be more efficient as you don’t need to worry about resource
procurement, capacity planning, software maintenance, patching, or any of the
other undifferentiated heavy lifting involved in running your application.

### Software as a Service (SaaS)
* Provides you with a complete product that is run and managed by the
  service provider
    * End-user applications, e.g. web-based email

## EC2

### 5 Types of EC2 Instances
#### General Purpose
Offer a balance of compute, memory and networking resources:
* application servers
* gaming servers
* enterprise application backend servers
* small to medium databases

#### Compute Optimized
Ideal for compute-bound applications.
High-performance processors.
Good for "batch processes"

#### Memory Optimized
Fast performance for workloads processing large datasets in memory.

#### Accelerated Computing
Use hardware accelerators (coprocessors) to perform some functions.

* Floating-point calculations
* Graphics processing
* Data pattern matching

#### Storage Optimized

Designed for workloads that require high sequential read/write access to large
datasets on local storage.

### Pricing

#### On-Demand
* Short-term, irregular workloads that cannot be interrupted.
* No upfront costs or contracts.
* Pay only for what you use.

#### Savings Plans
* Commit to consisted usage for 1-year or 3-year term, resulting in savings
  up to 72% over on-demand.
* Usage beyond commitment is charged at on-demand rates.

#### Reserved Instances
* Billing discount applied to on-demand instances.
* Standard Reserved or Convertible Reserved instances, for 1 or 3 year term
* Scheduled reserved instances, for 1 year term.

#### Spot Instances
* Ideal for workloads with flexible start and end times that can withstand
  interruptions.
    * Example: A background job that processes customer survey data.
* Reduce cost by up to 90% over on-demand
* No contract required

#### Dedicated Hosts
* Physical servers fully dedicated for your use (not multitenant)
* Most expensive

## Scalability and Elasticity

### Scalability

Begin with only the resources you need and design your architecture to
automatically respond to changing demand by scaling out or in.

#### Amazon EC2 Auto Scaling

Amazon EC2 Auto Scaling is the AWS service that provides scalability
functionality for EC2 instances.

##### Scaling methods/approaches
* Dynamic scaling - Responds to change in demand
* Predictive scaling - Automatically schedules the right number of EC2
  instances based on predicted demand.

Note: Dynamic and predictive scaling can be used together. (Need more details
on how that works)


### Elastic Load Balancing (ELB)
* Addresses the undifferentiated heavy lifting of load balancing
* Regional construct - Runs across all AZs within the region
* Can be used within an application (i.e. load balancing between backend
  and frontend)
* Single point of contact for all incoming web traffic to your Auto Scaling group
    * Elastic Load Balancing and Auto Scaling work together

### Messaging and Queuing
#### Amazon Simple Queuing Service (SQS)
**Payload** - Data contained within a message
**SQS Queue** - Where messages are placed until they are processed

#### Amazon Simple Notification Service (SNS)
Used to send messages to services or notifications to end users. Uses pub/sub.
Create SNS topic. Subscribers subscribe to the topic. Can use SMS, mobile push,
and e-mail to notify end users.

## Serverless compute options
### AWS Lambda
* Short running functions
* Lets you run code without needing to provision or manage servers
* Pay only for the compute time you consume. Charges only apply when your
  code is running.

### Container-based workloads
Manage docker containers and may or may not run on EC2

#### Amazon Elastic Container Service (ECS)
* Highly scalable
* high-prformance container management system
* Supports Docker Community Edition as well as Enterprise Edition
* Use API calls to manage containers

#### Amazon Elastic Kubernetes Service (EKS)
Fully managed service you can use to run K8s

#### AWS Fargate
Fargate is a serverless platform for ECS or EKS

## AWS Global Infrastructure

### Regions
Data does not move between regions unless you've granted explicit permission.

Four business factors go into choosing a region:
1. Compliance
2. Proximity
3. Feature availability (Not all regions have all features)
4. Pricing (Varies between region)

#### Availability zones (AZ)
Each region is made up of AZs. An AZ is a datacenter (or maybe a group of
datacenters).

**BEST PRACTICE**: Run across at least two availability zones in a region.


### Edge Locations

Amazon Cloudfront is Amazon's CDN

Edge locations are separate from regions. Edge Locations run Cloudfront so you
can cache data closer to users.

Amazon Route 53 is a DNS service run in edge locations.

AWS Outposts - AWS installs mini-region within your datacenter


## AWS APIs
* AWS Management Console - Browser-based
* AWS CLI
* AWS SDKs

### AWS Elastic Beanstalk
AWS Elastic Beanstalk is an easy-to-use service for deploying and scaling web
applications and services. You can simply upload your code, and AWS Elastic
Beanstalk automatically handles the deployment, from capacity provisioning,
load balancing, and auto scaling to application health monitoring.

With AWS Elastic Beanstalk, you provide code and configuration settings, and
Elastic Beanstalk deploys the resources necessary to perform the following
tasks:

* Adjust capacity
* Load balancing
* Automatic scaling
* Application health monitoring

### AWS Cloud Formation
Infrastructure-as-code tool used to define a wide variety of AWS resources.

## Additional resources
* Overview of AWS whitepater - https://d0.awsstatic.com/whitepapers/aws-overview.pdf
* AWS Glossary - https://docs.aws.amazon.com/general/latest/gr/glos-chap.html
* AWS Fundamentals Core Concepts - https://aws.amazon.com/getting-started/fundamentals-core-concepts/?e=gs2020&p=fundoverview&p=gsrc&c=fo
* Compute Services Documentation - https://docs.aws.amazon.com/whitepapers/latest/aws-overview/compute-services.html
* Category deep dive (Serverless) - https://aws.amazon.com/getting-started/deep-dive-serverless/

## AWS Virtual Private Cloud (VPC)
* "Amazon VPC is the networking layer for Amazon EC2"
* "A virtual network dedicated to you AWS account."
* A logically provisioned section of amazon's cloud.
* Provides public and private subnets
* A VPC exists in a single region

Internet Gateway (IGW) - Used to connect a VPC to the internet

Virtual Private Gateway - Let's private traffic from an approved network into
VPC. Basically VPN.

AWS Direct Connect - Allows you to create a dedicated, private, fiber
connection from your datacenter to AWS.


### Network Access Control Lists (ACLs)
* Basically firewall rules
* Lives at subnet boundry. Network ACLs are evaluated on the way in and
  out.
* Each subnet comes with a default ACL that allows all traffic in and out.
* Custom ACLs deny all inbound and outbound traffic by default.
* All ACLs have an explicit deny rule to ensure that unmatched packets are
  denied.
* NETWORK ACLs ARE STATELESS

https://docs.aws.amazon.com/vpc/latest/userguide/vpc-network-acls.html

### Security Groups
* Host-based firewall
* Each AWS instance in a subnet comes with a "security group"
* Deny all inbound traffic by default
* Allow all outbound traffic by default
* Allow all inbound traffic from devices in the same security group by default.
# SECURITY GROUPS ARE STATEFUL

**Security groups are stateful, Network ACLs are stateless**

### AWS Route 53 (DNS)
* Highly available and scalable
* Supports several routing policies
    * Latency-based routing
    * Geolocation DNS
    * Geoproximity routing
    * Weighted round robin
* Can be used to register domain names.

https://aws.amazon.com/route53

## Databases and Data Storage

### Instance store volumes
* Block device attached to EC2 instance
* Physically attached the host that EC2 instance is running on
* Ephemeral -- If you stop or terminate an instance, instance store volumes
  will be deleted

### Amazon Elastic Block Store
* Create virtual hard drives name EBS volumes
* Storage persists if EC2 instance is stopped and started
* Allows taking snapshots of EBS volumes -- incremental backup
* Limited to 16TB
* AZ-level resource (instance and EBS must be in same AZ)
* Fixed size

### Amazon Simple Storage Service (S3)
* Store data as objects (files) in buckets (directories)
* Maximum object size of 5TB
* Unlimited storage
* Version control for objects
* Glacier is for long term storage
    * Can lock the volume and write once/read many (WORM) for auditing
      purposes
* Lifecycle policies allow you to automatically move data between storage
  tiers
* 11 9's (99.999999999%) durability
* 99.99% availability

#### S3 Storage Tiers

* S3 Standard (Frequent access tier)
    * Designed for frequently accessd data (high availaility)
    * Stores data in a minimum of three AZs
* S3 Standard-Infrequent Access (S3 Standard-IA)
    * Ideal for infrequently accessd data (but high availability when
      needed)
    * Lower storage price but higher retreival price than standard
    * Stores data in a minimum of three AZs
* S3 One Zone-Infrequent Access (S3 One Zone-IA)
    * Like S3 Standard-IA, but only stores data in one AZ
* S3 Intelligent-Tiering
    * For data with unknown or changin access patterns
    * Additional monthly monitoring and automation fee
    * Objects not accessed for 30 consecutive days are moved to Standard-IA.
    * Accessed objects are moved to S3 Standard
* S3 Glacier
    * Low cost storage for archiving
    * Retrieval within a few minutes to hours
* S3 Glacier Deep Archive
    * Lowest cost
    * Retreval within 12 hours

### Amazon Elastic File System (EFS)
* Data can be accessed simultaneously from multiple instances
* Dynamically sized (grows and shrinks)
* Linux file system
* Regionally scoped
* on-prem servers can access EFS using AWS Direct Connect

### Amazon Relational Database Service (RDS)
Amazon RDS is available on several database instance types - optimized for
memory, performance, or I/O - and provides you with six familiar database
engines to choose from, including Amazon Aurora, PostgreSQL, MySQL, MariaDB,
Oracle Database, and SQL Server. You can use the AWS Database Migration Service
to easily migrate or replicate your existing databases to Amazon RDS.

Provides:
* Automated patching
* backups
* redundancy
* failover
* disaster recovery

#### Amazon Aurora

Amazon Aurora is a MySQL and PostgreSQL compatible relational database engine
that combines the speed and availability of high-end commercial databases with
the simplicity and cost-effectiveness of open source databases.


* 5x faster than standard MySQl
* 3x faster than standard PostgreSQL

#### Amazon Database Migration Service (DMS)

Migrate existing database to AWS

### DynamoDB
* Serverless database
* non-relational, NoSQL
* Create tables where you store data
* key-value store

### Amazon Redshift

* Data warehouse
* Historical analytics
* Big data

## Security

### Shared Security Model
![Shared Responsibility Model](./shared_responsibility_model.jpg "Shared
Responsibility Model")

Customers are responsible for security *in* the cloud. AWS is responsible for
security *of* the cloud.

### Benefits of AWS Security
* Keep Your Data Safe - The AWS infrastructure puts strong safeguards in place
  to help protect your privacy. All data is stored in highly secure AWS data
  centers.
* Meet Compliance Requirements - AWS manages dozens of compliance programs in
  its infrastructure. This means that segments of your compliance have already
  been completed.
* Save Money - Cut costs by using AWS data centers. Maintain the highest
  standard of security without having to manage your own facility.
* Scale Quickly - Security scales with your AWS Cloud usage. No matter the size
  of your business, the AWS infrastructure is designed to keep your data safe.

### AWS Identity and Access Management (IAM)

AWS accounts have a root user with total control over the AWS account.

In IAM, you can create an IAM user. No permissions by default. Need to
explicitly grant privileges to IAM users.

Grant privileges by associating an IAM policy to an IAM user. An IAM policy is
a JSON document that specifies what API calls the IAM user can make.

IAM groups are groups of users. You can attach policies to groups.

An IAM role is an identity that you can assume to gain temporary access to
permissions. Before an IAM user, application, or service can assume an IAM
role, they must be granted permissions to switch to the role. When someone
assumes an IAM role, they abandon all previous permissions that they had under
a previous role and assume the permissions of the new role. IAM roles are ideal
for situations in which access to services or resources needs to be granted
temporarily, instead of long-term.

### AWS Organizations
A cental location to manage multiple AWS accounts.

* Centralized management
* Consolidated billing
* Hierarchical groupings of accounts
* AWS service and API actions access control

In AWS Organizations, you can centrally control permissions for the accounts in
your organization by using service control policies (SCPs).

In AWS Organizations, you can group accounts into organizational units (OUs) to
make it easier to manage accounts with similar business or security
requirements.

### Compliance and Auditing

#### AWS Artifact

AWS Artifact is a service that provides on-demand access to AWS security and
compliance reports and select online agreements. AWS Artifact consists of two
main sections:

* AWS Artifact Agreements
    * Suppose that your company needs to sign an agreement with AWS regarding
      your use of certain types of information throughout AWS services. You can
      do this through AWS Artifact Agreements.
* AWS Artifact Reports
    * Suppose that a member of your company’s development team is building an
      application and needs more information about their responsibility for
      complying with certain regulatory standards. You can advise them to
      access this information in AWS Artifact Reports.

### AWS Shield

Protects applications against DDoS attacks.

* AWS Shield Standard
    * Automatically protects all AWS customers at no cost
* AWS Shield Advanced
    * Paid service that provides detailed attack diagnostic ands and the
      ability to detect and mitigate sophisticated DDoS attacks.

### AWS WAF

WAF, not much to say

Works together with CloudFront and Application Load Balancer.

### AWS Key Management Service (KMS)

With AWS KMS, you can choose the specific levels of access control that you
need for your keys. For example, you can specify which IAM users and roles are
able to manage keys. Alternatively, you can temporarily disable keys so that
they are no longer in use by anyone. Your keys never leave AWS KMS, and you are
always in control of them.

### Amazon Inspector

* Inspects AWS for potential security issues

### Amazon GuardDuty

* Threat detection
* Can configure AWS Lambda functions to automatically take remediation steps

## Monitoring

### AWS CloudWatch
* AWS infrastructure and application monitoring service
* Metrics - Variables tied to your resources
* CloudWatch alarm - Set alert based on metic
* Has dashboards
* Benefits
    * Access all metrics from a central location
    * Gain visibility into your applications, infrastructure and services
    * Reduce MTTR and improve TCO
    * Drive insights to optimize applications and opirational resources

### AWS CloudTrail

* API Auditing tool
* Every AWS request is logged in the CloudTrail engine
* Can save audit logs indefinitely

#### CloudTrail Insights

* Optional CloudTrail feature
* Allows CloudTrail to automatically detect unusual API activities

### AWS Trusted Advisor

* A web service that inspects your AWS environment and provide sreal-time
  recommendations in accordance with AWS best practices.
* Provides recommendations in 5 categories/pillars:
    * Cost optimization
    * Performance
    * Security
    * Fault tolerance
    * Service limits - Soft limits, can be modified by contacting support

## Pricing

### AWS free tier

3 ways to try a service:
* Always free
* 12 months free
* Trials

### How pricing works

* Pay for what you use
* Pay less when you reserve
* Pay less with volume-based discounts when you use more

### Billing

* Billing Dashboard - Full breakdown of costs
* Manage multiple accounts using AWS Organizations via Consolidated Builling
    * Share bulk discount pricing, savings plans, and reserved instances
      across accounts in your organization.


### AWS Budgets

* Set custom budgets for a variety of services
* Proactively notified if you're projected to exceed your budget

### AWS Cost Explorer

AWS Cost Explorer is a tool that enables you to visualize, understand, and
manage your AWS costs and usage over time.

## Support Plans

### Basic support

Free for everyone. Provides:
* 24/7 customer service
* Documentation
* Whitepapers
* Support forums
* AWS Trusted Advisor
* AWS Personal Health Dashboard

### Developer support

Includes:
* Basic support
* Email access to customer support

### Business Support

Includes:
* Basic and developer support
* AWS Trusted Advisor provides full set of best practice checks
* Direct phone access to cloud support engineers
    * 4 hour SLA for impaired production system
    * 1 hour SLA if production system is down

### Enterprise support

Includes:
* Everything in previous tiers
* 15-minute SLA for buisness critical workloads
* Tech account manager

## AWS Marketplace

Curated digital catalog that includes thousands of software listings from
independent software vendors.

## Migration

### Six core perspectives of the Cloud Adoption Framework (CAF)

* Business - Ensures that IT aligns with buisness needs
* People - Evaluate organizational structures and roles, new skills
* Governance - Understand how to update the staff skills, align IT strategy
               with business strategy
* Platform - Principles and patterns for implementing new solutions in the
             cloud.
* Security - Ensures the organization meets security objectives
* Operations - Enable ,run, use, operat, and recover IT workloads

### 6 strategies for migration (6 R's)

* Rehosting (Lift-and-shift) - Move application without changes
* Replatforming (lift, tinker, and shift) - Make a few cloug optimizations, but
  core architecture doesn't change.
* Retiring - Don't move to AWS,
* Retaining - Depricate for a few months but leave in old environment.
* Refactoring/re-architecting - Reimagine and rearchitect the application to be
  cloud-native.
* Repurchasing -  End contract with an old vendor, replace with AWS.

### AWS Snow Family
The AWS Snow Family is a collection of physical devices that help to physically
transport up to exabytes of data into and out of AWS. Designed to be
tamper-resistant.

* AWS Snowcone
    * holds 8 TB of data
    * edge computing and data transfer device
* AWS Snowball
    * Snowball edge storage optimized
        * 80 TB HDD apacity - S3 compatible storage
        * 1 TB SSD - block storage
        * Compute: 40 vCPUs, and 80 GiB of memory to support Amazon EC2 sbe1
          instances (equivalent to C5).
    * Snowball edge compute optimized
        * 42 TB HDD - s3 compatible or EBS compatible
        * 7.68 TB NVME SSD - block storage
        * Compute: 52 vCPUs, 208 GiB of memory, and an optional NVIDIA Tesla
          V100 GPU. Devices run Amazon EC2 sbe-c and sbe-g instances, which are
          equivalent to C5, M5a, G3, and P3 instances.
* AWS Snowmobile - 100 petabytes, hauled by a truck

## AWS Well-Architected Framework

The AWS Well-Architected Tool analyzes your architecture and provides feedback

### Operational excellence

Operational excellence is the ability to run and monitor systems to deliver
business value and to continually improve supporting processes and procedures.  

Design principles for operational excellence in the cloud include performing
operations as code, annotating documentation, anticipating failure, and
frequently making small, reversible changes.

### Security

* Automate security best practices when possible.
* Apply security at all layers.
* Protect data in transit and at rest.

### Reliability

* Recover from infrastructure or service disruptions
* Dynamically acquire computing resources to meet demand
* Mitigate disruptions such as misconfigurations or transient network issues

### Performance efficiency

Performance efficiency is the ability to use computing resources efficiently to
meet system requirements and to maintain that efficiency as demand changes and
technologies evolve.

Evaluating the performance efficiency of your architecture includes
experimenting more often, using serverless architectures, and designing systems
to be able to go global in minutes

### Cost optimization

Cost optimization is the ability to run systems to deliver business value at
the lowest price point.

Cost optimization includes adopting a consumption model, analyzing and
attributing expenditure, and using managed services to reduce the cost of
ownership.



## Most important reading

"As part of your preparation for the AWS Certified Cloud Practitioner exam, we
recommend that you review the following whitepapers and resources:"

* [AWS Certified cloud practitioner exam guide](https://d1.awsstatic.com/training-and-certification/docs-cloud-practitioner/AWS-Certified-Cloud-Practitioner_Exam-Guide.pdf)
* [Overview of Amazon Web Services](https://d1.awsstatic.com/whitepapers/aws-overview.pdf)
* [How AWS Pricing Works](http://d1.awsstatic.com/whitepapers/aws_pricing_overview.pdf)
* [Compare AWS Support Plans](https://aws.amazon.com/prEmiumsupport/plans/)
* [Introduction to AWS Security](https://docs.aws.amazon.com/whitepapers/latest/introduction-aws-security/welcome.html)
* [Security, Identity, and Compliance on AWS](https://aws.amazon.com/products/security)
* [Whitepaper: An Overview of the AWS Cloud Adoption Framework](https://d1.awsstatic.com/whitepapers/aws_cloud_adoption_framework.pdf) <-- READ THIS!
* [https://d1.awsstatic.com/whitepapers/architecture/AWS_Well-Architected_Framework.pdf](https://d1.awsstatic.com/whitepapers/architecture/AWS_Well-Architected_Framework.pdf)

## Questions you got wrong

**Q:** What is the purpose of the AWS Customer Success Site?

**A:** A resource for finding
use cases to help inspire solution design and build confidence with customers.
