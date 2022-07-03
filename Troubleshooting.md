# Intune-Autopilot TPM <br/>

If testing on a VM on a hyperV <br/>
Run the wizard and select** Generation v2** <br/>
This will get you the ability to use **Bitlocker** and Secure **Boot Options**
![image](https://user-images.githubusercontent.com/44326428/134090119-0c6ca7f0-67d2-45f9-8b2c-698117596b48.png)
![image](https://user-images.githubusercontent.com/44326428/134090243-e5362486-df26-486e-90f3-0e42baf9c3e9.png)
Make sure you are using 2 Processors if you are doing a VM, Windows 11 Demands it <br/>
![image](https://user-images.githubusercontent.com/44326428/177059219-4fa56da1-7ce8-4fd7-8a7a-62ca40556954.png)
make sure the boot order is correct and not boot from PXE <br/>
![image](https://user-images.githubusercontent.com/44326428/134090308-26dfc10f-8d9c-4ecc-9f37-a23201cd6d88.png)



Note: <br/>
- I have only found that works if only assisned to the profile and nothing else, then type the credentials    <br/>
- OOBE, does not work (if it did work, On-Screen Keyboard on host will help you do the Windows key 5 times)   <br/>

Tips If testing it from a VM:
# Windows Hello Might not work, first time but after after a while when restarting...
# If trying to initiate Autopilot with the 5 windows Key... then this will always fail.
# To succeed, Upload the hash, assign it, then enroll as normal as a Registration

# Getting to know where the ESP error source is coming from: <br/>
depending on the Step here, it will give you a better idea of where is failing: <br/>
Example below: <br/>
![image](https://user-images.githubusercontent.com/44326428/177058980-207373a9-92d8-46bc-b03f-b82904904ced.png)

# Getting Logs: <br/>
# Get-AutopilotDiagnostics Quick Overview
Press "F10" to get to the Prompt. <br/>
if fails.<br/>
Press the "Windows" key and look for CMD, and Right Click and Open it Under Admin.<br/>
``` Javascript
Powershell
Set-ExecutionPolicy Bypass
Install-Script Get-AutopilotDiagnostics -force
Get-AutopilotDiagnostics -online
```
Then Login with your UPN. <br/>
then it will give you a quick GUI of the status: <br/>
![image](https://user-images.githubusercontent.com/44326428/177059370-f8ee2fbc-1986-4cec-8345-cd111d23a07d.png)


# MDMDiagnosticsTool Extracting Logs
``` Javascript
md C:\Temp
MDMDiagnosticsTool.exe -area Autopilot -cab C:\Temp\Autopilot.cab
```
Extract this File with an Uncompresser such 7zip, to get all files.<br/>
![image](https://user-images.githubusercontent.com/44326428/177059637-624ff438-e2b7-4279-8a38-7c81ea1ff563.png)
This is a Reference for these files:  <br/>
https://oofhours.com/2019/10/08/troubleshooting-windows-autopilot-a-reference/

# AutopilotESPStatus Extracting Logs
``` JavaScript
Set-ExecutionPolicy bypass
Install-Script -Name Get-AutopilotESPStatus -RequiredVersion 4.1 -f
```
![image](https://user-images.githubusercontent.com/44326428/177059703-6123c0f6-37c2-4f0a-8b51-a1ddcb1a4ca7.png)






