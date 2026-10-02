# PaaS.net

## Secure Virtualized Service Network

PaaS.net is a fully virtualized enterprise network infrastructure designed to provide a wide range of network, system administration, security, communication, cloud, and automation services from a single physical machine.

The project consists of building an isolated **Virtual LAN (VLAN/LAN environment)** containing multiple interconnected virtual servers, each responsible for a specific service. The infrastructure was designed to resemble a small enterprise environment while demonstrating the deployment and integration of modern IT technologies.

A major focus of the project is **security and service isolation**. Several services use encrypted communication, while an internal **Certificate Authority (CA)** was created using OpenSSL to generate and sign certificates for services requiring HTTPS.

The entire environment relies extensively on virtualization, allowing the complete infrastructure to operate on a single physical host.

## Architecture

PaaS.net is composed of multiple virtualized servers distributed according to their individual responsibilities:

| Service | Technologies |
|---|---|
| Windows Domain Controller | Active Directory, RDP, SSH |
| Database Server | MySQL |
| Web Server | WordPress, HTTP, HTTPS |
| Email Server | Mail services |
| Encrypted Mailing List | Schleuder, OpenPGP |
| File Server | FreeBSD Jails, FTP, SMB, NFS |
| Certificate Authority | OpenSSL |
| PBX | Asterisk, CallMyWay |
| Linux Domain Controller | LDAP |
| DNS Server | BIND |
| DHCP Server | DHCPD |
| Thin Client Server | LTSP, PXE |
| Private Cloud | OwnCloud |
| VPN | OpenVPN, TCP, TAP |
| Container Orchestration | Kubernetes, Docker |
| Virtual Learning Environment | BigBlueButton |
| Cloud Infrastructure | OpenStack |
| Infrastructure as Code | Ansible, Terraform |

## Core Concept

The infrastructure is built around three main principles:

### Virtualization

The complete environment is deployed on a single physical machine using virtualization technologies. This allows multiple independent servers and operating systems to coexist while maintaining logical separation between services.

### Network Services

The virtual LAN provides a centralized environment where clients can interact with authentication, database, web, file-sharing, communication, cloud, and network services.

### Security

Security is incorporated throughout the infrastructure through encrypted communication, certificate management, VPN access, encrypted email, isolated services, and centralized authentication.

## Implemented Services

### Windows Domain Controller

Provides centralized identity and authentication through Active Directory.

Features include:

- Active Directory domain services
- Remote Desktop Services
- Support for up to five simultaneous RDP users
- SSH remote administration
- Registered Windows client
- Optional synchronization with the Linux Domain Controller

### Database Server

A dedicated **MySQL** server provides database services for applications hosted elsewhere in the infrastructure.

The database is separated from the web server, allowing CMS applications such as WordPress to access the database remotely.

### Web Server

Hosts a CMS such as **WordPress** using a dedicated database server.

The web infrastructure provides:

- HTTP
- HTTPS
- WordPress/CMS hosting
- Remote MySQL connectivity
- SSL/TLS certificate integration

### Email Server

Provides email services for the configured domain, including:

- Sending messages
- Receiving messages
- Mailbox management

### Encrypted Mailing List

An encrypted mailing-list service was implemented using **Schleuder**.

The service allows messages sent to a mailing-list address to be securely redistributed to its members using their public encryption keys.

### File Server

The file server runs on **FreeBSD** and uses **Jails** to isolate services within separate filesystem environments.

The following file-sharing protocols are provided:

- FTP
- SMB
- NFS

These services can be accessed and mounted from Linux clients connected to the virtual network.

### Certificate Authority

PaaS.net includes an internally managed Certificate Authority built with **OpenSSL**.

The CA is responsible for generating and signing certificates used by internal services, particularly the HTTPS web server.

This allows encrypted communication to be implemented without relying on an external certificate authority.

### PBX / VoIP

A virtual PBX based on **Asterisk** was deployed and integrated with **CallMyWay**.

The PBX includes:

