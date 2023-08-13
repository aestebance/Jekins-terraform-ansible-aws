# Jenkins, terraform and ansible in AWS
With this project you can deploy **Jenkins** in **AWS** (EC2) with **terraform** and provisioned by **ansible**. 

## Prerequisites
- AWS CLI
- Python
- Boto3
- Terraform
- Ansible
- An AWS account with administrator privileges and custom domain in Route 53 hosted zone.

## Installing
- Create a S3 bucket in your AWS account.
- Configure aws cli with your keys.
- Modify `backend.tf` file.
  - region: The region of the S3 bucket where you´ll save the state of the project
  - profile: Profile of the aws cli keys
  - key: Name of the state in the bucket
  - bucket: Name of the bucket in your AWS account.
- Create RSA key
  - `ssh-keygen -t rsa`

## Deploying
 ```
 - terraform init
 ```
 ```
 - terraform plan
 ```
 ```
 - terraform apply
 ```

 ## Login in jenkins
 After deploying you can enter into your jenkins app with next user/pass: `admin:password` (you can change if after). The url will by prompted by console, but, by default, will be `jenkins.yourdomain.com`

 ## Scaling
 You can add or delete nodes changing in `variables.tf` the worker-count variable and re-redeploying with `terraform apply`

 ## Remember
 If you want to use these jenkins application you´ll need to update the url in global configuration and change the user and password.