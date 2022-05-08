# Setting Up VPN Server

<h2>Description</h2>
Project consists of a simple static website created in AWS. The project provides a step by step guide on how to build the static website and what the end result would look like.
<br />


<h2>Services Used</h2>

- <b>EC2</b> 
- <b>Powershell</b>
- <b>OpenVPN Access Server</b> 

<h2>Environments Used </h2>

- <b>AWS</b>

<h2>Program walk-through:</h2>
<H3>Step 1 - Select AMI image</H3>

Once you have log into the AWS account you would need to click on services>EC2>launch instance>AWS Marketplace>search for OpenVPN. Click select on the first link (OpenVPN Access Server) make sure it says free tier eligible.
<img src="https://i.imgur.com/rFqvIMC.png" height="80%" width="80%" alt="Image 1"/>

Click select which will bring you to the “Choose an Instance Type” page. Make sure you select t2.micro (free tier eligible) click review and launch.
<br />
<br />
<img src="https://i.imgur.com/IdkyHHF.png" height="80%" width="80%" alt="Image 2"/>
<br />
<br />
Select create a new key pair and click download key pair as you will need this in the next section. Click launch instance you would likely have to wait to a few minutes for the instances to become available. <br/>
<img src="https://i.imgur.com/1zVe9of.png" height="80%" width="80%" alt="Image 3"/>
<br />
<br />
<H3>Step 2 – Connecting to the EC2 instance </H3>
You will now need to connect to the EC2 instance, right click and select connect.
<img src="https://i.imgur.com/GcP8Yyh.png" height="80%" width="80%" alt="Image 4"/>
<br />
<br />
From there you would need to click on the SSH client tab.
<img src="https://i.imgur.com/fPOxscO.png" height="80%" width="80%" alt="Image 5"/>
<br />
<br />
Copy the example command and enter it in your terminal windows making sure to specify the location of where your key pair is: ssh -i "vpnserverkey.pem" root@ec2-34-239-248-197.compute-1.amazonaws.com
<img src="https://i.imgur.com/pLEGo1T.png" height="80%" width="80%" alt="Image 6"/>

<img src="https://i.imgur.com/BF3BVwZ.png" height="80%" width="80%" alt="Image 7"/>

Click yes to accept the certificate. There will be a few prompts that you need to click enter in order to install OpenVPN.

<img src="https://i.imgur.com/uXYOowQ.png" height="80%" width="80%" alt="Image 8"/>


Once completed you would need to login with OpenVPN rather than the root user. You would need to enter in this command to login to OpenVPN: ssh -i Downloads/vpnserverkey.pem openvpnas@ec2-34-239-248-197.compute-1.amazonaws.com

<img src="https://i.imgur.com/6k2EDmO.png" height="80%" width="80%" alt="Image 9"/>

Now you are logged in you would need to change the password for admin and client user.


<img src="https://i.imgur.com/AP5tEFp.png" height="80%" width="80%" alt="Image 10"/>

You need to enter sudo passwd OpenVPN.

<img src="https://i.imgur.com/ljgwFgf.png" height="80%" width="80%" alt="Image 11"/>

<H3>Step 3 – Accessing OpenVPN via public ip address</H3>
Once you have successfully changed the password for admin and client user you would need to go back to the AWS console in the EC2 section, with the instance currently available copy the ipv4 public ip address, open a new browser tab enter in https://34.239.248.197:943/admin (943 is the port number and the admin part is to access the admin page). You will be present with an error which says “your connection is not private” just click advance then click proceed.

<img src="https://i.imgur.com/MnSL2OK.png" height="80%" width="80%" alt="Image 12"/>

<img src="https://i.imgur.com/xguCZ1H.png" height="80%" width="80%" alt="Image 13"/>

<img src="https://i.imgur.com/SSDNi94.png" height="80%" width="80%" alt="Image 14"/>

Enter in OpenVPN as the username and enter the password you created earlier.
<img src="https://i.imgur.com/VxHXhRW.png" height="80%" width="80%" alt="Image 15"/>

<H3>Step 4 - Configuring internet traffic</H3>
Once you have logged in you need to make sure that the internet traffic is routed through the VPN. To enable this option you need to go to configuration>VPN settings>scroll down to the routing section and where it says “Should client Internet traffic be routed through the VPN?” click yes. Then click save settings at the bottom of the page.

<img src="https://i.imgur.com/kFEwNEk.png" height="80%" width="80%" alt="Image 16"/>

At the top of the page you would need to click “update running server” just to make sure the changes take place.
<img src="https://i.imgur.com/KN7pMlm.png" height="80%" width="80%" alt="Image 17"/>

<H3>Step 5 - Login as the end user</H3>
In order to connect a client to OpenVPN, in the same web browser enter in https://34.239.248.197:943 which should bring up the user login page (you can use the same credentials that you used for the admin login).
<img src="https://i.imgur.com/J3748mS.png" height="80%" width="80%" alt="Image 18"/>


<H3>Step 6 - Downloading OpenVPN application</H3>
From here you will be able to download which application you would like to connect to.
<img src="https://i.imgur.com/Uclrkny.png" height="80%" width="80%" alt="Image 19"/>

Click on Windows icon to start the download: You might be present with a Windows protected your PC on screen message, just click more info, then click run anyway.

<img src="https://i.imgur.com/8IrSqvV.png" height="80%" width="80%" alt="Image 20"/>

<img src="https://i.imgur.com/UAhgOsm.png" height="80%" width="80%" alt="Image 21"/>



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
