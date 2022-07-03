Example this is the **Security group** with a **dynamic Membership** to create the Profile, then assign it to the user. <br/>
![image](https://user-images.githubusercontent.com/44326428/133510520-336b0d0d-1c0f-44ef-891b-9576a13de9d5.png)

to be more descriptivie here's more Rules: <br/>


```
(device.devicePhysicalIDs -any (_ -contains "[ZTDId]"))
```
_The idea here is to have all the Physical IDs Main Group so they get listed, then have another group from there_
```
(device.devicePhysicalIds -any (_ -eq "[OrderID]:179887111881"))
```
```
(device.devicePhysicalIds -any (_ -eq "[PurchaseOrderId]:76222342342"))
```
more examples here: https://docs.microsoft.com/en-us/mem/autopilot/enrollment-autopilot
