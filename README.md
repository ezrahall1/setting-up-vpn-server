# Setting Up VPN Server

<h2>Description</h2>
Project consists of a simple static website created in AWS. The project provides a step by step guide on how to build the static website and what the end result would look like.
<br />


<h2>Services Used</h2>

- <b>EC2</b> 
- <b>Powershell</b>
- <b>OpenVPN Access Server/b> 

<h2>Environments Used </h2>

- <b>AWS</b>

<h2>Program walk-through:</h2>
<H3>Step 1 - Creating S3 bucket</H3>

Once you have log into the AWS account you would need to click on services>S3>click on create bucket. Make sure the bucket name is unique or you would not be able to create the bucket successfully. 
<img src="https://i.imgur.com/O3PUwO6.png" height="80%" width="80%" alt="Image 1"/>

Scroll down and untick block all public access. This is a safety feature of S3, but because you are intentionally creating a S3 bucket to be used as a static website, you need to untick this box. Unticking this box means that you will be able to grant public access. It does not mean that public access is granted automatically.
<br />
<br />
<img src="https://i.imgur.com/YLFvbiO.png" height="80%" width="80%" alt="Image 2"/>
<br />
<br />
Tick the acknowledge box to show that you understand the changes you are making. <br/>
<img src="https://i.imgur.com/vn34t2z.png" height="80%" width="80%" alt="Image 3"/>
<br />
<br />
Leave everything else as default scroll to the bottom and click create bucket. <br/>
<img src="https://i.imgur.com/OlsCav4.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
<H3>Step 2 – Enable static website hosting </H3>
Click on the name of your bucket, then click on properties scroll down to the bottom where it says static website hosting and click on edit. Click on enable and make sure host a static website is selected.
<img src="https://i.imgur.com/D92cAzu.png" height="80%" width="80%" alt="Image 4"/>
<br />
<br />
In the index document section make sure you have added index.html and error.html in the correct text area, click save changes.
<img src="https://i.imgur.com/agU4L6a.png" height="80%" width="80%" alt="Image 6"/>
<br />
<br />
Scroll down to static website hosting section and make a note of your bucket URL.
<img src="https://i.imgur.com/bCb30OR.png" height="80%" width="80%" alt="Image 7"/>

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
