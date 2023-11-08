## Using Kaseya VSA Agent Procedures to deploy Cisco Secure Client 5.0

### Step 1 - Select and Download Cisco Secure Client Components.
   
Umbrella dashboard, under Deployments --> Roaming Computers --> top right: Roaming Client. Then, select your appropriate deployment package in respective to your OS.
 
Download the “OrgInfo.json” file from the Umbrella dashboard, under Deployments --> Roaming Computers --> top right: Roaming Client  Download Module Profile.

Once the Cisco Secure Client zip and the orginfo.json file have been downloaded, it is incumbent of the administrator to add the originfo.json file to the zip file to be added the KVSA ‘managedfiles’ share.  At that point all required files will be in the resulting zip file

### Step 2 - Upload the new combined Zip file to the KVSA RMM server

1. Click on the Manage Files button at the top of the module pane: A Pop-Up will appear with a link to two folders: Private Files and Shared Files.
 
2. Click on the Red Upload a File button to browse to and upload the ZIP file from Step 1. From there, you can close the pop-up window and continue on.
 
An alternate method (from the VSA help files) of uploading files is to copy them directly to the managed files directory on the IIS server. This directory is normally located in the C:\Kaseya\WebPages\ManagedFiles directory. In that directory are several sub-directories. Put private files into the directory named for that user. Put shared files into the VSASharedFiles directory. Any files located in this directory will automatically update what is available in the Manage Files Stored on Server user interface at the next user logon.
Step 3 - Add the Secure Client Zip to the RMM script.
The Scripts that use the MSI from the above creation instructions will need to be changed. For the Install Secure Endpoint script file name changes are needed in line 10. 
 


