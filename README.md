<p align="center">
<img src="https://i.imgur.com/pU5A58S.png" alt="Microsoft Active Directory Logo"/>
</p>

<h1>Deploying-Active-Directory-Part-2</h1>
This tutorial walks you through enabling Remote Desktop access for non-administrative users on Client-1 and demonstrates how to create multiple user accounts using PowerShell on the Domain Controller. It covers how to grant domain users access to Remote Desktop and test login with newly created accounts. The tutorial also explores observing account creation in Active Directory Users and Computers (ADUC) and logging into Client-1 with those accounts.<br />


<h2>Video Demonstration</h2>

- ### [Deploying-Active-Directory-Part-2](https://youtu.be/HbpaG6zGgfs?si=s1jPGpWyiyal57WR)

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



![Part3Part1](https://github.com/user-attachments/assets/3edf80b8-4255-403f-afe2-aca6334d25e2)



</p>
<p>

Login to Client-1 as jane_admin.

Open System Properties and enable Remote Desktop.

Allow Domain Users access to Remote Desktop.


</p>
<br />

<p>


![Part3Part2](https://github.com/user-attachments/assets/d5544ae5-58cb-400d-b5b0-e66b6b52847c)




</p>
<p>
Login to DC-1 as jane_admin

Open PowerShell ISE as administrator.
  
Paste and run the PowerShell script to create new user accounts.

Verify new users are created in the _EMPLOYEES OU via ADUC.

Attempt to log into Client-1 using one of the new user accounts to ensure successful login.

</p>
<br />

<p>
