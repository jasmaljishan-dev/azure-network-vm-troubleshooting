# Troubleshooting Azure Windows VM RDP Connectivity Using NSG Rules

## 1. Problem Description

This project demonstrates how to investigate and troubleshoot Remote Desktop Protocol (RDP) connectivity issues involving a Windows Virtual Machine in Microsoft Azure.

The objective is to identify how Network Security Group rules affect inbound connectivity and restore access by correcting the security configuration.

## 2. Environment

| Component | Configuration |
|---|---|
| Virtual Machine | `vm1` |
| Virtual Network | `vnet1` |
| Subnet | `default` |
| Private IP Address | `10.0.0.4` |
| Network Security Group | `vm1-nsg` |
| Protocol | TCP |
| RDP Port | 3389 |

## 3. Initial Investigation

The following checks are performed during the troubleshooting process:

1. Verify that the VM is running.
2. Check the VM's network interface.
3. Verify the private IP address.
4. Check the subnet and NSG association.
5. Review NSG inbound security rules.
6. Test RDP connectivity from the Windows client.

## 4. Simulating the Network Issue

An RDP connectivity issue can be simulated by temporarily configuring an NSG rule to deny inbound traffic on TCP port 3389.

### Steps

1. Open the Azure Portal.
2. Navigate to Network Security Groups.
3. Select `vm1-nsg`.
4. Open Inbound Security Rules.
5. Identify the rule allowing RDP traffic.
6. Temporarily configure a rule to deny TCP port 3389.
7. Save the configuration.
8. Attempt to connect to the VM using Remote Desktop.

The RDP connection should fail if the effective security rules block the traffic.

## 5. Root Cause

The simulated issue is caused by an NSG security rule denying inbound RDP traffic.

The NSG filters traffic based on the configured source, destination, protocol, port, priority, and action.

## 6. Resolution

The following steps are used to restore connectivity:

1. Open the Azure Portal.
2. Navigate to `vm1-nsg`.
3. Open Inbound Security Rules.
4. Identify the rule blocking TCP port 3389.
5. Remove or correct the blocking rule.
6. Configure RDP access from the authorized source IP address.
7. Save the changes.
8. Retry the RDP connection.

## 7. Verification

After correcting the NSG configuration:

- Verify that the VM is running.
- Confirm that the RDP rule allows the authorized source.
- Test connectivity to TCP port 3389.
- Connect to the Windows VM using Remote Desktop.
- Confirm that the Windows Server desktop is accessible.

## 8. Learning Outcomes

This project demonstrates practical knowledge of:

- Azure Virtual Network configuration.
- Network Security Groups.
- Inbound traffic filtering.
- Windows VM networking.
- RDP connectivity troubleshooting.
- Root cause analysis.
- Cloud infrastructure security.

## 9. Conclusion

This troubleshooting exercise demonstrates how NSG security rules affect access to Azure Virtual Machines.

By identifying and correcting an inbound security rule, connectivity can be restored while maintaining appropriate network security.
