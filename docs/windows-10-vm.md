# Windows 10

## Purpose
Windows 10 is used to connect to the Domain Controller (DC). It serves as a client machine to test and manage Active Directory interactions and policies.

## Download
You can download Windows 10 from the following link: [Windows 10](https://www.microsoft.com/en-in/software-download/windows10)

## Configuration

- **OS**: Windows 10
- **CPU**: 4
- **Memory**: 4GB
- **Disk**: 50GB
- **Network**: NAT, Static IP 192.168.100.130

## Setup Instructions

### Step 1: Download the ISO

1. Visit the [Windows 10](https://www.microsoft.com/en-in/software-download/windows10) download page.
2. Use the Media Creation Tool to download the Windows 10 ISO file.

### Step 2: Create a New VM in VMware Workstation

1. Open VMware Workstation and select `Create a New Virtual Machine`.
2. Choose `Installer disc image file (iso)` and browse to the location of the downloaded ISO file.
3. Follow the prompts to configure the VM settings:
   - **Name**: Give your VM a meaningful name, such as `Windows 10`.
   - **Location**: Choose a location on your host machine where the VM files will be stored.

### Step 3: Configure VM Hardware

1. In the `Customize Hardware` section:
   - **Memory**: Allocate 4GB (4096 MB) of RAM.
   - **Processors**: Allocate 4 CPUs.
   - **Hard Disk**: Allocate 50GB of disk space.
   - **Network Adapter**: Set to `NAT`.

### Step 4: Install Windows 10

1. Start the VM and boot from the ISO.
2. Follow the installation prompts to install Windows 10.
3. During installation, set up a username and password for the administrator account.

### Step 5: Configure the VM

1. After the installation completes, log in with the administrator account.
2. Open `Settings` and perform the following configurations:

#### Change the Computer Name

1. Go to `Settings > System > About`.
2. Click on `Rename this PC`.
3. Enter the new name `win10-VM` and click `Next`.
4. Restart the computer to apply the changes.

#### Set a Static IP Address

1. Open `Settings > Network & Internet > Status`.
2. Click on `Change adapter options`.
3. Right-click on the network adapter and select `Properties`.
4. Select `Internet Protocol Version 4 (TCP/IPv4)` and click `Properties`.
5. Choose `Use the following IP address` and enter the following:
   - **IP address**: 192.168.100.130
   - **Subnet mask**: 255.255.255.0
   - **Default gateway**: (leave blank or set as needed)
6. Choose `Use the following DNS server addresses` and enter the IP address of your DNS server (e.g., 192.168.100.129 if it's the AD server).

This completes the setup for the Windows 10 VM in your homelab.
