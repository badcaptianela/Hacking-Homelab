# Windows Server 2022 (Active Directory)

## Purpose
Windows Server 2022 is used for Active Directory services in this homelab setup. It provides essential directory services, DNS, and network management functionalities.

## Download
You can download Windows Server 2022 from the following link: [Windows Server 2022](https://info.microsoft.com/ww-landing-windows-server-2022.html)

## Configuration

- **OS**: Windows Server 2022
- **CPU**: 2 or greater
- **Memory**: 2GB or greater
- **Disk**: Based on your host capabilities
- **Network**: NAT, Static IP 192.168.100.129

## Setup Instructions

### Step 1: Download the ISO

1. Visit the [Windows Server 2022](https://info.microsoft.com/ww-landing-windows-server-2022.html) download page.
2. Sign up or log in to your Microsoft account.
3. Download the Windows Server 2022 ISO file.

### Step 2: Create a New VM in VMware Workstation

1. Open VMware Workstation and select `Create a New Virtual Machine`.
2. Choose `Installer disc image file (iso)` and browse to the location of the downloaded ISO file.
3. Follow the prompts to configure the VM settings:
   - **Name**: Give your VM a meaningful name, such as `Windows Server 2022 AD`.
   - **Location**: Choose a location on your host machine where the VM files will be stored.

### Step 3: Configure VM Hardware

1. In the `Customize Hardware` section:
   - **Memory**: Allocate at least 2GB (2048 MB) of RAM.
   - **Processors**: Allocate at least 2 CPUs.
   - **Hard Disk**: Allocate enough disk space based on your requirements.
   - **Network Adapter**: Set to `NAT`.

2. Remove the floppy disk in the `Hardware` section if it is added by default.

### Step 4: Install Windows Server 2022

1. Start the VM and boot from the ISO.
2. Follow the installation prompts to install Windows Server 2022.
3. During installation, set up a username and password for the administrator account.

### Step 5: Configure the Server

1. After the installation completes, log in with the administrator account.
2. Open `Server Manager` and perform the following configurations:

#### Turn Off Firewall and Defender

1. Open `Windows Defender Firewall`.
2. Turn off the firewall for all network profiles (Domain, Private, Public).
3. Open `Windows Security` and disable `Real-time protection` under `Virus & threat protection settings`.

#### Set DNS Forward Lookup Zone

1. In `Server Manager`, open the `DNS` management console.
2. Right-click on `Forward Lookup Zones` and select `New Zone`.
3. Follow the wizard to create a new forward lookup zone:
   - **Zone Type**: Primary Zone
   - **Zone Name**: youtube.local
   - **Dynamic Update**: Allow both nonsecure and secure dynamic updates

#### Configure Active Directory Domain Services (AD DS)

1. In `Server Manager`, open the `Add Roles and Features` wizard.
2. Install `Active Directory Domain Services` and `DNS Server`.
3. After installation, promote the server to a domain controller:
   - **Deployment Configuration**: Add a new forest
   - **Root Domain Name**: youtube.local
   - **Forest Functional Level**: Windows Server 2016 or later
   - **Domain Controller Capabilities**: DNS server, Global Catalog (GC)
   - **Directory Services Restore Mode (DSRM) Password**: Set a password

4. Complete the wizard and the server will restart.

### Step 6: Post-Installation Configuration

1. After the server restarts, log in with the domain administrator account.
2. Verify the Active Directory installation by opening `Active Directory Users and Computers`.
3. Create organizational units (OUs), user accounts, and groups as needed.

### Additional Notes

- **Static IP Configuration**: Ensure the server's network adapter is set to a static IP (192.168.100.129).
- **Network Isolation**: Ensure the VM is isolated from the internet for security reasons, especially if used in a vulnerable environment.

This completes the setup for Windows Server 2022 as an Active Directory Domain Controller in your homelab.
