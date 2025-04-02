problem with the container:
--------------------------
containers will not support the auto-screening
```
- scale up - whenever profit increase, we hav to increase the number of servers
     - vertical scaling - u hav to increase the system resources
     - horizontal auto-scaling  - we hav to add additional server to existing infrastructure
```
```
- scale down - whenever traffic goes down , we hav remove the additional servers
             - containers will not support load balancing
             - if the container is down , we are going to get application downtime so we hav to with containers\
             - containers will not support self healing process.
```
to overcome the problems we are moving towards to war orchestration tool
<br>
what us kubernetes??
+ kubernetes is a container management tool, it is going to manage all the containers
+ kubernetes performs the automatic deployment of the application

kubernetes features:
---------------------
+ orchestration
+ auto-scaling
+ load balancing
+ self healing
+ it is platform independent - can run on any cloud
+ to perform the automation kubernetes , we write manifested (aml) file


1. Create a jump server or bastion host  (create instance using ubuntu) (sameeksha-bastianhost)

2. we hav to install kubectl ekctl, awscli
   ![image](https://github.com/user-attachments/assets/f1dbb659-26a0-4ddb-b82e-29524cc48be4) <br> (copy from here )
   - vi cluster.sh (in putty) and right click (if not enter I and right click )
   - esc and enter :wq
   - chmod 777 cluster.sh
   - sh cluster.sh
   - sudo su
   - ls
   - sh cluster.sh (long package download) (output: cluster.sh: 42: source: not found)
   - now in aws --> search for IAM and select users from the sidebar --> create user --> sameeksha-k8s -->next -->3rd block & 2nd option administrativeaccess --> create user --> cliateck on sameeksha-k8s -->security credential --> create access key -->user key - keep it blank --> next and download csv file

     ![image](https://github.com/user-attachments/assets/be8f6a57-e0c6-485f-bb64-cd212bec3ef4)
  - copy access key other from here
     ![image](https://github.com/user-attachments/assets/803d06cd-787f-42de-80e3-2c96c7972019)
     ![image](https://github.com/user-attachments/assets/ef2754d6-0a68-4c75-964f-f279df0c8129)

     in putty
     - eksctl
     - clear
     - eksctl create cluster --name sameeksha-cluster --version 1.31 --region ap-south-1 --nodegroup-name test-linux --node-type t2.micro --nodes 3 --nodes-min 3 --nodes-max 5 --managed  (to create cluster)

     

