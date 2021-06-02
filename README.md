# Webserver-on-AWS-using-terraform
Deploying Apache webserver on AWS using Terraform for infrastructure provisioning
# Brief Description
Main objective is to learn the fundamentals of virtualized infrastructure provisioning using Terraform. Here, Terraform is used to deploy an EC2 instance of Ubuntu on a vpc which automatically installs apache webserver that can handle web-traffic.To check if the web-server is up and running we can use the public IP address to access it or SSH into the Ubuntu instance and check if apache is running or not.
# File organization
# Step by step instructions
### Before getting started
Make sure to have an account on AWS which we will use to deploy our Ubuntu instance. 
Download and install Terraform on your machine from www.terraform.io by following their instructions.
Have an IDE on your machine, I personally prefer VScode.
Install Terraform extension on VScode.
### Time to code
There are examples on the registry provided by hashicorp about what syntax and how to use terraform to create resources. For AWS they can be found here: https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/

Step 1 Firstly, you need to install plugins for your provider here we are using AWS as our provider. The syntax is as follows 
```
provider "aws" {
  region     = "your_region"
  access_key = "your_access_key"
  secret_key = "secret_key"
}
```
Step 2 Create a VPC, which is a virtualized private cloud basically a virtualized network where we will launch our instances. The example usage is shown below from the terraform registry.
````
resource "aws_vpc" "main" {
  cidr_block = "10.0.0.0/16"
}
````
where "main" is the name, resource type is "aws_vpc" and cidr_block is the classless IP address for the network
