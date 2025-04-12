# Proxmox Homelab Notes

This repository contains personal notes, guides, and fixes for issues encountered when working with Proxmox in a homelab environment.  
It is structured so that **more problems, solutions, and installation tips can be easily added over time**.

---

## 📜 Guides

### Delete Local LVM and Resize Storage
[Video Tutorial](https://www.youtube.com/watch?v=rMe3pd2sBf4)

#### Steps:
1. Go to **Datacenter**, and under **Storage**, delete **local-lvm**.
2. Select **local (pve)**, then click **Edit**, and select all content types:
   - Disk Image
   - Backup
   - Container Template
   - Container
   - Snippets
   - Import
   - ISO Images
3. Open the **Shell** for your PVE node.
4. Run the following commands:

   ```bash
   lvremove /dev/pve/data -y
   lvresize -l +100%FREE /dev/pve/root
   resize2fs /dev/mapper/pve-root


Linux pve 6.8.12-9-pve #1 SMP PREEMPT_DYNAMIC PMX 6.8.12-9 (2025-03-16T19:18Z) x86_64

The programs included with the Debian GNU/Linux system are free software;
the exact distribution terms for each program are described in the
individual files in /usr/share/doc/*/copyright.

Debian GNU/Linux comes with ABSOLUTELY NO WARRANTY, to the extent
permitted by applicable law.

Last login: Sat Apr 12 22:51:42 AEST 2025 on pts/0

root@pve:~# lvremove /dev/pve/data -y
  Logical volume "data" successfully removed.

root@pve:~# lvresize -l 100%FREE /dev/pve/root
  Size of logical volume pve/root changed from 96.00 GiB (24576 extents) to <360.76 GiB (92354 extents).
  Logical volume pve/root successfully resized.

root@pve:~# resize2fs /dev/mapper/pve-root
resize2fs 1.47.0 (5-Feb-2023)
Filesystem at /dev/mapper/pve-root is mounted on /; on-line resizing required
old_desc_blocks = 12, new_desc_blocks = 46
The filesystem on /dev/mapper/pve-root is now 94570496 (4k) blocks long.


🛠️ Problems Encountered and Solutions
1. Proxmox Not Detecting Internal NVMe M.2 SSD (Dell Optiplex 7040)
Reddit Thread 1 (https://www.reddit.com/r/Proxmox/comments/sf8aul/proxmox_not_detecting_nvme/)
Reddit Thread 2 - Solution Comment (https://www.reddit.com/r/Proxmox/comments/sf8aul/comment/jtgn5nv/?utm_source=share&utm_medium=web3x&utm_name=web3xcss&utm_term=1&utm_content=share_button)

Problem:
Proxmox did not detect the internal NVMe M.2 SSD.

Fix:

Go to System BIOS:

Enable Legacy Option ROMs.

Enable Attempt Legacy Boot.

Go to System BIOS:

Under SATA Configuration, set SATA Operation to AHCI (change from RAID ON).
