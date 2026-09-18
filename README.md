<p align="center">
<img src="https://upload.wikimedia.org/wikipedia/commons/4/48/Windows_logo_-_2012.svg" height="100" alt="Windows Logo"/>
</p>

# Hybrid Active Directory & Endpoint Management Lab

This tutorial outlines the implementation of an on-premises Active Directory synchronized with Microsoft Entra ID (Azure AD), including device enrollment via Microsoft Intune and service management through Jira.

### Environments and Technologies Used

- Microsoft Hyper-V (Virtualization)
- Active Directory Domain Services (AD DS)
- Microsoft Entra Connect
- Microsoft 365 / Entra ID 
- Microsoft Intune (MDM)
- Jira Service Management
- Windows Server 2022 & Windows 11

### Architecture and Configuration Steps

In this lab, a local Windows Server 2022 machine was configured to act as a Domain Controller for the on-premises network. A hybrid cloud environment was then established using Microsoft Entra Connect to synchronize local Active Directory users to a Microsoft 365 tenant. Finally, client machines were enrolled in Microsoft Intune for modern endpoint management.

[Drag and drop your Network Diagram image here (if you have one)]

**0. Virtual Infrastructure Setup (Hyper-V)**


To simulate the on-premises data center, Microsoft Hyper-V was utilized as the virtualization hypervisor. Virtual machines were allocated dedicated compute, memory, and virtual switch networking resources to host the Windows Server 2022 Domain Controller and the client machines.

<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/c7f1fc1e-1a4c-4a42-8eb1-a49f55dec132" />


**1. Server Provisioning & Network Setup**


A virtual machine was provisioned with Windows Server 2022 Standard (Desktop Experience). To ensure reliable DNS resolution and domain functionality, the server was assigned a static IPv4 address and renamed to align with enterprise naming conventions.

<img width="1366" height="765" alt="image" src="https://github.com/user-attachments/assets/76fd4e08-0e2c-40aa-b409-34457a9b6c77" />



**2. Domain Controller Promotion**


The Active Directory Domain Services (AD DS) role was installed, and the server was promoted to a Domain Controller. A new local forest and domain were established to serve as the foundation for the on-premises network identity management.

<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/287450b4-93f9-45c3-bef7-e1463748b833" />



**3. Directory Structure & User Management**


Organizational Units (OUs) were created to logically categorize departments and enforce structured management. Test user accounts and security groups were provisioned to simulate an active workforce and prepare for cloud synchronization.

<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/009228e7-88b5-4450-9946-06ab25640a4b" />


**4. Microsoft Entra Connect Cloud Synchronization**
To establish the hybrid identity, Microsoft Entra Connect was installed. On-premises identities were successfully synced to the cloud, verified by checking the Entra ID portal for the "On-premises sync enabled" status.

[Drag and drop your Entra Connect / Entra ID portal screenshot here]

**5. Microsoft Intune Device Enrollment**
To manage the endpoints, auto-enrollment for Windows devices into Microsoft Intune was configured. Configuration profiles and compliance policies were pushed to the test client machine.

[Drag and drop your Intune dashboard screenshot here]

**6. Jira Service Management**
A Jira Service Management portal was configured to simulate help desk workflows. Simulated user tickets (e.g., password resets) were generated and documented through the portal to mimic a real-world IT support lifecycle.

[Drag and drop your Jira ticket screenshot here]
