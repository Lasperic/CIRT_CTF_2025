Mumbai

Description : This Excel file is triggering all sorts of IDS alerts. Please determine why and retrieve the containment code.  

*(This challenge might trigger Microsoft Defender because it uses obfuscation often associated with viruses, but the file itself is free of malware.)

Category : Misc

File : [ACTIONREQUIRED.xlsm](https://github.com/user-attachments/files/24108482/ACTIONREQUIRED.xlsm)


When you open the Macro window (alt + F11) you can see some functions and variables being stored. 
First we write down the b64Trigger that is used in the RevealFlag() function.

<img width="500" height="27" alt="image" src="https://github.com/user-attachments/assets/3fd5a80f-16b7-4bb9-ba20-e62e68a021eb" />


Private Const b64Trigger As String = "Q0lSVCBEZWNyeXB0b3I="


Putting this into CyberChef gives us the "CIRT Decryptor"


<img width="1540" height="234" alt="image" src="https://github.com/user-attachments/assets/7960a74a-b85e-4798-91c3-9cb754d67751" />



The RevealFlag() expects the CIRT Decryptor to be set as AppName in Document properties.



<img width="828" height="359" alt="image" src="https://github.com/user-attachments/assets/ab734d88-e104-497e-88dd-509bc5b7c705" />



Change the AppName to CIRT Decryptor


<img width="1266" height="619" alt="image" src="https://github.com/user-attachments/assets/be03ac9b-c0d3-45e3-8c37-46cf9c903b2b" />


And invoke RevealFlag()


<img width="342" height="85" alt="image" src="https://github.com/user-attachments/assets/240697ff-992d-4496-a2e8-1b4521313f4b" />
