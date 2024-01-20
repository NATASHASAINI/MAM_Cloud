<b>INTRODUCTION:</b></br>
Any tool that better organizes and automates work is a boon to resource-strapped companies, which is why MDM has become an essential part of IT management. MDM provides management of both company-supplied and employee-owned mobile devices and ensures that they are up-to-date, secure, and do not put the company’s network at risk. MDM is a core component of unified endpoint management (UEM), which covers a broader set of endpoints such as printers, ruggedized devices, Internet of Things (IoT) sensors and wearables, as well as mobile application and content management. In addition to saving time, MDM and UEM result in more consistent user experiences and higher productivity for hybrid workers, while avoiding the security risks associated with unprotected, unmonitored devices.Apple has allowed the use of the Automated Device Enrollment (ADE) for automatic enrollment into Meraki Systems Manager, which can be used to speed up the process into a no-touch experience for mass enrollment of devices. In this mini project we will be wiping the ios device enrolled in ADE remotely will be redeploying it to another user

<b>1.	Check the device is enrolled in DEP and is available in ADE:</b></br>
If the device has been enrolled via ADE, the configuration may prevent management profile removal. To ensure all management is removed on an iOS/iPadOS device:
•	Navigate to Systems Manager > ADE
•	Select the device(s) using the Serial number

<b>2.	Create the credentials of new user under Device owner:</b></br>
Under Systems manager > Configure > Owners, you can associate device owners with their managed devices. An owner entry contains the full name, email address, and username of the end user. On the page, you will also see how many devices are associated with each owner. Owners are organization-wide and will be seen on all System Manager networks within an organization. 

 ![image](https://github.com/NATASHASAINI/MAM_Cloud/assets/156629309/5b96c809-ca29-4dd5-89be-a3d3e7d8d296)


<b>3.Search using the Device serial number in ADE: </b></br>
To Remotely wipe the device and clear passcode and activation lock of the device. Kindly note erase command has been successfully sent for the device with Serial number Once you login to Meraki and are on the company’s device list, you’ll need to do the following: Navigate to Systems Manager > DEP.
Search for the S/N here:

![image](https://github.com/NATASHASAINI/MAM_Cloud/assets/156629309/5befe298-27f7-4f99-a11d-28719af4cba9)


Then click on the name of the device to open it and then scroll down to the MDM Commands section:

 ![image](https://github.com/NATASHASAINI/MAM_Cloud/assets/156629309/fb45fda0-6973-4321-ac25-207cec95eeaa)


Click on Erase Device
 ![image](https://github.com/NATASHASAINI/MAM_Cloud/assets/156629309/896c8bf4-a477-4f3b-80d5-7cee513c2cfe)


Leave the 3 boxes unselected and then click Erase. This will send the command to the device and the next time it checks into Meraki, the iPhone will start to automatically erase itself.. In case the end user is prompted for the Activation Lock screen. Please enter Activation Lock bypass code as mentioned below. The end user needs to enter the Bypass code in the password field and leave the Apple ID username field blank (As shown below):
       Bypass code for iPhone: NX1QGE3XLHH78XW5T05IUNPFC0
       
 ![image](https://github.com/NATASHASAINI/MAM_Cloud/assets/156629309/07c5a2e6-1e49-42a6-8be3-b1c90f92ad82)
  
 
Once reset, the device will  prompt for remote management and new user can login using the credentials.
Once the device gets wiped, below are the login credentials of new user” test user” for remote management screen:

<b>Username: testuser@ abc.com</b></br>
<b>Password: abc123</b></br>

Here the email and password are all lowercase as these fields are case-sensitive.

<b>Conclusion:</b></br>
Cisco Meraki has always been driven by a mission to simplify the lives of IT professionals with intuitive, easy-to-use tools and products. It helps in providing seamless and secure remote management
In this mini project we identified the ios device in ADE using serial number and then remotely removed activation lock and removed the owner of the device After remotely wiping the ios device enrolled in ADE remotely it can be redeployed to another user for which we can assign credentials under device owner.Cisco Meraki automatically import configurations from security applications and deploy changes to thousands of devices within a few clicks
