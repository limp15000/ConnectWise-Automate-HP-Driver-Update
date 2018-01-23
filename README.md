# ConnectWise-Automate-HP-Driver-Update

The goal of these scripts is to automate the download and update of HP drivers. At the moment tests have been done on workstations running Windows 8.1 and Windows 10 and soon 7.
I've created five scripts at the moment.

1. Install HP Softpaq Download Manager
Some important information. At the time of this script the lastest HPSDM is version 4.3.19.0.
The script will download directly from HP so when the version will change the MD5 checksum will need to be updated in the script.

2. HP SDM settings
This allow you to define the settings that you want applied to HP SDM. You can in example avoid download HP protect tools and so on.
Open HP SDM on a computer. Go to tools and configuration options. Now select the operating systems you have and the drivers and tools you want to update. Save the settings. 
Now copy the C:\ProgramData\HP\HP SoftPaq Download Manager\Default.sdm and place it on your Automate server in Transfer\Apps\hpsdm\default.txt and rename it to default.txt.

3. HP Softpaq Driver Download (Batch)
This script starts by setting the last run date in the EDF's. Then run a batch script which define the TEMP and TMP variables to c:\Windows\temp\hp
HP SDM when running in SYSTEM will fail to download the drivers if those variables aren't set. 
Once Download is complete the files are transferred automatically to C:\ProgramData\HP\HP SoftPaq Download Manager\SSMInstall

4. HP SSM Driver Install
This will run SSM locally using the setups downloaded by SDM.

5. HP Softpaq Driver (REPORT)
this will run SDM in report mode. It will then update the computer EDFs with the status of the drivers. Will also get the latest BIOS SP number

Thank you to @Darrenwhite99 @steveit and @gavsto for their help troubleshooting/testing all of this.
Usage

Download the latest release from here.
Import XML Scripts.
Twice; if you're still having problems reload the system cache and try again

As per the attached license, THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED.
