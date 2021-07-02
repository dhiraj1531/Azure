# Azure
What is 3-Tier Architecture?

There are layer in 3-Tier architecture 

1) User interface 

2) Web layer 

3) DB layer 

I would propose to build infra by terraform automation tool

── main.tf                   // The primary entrypoint for terraform resources.
├── vars.tf                   // It contain the declarations for variables.
├── output.tf                 // It contain the declarations for outputs.
├── terraform.tfvars          // The file to pass the terraform variables values.

For the solution, we have created and used five modules:

1  resourcegroup - creating resourcegroup
2 networking - creating azure virtual network and required subnets
3 securitygroup - creating network security group, setting desired security rules and associating them to subnets
compute - creating availability sets, network interfaces and virtual machines
4 database - creating database server and database

All the stacks are placed in the modules folder and the variable are stored under terraform.tfvars

To run the code you need to append the variables in the terraform.tfvars

Each module consists minimum two files: main.tf, vars.tf

resourcegroup and networking modules consists of one extra file named output.tf

Deployment :

Step 0 terraform init

used to initialize a working directory containing Terraform configuration files

Step 1 terraform plan

used to create an execution plan

Step 2 terraform validate

validates the configuration files in a directory, referring only to the configuration and not accessing any remote services such as remote state, provider APIs, etc

Step 3 terraform apply

used to apply the changes required to reach the desired state of the configuration


