Buenos Aires

Description : I managed to find an interesting artifact used to encrypt messages within the APT organization. Can you learn anything useful from it?

Category : Reverse Engineering

File : 


Tools : https://github.com/icsharpcode/ILSpy

The encryptor.exe is a .NET executable , and so it's best to decompile it in ILSpy instead of Binary Ninja or Ghidra.

After opening the executable in ILSpy, you can see a string called : encryption_key
<img width="1918" height="1029" alt="image" src="https://github.com/user-attachments/assets/4ca0283b-2bae-4c13-b98a-b29891a8584a" />

If you search for encryption_key usage you will find the following snippet
<img width="802" height="395" alt="image" src="https://github.com/user-attachments/assets/7f210f59-82c6-4d1a-877d-2db2263ace06" />


So we have the encryption key in base64 ran through ROT13 . You can now use CyberChef to put it together
https://gchq.github.io/CyberChef/#recipe=From_Base64('A-Za-z0-9%2B/%3D',true,false)ROT13(true,true,false,13)&input=VUVkVGV5b3FLbFJsTkVOMU1YQmZLbDlSTTJZeGRFRXFLaXA5Cg

<img width="1917" height="737" alt="image" src="https://github.com/user-attachments/assets/23496173-f64e-4a75-9104-f6155e66c931" />


