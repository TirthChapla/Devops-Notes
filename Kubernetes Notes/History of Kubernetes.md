# History of Kubernetes</span> 

> “It works on my machine but not on the server” 🤨


## <span style="color:magenta"> 1. Tradionaal Deployment 

- Ww have the sprig boot application in our personal PC, now we want to deploy.
- We run our Physical server/MAchine 24/7 and add the required depedencies(Internet , IP-Address ,Domain name). 
- We copy the application to the server and run it.
- Now the application is live and we can access it from anywhere.
- Now the user traffic increases and we need to scale the server/machine.
- So, we buy another cpu and rams and try to scale.

### Disadvantages:

- Very expensive
- Very slow to scale
- Hardware was mostly unused
- We require a team to manage the physical servers.

---

## <span style="color:magenta"> 2. Entry of Cloud (AWS, GCP, Azure)

- Cloud providers provide online machines on demand.
- We can create and destroy servers as needed.
- We can scale up or down quickly.

### Problems:
- We had build the application on the Windows machine but the server is Linux based.
- The application may not run the same way on different OS.
- Different servers may have different software versions. 


---

## <span style="color:magenta"> 3. Soluntion : Virtualization

- Virtualization allows us to create the template of the local machine.
- Virtualization allow us to user our own OS and applications.
- That template can be used to create multiple virtual machines on the cloud.

### Disadvantages:

- Each VM is heavy (Operating System + Application).
- Starting a VM takes time.
- Sending is not easy.
- Scaling is not easy.

---

## <span style="color:magenta"> 4. Lighter Weight Solution (Containers):

- Containers are lightweight beacuse they don't have their own OS.
- Containers share the host **OS kernel**.
- Containers start very fast.

- We create the image of the application with all its dependencies.
- That image can be run anywhere (local machine, cloud server, different OS).

- we run our image in the container runtime **(like Docker)**.

---

## <span style="color:magenta"> 5. Handling Containers

- We can run multiple containers on a single machine.
- Containers can be started and stopped quickly.

- Base on **user traffic** we can start more containers or stop some containers.

### Problems: **(Orchestration of Containers)**

- What if a container crashes?
- What if traffic suddenly increases?
- What if a server goes down?
- How do hundreds of containers communicate?


---

## <span style="color:magenta"> 6. Master of Orchestra : **Kubernetes**

- Kubernetes is a tool to manage containers automatically.
- It is also called **K8s**
- It handles:
  - Scaling
  - Healing
  - Load Balancing
  - Deployment
  - Networking
  - Storage

### Cloud vendor Lock-in Problem:

- If I use AWS ECS (Elastic Container Service):
  - We have to write the configuration in AWS specific way.
  - I am tied to AWS.
  - I cannot easily move to another cloud provider.

- Now if I decide to move to GCP or Azure:
  - I have to rewrite the configuration.
  - I have to learn their orchestration tool.

### Benefits of Kubernetes:

- It provide **Generic Orchestration Rules**.
- It works on any cloud provider (AWS, GCP, Azure).
- Migration between cloud providers is easy.

---
##  <span style="color:magenta"> 7. Architecture of Kubernetes :

![alt text](image.png)

1. Physical Machine (Control Plane / Master Node)
    *  We need to install: 
        - kube API Server
        - etcd KV Store
        - kube Scheduler
        - kube Controller Manager
2. Physical Machine (Worker Node)
    * We need to install:
        - kubelet
        - kube Proxy
        - Container Runtime (Docker)
3. User Machine
    * We need to install:
        - kubectl CLI tool  

---
                




