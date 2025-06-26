# Full CI/CD Pipeline with AWS

This project demonstrates a complete end-to-end **CI/CD pipeline** built on AWS to automate the build, test, and deployment of a sample application. It was created as a hands-on implementation to deepen my DevOps skills and showcase best practices in automation, scalability, and cloud-native deployments.

## 🛠️ Technologies Used

- **AWS CodeCommit** – Source control repository for application code  
- **AWS CodeBuild** – Automated build service to compile and test the code  
- **AWS CodeDeploy** – Deployment service to automate releases to EC2/ECS  
- **AWS CodePipeline** – Orchestrates the entire CI/CD flow  
- **Amazon ECR** – Hosts Docker images for containerized apps  
- **AWS IAM** – Manages permissions for secure service interaction  
- **Docker** – Containerization platform  
- **Shell Scripting / buildspec.yml** – Build and test automation scripts

## 📁 Project Structure

```bash
.
├── app/                      # Application source code
├── Dockerfile               # Container configuration
├── buildspec.yml            # Build and test instructions
├── README.md                # Project overview

## 🚀 Pipeline Flow

Here's how the CI/CD pipeline works:

1. Developer pushes code to GitHub repository.
2. GitHub webhook triggers AWS CodePipeline.
3. CodePipeline uses AWS CodeBuild to:
   - Install dependencies
   - Run tests (if applicable)
   - Build the Docker image
   - Push the image to Amazon ECR
4. CodePipeline deploys the image to:
   - AWS Elastic Beanstalk **or**
   - Amazon ECS (depending on setup)
5. Notifications or logs are pushed to Amazon CloudWatch.
