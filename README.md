# CloudFormation Template creating EC2 instance 

CloudFormation template to create EC2 instance hosting html page located in s3 bucket 

## Prequests 
1. HTML page uploaded in S3 bucket
2. SSH key generated from AWS console

## INPUTS
 Name | Description | Type | Default | 
|------|-------------|:----:|:-----:|
| InstanceType | WebServer EC2 instance type. | string | t2.micro |
| InstanceName | Name of EC2 instance. | string | n/a |
| ImageId | Latest Amazon Linux AMI SSM . | string | Latest Amazon Linux AMI |
| KeyName | Name of an existing EC2 KeyPair to enable SSH access to the instances. | string | n/a |
| SubnetIDs | List of available subnets | list | n/a |
| S3BucketName | Name of bucket to download HTML file from | string | n/a |
| IndexPrefix | Prefix of HTML file uploaded to S3 | string | n/a |

## OUTPUTS
| Name | Description |
|------|-------------|
|InstanceId | The instance ID of the web server |
| WebsiteURL | URL for newly created LAMP stack |
| PublicIP | Public IP address of the web server |
