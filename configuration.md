# Azure Network and Windows VM Configuration

## 1. Project Overview

This project demonstrates the deployment and configuration of a Windows Virtual Machine in Microsoft Azure.

The project covers Virtual Network configuration, subnet management, Network Security Group (NSG) association, VM networking, and network connectivity testing.

## 2. Azure Resources

| Resource | Configuration |
|---|---|
| Virtual Network | `vnet1` |
| Address Space | `10.0.0.0/16` |
| Subnet Name | `default` |
| Subnet Address Range | `10.0.0.0/24` |
| Virtual Machine | `vm1` |
| Network Interface | `vm1767` |
| Private IP Address | `10.0.0.4` |
| Network Security Group | `vm1-nsg` |
| Operating System | Windows Server |
| Remote Desktop Port | TCP 3389 |

## 3. Virtual Network Configuration

A Virtual Network named `vnet1` was configured to provide private network connectivity for Azure resources.

### Address Space

- Address space: `10.0.0.0/16`
- Address range: `10.0.0.0 – 10.0.255.255`

### Subnet Configuration

A subnet named `default` was configured within the Virtual Network.

- Subnet name: `default`
- Address range: `10.0.0.0/24`
- Starting address: `10.0.0.0`
- Address space: `10.0.0.0/16`

The subnet provides a dedicated IP address range for resources deployed within the Virtual Network.

## 4. Windows Virtual Machine Configuration

A Windows Virtual Machine named `vm1` was deployed in the Azure Virtual Network.

### Network Interface

- Network interface: `vm1767`
- Virtual Network: `vnet1`
- Subnet: `default`
- Private IP address: `10.0.0.4`
- Public IP address: Configured

The VM uses a network interface to communicate with other Azure resources and external networks.

## 5. Network Security Group

A Network Security Group named `vm1-nsg` is associated with the VM's subnet.

The NSG controls inbound and outbound network traffic using security rules.

### RDP Configuration

Remote Desktop Protocol (RDP) uses TCP port `3389` for remote access to Windows Server.

RDP access should be restricted to trusted source IP addresses.

## 6. Network Connectivity Testing

Network connectivity was tested using PowerShell.

### HTTPS Connectivity Test

```powershell
Test-NetConnection google.com -Port 443
```

The `TcpTestSucceeded` output indicates whether the TCP connection to the destination port was successful.

### RDP Connectivity Test

```powershell
Test-NetConnection <VM-Public-IP> -Port 3389
```

This command checks whether the RDP port is reachable from the client.

## 7. Project Outcome

This project demonstrates:

- Azure Virtual Network configuration.
- Subnet configuration.
- Windows Virtual Machine networking.
- Private IP address management.
- Network Security Group association.
- RDP connectivity testing.
- Basic Azure network troubleshooting.
