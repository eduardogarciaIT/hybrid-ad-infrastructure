<p align="center">
<img src="https://upload.wikimedia.org/wikipedia/commons/thumb/4/48/Windows_logo_-_2012.svg/1024px-Windows_logo_-_2012.svg.png" height="20%" width="20%" alt="Windows Logo"/>
</p>

# Hybrid Active Directory & Endpoint Management Lab

This tutorial outlines the implementation of an on-premises Active Directory synchronized with Microsoft Entra ID (Azure AD), including device enrollment via Microsoft Intune and service management through Jira.

### Environments and Technologies Used

- Active Directory Domain Services (AD DS)
- Microsoft Entra Connect
- Microsoft 365 / Entra ID 
- Microsoft Intune (MDM)
- Jira Service Management
- Windows Server 2022 & Windows 11

### Architecture and Configuration Steps

In this lab, a local Windows Server 2022 machine was configured to act as a Domain Controller for the on-premises network. A hybrid cloud environment was then established using Microsoft Entra Connect to synchronize local Active Directory users to a Microsoft 365 tenant. Finally, client machines were enrolled in Microsoft Intune for modern endpoint management.

[Drag and drop your Network Diagram image here (if you have one)]

**1. On-Premises Active Directory Setup**
The local Domain Controller was configured with a static IP address to serve as the primary DNS. Once AD DS was configured, test user accounts, security groups, and Organizational Units (OUs) were created. 

[Drag and drop your Active Directory (ADUC) screenshot here]

**2. Microsoft Entra Connect Cloud Synchronization**
To establish the hybrid identity, Microsoft Entra Connect was installed. On-premises identities were successfully synced to the cloud, verified by checking the Entra ID portal for the "On-premises sync enabled" status.

[Drag and drop your Entra Connect / Entra ID portal screenshot here]

**3. Microsoft Intune Device Enrollment**
To manage the endpoints, auto-enrollment for Windows devices into Microsoft Intune was configured. Configuration profiles and compliance policies were pushed to the test client machine.

[Drag and drop your Intune dashboard screenshot here]

**4. Jira Service Management**
A Jira Service Management portal was configured to simulate help desk workflows. Simulated user tickets (e.g., password resets) were generated and documented through the portal to mimic a real-world IT support lifecycle.

[Drag and drop your Jira ticket screenshot here]
