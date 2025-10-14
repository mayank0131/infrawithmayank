## 🧩 Projects

### 🔹 AWS Infrastructure Experiments

**Stack:** AWS, Terraform, EC2, Nginx, Apache, GitHub Actions, Route53, Let’s Encrypt, PM2

A personal experimentation space where I implement, test, and document interesting AWS infrastructure and deployment scenarios using Terraform, EC2, Route53, and GitHub Actions.

**Highlights:**
- **Web Hosting on EC2:**  
  - Application hosted in private subnet via Apache, served through Application Load Balancer (ALB).  
  - Domain integrated with Route 53; outbound internet access via NAT Gateway.  
- **Disaster Recovery (DR) Scenario:**  
  - Apache web app hardened against server and AZ failures.  
  - Ensures data persistence and DNS continuity during failover.  
- **NodeJS App Hosting (EC2 + Nginx + Let’s Encrypt):**  
  - Node.js app served via Nginx reverse proxy, SSL secured with Let’s Encrypt, process managed using PM2.  
- **GitHub Actions Setup:**  
  - Complete CI/CD via Terraform workflows using OIDC-based authentication.  
  - Separate workflows for PRs and pushes, reusing a shared boilerplate workflow for plan/apply logic.
  
**Repository:** [mayank0131/AWSFiddling](https://github.com/mayank0131/AWSFiddling)

---

### 🔹 Azure DevOps — ComfyUI Infra Pipeline
**Private Project (Azure DevOps + Terraform + VM Orchestration)**  

An Azure DevOps pipeline that automates infrastructure provisioning and VM configuration for ComfyUI, including SSH access, persistent disks, and app deployment.

**Pipeline Overview:**
- **Variables Managed:** Azure subscription ID, user object ID, and whitelisted IPs.  
- **Modes of Execution:**
  - *Infra Creation:* Builds base infrastructure (networking, disks, key vaults).  
  - *VM Attach:* Creates or destroys VMs attached to that infrastructure.  
- **End-to-End Automation:**  
  - Uses pipeline parameters to decide infra/VM scope and deploy/destroy actions.  
  - Configures SSH keys, installs ComfyUI, and persists models on Azure Disk.  
- **Custom Model Deployments:**  
  - Secure SCP upload of models via retrieved SSH key from Key Vault.  
  - Persistent storage ensures data survives VM teardown.

**Stack:** Azure DevOps, Terraform, Azure VM, Key Vault, SSH, ComfyUI  

---

### 🔹 Azure DevOps — Secure WebApp Deployment Setup
**Private Project (Azure DevOps + App Service + ACR + Entra ID + Azure CLI)**  

A secure, end-to-end web application deployment setup combining manual Azure configuration with automated CI/CD pipelines. The project established identity, access, and registry integrations using Azure CLI and Entra ID, followed by automated deployment through Azure DevOps.

**Setup Overview:**
- **Identity & Access Configuration:**
  - Created App Registrations and Service Principals in Entra ID to represent the CI/CD pipelines and App Services.
  - Defined custom App Roles and secrets under Certificates + Secrets for controlled authentication.
  - Linked the Service Principals to resource groups via IAM role assignments (Contributor, AcrPull, Storage Blob Data Contributor)
  - Enabled Managed Identity for App Services to pull images directly from Azure Container Registry (ACR)
  - Automated role bindings and App Service configuration.
  - Configured federated identities for Azure DevOps pipelines — ensuring passwordless, OIDC-based access to Azure resources.
- **Pipeline Automation:**  
  - Established secure Azure Resource Manager and Docker Registry service connections in Azure DevOps.  
  - Implemented CI/CD to build Docker images, push them to ACR, and deploy to App Services.
  - Integrated Terraform templates (from private repo) to handle infrastructure provisioning when required.
- **Governance & Access:** 
  - Created a controlled DevOps organization and teams in Azure DevOps with restricted user access.
  - Separated build and release identities to ensure least-privilege access in multi-stage pipelines.

**Stack:** Azure DevOps, Azure CLI, App Service, ACR, Entra ID, Docker  

---

### 🔹 Multi-Layer AWS Infrastructure for Travel Realm
**Private Project (Terraform + AWS Multi-Account + GitHub Actions CI/CD)**  

Designed a **three-layer AWS infrastructure system** for Travel Realm that modularizes the organization setup, environment provisioning, and application delivery pipelines. Enables secure, automated, and scalable infrastructure deployments across multiple AWS accounts.

**Layers Overview:**
1. **Organization Setup:**  
   - Creates organizations, SSO users, budgets, and DNS.  
   - Configures OIDC for GitHub Actions and sets up IAM policies for pipeline access.  
2. **Child Account Environments:**  
   - Creates complete infra stacks (VPC, RDS, Redis, ECS, S3, CloudFront).  
   - Manages secrets, load balancers, and environment isolation.  
3. **CI/CD Pipelines:**  
   - GitHub Actions workflows for frontend, backend, and database delivery.  
   - Fully automated deployments with cache invalidation and OIDC authentication.  

**Outcome:**  
- Automated end-to-end environment provisioning.  
- Clear separation between governance, infra, and app delivery layers.  
- Reduced environment setup time from days to hours.  

**Stack:** AWS Organizations, Terraform, ECS, RDS, CloudFront, GitHub Actions, Secrets Manager, IAM Identity Center  

---

## 🧠 Notes for Future Additions
- **AI-assisted Infrastructure Provisioning**: Experimenting with AI-driven Terraform plan recommendations.  
- **Container Cost Optimization Suite**: Planned project analyzing ECS cost and scaling efficiency.  
- **Cross-Cloud Comparison Framework**: Comparing Azure vs AWS Terraform pipelines with same IaC logic.

---

### 💼 [View Full Case Study → Travel Realm Infrastructure](./travel_realm_case_study.md)
