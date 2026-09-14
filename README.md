# ☁️ AWS Multi-Tier Resilient & Secure VPC Architecture

An enterprise-grade, highly available 2-Tier cloud infrastructure built on Amazon Web Services (AWS). The core compute workload runs strictly inside private subnets across multiple physical Availability Zones, automated by an Auto Scaling Group, fronted by an internet-facing Application Load Balancer, and securely managed through a hardened Bastion Jump Host.

---

## 📸 Architecture Preview

<p align="center">
  <img src="docs/images/vpc-example-private-subnets.png" width="80%" alt="Architecture Overview" />
</p>

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

## 📸 Implementation Gallery

### 1. VPC and Subnet Configuration
<p align="center">
  <img src="docs/images/img1.jpg" width="48%" alt="VPC Setup 1" />
  <img src="docs/images/img2.jpg" width="48%" alt="VPC Setup 2" />
</p>
<p align="center">
  <img src="docs/images/img3.jpg" width="48%" alt="VPC Setup 3" />
  <img src="docs/images/img4.jpg" width="48%" alt="VPC Setup 4" />
</p>

> Full set: `img1.jpg` – `img12.jpg`

### 2. Launch Template & Security Groups
<p align="center">
  <img src="docs/images/img16.jpg" width="48%" alt="Launch Template 1" />
  <img src="docs/images/img17.jpg" width="48%" alt="Launch Template 2" />
</p>

> Full set: `img16.jpg` – `img22.jpg`

### 3. Auto Scaling Group & Private Fleet
<p align="center">
  <img src="docs/images/img27.jpg" width="48%" alt="Auto Scaling 1" />
  <img src="docs/images/img28.jpg" width="48%" alt="Auto Scaling 2" />
</p>

> Full set: `img27.jpg` – `img34.jpg`

### 4. Bastion Host & Secure Multi-Hop SSH
<p align="center">
  <img src="docs/images/img37.jpg" width="48%" alt="Bastion Host 1" />
  <img src="docs/images/img38.jpg" width="48%" alt="Bastion Host 2" />
</p>

> Full set: `img37.jpg` – `img46.png`

### 5. Nginx Deployment & Local Verification
<p align="center">
  <img src="docs/images/img48.png" width="48%" alt="Nginx Setup 1" />
  <img src="docs/images/img49.png" width="48%" alt="Nginx Setup 2" />
</p>

> Full set: `img48.png` – `img53.png`

### 6. Target Group & Application Load Balancer
<p align="center">
  <img src="docs/images/img55.png" width="48%" alt="ALB Setup 1" />
  <img src="docs/images/img56.png" width="48%" alt="ALB Setup 2" />
</p>

> Full set: `img55.png` – `img67.jpg`

### 7. Live Web Application Verification
<p align="center">
  <img src="docs/images/img68.jpg" width="48%" alt="Live App 1" />
  <img src="docs/images/img69.jpg" width="48%" alt="Live App 2" />
</p>

> Full set: `img68.jpg` – `img70.jpg`

### 8. Observability & CloudWatch Telemetry
<p align="center">
  <img src="docs/images/img72.jpg" width="48%" alt="CloudWatch 1" />
  <img src="docs/images/img73.jpg" width="48%" alt="CloudWatch 2" />
</p>

> Full set: `img72.jpg` – `img75.jpg`

---
---

## 👤 Author

**Jai Vishun Singh**
- GitHub: [@SinghVishunJai1](https://github.com/SinghVishunJai1)
- Degree: B.Tech in Computer Science & Engineering
