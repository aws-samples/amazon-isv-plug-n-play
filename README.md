# ISV Plug & Play

Amazon Relational Database Service (Amazon RDS) makes it easy to set up, operate, and scale a relational database in the cloud. Amazon RDS offloads the undifferentiated heavy lifting of keeping the lights on by automating time-consuming administration tasks such as hardware provisioning, database setup, patching, and backups. Amazon RDS frees ISV Startups to focus on higher-level efforts such as performance tuning, schema design, and developing new application features.

The ISV Plug & Play program consists of a packaged bundle that ISV Startups can leverage to accelerate the creation of a new RDS environment using baked in best practices.

## Architecture overview
Here is a diagram of our architecture and a brief summary of what you are going to set up.

![alt text](https://github.com/aws-samples/amazon-isv-plug-n-play/blob/main/media/RDS%20DB%20Cluster.png?raw=true)

The sample CloudFormation templates provision the network infrastructure and all the components shown in the architecture diagram. The CloudFormation templates are broken into the following three stacks.

1. CloudFormation template to set up VPC, subnets, route tables, internet gateway, NAT gateway, S3 gateway endpoint, AWS Secrets Manager interface endpoint, and other networking components.
    
2. CloudFormation template to set up an Amazon Linux bastion host in an Auto Scaling group to connect to the RDS DB cluster.
    
3. CloudFormation template to set up any of the following databases: Aurora PostgreSQL, RDS PostgreSQL, Aurora MySQL, RDS MySQL, with master user password stored in AWS Secrets Manager and bootstrap the database using AWS Lambda.

The stacks are integrated using exported output values. Using three different CloudFormation stacks instead of one nested stack gives you some flexibility. For example, you can choose to deploy the VPC and bastion host CloudFormation stacks once and Aurora PostgreSQL DB cluster CloudFormation stack multiple times in an AWS Region.

## Best practices, prerequisites, and setup instructions
For best practices incorporated in the sample AWS CloudFormation samples, prerequisites, and set up instructions, refer to the following documents.

[Deploy an Amazon Aurora PostgreSQL Serverless v2 DB cluster with recommended best practices using AWS CloudFormation](https://github.com/aws-samples/amazon-isv-plug-n-play/blob/main/Instructions/Deploy%20an%20Amazon%20Aurora%20PostgreSQL%20Serverless%20v2%20DB%20cluster%20with%20recommended%20best%20practices%20using%20AWS%20CloudFormation.pdf)

[Deploy an Amazon Aurora PostgreSQL DB cluster with recommended best practices using AWS CloudFormation](https://github.com/aws-samples/amazon-isv-plug-n-play/blob/main/Instructions/Deploy%20an%20Amazon%20Aurora%20PostgreSQL%20DB%20cluster%20with%20recommended%20best%20practices%20using%20AWS%20CloudFormation.pdf)

[Deploy an Amazon RDS PostgreSQL DB cluster with recommended best practices using AWS CloudFormation](https://github.com/aws-samples/amazon-isv-plug-n-play/blob/main/Instructions/Deploy%20an%20Amazon%20RDS%20PostgreSQL%20DB%20cluster%20with%20recommended%20best%20practices%20using%20AWS%20CloudFormation.pdf)

[Deploy an Amazon Aurora MySQL Serverless v2 DB cluster with recommended best practices using AWS CloudFormation](https://github.com/aws-samples/amazon-isv-plug-n-play/blob/main/Instructions/Deploy%20an%20Amazon%20Aurora%20MySQL%20Serverless%20v2%20DB%20cluster%20with%20recommended%20best%20practices%20using%20AWS%20CloudFormation.pdf)

[Deploy an Amazon Aurora MySQL DB cluster with recommended best practices using AWS CloudFormation](https://github.com/aws-samples/amazon-isv-plug-n-play/blob/main/Instructions/Deploy%20an%20Amazon%20Aurora%20MySQL%20DB%20cluster%20with%20recommended%20best%20practices%20using%20AWS%20CloudFormation.pdf)

[Deploy an Amazon RDS MySQL DB cluster with recommended best practices using AWS CloudFormation](https://github.com/aws-samples/amazon-isv-plug-n-play/blob/main/Instructions/Deploy%20an%20RDS%20MySQL%20DB%20with%20recommended%20best%20practices%20using%20AWS%20CloudFormation.pdf)
