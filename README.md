# 🛒 Emart Microservices Docker Project

[![Docker](https://img.shields.io/badge/Docker-Containerized-blue?logo=docker)](https://www.docker.com/)
[![AWS](https://img.shields.io/badge/AWS-EC2-orange?logo=amazon-aws)](https://aws.amazon.com/)
[![Microservices](https://img.shields.io/badge/Architecture-Microservices-green)](https://microservices.io/)
[![DevOps](https://img.shields.io/badge/DevOps-Implementation-red)](https://en.wikipedia.org/wiki/DevOps)

A comprehensive containerization project demonstrating the implementation of Docker and DevOps practices on a full-stack e-commerce microservices application.

## 📋 Table of Contents
- [Project Overview](#-project-overview)
- [Architecture](#-architecture)
- [Technologies Used](#-technologies-used)
- [Prerequisites](#-prerequisites)
- [Installation & Setup](#-installation--setup)
- [Docker Configuration](#-docker-configuration)
- [Deployment](#-deployment)
- [Screenshots](#-screenshots)
- [Learning Outcomes](#-learning-outcomes)
- [Acknowledgments](#-acknowledgments)
- [Contributing](#-contributing)
- [License](#-license)

## 🎯 Project Overview

This project focuses on **containerizing a multi-service e-commerce application** using Docker and implementing DevOps best practices. The original application was developed by DevOpsHyd Club, and this repository demonstrates the complete containerization workflow, from development to deployment on AWS EC2.

### 🎯 Objectives
- Transform a traditional application into containerized microservices
- Implement Docker best practices for multi-container applications
- Deploy on cloud infrastructure (AWS EC2)
- Demonstrate microservices communication patterns
- Showcase DevOps workflow automation

## 🏗️ Architecture

The application follows a microservices architecture pattern with the following components:

```
┌─────────────────┐    ┌──────────────────┐
│     Client      │────│   API Gateway    │
│   (Angular)     │    │     (Nginx)      │
└─────────────────┘    └──────────────────┘
                                │
                    ┌───────────┼───────────┐
                    │           │           │
            ┌───────▼──────┐ ┌──▼──────┐ ┌──▼────────┐
            │   Emart API  │ │Books API │ │  Static   │
            │  (Node.js)   │ │ (Java)   │ │  Assets   │
            └───────┬──────┘ └──┬──────┘ └───────────┘
                    │           │
            ┌───────▼──────┐ ┌──▼────────┐
            │   MongoDB    │ │   MySQL   │
            │   Database   │ │ Database  │
            └──────────────┘ └───────────┘
```

## 🛠️ Technologies Used

### Frontend
- **Angular** - Client-side application framework
- **HTML5/CSS3/TypeScript** - Web technologies

### Backend Services
- **Node.js** - Emart API service
- **Java Spring Boot** - Books API service
- **Nginx** - Reverse proxy and load balancer

### Databases
- **MongoDB** - NoSQL database for Emart service
- **MySQL** - Relational database for Books service

### DevOps & Infrastructure
- **Docker** - Containerization platform
- **Docker Compose** - Multi-container orchestration
- **AWS EC2** - Cloud compute instance (t3.medium)
- **Git** - Version control
- **Linux/Ubuntu** - Operating system

## ✅ Prerequisites

Before running this project, ensure you have:

- **Docker** installed (version 20.10+)
- **Docker Compose** installed (version 1.29+)
- **Git** for cloning the repository
- **AWS Account** (for cloud deployment)
- **Basic knowledge** of Docker and containerization concepts

### System Requirements
- **RAM**: Minimum 4GB (8GB recommended)
- **Storage**: At least 10GB free space
- **OS**: Linux, macOS, or Windows with WSL2

## 🚀 Installation & Setup

### 1. Clone the Repository
```bash
git clone https://github.com/VinitKarlekar/Emart-Microsvc-Docker.git
cd Emart-Microsvc-Docker
```

### 2. Project Structure
```
Emart-Microsvc-Docker/
├── client/                 # Angular frontend application
├── emartapi/              # Node.js backend service
├── booksapi/              # Java Spring Boot service
├── nginx/                 # Nginx configuration
├── docker-compose.yml     # Multi-container orchestration
├── README.md             # Project documentation
└── screenshots/          # Project screenshots
```

### 3. Environment Setup
```bash
# Make sure Docker is running
docker --version
docker-compose --version

# Verify Docker daemon is running
docker info
```

## 🐳 Docker Configuration

### Build All Services
```bash
# Build all Docker images
docker-compose build

# Build specific service
docker-compose build <service-name>
```

### Run the Application
```bash
# Start all services
docker-compose up -d

# View running containers
docker ps

# View logs
docker-compose logs -f
```

### Key Docker Commands
```bash
# Stop all services
docker-compose down

# Remove all containers and volumes
docker-compose down -v

# Rebuild and restart
docker-compose up --build -d

# Scale specific service
docker-compose up --scale emartapi=3
```

## ☁️ Deployment

### AWS EC2 Deployment

#### 1. Launch EC2 Instance
- **Instance Type**: t3.medium (2 vCPU, 4GB RAM)
- **OS**: Ubuntu Server 20.04 LTS
- **Security Group**: Open ports 80, 443, 22, 3000, 8080

#### 2. Server Setup
```bash
# Update system
sudo apt update && sudo apt upgrade -y

# Install Docker
curl -fsSL https://get.docker.com -o get-docker.sh
sudo sh get-docker.sh
sudo usermod -aG docker $USER

# Install Docker Compose
sudo curl -L "https://github.com/docker/compose/releases/download/v2.20.0/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
sudo chmod +x /usr/local/bin/docker-compose
```

#### 3. Deploy Application
```bash
# Clone and deploy
git clone https://github.com/VinitKarlekar/Emart-Microsvc-Docker.git
cd Emart-Microsvc-Docker
docker-compose up -d
```

#### 4. Access Application
- **Frontend**: `http://your-ec2-public-ip`
- **Emart API**: `http://your-ec2-public-ip:3000`
- **Books API**: `http://your-ec2-public-ip:8080`

## 📸 Screenshots

> **Note**: Add your project screenshots here

- EC2 Instance Configuration
- Docker Compose Build Process
- Running Containers
- Application Interface
- API Endpoints Testing

## 📚 Learning Outcomes

Through this project, I gained hands-on experience with:

### Docker & Containerization
- Writing efficient Dockerfiles
- Multi-stage builds optimization
- Container networking and communication
- Volume management and data persistence
- Docker Compose orchestration

### DevOps Practices
- Infrastructure as Code (IaC) concepts
- CI/CD pipeline fundamentals
- Cloud deployment strategies
- Monitoring and logging best practices
- Container security considerations

### Microservices Architecture
- Service decomposition patterns
- Inter-service communication
- Database per service pattern
- API Gateway implementation
- Load balancing and scaling

### Cloud Computing
- AWS EC2 instance management
- Security group configuration
- Cloud resource optimization
- Cost management strategies

## 🙏 Acknowledgments

- **Original Application**: This project uses the e-commerce application developed by [DevOpsHyd Club](https://github.com/devopshydclub/emartapp)
- **Special Thanks**: To the open-source community for providing excellent documentation and resources
- **Learning Resources**: Docker official documentation, AWS documentation, and various DevOps learning platforms

## 🤝 Contributing

Contributions are welcome! Please feel free to submit a Pull Request. For major changes:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 📞 Contact

**Vinit Karlekar**
- LinkedIn: [Your LinkedIn Profile]
- GitHub: [@VinitKarlekar](https://github.com/VinitKarlekar)
- Email: [your.email@example.com]

---

⭐ **If you found this project helpful, please give it a star!** ⭐

---

**Tags**: `#Docker` `#DevOps` `#Microservices` `#AWS` `#Containerization` `#Angular` `#NodeJS` `#Java` `#MongoDB` `#MySQL` `#Nginx`