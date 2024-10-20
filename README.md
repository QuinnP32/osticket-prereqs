<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket: Prerequisites and Installation</h1>
<h2>Why osTicket?</h2>
<p>Learn how to set up your own help desk solution using osTicket. This open-source ticketing system is perfect for businesses of all sizes.</p>

<h2>Video Walkthrough</h2>
<iframe width="560" height="315" src="https://www.youtube.com/embed/your_vdeo_id" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>

<h2>Prerequisites</h2>
<ul>
  <li>A Microsoft Azure account</li>
  <li>Windows 10 (or later)</li>
  <li>Basic understanding of virtual machines and IIS</li>
  <li>A MySQL database (can be hosted elsewhere or created on a separate Azure VM)</li>
  <li>PHP installed</li>
  <li><a href="https://drive.google.com/uc?export=download&id=1b3RBkXTLNGXbibeMuAynkfzdBC1NnqaD">osTicket-instalation-Files.zip</a> (Essential Components for osTicket Deployment)</li>
</ul>

<h2>Getting Started: Create a Virtual Machine on Azure</h2>

**Before you begin the osTicket installation, you'll need a virtual machine (VM) running Windows Server on Microsoft Azure.** Here's a step-by-step guide to create your VM:

### 1. Log in to Azure Portal ([https://azure.microsoft.com/en-us](https://azure.microsoft.com/en-us))

![image](https://github.com/user-attachments/assets/c55c75b1-2c5c-47e9-8309-0b016a349227)


### 2. Create a Resource Group

* Click on "Create a resource" in the top left corner.
* Search for "Resource group" and select it.
* Click "Create" to start the creation process.

![image](https://github.com/user-attachments/assets/f2c1d853-68c4-42b1-a57d-ac4b137fc137)



### 3. Configure Resource Group Details

* Give your resource group a meaningful name (e.g., "my-vm-resource-group").
* Choose a location for your resource group (consider latency to your users).
* Click "Create" to create the resource group.

![image](https://github.com/user-attachments/assets/b646a92b-d169-47cf-867e-09ee32867926)


### 4. Create a Virtual Machine

* Click on "Create a resource" again.
* Search for "Virtual machine" and select it.
* Click "Create" to start the creation process.

![image](https://github.com/user-attachments/assets/01f659e1-a18b-4c9c-9055-1e832e848562)

### 5. Configure Virtual Machine Settings

These are the core settings for your VM:

* **Subscription:** Choose your Azure subscription.
* **Resource group:** Select the resource group you just created.
* **Name:** Give your VM a name (e.g., "osticket-vm").
* **Region:** Choose a region based on your needs.
* **Image:** Select a Windows 10 Pro, version 22H2 x64 image.
* **Size:** Choose a size with enough resources for osTicket (e.g., "Standard_DS1_v2").
* **Login:** Choose and write down a username and password.
<h2>Connecting and Configuring Virtual Machine for osTicket</h2>
<h3>1. Connect via Remote Desktop</h3>

![image](https://github.com/user-attachments/assets/bf99b72a-b9d0-4757-97a8-47667f4287ef)

<p>Connect to your newly created virtual machine using Remote Desktop using the public IP which is available to you on the virtual machine tab in Azure.</p>

![image](https://github.com/user-attachments/assets/118fcc01-c58c-4cb3-8349-b170e8c2e016)

<p>Successfully logging in will allow you to interact with the server's desktop.</p>

<h3>2. Install <a href="https://www.iis.net/downloads/community/2018/05/php-manager-150-for-iis-10">IIS</a>, <a href="https://www.iis.net/downloads/community/2018/05/php-manager-150-for-iis-10">PHP</a>, Rewrite Module, and Enable CGI</h3>

![image](https://github.com/user-attachments/assets/cb511e02-66ae-4220-b4a1-61338b395ddb)
**Enable CGI in IIS:**

1. Open the Control Panel.
2. Go to Programs > Uninstall or Change a Program.
3. Click on "Turn Windows features on or off".
4. Expand "**Application Development Features**".
5. Check the box next to "**CGI**" and click "OK".


**Here's a breakdown of installing the additional components:**

1. **Install PHP Manager for IIS:** Double-click the `PHPManagerForIIS_V1.5.0.msi` file and follow the on-screen instructions.
2. **Install Rewrite Module:** Double-click the `rewrite_amd64_en-US.msi` file and follow the on-screen instructions.
3. **Create C:\PHP Directory:** Open a file explorer window and create a new folder named "PHP" at the root of your C drive (C:\PHP).

**Note:** You can create the directory manually or use the command prompt if preferred (e.g., `md C:\PHP`).

4. **Unzip PHP:** Extract the contents of the `php-7.3.8-nts-Win32-VC15-x86.zip` file from "osTicket-Installation-Files" into the newly created "C:\PHP" folder.
5. **Install VC_redist.x86.exe:** Double-click the `VC_redist.x86.exe` file and follow the on-screen instructions.
6. **Install MySQL:** Double-click the `mysql-5.5.62-win32.msi` file and choose "Typical Setup".
7. **Launch MySQL Configuration Wizard:** After installation, launch the MySQL Configuration Wizard and choose "Standard Configuration".
8. **Set MySQL Credentials:** Enter a Username and Password.

**Open IIS and Register PHP:**

1. Open Internet Information Services (IIS) as an administrator.
   ![image](https://github.com/user-attachments/assets/8b112b00-4dee-4fce-ab50-41969004d0c9)

2. Use the PHP Manager to register the PHP executable (C:\PHP\php-cgi.exe).
![image](https://github.com/user-attachments/assets/3b3c7cdb-f288-4bac-98a5-5cd2f3280bb0)

**Reload IIS:**

1. Open IIS again.
2. Stop the server and then start it again to reload the configuration.

By following these steps, you'll have installed IIS, enabled CGI, and prepared your virtual machine for osTicket installation.
<h3>3. Download and Install osTicket</h3>
<p>Download the latest <a href="https://docs.osticket.com/en/latest/Getting%20Started/Installation.html">osTicket</a> update from the official website or use zipfile provided above. Once you download it, you'll be well on your way to setting up your own ticketing system!</p>
