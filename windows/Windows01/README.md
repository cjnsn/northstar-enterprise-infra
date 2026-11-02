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

**Diagnostic steps:**
1. Opened Device Manager.
2. Located Base System Device.
3. Opened the device's Properties window.
4. Reviewed the Device status message.

**Reported error:** Code 28 — The drivers for this device are not installed. Windows reported that no compatible drivers were available.

**Current status:** Unresolved.

**Planned next step:** Identify the device using its hardware IDs and investigate an appropriate driver or VirtualBox configuration change.

## Outstanding Work

- Investigate and resolve the Code 28 driver warning.
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
- Basic troubleshooting documentation

## Project Status

**Initial deployment completed. Further configuration and troubleshooting remain in progress.**
