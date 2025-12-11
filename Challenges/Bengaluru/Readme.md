Bengaluru

Description : I found this sample coming through our audio equipment in the lab. When I tried to play it on our state-of-the-art equipment, it crashed. Can you analyze the sample and extract the containment code?

Category : Misc

File : [not.wav](https://github.com/user-attachments/files/24091609/not.wav)


After getting the file , use WSL to check what file format it actually is 



<img width="1058" height="64" alt="image" src="https://github.com/user-attachments/assets/b900500a-b6e6-4873-b6ad-40c6d4376447" />



This tells you it's a zip file , rename the extension and unzip the file to uncover a .synestesia file . Using the same command as above you can see that the true format is .flac.
After you use the correct extension you are able to open and play the file



<img width="1256" height="180" alt="image" src="https://github.com/user-attachments/assets/781bd9b2-dba5-408c-98ea-ba0eb15cbaaa" />



When you open the audio in Audacity, you can see that the left and right sound waves are not the same 



<img width="1896" height="303" alt="image" src="https://github.com/user-attachments/assets/851020bc-fe1d-461f-bc75-8589fa39b8aa" />



This suggests the two channels might be carrying separate data streams rather than normal stereo audio. When the audio is plugged into a XXY oscilloscope, it will show the flag.
You can use this web-based XXY oscilloscope 
https://dood.al/oscilloscope/



<img width="1412" height="975" alt="image" src="https://github.com/user-attachments/assets/0e5d3bba-589d-4adb-b4b4-bb420c6f3e0d" />
