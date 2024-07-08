# Windows Server 2022 (Active Directory)

**Purpose**: Windows Server 2022 for Active Directory.

**Download**: [Windows Server 2022](https://info.microsoft.com/ww-landing-windows-server-2022.html)

## Configuration

- **OS**: Windows Server 2022
- **CPU**: 2 or greater
- **Memory**: 2GB or greater
- **Disk**: Based on your host capabilities
- **Network**: NAT, Static IP 192.168.100.129

## Setup Instructions

1. Download the ISO from the URL above.
2. Create a VM and choose the ISO location. Set the default requirements.
3. Remove the floppy disk in the edit VM section.
4. Install the OS and set the following:
   - Turn off Firewall and Defender.
   - Set DNS Forward Lookup zone.
   - Name this server as `DC01-VM` (domain controller).
   - Domain name as `youtube.local`.
