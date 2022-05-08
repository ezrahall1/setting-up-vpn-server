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

The next step is to upload some objects to the bucket you have created. In order to do that you would need to scroll to the top of the page and click on objects, then click on upload.

Click on upload, click on add files and add the two html files (index.html and error.html). 
<img src="https://i.imgur.com/AQICKJI.png" height="80%" width="80%" alt="Image 8"/>
<H3>Step 3 – Grant permissions</H3>
The next step is you need to grant permissions to be able to read these objects. You would need to create a bucket policy. Click on the permission tab scroll down to where is says bucket policy click on edit. When entering the policy details remember to update the arn so it is not the same as mine or else it would not work, click on save changes.
<img src="https://i.imgur.com/mlZjKBx.png" height="80%" width="80%" alt="Image 9"/>
Based on the policy you have created you will now see a red banner stating, “publicly accessible”, which means the bucket can be access by anyone.

<img src="https://i.imgur.com/PGbBV1i.png" height="80%" width="80%" alt="Image 10"/>

This shows that I successfully created a static website in AWS
<img src="https://i.imgur.com/c8KFtkW.png" height="80%" width="80%" alt="Image 10"/>

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
