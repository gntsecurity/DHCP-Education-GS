
# Configuring DHCP Servers

This guide covers basic DHCP server configuration on Linux (using `dhcpd`) and Windows.

## Linux DHCP Configuration
1. **Install the DHCP server package** (e.g., `isc-dhcp-server`).
   - On Debian/Ubuntu:
     ```bash
     sudo apt update
     sudo apt install isc-dhcp-server
     ```
   - On Red Hat/CentOS:
     ```bash
     sudo yum install dhcp
     ```
   
2. **Edit the DHCP configuration file** (`/etc/dhcp/dhcpd.conf`):
   ```bash
   subnet 192.168.1.0 netmask 255.255.255.0 {
       range 192.168.1.100 192.168.1.200;
       option routers 192.168.1.1;
       option domain-name-servers 8.8.8.8, 8.8.4.4;
   }
   ```
   - This configuration specifies an IP address range, router, and DNS servers for clients in the `192.168.1.0/24` network.

3. **Start and enable the DHCP service**:
   ```bash
   sudo systemctl start isc-dhcp-server
   sudo systemctl enable isc-dhcp-server
   ```
   - Use `systemctl status isc-dhcp-server` to verify the service is running.

## Windows DHCP Server Configuration
1. **Install the DHCP Server Role**:
   - Open **Server Manager**.
   - Go to **Add Roles and Features** > **DHCP Server** and follow the prompts to install.

2. **Create a New DHCP Scope**:
   - Open the **DHCP management console**.
   - Right-click on **IPv4** and select **New Scope**.
   - Enter the scope's name and IP address range, lease duration, and DNS servers.

3. **Activate the Scope**:
   - Once the scope is created, right-click the new scope and select **Activate**.
   - Authorize the DHCP server in Active Directory if prompted.

After configuration, verify that clients receive IP addresses within the defined scope.
