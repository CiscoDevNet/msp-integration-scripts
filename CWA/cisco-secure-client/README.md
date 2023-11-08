## Using ConnectWise (Automate) RMM scripts to deploy Cisco Secure Client 5.0

### Step 1 - Select and Download Secure Client Components.
 
Umbrella dashboard, under Deployments --> Roaming Computers --> top right: Roaming Client. Then, select your appropriate deployment package in respective to your OS.
 
Download the “OrgInfo.json” file from the Umbrella dashboard, under Deployments --> Roaming Computers --> top right: Roaming Client  Download Module Profile.

Once the Cisco Secure Client zip and the orginfo.json file have been downloaded, it is incumbent of the admin to unzip the Cisco Secure Client zip file and isolate the following required files for the deployment scripts:
1.	cisco-secure-client-win-5.0.04032-core-vpn-predeploy-k9.msi
2.	cisco-secure-client-win-5.0.04032-dart-predeploy-k9.msi
3.	cisco-secure-client-win-5.0.04032-umbrella-predeploy-k9.msi
4.	OrgInfo.json

### Step 2  - Copying files from Step 1 into ConnectWise Server Share 

Copy the files from Step 1 to the CW RMM (Automate) LTShare folder (C:\LTShare) :
•	cisco-secure-client-win-5.0.04032-core-vpn-predeploy-k9.msi
•	cisco-secure-client-win-5.0.04032-dart-predeploy-k9.msi
•	cisco-secure-client-win-5.0.04032-umbrella-predeploy-k9.msi
•	OrgInfo.json

### Step 3  - Changes needed in “CW Install Cisco Secure Client” 

The "CW Install Cisco Secure Client" will create a folder 'CSC' on the CW Agent working directory (c:\windows\ltsvc\CSC) and copy these files there to be used in the msiexe install commands.

 
