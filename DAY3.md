![image](https://github.com/user-attachments/assets/64c93d88-8a0a-49ad-8590-e9d0689e0428)tereform script --> to avoid doing the same job again n again
whenever we want to create a cloud resources like EC2,subnet,internet gareway,loadbalancer,database servers, any resources u want to create by using automation or script - we use teraform
teraform --> widely used in  companies

-step 1:
 -install teraform on ur windows machine

-step 2:
 -set terraform path on windows machine
 -![image](https://github.com/user-attachments/assets/c09d2a33-0893-4bf7-9018-239da2b23085)

-install terraform from https://developer.hashicorp.com/terraform/install
-create terraform folder in program files in c drive
-extract the zip file downloaded(teraform) ---> browse it to the new folder created(terraform)
-add path to environmental variable


-step 3:
 -configure AWS credentials from CLI (command line interface)
 -install AWS CLI
 -https://docs.aws.amazon.com/cli/latest/userguide/getting-started-install.html
 -![image](https://github.com/user-attachments/assets/e260f4ab-7091-49b1-97e7-50005cc3bdf6)
 -![image](https://github.com/user-attachments/assets/5ab5dcd7-560d-423a-aa02-bd7e7fa5adee)
 -check version --> aws --version

in AWS,
 ![image](https://github.com/user-attachments/assets/6fad3de2-9bd9-4ce8-af4c-bae2a9df0237)

when ur writing terraform files we need to write blocks
-mention provider - provider blocks defines in which we are doing automatio(aws)
-resource block - what kind of resourse that u want to create on cloud (vpc,loadbalancers,subnets)
-define variable blocks - u want to pass any parameter as variables
-output files - if u want to print output in console like public/private ip address,vpc id


when u create instance using terraform scripts - make sure to pass these 5 parameters
- amazon id
- instance type
- key-pair name
- storage
- instance name
- https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/instance

commands:
 -terraform init -> will insitialize terraform backend configuration with the cloud api . It is going to generate a liciencse key to authenticate cloud provider api as well as it is going to create . terraform folder which contains -> license and neccesary files
 -terraform validate
 -terraform plan   -tells what u plan to do in the cloud
 -terraform apply
 now ur server is ready
 -terraform destroy - will automatically delete all the resources 
 when u execute the command terraform plan --> it will create automatically terraform .tf state file which contains the current state of the infrastructure



 whenever u craete vpc - vpc should contain name and ip address range  & tennancy -
