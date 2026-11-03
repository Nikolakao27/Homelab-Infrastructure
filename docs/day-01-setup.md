# Day 01 — Initial Homelab Setup

**Status:** Completed  
**Focus:** Virtualisation, Linux Administration, Docker & Networking

## Overview

The first stage of this homelab project focused on establishing a functional, remotely managed server environment capable of hosting multiple containerised applications.

The infrastructure was built using **Proxmox VE**, **Ubuntu Server**, and **Docker**, with an emphasis on understanding how these technologies interact.

## 1. Virtualisation & Linux

Installed **Proxmox VE 9** on a dedicated mini PC to manage virtual machines.

Created an Ubuntu Server 24.04 LTS virtual machine with the following resources:

| Resource | Allocation |
|---|---|
| CPU | 2 vCPUs |
| Memory | 3 GB |
| Storage | 32 GB |
| Networking | Virtual bridge (vmbr0) |

Configured SSH for remote administration and updated the operating system.

**Key takeaway:** Gained practical experience with hypervisors, virtual machines, Linux administration, and remote server management.

## 2. Docker & Containerisation

Installed Docker Engine and Docker Compose to deploy applications in isolated environments.

Deployed two initial services:

- **Nginx:** A lightweight web server used to test container deployment and port mapping.
- **Uptime Kuma:** A self-hosted monitoring application used to track service availability.

Practised managing container lifecycles, inspecting logs, and deploying applications through Docker Compose.

**Key takeaway:** Developed an understanding of containerisation, image management, port mapping, and persistent Docker volumes.

## 3. Docker Networking

Created a custom Docker bridge network to enable communication between Nginx and Uptime Kuma.

```bash
docker network create homelab-net
docker network connect homelab-net nginx-test
```

Updated the Uptime Kuma Compose configuration to use the existing network:

```yaml
networks:
  homelab-net:
    external: true
```

Both containers were successfully connected to the same network.

Uptime Kuma was then configured to monitor Nginx using Docker's internal DNS:

```text
http://nginx-test:80
```

**Result:** Successfully established container-to-container communication without relying on the host's IP address.

## 4. Remote Development

Configured **VS Code Remote SSH** to manage the Ubuntu Server environment directly from a development machine.

This enables remote file editing, terminal access, and Docker Compose configuration without requiring a graphical desktop environment on the server.

## 5. Challenges & Lessons Learned

During the initial setup, several issues provided useful troubleshooting experience:

- **SSH connectivity:** Diagnosed and enabled the SSH service to establish remote access.
- **HTTP vs HTTPS:** Corrected a protocol mismatch affecting service monitoring.
- **YAML configuration:** Resolved an indentation error in Docker Compose.
- **Container networking:** Learned how Docker DNS resolves container names within user-defined networks.

These exercises reinforced the importance of configuration validation, systematic troubleshooting, and understanding networking fundamentals.

## Next Steps

- [ ] Deploy a central Homepage dashboard.
- [ ] Configure Jellyfin for media streaming.
- [ ] Integrate additional storage.
- [ ] Explore backup and recovery strategies.
- [ ] Improve remote access security using SSH keys.

---

**Day 01 Outcome:** Established a functional virtualised Linux environment with remotely managed Docker services, persistent application data, and internal container networking.