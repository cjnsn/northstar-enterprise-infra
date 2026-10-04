# Network Addressing Plan

## Overview

NorthStar Solutions uses the 10.10.10.0/24 network for its initial infrastructure environment. The addressing strategy separates core infrastructure from dynamically assigned employee endpoints while reserving address space for future expansion.

## Addressing Scheme

| Component | IP Address / Range | Assignment |
|---|---|---|
| Default Gateway | 10.10.10.1 | Static |
| Linux01 | 10.10.10.2 | Static |
| Linux02 | 10.10.10.3 | Static |
| Domain Controller / DNS | 10.10.10.10 | Static |
| Core Infrastructure | 10.10.10.1 - 10.10.10.19 | Reserved |
| Employee Endpoints | 10.10.10.20 - 10.10.10.149 | DHCP |
| Future Use | 10.10.10.150 - 10.10.10.254 | Reserved |

## Design Decisions

### Static Infrastructure Addressing

Core infrastructure systems use static IP addresses because other systems and administrators need to locate these services reliably. Employee workstations use DHCP because endpoint devices are expected to change as employees and equipment are added or removed.

### Address Reservation

Addresses 10.10.10.1 through 10.10.10.19 are reserved for infrastructure. This prevents DHCP from assigning addresses intended for servers or other critical network devices.

### DHCP Scope

The initial DHCP pool is 10.10.10.20 through 10.10.10.149. This provides sufficient capacity for the organization's expected growth from approximately 50 to 100 employees while leaving additional address space available for future infrastructure requirements.

### Default Gateway

10.10.10.1 is designated as the default gateway. Hosts send traffic to the default gateway when the destination exists outside the local 10.10.10.0/24 network.

### Internal DNS Namespace

The planned internal namespace is:

`corp.northstarsolutions.com`

The `corp` subdomain distinguishes NorthStar's internal corporate environment from its public-facing domain and can support hostnames such as:

`linux01.corp.northstarsolutions.com`
