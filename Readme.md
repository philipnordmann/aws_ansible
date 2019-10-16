# Ansible AWS demo
## Requirements
### Ansible and AWS Python Packages
First you need to install [ansible](https://docs.ansible.com) and all aws python packages.
You can just `pip install -r requirements.txt` to get all relevant changes
### Export environment variables
To get this ansible installation running and authenticating against AWS you have to export some variables:
```shell
export AWS_ACCESS_KEY_ID='YOUR_ACCESS_KEY'
export AWS_SECRET_ACCESS_KEY='YOUR_SECRET_ACCESS_KEY'
export AWS_VPC_ID='YOUR_VPC_ID'
export AWS_REGION='eu-central-1' # here you can choose a region you like
export AWS_PRIVATE_KEY_FILE="PATH_TO_YOUR_PRIVATE_KEY_FILE"
```
These will be used in ansible. You can find references to them here `inventory/group_vars/all/vars`.
Maybe create an awsrc and source it in. 

## How to use
### Playbooks
In the root there are 3 different playbooks. 
- **ec2_up.yml**: Will install 2 webserver and 2 application server instances. Also it will install some security groups and subnets.
- **ec2_down.yml**: Will remove everything from ec2_up.yml.
- **install_stack.yml**: Will install nginx to the webserver instances and wildfly to the application server instances. 