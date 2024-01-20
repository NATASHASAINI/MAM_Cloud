<b>INTRODUCTION:</b></br>
Apple has allowed the use of the Automated Device Enrollment (ADE) for automatic enrollment into Meraki Systems Manager, which can be used to speed up the process into a no-touch experience for mass enrollment of devices. In this mini project we will be wiping the ios device enrolled in ADE remotely will be redeploying it to another user

<b>1.	Check the device is enrolled in DEP and is available in ADE:</b></br>
If the device has been enrolled via ADE, the configuration may prevent management profile removal. To ensure all management is removed on an iOS/iPadOS device:
•	Navigate to Systems Manager > ADE
•	Select the device(s) using the Serial number


<b>2.	Create the credentials of new user under Device owner:</b></br>
Under Systems manager > Configure > Owners, you can associate device owners with their managed devices. An owner entry contains the full name, email address, and username of the end user. On the page, you will also see how many devices are associated with each owner. Owners are organization-wide and will be seen on all System Manager networks within an organization. 

 

<b>3.Search using the Device serial number in ADE: </b></br>
To Remotely wipe the device and clear passcode and activation lock of the device. Kindly note erase command has been successfully sent for the device with Serial number Once you login to Meraki and are on the company’s device list, you’ll need to do the following: Navigate to Systems Manager > DEP.
Search for the S/N here:
 

Then click on the name of the device to open it and then scroll down to the MDM Commands section:
 

Click on Erase Device
 

Leave the 3 boxes unselected and then click Erase. This will send the command to the device and the next time it checks into Meraki, the iPhone will start to automatically erase itself.. In case the end user is prompted for the Activation Lock screen. Please enter Activation Lock bypass code as mentioned below. The end user needs to enter the Bypass code in the password field and leave the Apple ID username field blank (As shown below):
       Bypass code for iPhone: NX1QGE3XLHH78XW5T05IUNPFC0
 
Once reset, the device will  prompt for remote management and new user can login using the credentials.
Once the device gets wiped, below are the login credentials of new user” test user” for remote management screen:

Username: testuser@abc.com
Password: abc123
Here the email and password are all lowercase as these fields are case-sensitive.

<b>Conclusion:</b></br>
