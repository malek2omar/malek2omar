- 👋 Hi, I’m @malek2omar
- 👀 I’m interested in ...
- 🌱 I’m currently learning ...
- 💞️ I’m looking to collaborate on ...
- 📫 How to reach me ...



# Initial security approaches for AWS Cloud Environment 
## Table of Content

**1.0 Introduction**
+ 1.1	Your responsibilities  
+ 1.2	Cloud provider responsibilities
+ 1.3	Detailed Examples of shared security management responsibilities between you & AWS:
 * 1.3.1	AWS Lambda (Severless Functions)
 * 1.3.2	AWS Fargate (Serve less Containers)
 * 1.3.3	Amazon ECS/EKS  (Container management as a service)
 * 1.3.4	Amazon EC2 (Infrastructure as a service)		
 
**2.0	Potential Vulnerabilities that Exist Surrounding your Container**
+ 2.1	Images that you use to build your containers.
+ 2.2	Image registries that you use to store the images. 
+ 2.3	Container runtime that you use to execute your containers. 
+ 2.4	Orchestration platforms which you use to manage life cycle of multiple containers with.
+ 2.5	Host OS. 	

**3.0	Tools to for Security**
+ **3.1 Scanning Tools Category**
  * 3.1.1 AWS ECR (Clair)
  * 3.1.2 Docker Bench
  * 3.1.3 OpenScap for AWS (Security Content Automation Protocol)
  * 3.1.4 DevSecOps for the applications 
  > * 3.1.4.1 AWS CodeCommit
  > * 3.1.4.2  Software Composition Analysis (OWASP Dependency Check)
  > * 3.1.4.3 Static Analysis Security testing (SAST) Sonarqube 
  > * 3.1.4.4 Dynamic Analysis Security Testing (DAST) OWASP ZAP


+ **3.2	Monitoring Tools Category**  
  * 3.2.1  AWS CloudWatch
  * 3.2.2 Prometheus 
  * 3.2.3 AWS CloudTrail 
  * 3.2.4 AWS Config  
  * 3.2.5  Datadog:  
 
+ **3.3 AWS Firewall Tools Category**
  * 3.3.1  Activate AWS Shield
  * 3.3.2  Activate AWS WAF

+ **3.4	AWS Backup & Restore Tools Category (Apps, DBs, etc )**
+ **4.0	Compliances Planning**

+ **5.0	Extra: Red Team approach**




# Initial security approaches for AWS Cloud Environment 
## 1.0	 Introduction
Cloud Security is a shared management responsibility between you and the cloud provider.
### 1.1	Your responsibilities  
You secure the applications, workloads, and data you bring to the cloud. 
You secure data encryption, and key management using the hardware security module HSM.

### 1.2	Cloud provider responsibilities
Manages security of the entire Cloud platforms, compliance and securing network such as down and run time and isolations.

### 1.3	Detailed Examples of shared security management responsibilities between you & AWS: 
#### 1.3.1	AWS Lambda (Severless Functions)
##### AWS manages: 
+ Data Source integrations, physical hardware, software, networking, provisioning
##### You manage: 
+ Application code

#### 1.3.2	AWS Fargate (Serve less Containers)
##### AWS manages:
+ Container orchestration, provisioning, cluster scaling, physical hardware, OS/kernel, networking and facilities. 
##### You manage: 
+ Application code, data source integration, security config and updates, networking config, and management tasks.

#### 1.3.3	Amazon ECS/EKS  (Container management as a service)
##### AWS manages: 
+ Container orchestration control plane, physical hardware software,  networking and facilities.
##### You manage: 
+ Application code, data source integration, security config and updates, networking config, management tasks, firewall, and work clusters.

#### 1.3.4	Amazon EC2 (Infrastructure as a service)
##### AWS manages: 
+ Physical hardware software,  networking and facilities.
##### You manage: 
+ Application code, Data source Integration, security config and updates, networking config, management tasks, firewall, scaling and patching of servers. 

## 2.0	Potential Vulnerabilities that Exist Surrounding your Container

### 2.1	Images that you use to build your containers.
- Keep the images up to date (so we will have the latest security patches of the vulnerabilities)
- Scanning the images to detect new vulnerabilities and validation secure images. 
- Signing your images will essentially create a digital fingerprint  that you can use. 

### 2.2	Image registries that you use to store the images. 
Potential vulnerability because they contain all the images which contain you application code.
-	Keep it private: how many images you have, private access control of the users accessing the registry 
-	Regularly monitoring your registry: so you can track any vulnerability that come out.
-	Make sure host server for the registry is secure: so you can protect it from being compromised to protect your images and applications.

### 2.3	Container runtime that you use to execute your containers. 
-	Ensure Apps security 
-	Monitor you network protocols and network resources. 

### 2.4	Orchestration platforms which you use to manage life cycle of multiple containers with
-	Limiting the number of Privileged users 
-	Limiting the amount of Privilege that you give any user.   
-	Monitoring your Orchestration platform as well as your resources.

### 2.5	Host OS
which manages the Docker client, Docker daemon and the Kernel that is shared with our running Docker Containers.
It is one of the greatest vulnerabilities you can have in you container environment is compromised, the attacker will access your entire application environment.
-	Monitor the host.
-	Access Control.
-	Regularly, monitoring the OS and ensure patching against the updated vulnerabilities 


## 3.0	Tools to for Security 
### 3.1 Scanning Tools Category
#### 3.1.1 AWS ECR (Clair): Performs static scanning  for Docker images prior to deployment .




