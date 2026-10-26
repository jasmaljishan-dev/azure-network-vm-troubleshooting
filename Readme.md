
# Troubleshooting Azure Windows VM RDP Connectivity Using NSG Rules

## Project Overview

This project demonstrates how to configure Azure networking and troubleshoot Remote Desktop Protocol (RDP) connectivity issues on a Windows Virtual Machine.

## Objectives

- Create an Azure Virtual Network (VNet).
- Configure subnets.
- Create and configure Network Security Groups (NSGs).
- Deploy a Windows Virtual Machine.
- Test network connectivity.
- Troubleshoot RDP connectivity issues.

## Technologies Used

- Microsoft Azure
- Azure Virtual Network
- Azure Network Security Groups
- Windows Server
- Remote Desktop Protocol (RDP)
- PowerShell

## Network Configuration

- Virtual Network: 10.0.0.0/16
- Subnet 1: 10.0.1.0/24
- Subnet 2: 10.0.2.0/24
- RDP Port: 3389
- Protocol: TCP

## Troubleshooting Scenario

An RDP connection to the Windows Virtual Machine was blocked by an NSG inbound security rule.

### Root Cause

The NSG rule was configured to deny inbound traffic on TCP port 3389.

### Solution

The NSG rule was corrected to allow RDP traffic from the authorized source IP address.

### Result

The RDP connection was successfully restored.

## Screenshots

Screenshots of the Azure configurations and troubleshooting process are available in the screenshots folder.

## Skills Demonstrated

- Azure Networking
- Virtual Machine Administration
- NSG Configuration
- Network Troubleshooting
- Windows Server Administration
- Cloud Infrastructure Management
