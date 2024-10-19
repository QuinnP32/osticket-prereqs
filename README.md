<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket Installation Tutorial: A Step-by-Step Guide</h1>
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
</ul>

<h2>Getting Started: Create a Virtual Machine on Azure</h2>

**Before you begin the osTicket installation, you'll need a virtual machine (VM) running Windows Server on Microsoft Azure.** Here's a step-by-step guide to create your VM:

### 1. Log in to Azure Portal ([https://azure.microsoft.com/en-us](https://azure.microsoft.com/en-us))

**Screenshot:** Capture the Azure portal login screen.

### 2. Create a Resource Group

* Click on "Create a resource" in the top left corner.
* Search for "Resource group" and select it.
* Click "Create" to start the creation process.

**Screenshot:** Capture the resource group creation blade.

### 3. Configure Resource Group Details

* Give your resource group a meaningful name (e.g., "my-vm-resource-group").
* Choose a location for your resource group (consider latency to your users).
* Click "Create" to create the resource group.

**Screenshot:** Capture the resource group creation blade with the configured details.

### 4. Create a Virtual Machine

* Click on "Create a resource" again.
* Search for "Virtual machine" and select it.
* Click "Create" to start the creation process.

**Screenshot:** Capture the virtual machine creation blade.

### 5. Configure Virtual Machine Settings

These are the core settings for your VM:

* **Subscription:** Choose your Azure subscription.
* **Resource group:** Select the resource group you just created.
* **Name:** Give your VM a name (e.g., "osticket-vm").
* **Region:** Choose a region based on your needs.
* **Image:** Select a Windows Server image (e.g., "Windows Server 2022 Datacenter").
* **Size:** Choose a size with enough resources for osTicket (e.g., "Standard_DS1_v2").
<h2>Connecting and Configuring Virtual Machine for osTicket</h2>
<h3>1. Connect via Remote Desktop</h3>
<img src="https://i.imgur.com/remote_desktop.png" alt="Connecting to the virtual machine via Remote Desktop">
<p>Connect to your newly created virtual machine using Remote Desktop. This will allow you to interact with the server's desktop.</p>

<h3>2. Install IIS and PHP</h3>
<img src="https://i.imgur.com/iis_installation.png" alt="Installing IIS and PHP">
<p>Use the Server Manager to install IIS and PHP. Configure IIS to handle PHP requests.</p>

<h3>3. Download and Install osTicket</h3>
<p>Download the latest osTicket package from the official website. Follow the installation instructions provided in the documentation.</p>

<h3>4. Configure Database</h3>
<img src="https://i.imgur.com/database_configuration.png" alt="Configuring the osTicket database">
<p>Create a new database in MySQL and configure osTicket to use it. Enter the database credentials during the installation process.</p>
