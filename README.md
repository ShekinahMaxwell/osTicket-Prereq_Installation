<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
This tutorial outlines the prerequisites and installation of the open-source help desk ticketing system osTicket. What is osTicket? osTicket is essentially a widely used, free Help Desk ticketing sytem to help steamline customer service and support.<br/>

<h2> Overview </h2>
<p>
<img width="657" alt="Screen Shot 2024-08-10 at 12 29 58 PM" src="https://github.com/user-attachments/assets/5aee548a-db10-4b77-85a3-25caa822cbc1">
</p>

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)

<h2>Operating Systems Used </h2>

- Windows 10</b> (21H2)

<h2>List of Prerequisites</h2>

- Step 1: Install the osTicket requirements
- Step 2: Install osTicket itself
- Step 3: After installation of osTicket
- Step 4: Explore osTicket as both Admin and Help Desk Professional- create, interact, close tickets
- Step 5: Clean up virtual environment in Azure

<h2>Installation Steps</h2>
<b>Step 1: Install the osTicket requirements </b>

<p>
<img width="1303" alt="01" src="https://github.com/user-attachments/assets/3561ff38-ed3f-4417-86c6-b9846e3b7321">
</p>
<p>
Go to portal.azure.com and assuming you already have a subscription set up, search resources in the search bar and click Create.
</p>
<br />

<p>
<img width="1440" alt="01" src="https://github.com/user-attachments/assets/1dda7f43-7340-4282-9636-fd974ebf1a88">
</p>
<p>
Label RG-osTicket and click Review+Create and then click Create.
</p>
<br />

<p>
<img width="1435" alt="06" src="https://github.com/user-attachments/assets/e0fe1a8e-f31c-41d1-8ae3-c4ce299e6d26">
</p>
<p>
Next, search for Virtual Machines in the search bar. Click Create and then click Azure Virtual Machines.
</p>
<br />

<p>
<img width="1439" alt="02" src="https://github.com/user-attachments/assets/17bfe8f6-08a1-4a00-aa28-6dc5eb0a8b33">
</p>
<p>
Name the Virtual machine VM-osTicket for ease of identification. Select your appropriate region (if you experience any difficulty later on, then you may need to change your region). Select Windows 10 for the image. Select see all sizes for size and choose Standard_D4s_v4 - 4 vcpus, 16 GiB memory $140.16/month. 
</p>
<br />

<p>
<img width="1440" alt="0202" src="https://github.com/user-attachments/assets/9082d7fb-c8bc-4404-8619-3f2bf0893afa">
</p>
<p>
Pick your username and password (DO NOT FORGET YOUR USERNAME AND PASSWORD). Click Next: Disks> then Next: Networking> then Review+Create > (You should get a page with a green bar that says validation recieved) Then click Create.
</p>
<br />

<p>
<img width="1440" alt="Checkpoint screen" src="https://github.com/user-attachments/assets/a6cd4df0-b9be-471c-8564-b3d49402d145">
</p>
<p>
Checkpoint screen. Deployment is in progress.
</p>
<br />

<b>Step 2: Installation of osTicket</b>
<p> Here we will remote desktop into the vritual machine we just created and install osTicket there.</p>
<p>
<img width="1440" alt="deployment complete" src="https://github.com/user-attachments/assets/dc1d0598-735a-44a2-9217-c76ccc1f7728">
</p>

<p>
<img width="1440" alt="06" src="https://github.com/user-attachments/assets/376a182c-a191-47ff-a1bf-a4af9e9e36aa">
</p>

<p>
Once deployment is complete, click on Go to Resource. From this screen copy the ip address of our vm-osTicket.
</p>
<br />

<p>
<img width="567" alt="07" src="https://github.com/user-attachments/assets/a822f63c-8910-4e11-9fdf-d450c466397c">
</p>
<p>
Open Microsoft Remote Desktop on your computer and click the + to add PC. Paste the IP address into PC name and click add. Select continue and then for the Privacy Settings screen, select no to all. 
</p>
<br />

<p>
<img width="600" alt="08" src="https://github.com/user-attachments/assets/808c76dd-5850-4047-8850-4acb862c36cf">
</p>
<p>
Double click on the PC screen you have just added and enter in the user id and password you created earlier.
</p>
<br />

<p>
<img width="567" alt="07" src="https://github.com/user-attachments/assets/a822f63c-8910-4e11-9fdf-d450c466397c">
</p>
<p>
Open a seperate browser and for ease of use, copy past this url into a new tab ----> https://docs.google.com/document/d/12QH7yrsaiUfYNOgZK7KgTSZQSJ-HYTSVcGFildWMRig/edit#bookmark=id.cajb4ktub1km
We will use this to easily open other applications from within the browser.
</p>
<br />

<p>
<img width="1431" alt="09 Control panel" src="https://github.com/user-attachments/assets/07f5a723-261f-4a42-b6b7-ee25334caa73">
</p>
<p>
Next we will Install and Enable IIS with Windows CGI. Right click the start menu and search for Run. Type in control (for the control panel). 
</p>
<br />

