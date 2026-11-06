# Windows01 — Windows 11 Pro Workstation Deployment

## Business Context

NorthStar Solutions is a simulated organization with 50 users and plans to expand to 100 users. As part of its infrastructure modernization project, Windows01 was deployed to establish a Windows workstation environment for practicing IT support, system administration, and troubleshooting.

## Objective

Deploy a Windows 11 Pro virtual workstation, configure a local administrator account, verify the operating system and virtual hardware, and identify any initial configuration issues.

## Virtual Machine Configuration

| Component | Configuration |
|---|---|
| Hypervisor | Oracle VirtualBox |
| Operating System | Windows 11 Pro |
| Computer Name | Windows01 |
| Virtual CPUs | 2 |
| Memory | 4 GB |
| Virtual Hard Disk | 70 GB, dynamically allocated |
| Firmware | UEFI |
| TPM | Virtual TPM 2.0 |
| Initial Account | northstaradmin (local account) |

## Deployment Steps Completed

1. Downloaded the official Windows 11 installation ISO.
2. Created a new virtual machine in VirtualBox.
3. Allocated virtual CPU, memory, and storage resources.
4. Mounted the Windows installation ISO.
5. Selected Windows 11 Pro and performed a clean installation.
6. Selected the virtual hard drive as the installation destination.
7. Configured the computer name as `Windows01`.
8. Created a local user account named `northstaradmin`.
9. Reviewed and configured initial Windows privacy settings.
10. Opened System Information to verify the installation.
11. Inspected Device Manager for hardware and driver warnings.
12. Shut down the virtual machine safely.

## Verification Results

| Check | Result |
|---|---|
| Operating System | Microsoft Windows 11 Pro |
| Computer Name | Windows01 |
| System Type | x64-based PC |
| Installed Memory | 3.98 GB reported |
| Processor | Intel Core i7-4870HQ, 2 virtual cores |
| Windows Activation | Not active |
| Device Manager | Base System Device warning identified |

## Troubleshooting Finding: Device Manager Code 28

**Observed issue:** Device Manager displayed a yellow warning triangle beside Base System Device.

**Reported error:** Code 28 — The drivers for this device are not installed.

**Investigation:**
1. Opened Device Manager and examined Base System Device properties.
2. Reviewed the device status and confirmed Code 28.
3. Examined the hardware ID: `PCI\VEN_80EE&DEV_CAFE`.
4. Identified the vendor ID as Oracle VirtualBox and investigated VirtualBox Guest Additions as a potential solution.

**Resolution:**
1. Mounted the Oracle VirtualBox Guest Additions installation image.
2. Launched the Windows Guest Additions installer.
3. Installed Guest Additions 7.2.4 using the default installation options.
4. Restarted Windows01 to allow the drivers to load.

**Verification:** Reopened Device Manager after restarting Windows01. Base System Device was no longer listed with a warning, and no yellow warning triangles were visible.


**Final status:** Resolved.

**Lesson learned:** Hardware IDs can help identify devices with missing drivers. Using drivers from the appropriate official vendor provides a more reliable troubleshooting approach than installing unverified drivers.

## Outstanding Work

- Verify Windows01 network configuration and connectivity.
- Practice local user and group administration.
- Configure and test Windows security settings.
- Perform Windows troubleshooting exercises.
- Verify appropriate Windows licensing and activation.

## Skills Practiced

- Virtual machine provisioning
- Windows 11 clean installation
- Initial workstation configuration
- Local account creation
- Windows System Information (`msinfo32`)
- Device Manager diagnostics
- Hardware identification using PCI hardware IDs
- Windows driver installation and verification
- Basic troubleshooting documentation

## Deployment and Troubleshooting Evidence

### 1. Windows System Information

Verified the Windows 11 Pro edition, computer name, system architecture, processor, and installed memory.

![Windows01 System Information](System%20Info%20-%20Windows01.png)

### 2. Device Manager Warning

Identified a warning associated with Base System Device during the initial workstation inspection.

![Windows01 Base System Device](Base%20System%20Dev.%20-%20Windows01.png)

### 3. Device Driver Error — Code 28

Inspected the device properties and confirmed that Windows reported missing drivers (Code 28). Captured the original error as evidence before investigating and resolving the issue.

![Windows01 Code 28](Device%20Mgr%20-%20Code%2028%20-%20Windows01.png)

### 4. Device Driver Resolution — Code 28

Installed Oracle VirtualBox Guest Additions 7.2.4 to address the missing driver associated with Base System Device.

After restarting Windows01, reopened Device Manager and verified that Base System Device was no longer listed with a warning and no yellow warning triangles were visible.

**Result:** Code 28 resolved.

![Device Manager showing Code 28 resolved](Dev%20Mgr%20Code%2028%20Resolved.png)

**Initial deployment completed. Further configuration and troubleshooting remain in progress.**
