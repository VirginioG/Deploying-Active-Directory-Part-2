<p align="center">
<img src="https://i.imgur.com/pU5A58S.png" alt="Microsoft Active Directory Logo"/>
</p>

<h1>Deploying-Active-Directory-Part-2</h1>
This tutorial walks you through enabling Remote Desktop access for non-administrative users on Client-1 and demonstrates how to create multiple user accounts using PowerShell on the Domain Controller. It covers how to grant domain users access to Remote Desktop and test login with newly created accounts. The tutorial also explores observing account creation in Active Directory Users and Computers (ADUC) and logging into Client-1 with those accounts.<br />


<h2>Video Demonstration</h2>

- ### [YouTube: How to Deploy on-premises Active Directory within Azure Compute](https://www.youtube.com)

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Active Directory Domain Services
- PowerShell

<h2>Operating Systems Used </h2>

- Windows Server 2022
- Windows 10 (21H2)

<h2>High-Level Deployment and Configuration Steps</h2>

- Log into Client-1 as mydomain.com\jane_admin. Open System Properties, enable Remote Desktop, and allow domain users to access it. Now, you can log into Client-1 as a non-administrative user.
- Log into DC-1 as jane_admin, open PowerShell ISE as an administrator, and run a script to create multiple new users. Observe the accounts being created and ensure they appear in the _EMPLOYEES OU in ADUC.
- After creating the users, attempt to log into Client-1 using one of the newly created accounts. Use the password specified in the script to verify access.


<h2>Deployment and Configuration Steps</h2>

<p>


![Part2Part1](https://github.com/user-attachments/assets/dbefa179-c95d-4fab-a266-3ea5ae9cc6ba)



</p>
<p>

Access the DC-1 server.

Open Server Manager > Manage > Add Roles and Features.

Choose Role-based or feature-based installation, then select Active Directory Domain Services.

Follow the prompts to install AD DS.

After installation, open Server Manager, and click on the Notification Flag. 

Select Promote this server to a domain controller.

Choose Add a new forest and name it mydomain.com (or any other domain name you prefer).

Set up Directory Services Restore Mode (DSRM) password and complete the wizard.

Restart the server when prompted.

After the restart, log into DC-1 as mydomain.com\labuser.

</p>
<br />

<p>


![Part2Part2](https://github.com/user-attachments/assets/b4912754-ae2f-48ff-b6ef-bc312623a047)



</p>
<p>
Open Active Directory Users and Computers (ADUC).

Right-click on the domain name (mydomain.com) and select New > Organizational Unit.

Create an OU named _EMPLOYEES.

Create another OU named _ADMINS.

Right-click on the _ADMINS OU, select New > User.

Name the user Jane Doe with the username jane_admin.

Set the password as Cyberlab123!.

Click Next and finish creating the user.

In ADUC, locate the jane_admin user in the _ADMINS OU.

Right-click on jane_admin, select Add to a group, and add it to the Domain Admins group.

Log out of the DC-1 server and log back in as jane_admin (using the credentials mydomain.com\jane_admin).
</p>
<br />

<p>


![Part2Part3](https://github.com/user-attachments/assets/363d22ac-f87a-4e25-bf4c-ce193b4db0ab)



</p>
On Client-1, log in as the local admin user (labuser).

Go to Control Panel > System and Security > System and select Change settings under Computer name, domain, and workgroup settings.

Click Change, select Domain, and enter mydomain.com.

When prompted, enter the credentials for a domain admin (e.g., jane_admin).

Restart Client-1 after the domain join process is complete.

On DC-1, open ADUC and verify that Client-1 appears in the domain.

In ADUC, right-click on mydomain.com, select New > Organizational Unit, and create an OU named _CLIENTS.

Drag Client-1 into the _CLIENTS OU.

<p>
