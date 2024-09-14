# Home-Lab

Documenting my home lab journey in this repo.

## What I am Working With:
1. **Dell Optiplex 7040 SFF**: 48GB RAM, 2TB NVMe M.2, 1TB boot SSD  
   *(Planning to add an extra Network Interface Card for OpenSense, currently using TP-Link's USB to Ethernet Adapter as my second source.)*
2. **TP-Link 5 Port Switch**
3. **TP-Link USB to Ethernet Adapter**
4. **ASUS Vivobook**: 16GB RAM, 500GB SSD
5. **Lenovo Thinkpad**: 4GB RAM, 64GB SSD

## Usage Overview:
- **Dell Optiplex**: This is my main Proxmox server. I use the ASUS laptop to remote into it via SSH.
  - The server will host virtual machines for **Home Assistant**, **OpenSense**, and more. These VMs will be stored on the NVMe drive for faster performance and larger storage capacity.
  - The SSD is primarily used to boot up the Proxmox server.
  - Future plans include adding an external drive for server backups.
  
- **Lenovo Laptop**: This is my main hacking machine, where I have **Kali Linux** installed for penetration testing and security work.

## Learning Resources:

- [Reddit: Homelab Hardware Wiki](https://www.reddit.com/r/homelab/wiki/hardware/)
- [Domalab: Homelab Setup Ideas](https://domalab.com/build-homelab-setup-idea/)
- [NetSecFocus: Guide to Building a Home Lab](https://www.netsecfocus.com/home/lab/2022/07/31/Tjnulls_guide_to_building_a_Home_Lab.html)
  - [Avatar Project by Adrian Crenshaw](https://www.youtube.com/watch?v=gd_5r-cMlRU&t=1251s&ab_channel=AdrianCrenshaw)
- [Brian C. Moses: Building a Home Lab Server](https://blog.briancmoses.com/2016/07/building-a-homelab-server.html)
- [MT Lynch: Building a VM Homelab (2017)](https://mtlynch.io/building-a-vm-homelab-2017/)
- [MT Lynch: Building a First Homelab Rack](https://mtlynch.io/building-first-homelab-rack/)
- [NetSecFocus: Home Camera Security](https://www.netsecfocus.com/home/lab/2022/07/31/Tjnulls_guide_to_building_a_Home_Lab.html)

## Video Resources:

1. **Ubuntu Server running Portainer and Docker**  
   [TechnoTim Video](https://www.youtube.com/watch?v=Aq6eoMjW7V0&list=PL8cwSAAaP9W37Vnxkw6__sshVY-XohWNm&index=2&ab_channel=TechnoTim)

2. **A Homelabber's Networking Playground**  
   [Opnsense, Proxmox, VLANs, and Tailscale](https://www.youtube.com/watch?v=XXx7NDgDaRU&ab_channel=Tailscale)

3. **Reddit: Getting Started with Homelabs**  
   [Cybersecurity Thread](https://www.reddit.com/r/cybersecurity/comments/lozs05/home_lab_essentials_for_a_beginner/)

*(Adding more as I go)*
