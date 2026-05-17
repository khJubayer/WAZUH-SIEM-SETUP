# WAZUH-SIEM-SETUP
## Introduction
A step-by-step guide to provisioning an Ubuntu 22.04 virtual machine, deploying the Wazuh security platform, and accessing the environment remotely via PuTTY.
## **📋 Table of Contents**

- [Prerequisites](#prerequisites)
- [Part 1 — Setting Up Ubuntu 22.04 in a VM](#part-1--setting-up-ubuntu-2204-in-a-vm)
- [Part 2 — Initial Ubuntu Configuration](#part-2--initial-ubuntu-configuration)
- [Part 3 — Deploying Wazuh](#part-3--deploying-wazuh)
- [Part 4 — Remote Access via PuTTY](#part-4--remote-access-via-putty)

## **Prerequisites**

| Requirement | Details |
|---|---|
| Hypervisor | VirtualBox 7.x or VMware Workstation 17+ |
| Ubuntu ISO | Ubuntu 22.04.x LTS (Jammy Jellyfish) |
| Host RAM | Minimum 8 GB (16 GB recommended) |
| Disk Space | Minimum 50 GB free on host |
| PuTTY | Download PuTTY (Windows) |
| Internet | Active connection required |
## **Part 1 — Setting Up Ubuntu 22.04 in a Virtual Machine**

### **1.1 Create a New Virtual Machine**

1. Open VirtualBox and click **New**.

2. Configure the VM with the following settings.
| Setting | Value |
|---|---|
| Name | Ubuntu-22.04-Wazuh |
| Type | Linux |
| Version | Ubuntu (64-bit) |
| Base Memory | 4096 MB (4 GB minimum) |
| Processors | 2 CPUs minimum |
| Virtual Hard Disk | 50 GB (dynamically allocated) |
3.Click Finish to create the VM.
### **1.2 Attach the Ubuntu ISO**

1. Select your new VM and click **Settings → Storage**.

2. Under **Controller: IDE**, click the **Empty optical drive**.

3. Click the disc icon on the right → **Choose a disk file…**

4. Browse to your downloaded `ubuntu-22.04-live-server-amd64.iso` and click **Open**.

5. Click **OK** to save.

---

### **1.3 Configure Network Adapter**

1. Go to **Settings → Network → Adapter 1**.

2. Set **Attached to:** `Bridged Adapter`.

3. Select your host's active network interface from the **Name** dropdown.

4. Click **OK**.
### **1.4 Install Ubuntu 22.04**

1. Start the VM by clicking **Start**.

2. Select **Try or Install Ubuntu Server** and press **Enter**.

3. Follow the installer prompts:

- **Language:** English  
- **Keyboard Layout:** Your preference  
- **Network:** Confirm your NIC is detected (note the assigned IP address)  
- **Storage:** Use the entire disk (default)  

#### **Profile Setup**

| Profile Setting | Value |
|---|---|
| Your name | `<your full name>` |
| Server name | `wazuh-server` |
| Username | `<your username>` |
| Password | `<strong password>` |
