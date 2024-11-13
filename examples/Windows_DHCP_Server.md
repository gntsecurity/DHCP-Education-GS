
# Configuring a DHCP Server on Windows

This guide explains how to install, configure, and manage a DHCP server on a Windows environment.

## Step 1: Install the DHCP Server Role
1. Open **Server Manager**.
2. Go to **Add Roles and Features Wizard** and select **Role-based or feature-based installation**.
3. From the **Server Roles** list, select **DHCP Server**.
4. Click **Next** and complete the wizard to install the DHCP role.
5. Once installed, launch the **DHCP Management Console** from the **Tools** menu in Server Manager.

## Step 2: Authorize the DHCP Server
1. Open the **DHCP Management Console**.
2. Right-click the DHCP server node and select **Authorize**.
3. This step is required if the server is part of an Active Directory domain and allows the DHCP server to lease IP addresses.

## Step 3: Configure a DHCP Scope
1. In the **DHCP Management Console**, right-click on **IPv4** and select **New Scope**.
2. Provide a **Name** and **Description** for the scope.
3. Define the **IP Address Range** for the scope by specifying the **Start IP address** and **End IP address**.
4. Set the **Subnet Mask** for the network.
5. Specify any IP addresses to **Exclude** from the range (e.g., addresses reserved for static IPs).
6. Set the **Lease Duration** to define how long clients will keep their IP addresses before they must renew.
7. Configure **Additional Scope Options** like **Router (Gateway)**, **DNS Servers**, and **WINS Servers** as needed.

## Step 4: Activate the DHCP Scope
1. After creating the scope, right-click the scope and select **Activate**.
2. Activating the scope enables DHCP clients to start receiving IP addresses from this scope.

## Step 5: Verify and Test
- To verify that the DHCP server is working, connect a client to the network and check if it receives an IP address automatically.
- Use `ipconfig /renew` on the client (Windows) or `dhclient` on Linux to manually trigger a DHCP lease renewal.

## Useful Commands and Logs
- **Commands**:
  - `ipconfig /all`: Show detailed IP configuration and DHCP server information on Windows clients.
  - `ipconfig /release` and `ipconfig /renew`: Commands to release and renew IP addresses on Windows.
  
- **Logs**:
  - Check the Event Viewer under **Applications and Services Logs** > **Microsoft** > **Windows** > **DHCP-Server** for DHCP events and troubleshooting.

By following these steps, you should have a fully functional DHCP server running on Windows, capable of dynamically assigning IP addresses to clients on your network.
