# ATTACK Machine (Kali)

**Purpose**: I am using Kali as my attack machine. It contains many pre-installed tools that are helpful in attacking.

**Download**: [Kali Linux](https://www.kali.org)

## Configuration

- **OS**: Kali Linux
- **CPU**: 4
- **Memory**: 5GB
- **Disk**: 50GB
- **Network**: NAT

## Setup Instructions

1. Download the ISO for bare metal or pre-installed VM for VMware from the Kali website.
2. If you downloaded the ISO:
   - Boot up the VM and run these commands to update the machine:
     ```bash
     sudo apt update
     ```
      ```bash
     sudo apt upgrade -y
     ```
   - Check for the recent OS release using:
     ```bash
     cat /etc/os-release
     ```
3. If you downloaded the pre-built VM:
   - Download Pimpmykali from the GitHub repository:
     ```bash
     git clone https://github.com/Dewalt-arch/pimpmykali.git
     ```
   - This helps the VM check for any breaks and fix them.
   
   - To run Pimpmykali
     ```bash
     sudo ./pimpmykali.sh
     ```
     -Then just Reboot the Machine You are Ready for Hacking
