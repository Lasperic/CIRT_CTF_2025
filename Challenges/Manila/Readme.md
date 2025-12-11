Manila

Description : I pulled a full memory dump before shutdown and found a single encrypted payload, flag2.enc, on disk. It appears to be encrypted with some form of AES. Before the shutdown, I saw some PowerShell windows flash and a login portal authentication page. The box is isolated, and RAM should still hold the key, nonce, or DPAPI material.

Category : Memory Analysis

File : 


The description mentions PowerShell. Lets check the processes using Volatility:
<img width="1217" height="67" alt="image" src="https://github.com/user-attachments/assets/c9f6f1c8-962d-4186-9c38-592d33edec8c" />

Let's dump the contents of pid 6424

vol -f vm.core -o out windows.memmap --pid 6424 --dump

Search the dmp file for AES to see if we can get any hit on decryption key
<img width="924" height="165" alt="image" src="https://github.com/user-attachments/assets/0eafcd31-c851-4834-8258-e367726f1053" />

We see Base64 encoded IV and Key strings.

Plug it into our ol' trusty CyberChef to extract the flag

<img width="1539" height="355" alt="image" src="https://github.com/user-attachments/assets/80e3387b-6324-46c2-a93b-57853eefd043" />






