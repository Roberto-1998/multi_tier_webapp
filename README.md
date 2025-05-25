# Multi-Tier Web Application Infrastructure with Vagrant

This project sets up a multi-tier architecture using Vagrant and VirtualBox, simulating a real-world web application stack with multiple services. It’s ideal for testing, learning, and development purposes.

## 🖼️ Architecture Diagram

![Architecture Diagram](images/architecture.png)

## 🧱 Project Structure

```
multi_tier_webapp/
│
├── scripts/                  # Provisioning scripts for each service
│   ├── mysql.sh
│   ├── memcached.sh
│   ├── rabbitmq.sh
│   ├── tomcat.sh
│   └── web.sh
│
├── images/                   # Folder containing architecture diagram
│   └── architecture.png
│
├── Vagrantfile               # Main configuration file (multi-machine)
└── README.md                 # Project documentation (this file)
```

## 🚀 Services Overview

### 1. **MySQL (`db01`)**
A relational database service to store structured application data.

### 2. **Memcached (`mc01`)**
A memory caching system used to speed up dynamic web applications by alleviating database load.

### 3. **RabbitMQ (`rmq01`)**
A message broker used for asynchronous communication between services.

### 4. **Tomcat (`app01`)**
An application server to run Java-based web applications (backend logic).

### 5. **NGINX (`web01`)**
A web server used as a reverse proxy to handle client requests and forward them to Tomcat.

## ⚙️ How to Use

### Prerequisites
- [Vagrant](https://www.vagrantup.com/)
- [VirtualBox](https://www.virtualbox.org/)

### Steps
```bash
git clone https://github.com/Roberto-1998/multi_tier_webapp.git
cd multi_tier_webapp
vagrant up
```

This will automatically spin up and provision all VMs with their respective configurations.

## 📄 License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for more details.