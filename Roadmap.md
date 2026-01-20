# DevOps & Cloud Engineer Roadmap: 2026 Edition

## Phase 1: The Foundation (Prerequisites)
Before touching any tools, you must understand where the code lives and runs.

### 1. Software Development Lifecycle (SDLC)
* **What & Why:** Understanding the journey of code from a developer's laptop to a production server.
* **Methodologies:** Agile, Waterfall, and where DevOps fits in (breaking the wall between Dev and Ops).

### 2. Linux & OS Fundamentals
* **Why it matters:** The cloud is mostly Linux. You cannot manage servers if you can't navigate them.
* **Shell Scripting:** Automating tasks using Bash.
* **Top 50 Commands:**
    * *File Manipulation:* `ls`, `cd`, `cp`, `mv`, `rm`, `touch`, `cat`, `grep`, `find`.
    * *System Status:* `top`/`htop`, `ps`, `df`, `du`, `free`.
    * *Permissions:* `chmod`, `chown`, `sudo`.
    * *Networking:* `ping`, `curl`, `wget`, `nslookup`, `netstat`/`ss`.

### 3. Networking Fundamentals (CRITICAL ADDITION)
* *Note: Dont miss this, because it is the #1 reason deployments fail.*
* **Core Concepts:** DNS, HTTP/HTTPS, SSL/TLS, Subnetting/CIDR, Ports, and the OSI Model.
* **Why:** You need to know why your Load Balancer can't talk to your App Server.

---

## Phase 2: Programming & Version Control
Automation requires code. You don't need to be a developer, but you need to be a scripter.

### 1. Python (or Go)
* **Usage:** Writing Lambda functions, complex automation scripts, and parsing JSON/YAML.
* **Libraries:** `boto3` (for AWS), `requests`, `os`, `sys`.

### 2. Git & GitHub
* **What is VCS:** How Version Control Systems track changes.
* **Workflow:** Branching strategies, Pull Requests, Merging.
* **Relevance to DevOps:** "GitOps" — managing infrastructure state through Git history.

---

## Phase 3: The Container Era
Moving away from "It works on my machine."

### 1. Docker (Containerization)
* **Concepts:** What are containers vs. Virtual Machines?
* **Architecture:** Docker Engine, Daemon.
* **Core Components:**
    * **Images:** The blueprint (Dockerfile).
    * **Containers:** The running instance.
    * **Volumes:** Persisting data (Stateful vs Stateless).
    * **Networking:** Bridge, Host, Overlay networks.

---

## Phase 4: Container Orchestration
Managing containers at scale.

### 1. Kubernetes (K8s)
* **Architecture:** Control Plane (Master) vs. Worker Nodes.
* **Key Objects:**
    * **Pod:** The smallest deployable unit.
    * **Deployment:** Managing replicas and updates.
    * **Service:** Exposing applications (ClusterIP, NodePort, LoadBalancer).
    * **ConfigMap & Secrets:** Managing environment variables securely.
* **Helm:** The package manager for Kubernetes (templating manifests).

---

## Phase 5: Infrastructure as Code (IaC)
Treating your infrastructure like software.

### 1. Terraform (The Industry Standard)
* **What is IaC?** Automating infrastructure provisioning (killing the "ClickOps" manual console work).
* **Core Concepts:**
    * **Providers:** Connecting to AWS, Azure, GCP, or K8s.
    * **State File (`tfstate`):** The source of truth for your infrastructure.
    * **State Locking:** Preventing team conflicts (DynamoDB/S3).
    * **Provisioners:** (Note: explain why these are often avoided in favor of user_data).
    * **Modules:** Reusable code blocks for scalability.

---

## Phase 6: Configuration Management
* **What is it?** Managing the settings and software *inside* the servers (or VMs) after they are provisioned.
* **Tools:** **Ansible** (Agentless, Push-based), Puppet, or Chef.
* **Modern Relevance:** Less critical in "Immutable Infrastructure" (Containers) but still vital for managing base VM configurations.

---

## Phase 7: The Cloud (Public Cloud Providers)
Pick ONE major provider(AWS, AZURE, GCP )  to start (AWS is usually the safe bet for learning).

### 1. Core Services (AWS Example)
* **Compute:** EC2 (Virtual Machines), Lambda (Serverless).
* **Networking:** VPC, Subnets, Route Tables, Internet Gateways, Security Groups.
* **Storage:** S3 (Object), EBS (Block), EFS (File).
* **IAM (Identity Access Management):** Users, Roles, Policies (Security foundation).
* **Database:** RDS (SQL), DynamoDB (NoSQL).
* **CICD TOOLS:** ECR , EKS etc.

---

## Phase 8: CI/CD (Continuous Integration/Deployment)
The pipeline that glues it all together.

* **Concepts:**
    * *CI:* Build, Test, Code Analysis.
    * *CD:* Deploy to Staging/Production.
* **Tools:** Jenkins (Legacy/Standard), GitHub Actions (Modern/Growing), GitLab CI.
* **Cloud Native:** AWS CodePipeline, Azure DevOps.

---

## Phase 9: Observability (CRITICAL ADDITION)
If you can't monitor it, you can't manage it.

* **Monitoring:** Metrics (CPU, RAM, Latency). Tools: **Prometheus & Grafana**.
* **Logging:** Centralized logs. Tools: **ELK Stack (Elastic, Logstash, Kibana)** or **Loki**.
* **Tracing:** Understanding request flows across microservices.
