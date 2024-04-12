## TOOLS USED
- **Terraform** for creating infrastructure on AWS.
- **GitHub Action** for CI part.
- **ArgoCD** for CD part.


## ARCHITECTURE OF APPLICATION
<img width="764" alt="voting-app-latest" src="https://github.com/anshuhtwt/CI-CD-using-Jenkins-and-ArgoCD-into-EKS-for-microservices/assets/95365748/c1a8030c-5129-4e19-913c-5a2686677686">

**The app consists of five components: Voting-App, Redis, Worker, Postgres and Result-App.**
   - **Voting-App:** A web interface for users to cast their votes.
   - **Redis:** A Redis database to collect new votes.
   - **Worker:** A background worker to process votes from Redis and store results in Postgres.
   - **Postgres:** A Postgres database to store the vote results.
   - **Result-App:** A web interface to display real-time vote count results.


## CONTINUOUS-INTEGRATION
**Create Secret**
![Screenshot 2024-04-13 at 1 51 07 AM](https://github.com/anshu049/Automated-CI-CD-Github-Action-ArgoCD-DockerHub-for-Microservices-on-EKS/assets/95365748/d662040a-4272-4fc5-a1a9-fbc3f5ec7327)

![CI PART 2](https://github.com/anshu049/CI-CD-using-Jenkins-and-ArgoCD-into-EKS-for-microservices/assets/95365748/dec4b8bc-aa36-473e-b274-bd3d831ab84e)


## CONTINUOUS-DELIVERY
**For git repository containing all the Manifests for the app, including the Kubernetes Deployment, Service and other resources [click here](https://github.com/anshuhtwt/Voting-App-Manifests).**

<img width="1315" alt="CD-PART" src="https://github.com/anshuhtwt/CI-CD-using-Jenkins-and-ArgoCD-into-EKS-for-microservices/assets/95365748/a84c7362-bff1-4d4a-8910-ec4f8bdfc051">




