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

## Existing vulnerabilities (Auto-Generated)
