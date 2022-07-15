# Zscaler Posture Control (ZPC) - Vulnerable Cloudformation Template

This is "Vulnerable by Design" Cloudformation repository.

## Table of Contents

* [Introduction](#introduction)
* [Installation](#Installation)
* [Contributing](#contributing)
* [Support](#support)

## Introduction

This repository was built to enable DevSecOps design and implement a sustainable misconfiguration prevention strategy. It can be used to test a policy-as-code framework, inline-linters, pre-commit hooks or other code scanning methods.

## Installation

```bash
aws cloudformation create-stack --stack-name zpcstack --template-body file://zscfn.yaml --region us-east-1 --parameters ParameterKey=Password,ParameterValue=MyPassword10 --capabilities CAPABILITY_NAMED_IAM
```

Expect provisioning to take at least 5 minutes.

Multiple stacks can be deployed simultaniously by changing the `--stack-name` and adding an `Environment` parameter:

```bash
aws cloudformation create-stack --stack-name zpcstack2 --template-body file://zscfn.yaml --region us-east-1 --parameters ParameterKey=Password,ParameterValue=MyPassword10 ParameterKey=Environment,ParameterValue=dev2 --capabilities CAPABILITY_NAMED_IAM
```

## Important notes

* **Where to get help:** the [Zscaler Community](https://community.zscaler.com/)

Before you proceed please take a note of these warning:
> :warning: These examples creates intentionally vulnerable AWS resources into your account.

**DO NOT deploy this template examples in a production environment or alongside any sensitive AWS resources.**
**All passwords in this repo are used as an example and should not be used in production**

## Requirements

* aws cli

## Contributing

Contribution is welcomed!

We would love to hear about more ideas on how to find vulnerable infrastructure-as-code design patterns.

## Support

[Zscaler-BD-SA Team](https://github.com/zscaler-bd-sa) builds and maintains TerraGoat to encourage the adoption of policy-as-code.

If you need direct support you can contact us at [zscaler-partner-labs@z-bd.com](mailto:zscaler-partner-labs@z-bd.com).

## Existing vulnerabilities (Auto-Generated)

|    | check_id    | file          | resource                                  | check_name                                                                                                                                                                                               | guideline                                                                                                                    |
|----|-------------|---------------|-------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------|
| 0 | ZS-AWS-00023   | /zscfn.yaml | AWS::KMS::Key.LogsKey                     | Ensure rotation for customer created CMKs is enabled                                                                                                                                                     |                                                                                     |
|  1 | ZS-AWS-00028  | /zscfn.yaml | AWS::EC2::Volume.WebHostStorage            | Ensure that encryption is enabled for EBS volumes                                                                                                                                                      |                                                                              |
|  2 | ZS-AWS-00054  | /zscfn.yaml | AWS::EC2::SecurityGroup.WebNodeSG            | Ensure that Security Groups does not have unrestricted public access                                                                                                                                                      |                                                                              |
|  3 | ZS-AWS-00044   | /zscfn.yaml | AWS::EC2::SecurityGroup.WebNodeSG           | Ensure that Security Groups does not have unrestricted HTTP access                                                                                                                                                  |                                                             |
|  4 | ZS-AWS-00020  | /zscfn.yaml | AWS::EC2::SecurityGroup.WebNodeSG         | nsure that Security Groups does not have unrestricted SSH access                                                                                                                                        |                                                                   |
|  5 | ZS-AWS-00034  | /zscfn.yaml | AWS::S3::Bucket.LogsBucket         | Ensure that lifecycle configuration is applied to S3 buckets                                                                                                                                                      |                                                                                |
|  6 | ZS-AWS-00034  | /zscfn.yaml | AWS::S3::Bucket.OperationsBucket         | Ensure that lifecycle configuration is applied to S3 buckets                                                                                                                                                      |                                                                                |
|  7 | ZS-AWS-00034  | /zscfn.yaml | AWS::S3::Bucket.DataBucket         | Ensure that lifecycle configuration is applied to S3 buckets                                                                                                                                                      |                                                                                |
|  8 | ZS-AWS-00034  | /zscfn.yaml | AWS::S3::Bucket.DataScienceBucket                | Ensure that lifecycle configuration is applied to S3 buckets                                                                                                                                                          |                                                                          |
|  9 | ZS-AWS-00034  | /zscfn.yaml | AWS::S3::Bucket.FinancialsBucket                | Ensure that lifecycle configuration is applied to S3 buckets                                                                                                                                                          |                                                                          |
|  10 | ZS-AWS-00034  | /zscfn.yaml | AWS::S3::Bucket.FlowBucket                | Ensure that lifecycle configuration is applied to S3 buckets                                                                                                                                                          |                                                                          |
|  11 | ZS-AWS-00018  | /zscfn.yaml | AWS::S3::Bucket.LogsBucket                | Ensure that S3 buckets have access logging enabled                                                                                                                                                          |                                                                          |
|  12 | ZS-AWS-00018  | /zscfn.yaml | AWS::S3::Bucket.OperationsBucket                | Ensure that S3 buckets have access logging enabled                                                                                                                                                              |                                                                      |
|  13 | ZS-AWS-00018  | /zscfn.yaml | AWS::S3::Bucket.DataBucket                | Ensure that S3 buckets have access logging enabled                                                                                                                                                              |                                                                      |
|  14 | ZS-AWS-00018  | /zscfn.yaml | AWS::S3::Bucket.FinancialsBucket                | Ensure that S3 buckets have access logging enabled                                                                                                                                                              |                                                                      |
|  15 | ZS-AWS-00018  | /zscfn.yaml | AWS::S3::Bucket.FlowBucket                | Ensure that S3 buckets have access logging enabled                                                                                                                                                              |                                                                      |
|  16 | ZS-AWS-00025  | /zscfn.yaml | AWS::S3::Bucket.FlowBucket                | Ensure default server side encryption is enabled for S3 buckets                                                                                                                                                              |                                                                      |
|  17 | ZS-AWS-00025  | /zscfn.yaml | AWS::S3::Bucket.DataBucket                | Ensure default server side encryption is enabled for S3 buckets                                                                                                                                                              |                                                                      |
|  18 | ZS-AWS-00025  | /zscfn.yaml | AWS::S3::Bucket.DataScienceBucket                | Ensure default server side encryption is enabled for S3 buckets                                                                                                                                                              |                                                                      |
|  19 | ZS-AWS-00025  | /zscfn.yaml | AWS::S3::Bucket.DataScienceBucket                | Ensure default server side encryption is enabled for S3 buckets                                                                                                                                                              |                                                                      |
|  20 | ZS-AWS-00025  | /zscfn.yaml | AWS::S3::Bucket.FlowBucket                | Ensure default server side encryption is enabled for S3 buckets                                                                                                                                                              |                                                                      |
|  21 | ZS-AWS-00030  | /zscfn.yaml | AWS::EC2::Instance.EC2Instance               | Ensure that EC2 has detailed monitoring enabled                                                                                                                                                              |                                                                      |
|  21 | ZS-AWS-00030  | /zscfn.yaml | AWS::S3::Bucket.DBAppInstance                | Ensure that EC2 has detailed monitoring enabled                                                                                                                                                              |                                                                      |
|  22 | ZS-AWS-00001  | /zscfn.yaml | AWS::S3::Bucket.EC2Instance                | Ensure that IAM instance roles used to provision access to AWS resources                                                                                                                                                              |                                                                      |
|  23 | ZS-AWS-00001  | /zscfn.yaml | AWS::S3::Bucket.DBAppInstance                | Ensure that IAM instance roles used to provision access to AWS resources                                                                                                                                                              |                                                                      |
|  24 | ZS-AWS-00032  | /zscfn.yaml | AWS::RDS::DBInstance.DefaultDB                | Ensure that backup retention is enabled for RDS Instances
