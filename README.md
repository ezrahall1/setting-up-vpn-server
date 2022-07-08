# Setting Up VPN Server

<h2>Description</h2>
This project is about how to create a free VPN server in AWS cloud. This is a cost effective way to save money and provide much needed security when browsing on the internet, it gives you a secure way to connect to your virtual private cloud in AWS using private ip addresses.
<br />


<h2>Services Used</h2>

- <b>EC2</b> 
- <b>Powershell</b>
- <b>OpenVPN Access Server</b> 

<h2>Environments Used </h2>

- <b>AWS</b>
- <b>Windows Powershell</b> 

<h2>Program walk-through:</h2>
<H3>Step 1 - Select AMI image</H3>

Once I have logged into the AWS account I clicked on services>EC2>launch instance>AWS Marketplace>search for OpenVPN. Click select on the first link (OpenVPN Access Server)

<img src="https://i.imgur.com/rFqvIMC.png" height="80%" width="80%" alt="Image 1"/>

<br />
<img src="https://i.imgur.com/IdkyHHF.png" height="80%" width="80%" alt="Image 2"/>
<br />
<img src="https://i.imgur.com/1zVe9of.png" height="80%" width="80%" alt="Image 3"/>

<H3>Step 2 – Connecting to the EC2 instance </H3>
I wil now need to connect to the EC2 instance.
<img src="https://i.imgur.com/GcP8Yyh.png" height="80%" width="80%" alt="Image 4"/>
<br />
<br />
<img src="https://i.imgur.com/fPOxscO.png" height="80%" width="80%" alt="Image 5"/>
<br />
<br />
<img src="https://i.imgur.com/pLEGo1T.png" height="80%" width="80%" alt="Image 6"/>

<img src="https://i.imgur.com/BF3BVwZ.png" height="80%" width="80%" alt="Image 7"/>

<img src="https://i.imgur.com/uXYOowQ.png" height="80%" width="80%" alt="Image 8"/>

<img src="https://i.imgur.com/6k2EDmO.png" height="80%" width="80%" alt="Image 9"/>

<img src="https://i.imgur.com/AP5tEFp.png" height="80%" width="80%" alt="Image 10"/>

<img src="https://i.imgur.com/ljgwFgf.png" height="80%" width="80%" alt="Image 11"/>

<H3>Step 3 – Accessing OpenVPN via public ip address</H3>
Once you I successfully changed the password for admin and client user I would need to go back to the AWS console in the EC2 section, with the instance currently available copy the ipv4 public ip address, open a new browser tab enter in https://34.239.248.197:943/admin (943 is the port number and the admin part is to access the admin page). 

<img src="https://i.imgur.com/MnSL2OK.png" height="80%" width="80%" alt="Image 12"/>

<img src="https://i.imgur.com/xguCZ1H.png" height="80%" width="80%" alt="Image 13"/>

<img src="https://i.imgur.com/SSDNi94.png" height="80%" width="80%" alt="Image 14"/>

<img src="https://i.imgur.com/VxHXhRW.png" height="80%" width="80%" alt="Image 15"/>

<H3>Step 4 - Configuring internet traffic</H3>
Once I have logged in I needed to make sure that the internet traffic was routed through the VPN. To enable this option I had to go to configuration>VPN settings>scroll down to the routing section and where it says “Should client Internet traffic be routed through the VPN?” click yes. Then click save settings at the bottom of the page.

<img src="https://i.imgur.com/kFEwNEk.png" height="80%" width="80%" alt="Image 16"/>

<img src="https://i.imgur.com/KN7pMlm.png" height="80%" width="80%" alt="Image 17"/>

<H3>Step 5 - Login as the end user</H3>
In order to connect a client to OpenVPN, in the same web browser enter in https://34.239.248.197:943 which should bring up the user login page.

<img src="https://i.imgur.com/J3748mS.png" height="80%" width="80%" alt="Image 18"/>


<H3>Step 6 - Downloading OpenVPN application</H3>
From here you will be able to download which application you would like to connect to.
<img src="https://i.imgur.com/Uclrkny.png" height="80%" width="80%" alt="Image 19"/>

Click on Windows icon to start the download: You might be present with a Windows protected your PC on screen message, just click more info, then click run anyway.

<img src="https://i.imgur.com/8IrSqvV.png" height="80%" width="80%" alt="Image 20"/>

<img src="https://i.imgur.com/UAhgOsm.png" height="80%" width="80%" alt="Image 21"/>

From here you would need to click next and accept the default requirements. Once the OpenVPN Connect has been installed an onboarding tour windows will appear on screen, click on the x button, and accept the terms. Slide the button across to connect and use OpenVPN Connect.

<img src="https://i.imgur.com/6PkqSME.png" height="80%" width="80%" alt="Image 22"/>
You would need to enter your credentials from earlier to successfully connect.

<img src="https://i.imgur.com/vh0OJCI.png" height="80%" width="80%" alt="Image 23"/>

If you see this screen it means you have successfully connected to OpenVPN Connect.

<img src="https://i.imgur.com/xZRHvEs.png" height="80%" width="80%" alt="Image 24"/>

You can check what your new ip address is by going to www.google.com and typing what is my ip address.

<img src="https://i.imgur.com/rIiQ9vD.png" height="80%" width="80%" alt="Image 25"/>

</p>

<!--
 ```diff
- text in red
+ text in green
! text in orange
# text in gray
@@ text in purple (and bold)@@
```
--!>
