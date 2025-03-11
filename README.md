# FreeRDP 2025

## Check The Config File  
**File:** `windows10.yaml`

---

## 🚀 Docker Installation  

```bash
## 🚀 Installation  

sudo su
sudo apt update
sudo apt install docker.io docker-compose
docker
pwd
mkdir dockercom
cd dockercom
nano windows10.yaml
---
## ✅ Docker configuration for win 10  
---
services:
  windows:
    image: dockurr/windows
    container_name: windows
    environment:
      VERSION: "10"
      USERNAME: "admin"
      PASSWORD: "admin@123"
      RAM_SIZE: "4G"
      CPU_CORES: "4"
      DISK_SIZE: "400G"
      DISK2_SIZE: "100G"
    devices:         
      - /dev/kvm
      - /dev/net/tun
    cap_add:
      - NET_ADMIN
    ports:
      - 8006:8006
      - 3389:3389/tcp
      - 3389:3389/udp
    stop_grace_period: 2m

## 🚀 Docker RUN

cat windows10.yaml
sudo docker-compose -f windows10.yaml up                                      
