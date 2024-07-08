# Pfsense

## Purpose
Pfsense acts as a Router/Firewall in the network, providing network security and management features such as firewalling, routing, VPN, and more.

## Download
You can download Pfsense from the following link: [Pfsense](https://www.pfsense.org/download/)

## Configuration

- **OS**: Pfsense
- **CPU**: 1
- **Memory**: 1.2GB
- **Disk**: 10GB
- **Network**: Two network adapters (one for WAN, one for LAN)

## Setup Instructions

### Step 1: Download the ISO

1. Visit the [Pfsense](https://www.pfsense.org/download/) download page.
2. Select the appropriate version and architecture for your setup.
3. Download the Pfsense ISO file.

### Step 2: Create a New VM in VMware Workstation

1. Open VMware Workstation and select `Create a New Virtual Machine`.
2. Choose `Installer disc image file (iso)` and browse to the location of the downloaded ISO file.
3. Follow the prompts to configure the VM settings:
   - **Name**: Give your VM a meaningful name, such as `Pfsense`.
   - **Location**: Choose a location on your host machine where the VM files will be stored.

### Step 3: Configure VM Hardware

1. In the `Customize Hardware` section:
   - **Memory**: Allocate 1.2GB (1228 MB) of RAM.
   - **Processors**: Allocate 1 CPU.
   - **Hard Disk**: Allocate 10GB of disk space.

2. Add two network adapters:
   - **Network Adapter 1**: Set to `NAT` (for WAN).
   - **Network Adapter 2**: Set to `Host-only` (for LAN).

### Step 4: Install Pfsense

1. Start the VM and boot from the ISO.
2. Follow the installation prompts to install Pfsense.
3. During installation, assign the network adapters:
   - **WAN Interface**: Assign the first network adapter.
   - **LAN Interface**: Assign the second network adapter.

### Step 5: Configure Pfsense

1. After the installation completes, log in to the Pfsense console.
2. Assign an IP address for the LAN interface.
3. Enable DHCP for the LAN interface.

### Step 6: Access the Pfsense Web GUI

1. Open a web browser on a machine within the LAN network.
2. Navigate to the LAN IP address of the Pfsense VM (e.g., `http://192.168.1.1`).
3. Log in using the default credentials (username: `admin`, password: `pfsense`).

### Step 7: Configure Interfaces and Rules

1. In the Web GUI, go to `Interfaces > Assignments` to review and configure your network interfaces.
2. Go to `Firewall > Rules` to create and manage firewall rules based on your network requirements.
3. Configure additional settings such as NAT, VPN, and other Pfsense features as needed.

This completes the setup for the Pfsense VM in your homelab.
