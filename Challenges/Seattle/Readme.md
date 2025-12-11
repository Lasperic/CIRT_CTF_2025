Seattle

Description : 
The beacon here claims the data was exfiltrated using PowerShell. I see some PowerShell commands, and lots of decoys. Can you check the memory dump I shared earlier to see whether you can recover the data? 
***use vmworking2G.zip memory dump from Manila challenge***"

Category : Memory Analysis

File : 

In the description it mentions powershell commands. So lets check using volatility.


<img width="1234" height="67" alt="image" src="https://github.com/user-attachments/assets/697679ab-4fec-43c1-9670-ecf2ec21aa0a" />

Lets check the variables for the first process 

<img width="1905" height="824" alt="image" src="https://github.com/user-attachments/assets/bce63ca6-b0e6-40f2-b054-6ab85c8f062e" />

We can see the FLAG3_XOR_KEY set to 55. 

Let's dump the VAD fr this process 

<img width="1521" height="879" alt="image" src="https://github.com/user-attachments/assets/ecfcbef8-de69-40a1-8d78-68b2c0568a18" />


You can see the MZ header on the file pid.6216.vad.0x24cbc300000-0x24cbc300fff.dmp.

We put it in CyberChef and apply the FLAG3_XOR_KEY to get the flag


<img width="1539" height="370" alt="image" src="https://github.com/user-attachments/assets/d7b9197a-c1c3-4c91-8715-c6e0a53a6a46" />


