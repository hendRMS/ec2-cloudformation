# CloudFormation Template for creating EC2 instance 

CloudFormation template for creating EC2 instance hosting html page located in s3 bucket <br /> 
It is using Cloudfromation Helper Scripts to configure and install apache WebServer

## Prequests 
1. HTML page uploaded in S3 bucket (attached in rep **webapp.html** as an example).
2. SSH key generated from AWS console.

## Parameters
 Name | Description | Type | Default | 
|------|-------------|:----:|:-----:|
| InstanceType | WebServer EC2 instance type | string | t2.micro |
| InstanceName | Name of EC2 instance | string | n/a |
| ImageId | Latest Amazon Linux AMI SSM  | AWS::SSM::Parameter::Value<String>| Latest Amazon Linux AMI |
| KeyName | Name of an existing EC2 KeyPair to enable SSH access to the instances | AWS::EC2::KeyPair::KeyName  | n/a |
| S3BucketName | Name of bucket to download HTML file from | string | n/a |
| IndexPrefix | Prefix of HTML file uploaded to S3 | string  | n/a |
| VPC | VPC that EC2 will operate in it | AWS::EC2::VPC::Id | n/a |
| SubnetId |Subnet ID that EC2 will operate in it, should be a subnet in selected VPC | AWS::EC2::Subnet::Id | n/a |


## Outputs
| Name | Description |
|------|-------------|
|InstanceId | The instance ID of the web server |
| WebsiteURL | URL for newly created LAMP stack |
| PublicIP | Public IP address of the web server |
