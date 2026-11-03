# 🖥️ Homelab Infrastructure

A personal homelab project focused on exploring **Linux, virtualisation, networking, containerisation, and self-hosted services** through hands-on experimentation.

The goal is to build and maintain a scalable learning environment while developing practical skills in **system administration, infrastructure management, and DevOps**.

**Project Starting Date:** 03/11/2026 at the end of my second year of the Bachelor of Software Engineering @ RMIT University.

## 🛠️ Tech Stack

| Category | Technologies |
|---|---|
| Hypervisor | Proxmox VE 9 |
| Operating System | Ubuntu Server 24.04 LTS |
| Containers | Docker & Docker Compose |
| Networking | SSH, Docker Bridge Networks |
| Web Server | Nginx |
| Monitoring | Uptime Kuma |
| Development | VS Code Remote SSH |

## 🏗️ Architecture

```text
Physical Mini PC
└── Proxmox VE
    └── Ubuntu Server VM
        └── Docker
            ├── Nginx
            ├── Uptime Kuma
            └── Custom Docker Network
```

## 🚀 Project Progress

- [x] Install and configure Proxmox VE
- [x] Deploy Ubuntu Server virtual machine
- [x] Configure SSH remote access
- [x] Install Docker Engine & Docker Compose
- [x] Deploy Nginx web server
- [x] Set up Uptime Kuma monitoring
- [x] Configure container-to-container networking
- [ ] Deploy Homepage dashboard
- [ ] Set up Jellyfin media server
- [ ] Integrate external storage
- [ ] Implement backup strategies

## 📚 Documentation

This repository documents the infrastructure setup, technical decisions, troubleshooting, and lessons learned throughout the project.

Detailed setup notes can be found in the [`docs/`](docs/) directory.

## 🎯 Project Goals

- Gain practical experience managing Linux servers and virtualised environments.
- Explore container orchestration, networking, and infrastructure automation.
- Deploy and maintain self-hosted applications.
- Apply software engineering principles to real-world infrastructure.

---

*An ongoing personal learning project — built, documented, and improved one service at a time.*