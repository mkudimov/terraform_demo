## _Self-managed EC2 instance_

## Features

_**Terraform**_ сode creates an S3 bucket and an EC2 instance. Both resources are tagged with Name=Flugel, Owner=InfraTeam. In the EC2 instance, it runs a simple HTTP service written in Python with two endpoints:
* /tags: displays EC2 instance tags.
* /shutdown: shutdowns the instance.

_**Terratest**_ code validates the terraform code that both resources are tagged properly.

There is a configured _**Github action**_ that runs a pipeline to validate implementations of above terraform and terratest features.


## Test
To run and test the automation you should have
* an IAM user that has _**AmazonEC2FullAccess**_, _**AmazonS3FullAccess**_ and _**IAMFullAccess**_ permissions
* a repository with two actions secrets: _**AWS_ACCESS_KEY_ID**_ and _**AWS_SECRET_ACCESS_KEY**_ that allow to act on behalf of the user from the previous step. This repository also must contain .github/workflows/main.yml file copied from this repo  

Now you should 
* create a local copy of your repository and create a new branch there
* clone this repository and copy the repository content to your local repository copy
* push the new branch
* create a Pull Request 

_***you should keep the same repository structure as this one**_