<p>
<img width="1440" alt="10" src="https://github.com/user-attachments/assets/b8e35d19-c11b-40d5-a872-c17a0c445083">
</p>
<p>
Click Program> and under Programs and Features click ---> Turn Windows feature on or off> Find Internet Information Service and check the box> Click the + next to Internet Information Service to show more options> Click the + next to World Wide Web services> Click the + next to Application Development features> Find CGI and check the box. 
</p>
<br />

<p>
<img width="1440" alt="11" src="https://github.com/user-attachments/assets/210d45e6-2a40-41d4-9ce7-90f8be394df1">
</p>
<p>
Collapse Application Development> Find Common HTTP Features> Select all the boxes next to each option> Click OK. After loading the screen should say Windows completed the rewuested changes > Click Close.
</p>
<br />

<p>
<img width="1440" alt="12 check point" src="https://github.com/user-attachments/assets/bb4b61c3-a4ae-4152-af76-31126da41209">
</p>
<p>
Test to be sure IIS is working by typing into a web browser ---> 127.0.0.1 
You should see a screen like the image above if IIS has been correctly downloaded.
</p>
<br />

<p>
<img width="1440" alt="13" src="https://github.com/user-attachments/assets/8066d560-1725-4294-a28e-643eb3e0b887">
</p>
<p>
Open the browser saved with the URL from earlier. This has our installation files on it. Click PHPManagerForIIS_V1.5.0.msi and download. Click Download Anyway when popup appears. Click Next> I Agree and then Next>
</p>
<br />

<p>
<img width="1440" alt="PHP manager" src="https://github.com/user-attachments/assets/df05a9a8-a06a-415a-83be-3828f681c013">
</p>
<p>
Should get this screen when complete. Exit. Go back to the browser with our installation files on it. Click and download rewrite_amd64_en-US.msi
Install.
</p>
<br />

<p>
<img width="1440" alt="14 Start" src="https://github.com/user-attachments/assets/d64c1d87-8dc4-4115-b175-10fda9a86e85">
</p>
<p>
Next we will create the directory C:\PHP. Open the Start search bar and search Downloads. Type C: in the bar that says This PC to search for Windows (C:)
</p>
<br />

<p>
<img width="1440" alt="15" src="https://github.com/user-attachments/assets/179c7096-fcfb-43f4-ac08-57609ee1d098">
</p>
<p>
  <img width="1440" alt="16" src="https://github.com/user-attachments/assets/38e7f4d6-90f1-45ee-9efc-e240788e95f9">
</p>
<p> Next we will download PHP. Go back to the installations files from the browser we have saved. This time go directly to the installation list of files and open it. Download php-7.3.8-nts-Win32-VC15-x86.zip.
</p> 
<br />

<p>
<img width="1440" alt="PHP extract all" src="https://github.com/user-attachments/assets/09944bbe-078e-4153-9bd5-d72cc191ce64">
</p>
<p>
Find it in downloads and Right click on it for more options. Click Extract all.
</p>
<br />

<p>
<img width="1406" alt="17" src="https://github.com/user-attachments/assets/f2d0c437-9735-46e8-bab6-f66f04e9bb7b">
</p>
<p>
Where it says Files will be extracted to this folder, Type C:\PHP into that bar. We want the files to go into the folder we just created.
</p>
<br />

<p>
<img width="1440" alt="18" src="https://github.com/user-attachments/assets/01d4637f-f454-4f37-8078-69c0a75631a4">
</p>
<p>
Next, continue downloading from the installation list of files. Select VC_redist.x86.exe and download. Install. Next install MySQL 5.5.62 from the installation list. Click Typical install and Install. Click Standard configuration> Next> Next again> Create your login credentials (DO NOT FORGET YOUR USERNAME AND PASSWORD)> Next> Execute
</p>
<br />

<p>
<img width="497" alt="19" src="https://github.com/user-attachments/assets/41ef6859-f9a6-45dd-b206-e60e537a0e00">
</p>
<p>
Next we will open IIS as an Admin. Search IIS from Start menu. Right click on ISS and select Run as Administrator.
</p>
<br />

<p>
<img width="1440" alt="20" src="https://github.com/user-attachments/assets/4e3ca0e4-e351-4e2e-8c40-096cbad18b1e">
</p>
<p> 
<img width="870" alt="21" src="https://github.com/user-attachments/assets/3575a360-f2a1-4d3a-b1e5-aebc6ff95e22">
</p>
<p>
Next we will Register PHP from within IIS. Select PHP manager> Click register new PHP version> Search in the PHP folder for php-cgi and select it> 
</p>
<br />

<p>
<img width="1440" alt="23" src="https://github.com/user-attachments/assets/7f1284fb-d2c6-4c0c-bfda-b19f58291acf">
</p>
<p>
Next lets download osTicket from the installation files list.
</p>
<br />

<p>
<img width="1440" alt="24" src="https://github.com/user-attachments/assets/d91c5fb4-7e45-4195-a050-9dbceeeb555d">
</p>
<p>
Next we will open IIS as an Admin, 
</p>
<br />

<p>
<img
</p>
<p>
Next we will open IIS as an Admin, 
</p>
<br />
