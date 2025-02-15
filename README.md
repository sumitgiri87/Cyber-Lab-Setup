# Cybersecurity Lab Setup

## Overview
This guide provides step-by-step instructions to set up virtual machines for cybersecurity labs using Oracle VirtualBox. The focus is on:
- **Kali Linux with OpenVAS** for penetration testing and vulnerability scanning.
- **Linux Server** for network services and security testing.
- **Windows 11** for security assessments in a modern Windows environment.

## Prerequisites
- Oracle VirtualBox (Download from [here](https://www.virtualbox.org/))
- Virtualization enabled in BIOS
- Minimum system requirements:
  - **8GB RAM** (recommended 16GB+)
  - **100GB+ free disk space**
  - **Multi-core processor**

---

## 1. Kali Linux with OpenVAS
Kali Linux is a penetration testing OS, and OpenVAS (Greenbone Vulnerability Manager) is used for vulnerability scanning.

### Installation Steps
1. Download the **Kali Linux VirtualBox Image** from [Kali Official Website](https://www.kali.org/get-kali/#kali-virtual-machines).
2. Import the image into VirtualBox:
   - Open VirtualBox → File → Import Appliance → Select the `.ova` file.
   - Adjust CPU and RAM settings as needed.
3. Start the VM and log in (Default: `kali/kali`).
4. Update the system:
   ```sh
   sudo apt update && sudo apt upgrade -y
   ```
5. Install OpenVAS:
   ```sh
   sudo apt install openvas -y
   sudo gvm-setup
   sudo gvm-check-setup
   ```
6. Start OpenVAS:
   ```sh
   sudo gvm-start
   ```
7. Access OpenVAS Web UI: `https://127.0.0.1:9392/`

---

## 2. Linux Server
A Linux server is essential for testing security configurations and networking.

### Installation Steps
1. Download **Ubuntu Server LTS** from [Ubuntu Official Site](https://ubuntu.com/download/server).
2. In VirtualBox:
   - Click **New**, set OS type to **Linux**, and allocate at least **2GB RAM**.
   - Attach the downloaded ISO and follow the installation process.
3. After installation, update and install essential packages:
   ```sh
   sudo apt update && sudo apt upgrade -y
   sudo apt install openssh-server net-tools -y
   ```
4. Verify SSH service:
   ```sh
   systemctl status ssh
   ```
5. Optional: Configure firewall rules:
   ```sh
   sudo ufw enable
   sudo ufw allow 22/tcp
   ```

---

## 3. Windows 11 on VirtualBox
Windows 11 can be used to simulate real-world security scenarios.

### Installation Steps
1. Download the **Windows 11 ISO** from [Microsoft](https://www.microsoft.com/en-us/software-download/windows11).
2. In VirtualBox:
   - Click **New**, select **Windows 11**, and allocate at least **4GB RAM** and **2 CPU cores**.
   - Attach the Windows 11 ISO and follow installation steps.
3. After installation, update the system and install security tools like **Wireshark, Sysinternals, and Microsoft Defender for Endpoint**.
4. Optional: Install **VirtualBox Guest Additions** for better performance:
   ```sh
   D:\VBoxWindowsAdditions.exe
   ```

---

## Conclusion
With these virtual machines, you can explore cybersecurity tools and techniques in a controlled environment. Ensure that you regularly update your systems and follow best security practices to maintain a safe lab setup.
