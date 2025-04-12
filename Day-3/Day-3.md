# Terraform 
![image](https://github.com/user-attachments/assets/64c93d88-8a0a-49ad-8590-e9d0689e0428)tereform script --> to avoid doing the same job again and again
whenever we want to create cloud resources like EC2, subnet, internet gateway,loadbalancer, database servers, or any resources u want to create by using automation or script, we use teraform
teraform --> widely used in  companies

Step 1:
 -install teraform on ur windows machine

Step 2:
 - set terraform path on Windows machine
 - ![image](https://github.com/user-attachments/assets/c09d2a33-0893-4bf7-9018-239da2b23085)

- install terraform from https://developer.hashicorp.com/terraform/install
- Create a terraform folder in program files in c drive
- extract the zip file downloaded(teraform) ---> browse it to the new folder created(terraform)
- add path to environmental variable


Step 3:
 - Configure AWS credentials from CLI (command line interface)
 - install AWS CLI
 - https://docs.aws.amazon.com/cli/latest/userguide/getting-started-install.html
 -![image](https://github.com/user-attachments/assets/e260f4ab-7091-49b1-97e7-50005cc3bdf6)
 -![image](https://github.com/user-attachments/assets/5ab5dcd7-560d-423a-aa02-bd7e7fa5adee)
 - check version --> aws --version

in AWS,
 ![image](https://github.com/user-attachments/assets/6fad3de2-9bd9-4ce8-af4c-bae2a9df0237)

When ur writing terraform files, we need to write blocks
- mention provider - provider blocks defines in which we are doing automatio(aws)
- resource block - what kind of resource that u want to create on the cloud (vpc,loadbalancers, subnets)
- define variable blocks - u want to pass any parameter as variables
- output files - if u want to print output in console like public/private ip address,vpc id


When u create an instance using terraform scripts, make sure to pass these 5 parameters
- amazon id
- instance type
- key-pair name
- storage
- instance name
- https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/instance

commands:
---------
 - terraform init --> will initialize terraform backend configuration with the cloud api. It is going to generate a license key to authenticate cloud provider 
   API as well as it is going to create. terraform folder, which contains -> license and neccesary files
 - terraform validate
 - terraform plan   -tells what u plan to do in the cloud
 - terraform apply
 Now ur server is ready!!!!
 - terraform destroy - will automatically delete all the resources 
 When u execute the command terraform plan --> it will automatically create terraform .tf state file, which contains the current state of the infrastructure



 whenever u create vpc - vpc should contain name and ip address range  & tennancy -
