# OPNsense Installation Guide on VMware

This repository provides a step-by-step guide to install OPNsense, a free and open-source firewall and routing platform, on VMware.  

---

## Table of Contents
1. [Introduction](#introduction)  
2. [Prerequisites](#prerequisites)  
3. [Downloading OPNsense](#downloading-opnsense)  
4. [Setting Up VMware for OPNsense](#setting-up-vmware-for-opnsense)  
5. [Installing OPNsense](#installing-opnsense)  
6. [Post-Installation Configuration](#post-installation-configuration)  
7. [References](#references)  

---

## Introduction
**OPNsense** is a powerful open-source firewall and routing platform designed for security and network management. This guide will help you set up and configure OPNsense on VMware Workstation or VMware ESXi.

---

## Prerequisites
Ensure the following before proceeding:

- **VMware Workstation** or **VMware ESXi** installed on your host machine.  
- A minimum of **2 CPU cores**, **2 GB RAM**, and **10 GB disk space** for the OPNsense virtual machine.  
- Internet access to download OPNsense and updates.  
- Familiarity with VMware basics (creating and configuring virtual machines).  

---

## Downloading OPNsense
1. Visit the [OPNsense official download page](https://opnsense.org/download/).  
2. Select the appropriate version:
   - **Architecture**: AMD64 (x86-64)  
   - **Image Type**: VGA (for virtual environments)  
   - **Mirror**: Choose a location near you.  
3. Download the `.img` or `.iso` file.  

---

## Setting Up VMware for OPNsense
### Step 1: Create a New Virtual Machine
1. Open VMware Workstation or ESXi and click **Create a New Virtual Machine**.  
2. Choose **Custom (Advanced)** and click **Next**.  

### Step 2: Configure Virtual Machine Settings
- **Guest Operating System**: Choose **Other** > **FreeBSD 64-bit**.  
- **Name the Virtual Machine**: Use a descriptive name like `OPNsense`.  
- **Processor Configuration**: Assign at least **2 CPU cores**.  
- **Memory**: Allocate at least **2 GB RAM**.  
- **Network Type**:  
  - Add **two virtual NICs**:  
    - First NIC: Bridged (WAN interface).  
    - Second NIC: Host-Only or NAT (LAN interface).  
- **Disk Configuration**: Create a new virtual disk with at least **10 GB**.  

### Step 3: Attach the OPNsense ISO
1. Under the **CD/DVD** device settings, select **Use ISO image file**.  
2. Browse to the downloaded OPNsense ISO file and attach it.  

---

## Installing OPNsense
1. Power on the virtual machine.  
2. Follow the on-screen prompts:  
   - Select the installation type (**Install OPNsense**).  
   - Partitioning: Choose **Auto (UFS)** for simplicity.  
   - Set a root password.  

3. After installation, reboot the VM and remove the ISO from the virtual drive.  

---

## Post-Installation Configuration
### Step 1: Access the Web Interface
1. Open a web browser and navigate to the default LAN IP: `http://192.168.1.1`.  
2. Log in with:  
   - **Username**: `root`  
   - **Password**: The password you set during installation.  

### Step 2: Complete the Setup Wizard
1. Follow the setup wizard to configure:  
   - WAN and LAN interfaces.  
   - Admin account password.  
   - Optional: Update to the latest version.  

### Step 3: Test Connectivity
- Ensure that the LAN and WAN interfaces are configured correctly and can communicate with external networks.  

---

## References
- [OPNsense Documentation](https://docs.opnsense.org/)  
- [VMware Documentation](https://www.vmware.com/support.html)  
- Community forums for additional help and tips.  

---

## Contributing
Contributions are welcome! If you find an issue or have suggestions, please open an issue or create a pull request.  

---

## License
This project is licensed under the [MIT License](LICENSE).  

