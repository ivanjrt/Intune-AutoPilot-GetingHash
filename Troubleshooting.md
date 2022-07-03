# Intune-Autopilot TPM <br/>

If testing on a VM on a hyperV <br/>
Run the wizard and select** Generation v2** <br/>
This will get you the ability to use **Bitlocker** and Secure **Boot Options**
![image](https://user-images.githubusercontent.com/44326428/134090119-0c6ca7f0-67d2-45f9-8b2c-698117596b48.png)
![image](https://user-images.githubusercontent.com/44326428/134090243-e5362486-df26-486e-90f3-0e42baf9c3e9.png)
Also make sure the boot order is correct and not boot from PXE <br/>
![image](https://user-images.githubusercontent.com/44326428/134090308-26dfc10f-8d9c-4ecc-9f37-a23201cd6d88.png)


Note: <br/>
- I have only found that works if only assisned to the profile and nothing else, then type the credentials    <br/>
- OOBE, does not work (if it did work, On-Screen Keyboard on host will help you do the Windows key 5 times)   <br/>





Tips If testing it from a VM:
# Windows Hello Might not work, first time but after after a while when restarting...
# If trying to initiate Autopilot with the 5 windows Key... then this will always fail.
# To succeed, Upload the hash, assign it, then enroll as normal as a Registration



