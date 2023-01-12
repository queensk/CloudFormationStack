# CloudFormationStack

## template for Ec2 vpc

A Virtual Private Cloud (VPC) stack is a collection of AWS resources, such as subnets, route tables, and security groups, that work together to provide a secure and isolated networking environment for your AWS resources.

This is a CloudFormation template written in YAML format, which can be used to create a new VPC stack in AWS. It defines one resource, a VPC, using the AWS resource type AWS::EC2::VPC.

It sets some properties on this resource like CidrBlock, which is the IP range of the VPC, in this case is set to 10.0.0.0/16 which means the VPC will have 65536 IP addresses available.

EnableDnsHostnames is set to true and it enable the VPC's instances to resolve hostnames and IP addresses when they connect to the Internet or to other VPCs.

It also set up a tag on this resource, a key-value pair with the key name and value 0x0MyVPC, this will be used for identifying and filtering resources in the AWS Management Console and command line interfaces.

### stack creation

```
aws cloudformation create-stack  --stack-name myStackTest --region us-east-1 --template-body file://ec2vpc.yml
```

### stack update

```
aws cloudformation update-stack  --stack-name myFirstTest --region us-east-1 --template-body file://ec2vpc.yml
```

### Describe stack

```
aws cloudformation describe-stacks --stack-name myStackTest
```

### Deflecting stack

```
aws cloudformation delete-stack --stack-name myStackTest --region us-east-1
```
