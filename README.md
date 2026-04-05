# 🚀 AWS CI/CD Pipeline for Java Web Application

This project demonstrates a complete end-to-end CI/CD pipeline for deploying a Java web application using AWS services.

The pipeline automates everything from code commit to production deployment, following modern DevOps practices.

---

## 🧠 Project Overview

This project showcases how to:

- Build and manage a Java web application using Apache Maven
- Store dependencies securely using AWS CodeArtifact
- Automate builds and testing with AWS CodeBuild
- Deploy infrastructure using AWS CloudFormation
- Deploy applications using AWS CodeDeploy
- Orchestrate the full pipeline using AWS CodePipeline

---

## 🏗️ Architecture
<img width="666" height="206" alt="Captura de pantalla 2026-04-05 a la(s) 01 33 21" src="https://github.com/user-attachments/assets/7670eef3-c432-4801-a22b-088e8f97be01" />



### Flow:

1. Developer pushes code to GitHub
2. CodePipeline triggers automatically
3. CodeBuild compiles and tests the application
4. Artifacts are stored in S3
5. CodeDeploy deploys the application to EC2
6. Application is served via Apache Tomcat

---

## 🛠️ Technologies Used

- **Java (Amazon Corretto 8)**
- **Apache Maven**
- **Apache Tomcat**
- **AWS EC2**
- **AWS S3**
- **AWS CodeArtifact**
- **AWS CodeBuild**
- **AWS CodeDeploy**
- **AWS CodePipeline**
- **AWS CloudFormation**
- **GitHub**

---

## ⚙️ Setup Steps

### 1. Launch EC2 Instance

- Amazon Linux
- Installed:
  - Apache Maven
  - Amazon Corretto 8 (Java 8)

```bash
sudo dnf install -y java-1.8.0-amazon-corretto-devel
```

### 2. Generate Web App with Maven

```bash
mvn archetype:generate \
   -DgroupId=com.nextwork.app \
   -DartifactId=nextwork-web-project \
   -DarchetypeArtifactId=maven-archetype-webapp \
   -DinteractiveMode=false
```


### 3. Configure AWS CodeArtifact
	
  -	Created repository for Maven dependencies
	-	Configured settings.xml
	-	Used IAM roles and policies for secure access


### 4. Connect to GitHub

-	Integrated repository using AWS CodeConnections
-	Pipeline triggers automatically on code push

⸻

## 5.🧪 Automated Testing

A custom test script validates the project before build:

```bash
./run-tests.sh
```


Tests include:
	-	Project structure validation
	-	Presence of required files
	-	Basic sanity checks



## 6. ⚙️ Build Process (CodeBuild)

The build is defined in buildspec.yml.




📦 Artifacts

  -	Output: .war file
	-	Stored in S3
	-	Used by CodeDeploy



## 7. 🚀 Deployment (CodeDeploy)
	
  -	Deployment automated using appspec.yml
	-	Application deployed to EC2 instance
	-	Served using Apache Tomcat



## 8. 🔄 CI/CD Pipeline (CodePipeline)

Pipeline stages:
-	1.	Source (GitHub)
-	2.	Build (CodeBuild)
-	3.	Deploy (CodeDeploy)


Features:
 
  -	Automatic deployment on code changes
	-	Continuous integration
	-	Continuous delivery



## 9. 🔁 Rollback Strategy

-	Manual rollback via CodePipeline
-	Restores last working deployment

⸻

## 10. 🌐 Live Application

Application is deployed on EC2 and served via Apache Tomcat.

⸻

## 💡 Key Learnings
	
  -	End-to-end CI/CD pipeline design
	-	Infrastructure as Code (CloudFormation)
	-	Secure dependency management (CodeArtifact)
	-	Automated testing in CI
	-	Deployment automation with CodeDeploy
	-	Real-world DevOps workflows using AWS


## 🔥 Future Improvements
	
  -	Add real unit tests (JUnit)
	-	Integrate CloudWatch monitoring
	-	Add HTTPS with ALB + ACM
	-	Dockerize the application
	-	Deploy using ECS/EKS



## 👨‍💻 Author

Adriana
Cloud & DevOps Enthusiast 🚀
:::



