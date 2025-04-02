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
... kubernetes is a container management tool, it is going to manage all the containers
