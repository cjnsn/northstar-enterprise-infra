# NorthStar Enterprise Infrastructure

## Project Overview

NorthStar Solutions is a simulated 50-user organization experiencing rapid growth and expecting to scale to approximately 100 employees within 18 months. Its existing IT environment relies on local user accounts, inconsistent permissions, manually configured Linux servers, shared credentials, and manual onboarding and offboarding processes.

This project involves designing and implementing a Linux-focused enterprise infrastructure that addresses these limitations while improving security, manageability, reliability, and scalability.

## Business Problems

NorthStar's existing environment presents several operational and security challenges:

* User access is not centrally managed.
* Employees may have more access than required for their roles.
* Onboarding and offboarding require multiple manual administrative tasks.
* Linux servers are configured manually and inconsistently.
* Shared credentials create security and accountability concerns.
* The existing infrastructure was not designed to support continued organizational growth.

## Project Objectives

The infrastructure will be designed to:

* Centralize identity and access management.
* Apply least-privilege access based on employee roles.
* Standardize Linux server administration.
* Provide reliable internal DNS and network services.
* Secure remote Linux administration.
* Improve onboarding and offboarding processes.
* Automate repetitive administrative tasks where appropriate.
* Improve infrastructure documentation and auditability.
* Provide an architecture capable of supporting future organizational growth.

## Initial Network Architecture

| Component               | Configuration                 |
| ----------------------- | ----------------------------- |
| Network                 | `10.10.10.0/24`               |
| Default Gateway         | `10.10.10.1`                  |
| Linux Server 01         | `10.10.10.2`                  |
| Linux Server 02         | `10.10.10.3`                  |
| Domain Controller / DNS | `10.10.10.10`                 |
| Infrastructure Range    | `10.10.10.1 - 10.10.10.19`    |
| DHCP Pool               | `10.10.10.20 - 10.10.10.149`  |
| Reserved/Future Use     | `10.10.10.150 - 10.10.10.254` |
| Internal Domain         | `corp.northstarsolutions.com` |

## Planned Technologies

Technologies will be added as the project develops. The environment is expected to incorporate:

* Linux
* Windows Server / Active Directory
* DNS and DHCP
* SSH
* Bash
* PowerShell
* Ansible
* Git
* Network and host-based security controls
* Infrastructure monitoring and logging

## Project Status

**Phase 1 — Architecture & Planning: In Progress**

The initial network addressing strategy and infrastructure requirements are defined. The next phase will establish the virtual network and deploy the first Linux server.
