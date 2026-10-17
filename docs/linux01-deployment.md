# Linux01 — Rocky Linux Server Deployment and Secure Remote Administration

## 1. Business Scenario

NorthStar Solutions is a fictional organization building an internal IT infrastructure to support business operations.

The organization requires a reliable Linux server that can be centrally managed, securely accessed by administrators, and expanded to support future infrastructure services.

**Business objectives:**
- Deploy a stable Linux server using an enterprise-oriented operating system.
- Configure consistent network addressing.
- Establish secure remote administration.
- Apply operating system updates and verify service health.
- Create a foundation for future infrastructure automation and monitoring.

## 2. Technology Stack

| Component | Configuration |
|---|---|
| Virtualization | Oracle VirtualBox |
| Operating system | Rocky Linux 9.8 |
| Server hostname | linux01.northstar.internal |
| Server IP address | 10.10.10.2/24 |
| Default gateway | 10.10.10.1 |
| Virtual network | NorthStar-Network |
| Administration | OpenSSH |
| SSH authentication | Ed25519 public-key authentication |
| Host firewall | firewalld |

## 3. Implementation

### Server Deployment

Created a Rocky Linux 9.8 virtual machine using a minimal installation to reduce unnecessary software and services.

Allocated two virtual CPUs, 2 GB of memory, and a 25 GB virtual disk.

Configured the server hostname as `linux01.northstar.internal`.

### Network Configuration

Configured Linux01 with the static IPv4 address `10.10.10.2/24` and default gateway `10.10.10.1`.

Connected the server to the VirtualBox NAT Network named `NorthStar-Network`.

Verified gateway connectivity, external network access, and DNS resolution.

### Operating System Maintenance

Used the DNF package manager to check for and install operating system updates.

Rebooted the server and confirmed that no failed systemd services were reported.

### Secure Remote Administration

Verified that the OpenSSH server was running and enabled.

Confirmed that the host firewall permitted SSH traffic.

Configured VirtualBox NAT Network port forwarding to allow administration from the macOS host.

Generated a passphrase-protected Ed25519 SSH key pair on the administrator workstation.

Installed the public key in the Linux administrator account's `authorized_keys` file and configured restrictive file permissions.

Successfully authenticated remotely using the private key.

## 4. Troubleshooting and Resolution

| Issue | Resolution |
|---|---|
| Administrator account initially lacked sudo privileges | Recovered administrative access and added the account to the wheel group |
| macOS host could not connect directly to the NAT Network guest IP | Configured VirtualBox NAT Network SSH port forwarding |
| Nano text editor unavailable on minimal installation | Installed Nano using DNF |
| SSH public-key authentication required verification | Inspected SSH server logs and confirmed successful public-key authentication |

## 5. Validation

Completed the following checks:

- Confirmed the server's hostname and static IP address.
- Verified connectivity to the default gateway and external network.
- Verified DNS resolution.
- Confirmed that the SSH service was active.
- Confirmed no failed systemd services after updates.
- Verified successful SSH public-key authentication in server logs.

Example SSH authentication log:

```text
Accepted publickey for northstaradmin from 10.10.10.1 port 53266 ssh2
```

## 6. Security Considerations

- The private SSH key remains on the administrator's workstation.
- The private key is protected by a passphrase.
- SSH public-key authentication has been verified.
- SSH password authentication settings will be reviewed during the next hardening stage.
- Passwords, passphrases, and private keys are excluded from the repository.

## 7. Business Outcome

NorthStar Solutions now has an updated Rocky Linux server with predictable network addressing and verified secure remote administrative access.

This server establishes the foundation for additional infrastructure services, centralized administration, automation, monitoring, and backup procedures.

## 8. Next Steps

- Review and harden SSH configuration.
- Deploy Linux02.
- Configure additional infrastructure services.
- Implement automated administration and monitoring.
- Document testing, recovery, and operational procedures.
