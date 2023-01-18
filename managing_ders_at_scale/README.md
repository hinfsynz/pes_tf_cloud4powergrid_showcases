# Aggregating and Managing DERs at Scale through the Cloud

## Solution Architecture Diagram
![solution arch diagram](docs/managing_ders_at_scale_soln_arch.png?raw=true "Solution Architecture for Cloud-based DER Aggregation and Management")

##  Installing and Configuring Prerequisites
Check [here](https://github.com/nvm-sh/nvm) to learn how to install Node.js and npm

Install the AWS CDK Toolkit globally using the following Node Package Manager command.
```ini
npm install -g aws-cdk
```
Run the following command to verify correct installation and print the version number of the AWS CDK.
```ini
cdk --version
```
Create a CDK project in your project folder
```ini
cdk init der-management --language=typescript
```

## Bootstrapping
Deploying stacks with the AWS CDK requires dedicated Amazon S3 buckets and other containers to be available to AWS CloudFormation during deployment. Creating these is called [bootstrapping](https://docs.aws.amazon.com/cdk/v2/guide/bootstrapping.html). To bootstrap, issue:
```ini
cdk bootstrap aws://${ACCOUNT-ID}/${AWS-REGION}
```

## Build CDK Project
To build the project, run the command below
```ini
cdk synth
```
To deploy the template that you synthesized with CDK synth on an AWS account. You need to install AWS CLI on the build machine and set up an AWS profile
```ini
cdk deploy
```

If you wish to remove the stack from your AWS account, then run the following command
```ini
cdk destroy
```