# demo-ec2-serial-console

Demo solution for EC2 Serial Console capabilities. The purpose of the demonstration is to show that the EC2 serial console can be leverage to access your EC2 instance even when networking is restricted or entirely blocked. The stack deployed creates a single EC2 instance that leverages AWS Nitro instances capable of leveraging the EC2 Serial Console connection. The EC2 deployed has networking cut off to any IP address except 127.0.0.1. Key points are:

1. EC2 instance does not rely on VPC networking to access. VPC could completed isolated and administrator could access.
2. Access does not rely on SSH running - SSHD disabled/not running on deployment
3. Access does not rely on Amazon Systems Manager running - SSM is disabled on deployment
4. Access does not rely on local firewall - iptables configured to block everything on deployment.

In summary, the demonstration deploys a network impaired EC2 that can still be accessed by administrators.

## Parameters

The only parameters needed to filled in upon deploy are:

| Parameter | Description |
| --------- | ----------- |
| VPC | Select the VPC you are deploying the EC2 in |
| Subnet | Select a subnet within the VPC you are deploying in |
| EC2 User | The username of for the local account to be added |
| EC2 User Password | The password to log into the EC2 locally using the EC2 User |

## Deploy as CloudFormation

The deployment process leverages AWS CloudFormation and is relatively simple once prerequisites are satisfied. Overall the process entails three steps

**Steps to Deploy:**

1. Open your web browser and login to your AWS Account.
2. Click the `Launch Stack` button below to launch stack.
3. Fill in the parameter values

> **Note:** If you want to open the link as a new tab use `ctrl+click` when clicking the *launch Stack* button below.

[![Launch Stack](https://cdn.rawgit.com/buildkite/cloudformation-launch-stack-button-svg/master/launch-stack.svg)](https://console.aws.amazon.com/cloudformation/home#/stacks/new?stackName=demo-ec2-serial-console&templateURL=https://rolston-cloud-library.s3-us-west-2.amazonaws.com/demo-ec2-serial-console/demo-ec2-serial-console.yml)
