## TOOLS USED
- **Terraform** for creating infrastructure on AWS.
- **GitHub Action** for CI part.
- **ArgoCD** for CD part.


## ARCHITECTURE OF APPLICATION
<img width="1027" alt="voting-app" src="https://github.com/anshu049/Automated-CI-CD-Github-Action-ArgoCD-DockerHub-for-Microservices-on-EKS/assets/95365748/3332eb78-3cd0-472c-9ede-fb145799a702">


**The app consists of five components: Voting-App, Redis, Worker, Postgres and Result-App.**
   - **Voting-App:** A web interface for users to cast their votes.
   - **Redis:** A Redis database to collect new votes.
   - **Worker:** A background worker to process votes from Redis and store results in Postgres.
   - **Postgres:** A Postgres database to store the vote results.
   - **Result-App:** A web interface to display real-time vote count results.


## CONTINUOUS-INTEGRATION
**Create Secret**
![Screenshot 2024-04-13 at 1 51 07 AM](https://github.com/anshu049/Automated-CI-CD-Github-Action-ArgoCD-DockerHub-for-Microservices-on-EKS/assets/95365748/d662040a-4272-4fc5-a1a9-fbc3f5ec7327)

![CI PART 2](https://github.com/anshu049/Automated-CI-CD-Github-Action-ArgoCD-DockerHub-for-Microservices-on-EKS/assets/95365748/8c2c769f-9f0c-4b46-bd22-97328f1ef95c)



## Create infrastructure using Terraform
- **Update kubeconfig to interact with EKS**
- `aws eks update-kubeconfig --name <cluster-name> --region <region-name>`


## CONTINUOUS-DELIVERY
**For git repository containing all the Manifests for the app, including the Kubernetes Deployment, Service and other resources [click here](https://github.com/anshuhtwt/Voting-App-Manifests).**




**Setup**
--------------
- Installed and configured the AWS Command Line Interface (CLI) to interact with EKS cluster.
- Installed kubectl to manage Kubernetes resources.
- Installed argocd CLI to interact with ArgoCD.
- Installed ArgoCD inside existing Kubernetes cluster.
- Expose the ArgoCD UI using a Kubernetes LoadBalancer service and retrieve the ArgoCD UI URL and login using the initial password and create application using [this](https://github.com/anshu049/Voting-App-Manifests/blob/master/application.yaml) yaml file.

![Argo UI](https://github.com/anshu049/Automated-CI-CD-Github-Action-ArgoCD-DockerHub-for-Microservices-on-EKS/assets/95365748/4460e7d9-8086-4ce5-adea-d53622a91e14)



- Access voting and result app using LoadBalancer attached to it.

![Vote UI](https://github.com/anshu049/Automated-CI-CD-Github-Action-ArgoCD-DockerHub-for-Microservices-on-EKS/assets/95365748/83ef9a51-a908-474f-97f7-bae6727f17f4)


![Result UI](https://github.com/anshu049/Automated-CI-CD-Github-Action-ArgoCD-DockerHub-for-Microservices-on-EKS/assets/95365748/49c156f8-9ab4-4e4e-83d8-2a2e4df931f4)


