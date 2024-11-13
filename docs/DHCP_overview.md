# DHCP Overview

The Dynamic Host Configuration Protocol (DHCP) is a network management protocol used to dynamically assign IP addresses to devices on a network. DHCP automates this process, ensuring each device has a unique IP address.

## Key Components of DHCP
- **DHCP Server:** The server providing configuration parameters to DHCP clients.
- **DHCP Client:** The device requesting network configuration from the DHCP server.
- **Lease:** The period for which an IP address is assigned to a device.

## DHCP Process (DORA)
1. **Discover**: The client sends out a broadcast to find available DHCP servers.
2. **Offer**: DHCP servers respond with an offer of IP configuration.
3. **Request**: The client requests the offered configuration.
4. **Acknowledge**: The server acknowledges, and the client configures itself with the provided information.

### Diagram of the DHCP Process
![DHCP Process](../images/dhcp_process.png)
