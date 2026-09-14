# ☁️ AWS Multi-Tier Resilient & Secure VPC Architecture

An enterprise-grade, highly available 2-Tier cloud infrastructure built on Amazon Web Services (AWS). The core compute workload runs strictly inside private subnets across multiple physical Availability Zones, automated by an Auto Scaling Group, fronted by an internet-facing Application Load Balancer, and securely managed through a hardened Bastion Jump Host.

---

## 📸 Architecture Preview

![VPC Setup](docs/vpc-example-private-subnets.png)

---

## ✨ Key Features

- 🛡️ **Zero Direct Public Exposure:** Backend application instances have no public IPv4 addresses, completely protecting compute nodes from external scanning.
- 🌐 **Multi-AZ High Availability:** Infrastructure spans multiple physical Availability Zones for seamless failure isolation.
- 📈 **Dynamic Auto Scaling:** The fleet automatically provisions and balances instances across zones based on real-time demand.
- 🚦 **Layer-7 Traffic Load Balancing:** An internet-facing Application Load Balancer terminates HTTP traffic and distributes client requests across healthy private target nodes.
- 🔐 **Hardened Bastion Jump Host:** A secure intermediate server with locked-down SSH key permissions (`chmod 400`) enables safe internal server administration.
- ⚡ **Automated Zonal NAT Egress:** Redundant NAT Gateways allow private instances to download packages without exposing open inbound ports to the internet.
- 🩺 **Automated Health Probes:** The Target Group monitors instance health at regular intervals to dynamically remove failing nodes from traffic routing.
- 📊 **Real-Time Fleet Telemetry:** Integrated AWS CloudWatch monitors Desired Capacity, In-Service count, and CPU utilization.

---

## 🎯 Architecture Benefits

- **High Availability:** If an entire AWS data center goes down, the remaining Availability Zone(s) continue serving traffic with zero disruption.
- **Enhanced Security:** Isolating application workloads inside private subnets shields backend servers from direct internet attacks.
- **Cost & Elasticity Optimization:** Auto Scaling automatically increases or decreases compute instances based on real-time traffic demand.
- **Centralized Admin Access:** Administrative tasks go through a single Bastion Host with restricted security groups for simple access auditing.

---

## 🧰 Tech Stack

### Cloud Infrastructure (AWS)
- **Networking:** Amazon VPC, Public & Private Subnets, Internet Gateway, NAT Gateways
- **Compute:** Amazon EC2, Amazon Linux, EC2 Launch Templates
- **Scaling & Traffic Management:** AWS Auto Scaling Groups (ASG), Application Load Balancer (ALB), Target Groups
- **Security:** AWS Security Groups (Port 22 SSH, Port 80 HTTP), Bastion Jump Host
- **Monitoring:** Amazon CloudWatch (ASG Metrics, CPU Utilization)

### Web & Application Tier
- **Web Server:** Nginx (Reverse Proxy & HTTP Server)

---

## Screenshots & Architecture Diagrams

### VPC & Subnet Architecture
![VPC Setup](docs/vpc-example-private-subnets.png)

### 1. VPC and Subnet Configuration
![Step 1](docs/img1.png)
![Step 4](docs/img4.png)
![Step 5](docs/img5.png)
![Step 9](docs/img9.png)
![Step 10](docs/img10.png)
![Step 12](docs/img12.png)

### 2. Launch Template & Security Groups
![Step 16](docs/img16.png)
![Step 19](docs/img19.png)
![Step 20](docs/img20.png)
![Step 22](docs/img22.png)

### 3. Auto Scaling Group & Private Fleet
![Step 27](docs/img27.png)
![Step 28](docs/img28.png)
![Step 31](docs/img31.png)
![Step 32](docs/img32.png)
![Step 34](docs/img34.png)

### 4. Bastion Host & Secure Multi-Hop SSH
![Step 37](docs/img37.png)
![Step 39](docs/img39.png)
![Step 44](docs/img44.png)
![Step 46](docs/img46.png)

### 5. Nginx Deployment & Local Verification
![Step 48](docs/img48.png)
![Step 50](docs/img50.png)
![Step 53](docs/img53.png)

### 6. Target Group & Application Load Balancer
![Step 55](docs/img55.png)
![Step 57](docs/img57.png)
![Step 59](docs/img59.png)
![Step 63](docs/img63.png)
![Step 64](docs/img64.png)
![Step 67](docs/img67.png)

### 7. Live Web Application Verification
![Step 68](docs/img68.png)
![Step 69](docs/img69.png)
![Step 70](docs/img70.png)

### 8. Observability & CloudWatch Telemetry
![Step 72](docs/img72.png)
![Step 74](docs/img74.png)
![Step 75](docs/img75.png)

---
---

## 👤 Author

**Jai Vishun Singh**
- GitHub: [@SinghVishunJai1](https://github.com/SinghVishunJai1)
- Degree: B.Tech in Computer Science & Engineering
