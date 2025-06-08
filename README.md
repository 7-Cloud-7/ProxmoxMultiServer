# ProxmoxMultiServer  
Proxmox system running Web Server, VPN, and AD (includes DNS, Database, Kubernetes + Docker)

## Description

This project aims to deploy a complete infrastructure on Proxmox VE to manage a critical service environment, including:

- Apache Web Server  
- MariaDB Database  
- Bind9 DNS Server  
- VPN Server for secure access  
- Active Directory Server for user and permission management  
- Container orchestration and management with Kubernetes for high availability, load balancing, auto-restart, and automatic backups.

The infrastructure allows the website to be accessible both from within the private network (via VPN and Active Directory) and from the outside.

---

### Architecture

<pre>

Physical Hardware (Server or PC)
└── Proxmox VE
    ├── VM: Ubuntu Server (Ansible + VPN)
    │    ├── Ansible Control Node
    │    └── WireGuard (or OpenVPN)
    │
    ├── VM: Ubuntu Server (Docker + Kubernetes)
    │    ├── Apache+PHPMyAdmin Container 
    │    ├── MariaDB Container
    │    └── Bind9 Container
    │
    └── VM: Windows Server (AD + DNS)
         ├── Active Directory DS
         └── DNS Server (integrado)
</pre>

After reviewing the architecture, you may (or may not) be wondering... Why choose Windows AD?

**Short answer:**  
It's simply *easy to configure*.

**The longer answer:**  
For small or lightweight projects, **Linux AD** (Samba) is often preferred — it’s *free*, uses *less memory*, and hey... some of us just like Linux better.

However, **Windows AD** offers clear advantages:

- Seamless **compatibility** with Windows clients  
- Prebuilt **Group Policies (GPOs)** ready to use  
- **Official support** from Microsoft  
- And sometimes... I just want to use a **GUI**

In bigger companies Windows is the main character so just get used to it as I did while working.  


---

### Features

- Automated installation of Docker and Kubernetes  
- Deployment of services in Kubernetes-managed containers  
- Secure private network via VPN  
- Access control and permission management with Active Directory  
- DNS configured for both internal and external resolution  
- High availability and load balancing for critical services  
- Automation scripts to simplify installation and deployment

---

### Requirements

- Hardware with virtualization support  
- Proxmox VE installed on physical hardware  
- Basic knowledge of Linux, Docker, Kubernetes, and network administration

---

### Quick Installation Guide

1. **Install Proxmox VE** on physical hardware  
2. **Create an Ubuntu VM** to host Docker and Kubernetes  
3. **Run the automation script** to install and configure Docker and Kubernetes  
4. **Deploy YAML files** (or automate them) for Apache, MariaDB, and Bind9 services on Kubernetes  
5. **Create VPN Server + Active Directory VMs**
6. **Configure network, firewall, and external access** to expose the web and secure the VPN  
7. **Validate access to services and communication between VMs**

---

### Scripts and Configurations

- `install_docker_kubernetes.sh`: Script to install Docker and Kubernetes on Ubuntu  
- `deploy_services.yaml`: YAML file to deploy Apache, MariaDB, and Bind9 on Kubernetes  
- VPN and Active Directory configuration scripts (in development)

---

### Future Improvements

- Integration with monitoring tools (Prometheus, Grafana)  
- Full automation of all VM deployments  
- Implementation of automated backups  
- Advanced configuration of load balancing and scalability

---

### Contributions

Contributions are welcome to improve automation, add new features, or enhance documentation. Please open an Issue or Pull Request.

---

### License

This project is licensed under the Apache 2.0 License. See the [LICENSE](LICENSE) file for more details.

---

### Contact

For questions or inquiries, contact: cloud71234567@gmail.com

---

**Thank you for using this project!**
