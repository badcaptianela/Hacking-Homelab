# Pfsense

**Purpose**: Pfsense acts as a Router/Firewall in the network.

**Download**: [Pfsense](https://www.pfsense.org/download/)

## Configuration

- **OS**: Pfsense
- **CPU**: 1
- **Memory**: 1.2GB
- **Disk**: 10GB
- **Network**: Two network adapters (one for WAN, one for LAN)

## Setup Instructions

1. Download the ISO from the URL above.
2. Create a new VM in VMware Workstation and install Pfsense.
3. Add two network adapters to this VM:
   - Assign one for WAN.
   - Assign the other for LAN.
4. Start the installation and assign the adapters for WAN and LAN.
5. Assign an IP for LAN.
6. Enable DHCP for LAN.
7. Go to the Web GUI to configure the settings:
   - Configure interfaces and rules based on the requirement.
