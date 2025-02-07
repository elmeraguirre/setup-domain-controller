# Setting Up a Domain Controller in Azure  

This guide will help you set up a Domain Controller (DC-1) and a Client VM (Client-1) in Microsoft Azure. Follow the steps carefully, and you’ll have everything running smoothly.  

## 1. Create a Resource Group  
1. Log in to the Azure Portal.  
2. Go to Resource Groups and click Create.  
3. Enter a name, pick a region, and click Review + Create.  

## 2. Set Up a Virtual Network and Subnet  
1. Go to Virtual Networks in Azure.  
2. Click Create, give it a name, and choose the same region as your resource group.  
3. Under IP Addressing, create a Subnet with a valid IP range.  

## 3. Create the Domain Controller VM (DC-1)  
1. Go to Virtual Machines and click Create.  
2. Select Windows Server 2022 as the operating system.  
3. Set the VM name to DC-1.  
4. Use these login credentials:  
   - Username: labuser  
   - Password: Cyberlab123!  
5. Attach it to the Virtual Network and Subnet you created earlier.  
6. Click Review + Create and wait for deployment to finish.  

## 4. Set a Static Private IP for DC-1  
1. Once DC-1 is deployed, go to its Networking settings.  
2. Click on the Network Interface, then go to IP Configurations.  
3. Change the Private IP from Dynamic to Static.  

## 5. Disable Windows Firewall on DC-1 (For Testing Only)  
1. Log into DC-1 using Remote Desktop (RDP).  
2. Open PowerShell as Administrator.  
3. Run this command:  
   ```powershell
   Set-NetFirewallProfile -Profile Domain,Public,Private -Enabled False
