# Requisites:
* Having the target Computer Online
* If a new device a USB Flash Drive will be required
<br/><br/>
# If the Target Computer is not new and on the internet:
Open PowerShell as Admin and run:

``` JavaScript
md c:\HWID
Set-Location c:\HWID
Set-ExecutionPolicy -Scope Process -ExecutionPolicy Unrestricted -Force
Install-Script -Name Get-WindowsAutopilotInfo -Force
$env:Path += ";C:\Program Files\WindowsPowerShell\Scripts"
Get-WindowsAutopilotInfo.ps1 -OutputFile AutopilotHWID.csv

```
You will recieve this output:
![image](https://user-images.githubusercontent.com/44326428/135945724-ef2c6493-fd7f-4f08-8a4d-bbf4e60bdfa6.png)

See -**Uploading Stage** below

<br/><br/>

# If the Target Computer is (New or freshly imaged) and on the internet: <br/>
Insert your USB Drive<br/>
At the **Region** Welcoming screen, press and Hold **shift** + **F10**  (_Sometimes the laptops will require to also press **FN** Key_) <br/>
This will open up the DOS terminal
![image](https://user-images.githubusercontent.com/44326428/135946830-6ab723ca-408a-46b1-8971-02ba4d2fdf5b.png)

Run the below
``` JavaScript
Powershell
md d:\HWID #Assuming that your Flash Drive is now D drive
Set-Location d:\HWID
Set-ExecutionPolicy -Scope Process -ExecutionPolicy Unrestricted -Force
Install-Script -Name Get-WindowsAutopilotInfo -Force
$env:Path += ";C:\Program Files\WindowsPowerShell\Scripts"
Get-WindowsAutopilotInfo.ps1 -OutputFile AutopilotHWID.csv
```

This will give you a similar output as below, But with the **D** Drive
![image](https://user-images.githubusercontent.com/44326428/135945724-ef2c6493-fd7f-4f08-8a4d-bbf4e60bdfa6.png)


AutopilotHWID.csv this is the file that would need to be uploaded to Intune<br/>
See -**Uploading Stage** below
<br/><br/>


# **Uploading Stage** below
click the link below <br/>
https://endpoint.microsoft.com/#blade/Microsoft_Intune_Enrollment/AutoPilotDevicesBlade
And Import the CSV file.  <br/>
![image](https://user-images.githubusercontent.com/44326428/135948003-24d61e79-917d-495c-8cdf-04c3a40d47ec.png)
This takes about 15 mins to upload the file and replicate <br/>
<br/><br/>

# If Target computer is in the process of purchasing <br/>
"Via Vendor" Most Retailers as Dell, HP and other major companies they already have a partnership with Microsoft where you can have them upload the Hash file prior to shipping the laptop. <br/>
To do this you would require to contact your seller at your retailer, ask for the feature to be activated and they will send a link that the Global Admin, would have to approve <br/>

# Once that CSV is been uploaded and comfirmed is replicated as well as the group Assigned with the device.
For a Autopilot Sealed Experienced: <br/>
  Start the Computer without Internet then when you get to the Window OOBE, connect the Computer via Wire, and Press the "Windows" key 5 Times. <br/>
  
Else you would have to have the user so he can login and the enrollment will happen under him   <br/>
