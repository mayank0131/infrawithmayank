# 🏗️ Travel Realm — Multi-Layer AWS Infrastructure Automation  
### Enterprise Infrastructure as Code | AWS Multi-Account | GitHub Actions CI/CD

---

### 📋 Overview  
The Travel Realm project implements a **three-tier AWS infrastructure system** that separates **governance**, **environment provisioning**, and **application delivery**. It demonstrates large-scale DevOps automation through Terraform modules and OIDC-secured CI/CD pipelines.

---

### 🧱 Architecture Layers

#### **Layer 1 — Organization Setup**
Handles governance and identity:
- AWS Organizations & sub-accounts creation  
- DNS and subdomain delegation  
- Budget monitoring and cost alerts  
- SSO users, permission sets, and IAM alignment  
- OIDC integration for GitHub Actions  

**Outcome:** Secure, policy-aligned multi-account AWS organization ready for CI/CD operations.

---

#### **Layer 2 — Environment Provisioning**
Creates reproducible infrastructure in child accounts:
- VPC, Subnets, NAT, IGW setup  
- RDS (PostgreSQL), Redis, ECS, ECR provisioning  
- Keycloak, Foundry API, and application deployment  
- Secrets management via AWS Secrets Manager  
- Load balancing and CloudFront routing  

**Outcome:** Parameterized environments ready for independent provisioning, with isolated data and traffic flow.

---

#### **Layer 3 — CI/CD Application Delivery**
Implements GitHub Actions pipelines for:
- **Frontend, Static, and POC Sites** – S3 + CloudFront builds with invalidation  
- **Backend Deployments** – ECS image updates from ECR  
- **SQL Deployment** – Optional DB bootstrap with CodeBuild  

**Outcome:** Complete build → deploy → test automation using Terraform + Actions.

---

### ⚙️ Key Highlights
| Category | Detail |
|-----------|---------|
| **IaC** | Fully modular Terraform with layered composition |
| **CI/CD Security** | OIDC-based authentication, no stored secrets |
| **Observability** | CloudWatch logging and custom metrics |
| **Resilience** | DR-aware network and DB configurations |
| **Extensibility** | New environments deployable via parameters |

---

### 🧩 Tech Stack
AWS Organizations, Terraform, ECS, RDS, CloudFront, S3, GitHub Actions, Secrets Manager, IAM, CloudWatch, Keycloak, Node.js, Vite.

---

### 🚀 Outcome
- 100% automated environment provisioning across AWS accounts.  
- Consistent CI/CD pipelines secured by temporary OIDC tokens.  
- Simplified onboarding for new dev environments.  
- Enterprise-grade reproducibility and governance.  