- Desktop and mobile clients
- Conference room
- Business-hours call routing
- Voicemail outside business hours
- Interactive Voice Response (IVR)
- Extension selection
- Simultaneous ringing
- Call forwarding and transfer
- Outbound calls through CallMyWay

Incoming calls can be routed through an interactive menu that allows callers to select individual extensions or predefined destinations.

### Linux Domain Controller

A Linux-based domain controller was deployed using **LDAP**.

The LDAP service can synchronize with the Active Directory environment, providing centralized identity management across Windows and Linux systems.

### DNS Server

A DNS infrastructure based on **BIND** provides name resolution and authoritative zones for the project's domain.

### DHCP Server

A **DHCPD** server automatically provides network configuration to clients within the required network environment.

### VPN

Remote access is provided through **OpenVPN**.

The VPN configuration uses:

- TCP
- TAP interface
- Packet routing through an AWS-hosted server
- Desktop client
- Mobile client

This allows remote devices to securely access the PaaS.net environment.

### Thin Client Server

The **Linux Terminal Server Project (LTSP)** provides network-based Ubuntu environments for thin clients.

Clients can boot through **PXE** and operate without requiring a local hard drive, demonstrating centralized workstation deployment.

### OwnCloud

**OwnCloud** provides private cloud storage and centralized file access within the infrastructure.

### Kubernetes

A **Kubernetes** environment was implemented for container orchestration and service deployment.

The platform is used to publish the CMS service using containerized workloads.

### BigBlueButton

**BigBlueButton** provides virtual classrooms and online learning environments with real-time collaboration capabilities.

### OpenStack

An **OpenStack** environment was created with:

- Controller node
- Compute node

This provides a private cloud infrastructure for managing virtualized computing resources.

### Infrastructure as Code

The project incorporates **Terraform** and **Ansible** to manage infrastructure through code.

Terraform is used for infrastructure provisioning, while Ansible is used for configuration and automation.

This approach improves:

- Reproducibility
- Automation
- Configuration consistency
- Deployment efficiency
- Infrastructure management

## Security

Security is one of the central components of PaaS.net.

The infrastructure incorporates several security mechanisms:

- HTTPS encryption
- Internal Certificate Authority
- OpenSSL certificate management
- OpenVPN remote access
- Encrypted email
- OpenPGP public-key encryption
- Active Directory authentication
- LDAP authentication
- Service isolation through FreeBSD Jails
- Network segmentation through virtualization

The internal Certificate Authority is particularly important because it allows PaaS.net to issue and manage its own certificates for internal services.

## Technology Stack

### Operating Systems

- Windows Server
- Linux
- FreeBSD

### Networking

- Active Directory
- LDAP
- BIND
- DHCPD
- OpenVPN
- PXE
- SSH
- RDP

### Applications and Services

- MySQL
- WordPress
- Asterisk
- Schleuder
- OwnCloud
- BigBlueButton

### Virtualization & Cloud

- Virtual Machines
- Docker
- Kubernetes
- OpenStack
- Amazon Web Services

### Automation

- Ansible
- Terraform

### Security

- OpenSSL
- HTTPS
- OpenPGP
- VPN
- FreeBSD Jails
- Certificate Authority

## Project Objectives

The main objectives of PaaS.net were to gain practical experience in:

- Enterprise network administration
- Server deployment and configuration
- Virtualization
- Windows and Linux interoperability
- Centralized authentication
- Network services
- Cybersecurity
- Public-key infrastructure
- VoIP and telecommunications
- Container orchestration
- Cloud infrastructure
- Infrastructure as Code
- Service automation

## Project Status

**Completed**

The required services were deployed, configured, and integrated into the virtualized PaaS.net infrastructure.

## Environment

The complete infrastructure is designed to run on a **single physical machine**, demonstrating how virtualization can consolidate multiple enterprise services into one physical host while maintaining logical separation between systems.

## Academic Project

PaaS.net was developed as an academic project focused on the practical implementation of enterprise infrastructure, virtualization, networking, security, cloud technologies, and system administration.

The project demonstrates how a complete service-oriented network can be designed, deployed, secured, and managed within a controlled virtualized environment.