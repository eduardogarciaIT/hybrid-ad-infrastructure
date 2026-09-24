<div align="center">
  <img src="https://github.com/user-attachments/assets/3b8c49a0-aac3-43be-8bb7-ee228c68183d" width="800" alt="Hybrid Active Directory and Entra ID Diagram"/>
</div>


# Enterprise Hybrid IT Infrastructure Lab

This tutorial outlines the implementation of an on-premises Active Directory synchronized with Microsoft Entra ID (Azure AD), including device enrollment via Microsoft Intune and service management through ServiceNow.

### Environments and Technologies Used

- Microsoft Hyper-V (Virtualization)
- Active Directory Domain Services (AD DS)
- Microsoft Entra Connect
- Microsoft 365 / Entra ID 
- Microsoft Intune (MDM)
- ServiceNow (ITSM / Incident Management)
- Windows Server 2022 & Windows 11

### Architecture and Configuration Steps

In this lab, a local Windows Server 2022 machine was configured to act as a Domain Controller for the on-premises network. A hybrid cloud environment was then established using Microsoft Entra Connect to synchronize local Active Directory users to a Microsoft 365 tenant. Finally, client machines were enrolled in Microsoft Intune for modern endpoint management.

<br><br>
<br><br>

### 0. Microsoft Hyper-V (On-Premises Virtualization)

To simulate the on-premises data center, Microsoft Hyper-V was utilized as the virtualization hypervisor. Virtual machines were allocated dedicated compute, memory, and virtual switch networking resources to host the Windows Server 2022 Domain Controller and the client machines.

<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/c7f1fc1e-1a4c-4a42-8eb1-a49f55dec132" />

<br><br>
<br><br>

### 1. Windows Server 2022 (Provisioning and Networking)

A virtual machine was provisioned with Windows Server 2022 Standard (Desktop Experience). To ensure reliable DNS resolution and domain functionality, the server was assigned a static IPv4 address and renamed to align with enterprise naming conventions.

<img width="1366" height="765" alt="image" src="https://github.com/user-attachments/assets/76fd4e08-0e2c-40aa-b409-34457a9b6c77" />

<br><br>
<br><br>

### 2. Active Directory Domain Services (Domain Promotion)

The Active Directory Domain Services (AD DS) role was installed, and the server was promoted to a Domain Controller. A new local forest and domain were established to serve as the foundation for the on-premises network identity management.

<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/287450b4-93f9-45c3-bef7-e1463748b833" />

<br><br>
<br><br>

### 3. Active Directory Organizational Units (Identity Management)

Organizational Units (OUs) were created to logically categorize departments and enforce structured management. Test user accounts and security groups were provisioned to simulate an active workforce and prepare for cloud synchronization.

<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/009228e7-88b5-4450-9946-06ab25640a4b" />

<br><br>
<br><br>

### 4. Microsoft Entra Connect (Cloud Synchronization)

To establish the hybrid identity, Microsoft Entra Connect was installed. On-premises identities were successfully synced to the cloud, verified by checking both the local Synchronization Service Manager and the Entra ID portal for the "On-premises sync enabled" status.

<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/86530b8a-7582-4fda-9ba2-50da43d003d7" />

<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/e21c467b-dab2-4b31-a3b3-9e4f57e86973" />

<br><br>
<br><br>

### 5. Microsoft Intune (Endpoint Management and MDM)

To establish modern endpoint management, the virtual machine (`CLIENT-01`) provisioned in the local Hyper-V environment was enrolled into Microsoft Intune via Microsoft Entra ID join. Device management and compliance policies were verified directly within the Intune admin center.

<img width="1365" height="762" alt="image" src="https://github.com/user-attachments/assets/5c0698ff-c4ad-41ac-bb06-eb170afae6d3" />

<br><br>
<br><br>

### 6. ServiceNow (ITSM)

To simulate an enterprise help desk lifecycle, a ServiceNow developer instance was integrated with the Microsoft tenant. An Incident ticket was generated for a simulated user access issue, assigned to the appropriate IT support queue, and tracked through resolution, demonstrating proper ITIL-aligned service management.

<img width="1365" height="767" alt="image" src="https://github.com/user-attachments/assets/39b231e6-3e5e-441d-af3e-993a3a0564a4" />

<img width="1365" height="765" alt="image" src="https://github.com/user-attachments/assets/435dca7b-9697-4ee6-9f3b-3a320d8b36bd" />

<img width="1365" height="767" alt="image" src="https://github.com/user-attachments/assets/71786517-1215-48d4-8947-505356964f4f" />
