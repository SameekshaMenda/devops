Cluster
=======
- Kubernetes will manage the application in a cluster
- What is cluster??
- It is a group of nodes; it contains a master node and a worker node.
  
   The master node
   -----------
  - it is the hero of the cluster which is going to take care of the cluster head
  - is responsible for the overall health of the cluster
  - we hav 4 components in master node ,
    1. API server - it is a hero of the server , whenever u want to perform load balancing,auto-scaling it plays a crucial role.
    2. ETCD - it is a distributed DB where ur going to store all the details abt the cluster, application info inside the etcd
    3. controlller - n is responsible for monitoring health of the application , it is always checked  desired status = actual status
    4. scheduler - it is component which is going to schedule a pod in a node.
    <br>
    **NOTE:** pod - in k8s , it will run the application in a pod, which contains containers, which containers docker image, it is the smallest deployable unit in  the kubernetes.
  
   The worker node
   -----------
  - it is where u deploy a server running on the cluster
  - worker node components:
    1. kubelet - this components exists inside worker node, it is responsible for creating pods, which is going to act as agent, if something goes wrong then it communicates to the master node.
    2. Container runtime - it is like a docker, it is responible for pulling the docker image, creating container, starting the container, it is responsible for managing the container lifecycle.
    3. kube-proxy - it is a networking component in the worker node, it is responsible for creating deployments, exposing application over the internet
 
  - in a cluster we should atleast 1 master node and worker node.
  - there are 2 types :
  - on premises - we hav to manage this cluster by ourselves, if something goess wrong in application downtime , we r responsible for that
  - cloud manage clusters - this cluster is managed by the cloud providers , if something goess wrong , they are responsible for our application
  - in aws , if u want to create a cluster , we hav a service called EKS (elastic kubernetes service)

 in putty:
 
  - snap install kubectl --classic
  - aws eks update-kubeconfig --name sameeksha-cluster --region ap-south-1
  - kubectl get nodes (to get list of nodes)(there should be 3 since we mentioned earlier as 3)

     when u create pod file , 4 things are imp:
    1. API version - defines the schema representation of the object
    2. kind - defines what kind of object u are creating
    3. Meta-data - defines name of the object (if u want to assign labels we need to define meta data)
    4. spec - defines behaviour of the object
   
    1 cpu = 100 milliqoates
    1gb = 1024 megabytes

    
in vscode :

1. create a folder called sameeksha-k8s-maifests
2. create pod.yaml and write code
3. open terminal and enter  " git add . ; git commit -m "my first yaml file" " and publish as public

   
in putty:

- git clone https://github.com/SameekshaMenda/sameeksha-k8s-manifests.git
- ls
- cd sameeksha-k8s-manifests
- kubectl apply -f pod.yaml
- kubectl get pods
-  kubectl get pods -o wide
-  kubectl describe pod sample-pod



new class:
=========
 in putty:

 - sudo su
 - kubectl get  nodes
 - ![image](https://github.com/user-attachments/assets/e8b86a6e-1d59-4bbc-9088-615fde1f8d1c)
 -  kubectl get namespace
 -  kubectl get all -n kube-system
 -  kubectl create ns sameeksha-ns
 -  kubectl get ns
 - kubectl get pods
 - kubectl run test-pod --image ngnix --port 80 -n sameeksha-ns (to create pod)
 - kubectl get pods (doesnt give ut pod name)
 - get pods -n sameeksha-ns (so enter this)
 -  kubectl delete pod test-pod -n sameeksha-ns (if the pod goes down the n we face 3 problems)
 1.  problem 1: we ll get application down time - to overcome this we hav to attach controllers to the pod
 2.  every pod has own IP address , if pod goes down , the ip address will change - to overcome this we hav have to create services in kuberntes (it will create static URL)
 3.  if pod goes down, along with the pod, we will loose the data - to overome this, we hav to implement volumes in k8s

Replica set:
it is a k8s object, it is going to maintain minimum number of nodes 24 x 7 ( replica set is always desire state == actual state)




namespace:
=========

Dividing cluster into an isolated environment, when we have multiple teams and projects, we use the concept of namespace
default - it is created automatically in k8s, to create a resource with default namespace
kube-node-lease  - to check the health of the node, kubernetes master node use this objects
kube-public  - anyone can access resources in this namespace

- the time of cluster creation by default all the resources such metric server, core DNS .. all the resources are created in this ( kube-system )

- note : when u deploing application production server, we ll never deploy any application with default namespace

in vscode:

![image](https://github.com/user-attachments/assets/af27ab30-7a55-4771-b678-033cb6abf7b7)

now in putty:

- ls 
- cd sameeksha-k8s-manifests
- git pull
- kubectl apply -f rs.yaml
- ![image](https://github.com/user-attachments/assets/5e79f5cf-9c42-4f60-94f2-c64523fa2fa6)
- kubectl get pods -n sameeksha-n
-  kubectl get rs -n sameeksha-ns
-  ![image](https://github.com/user-attachments/assets/dba8251a-c28c-4c8b-86fb-ceffc0639709)
![image](https://github.com/user-attachments/assets/89e7c7f0-0aeb-4614-941e-504fb197e94d)
![image](https://github.com/user-attachments/assets/56e8f368-ad6b-4827-b892-797b7dbc84cf)
![image](https://github.com/user-attachments/assets/59386ada-a536-4d7a-ad5f-44896724795c)




- replica set problmes
in real time application ,we dont recommend use of replica set, because we cant able to perform rollout, rollback operations
-deployments?
-in k8s , we deploy applications using deployment controllers; deployment will manage the replica set. The replica set will manage the pod


if u want to expose application through web browser, k8s will execute 
3 services we have:
1. cluster ip service
2. 2 node pod service
3. load balancer service

we r going to implement load balancer services

SRE job

MONITORING:
- to understand whats going inside the application, we r implementing monitoring dashboard, whith the help of these we can recognise if something goes wrong in the application and also we are able to identify how much CPU, memory consuming podes, nodes, cluster heads -- can be identified
- monitoring tools like promethus , graphana
- promethus is a metrix server where it is going to collect times series od data tstb , it sends data to graphana dashboards
- grafana , with help of this, we can setup monitoring dashboards, where we can see ur data in the form of pycharts or graphs

- ansebl is a configuration management tool, 
