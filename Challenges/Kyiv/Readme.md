Kyiv

Description : Every time I try to open the file, more files appear. It's like a never-ending nesting doll. Can you help me out? I'm sending the artifact over.

Category : Forensics

File : corrupted.file

Using command file in WSL we can identify the corrupted file as a pcap file. Its quite large so we can try to extract all objects to see what is inside.


<img width="1092" height="36" alt="image" src="https://github.com/user-attachments/assets/c8023d4b-7341-48cf-815b-545621cd41be" />


<img width="667" height="202" alt="image" src="https://github.com/user-attachments/assets/4ea8449b-b851-4845-8d03-9e1e926d0083" />


The ajax php file seems too large. If we open it in HxD we can see a zip file header and a bunch of metadata (including file name RDP.zip). Remove the metadata and rename the extension to .zip.

<img width="634" height="167" alt="image" src="https://github.com/user-attachments/assets/448cc978-1d20-4430-977e-9580eb5d490d" />


We can see that the archive contains Cache00072.bin, but it is password protected.

Using 7zip we can determine what encryption method it uses


<img width="883" height="685" alt="image" src="https://github.com/user-attachments/assets/14bc8b23-7340-4664-a4e6-5401dd406d6a" />


Luckily that is a breakable encryption . We can use bkcrack https://github.com/kimci86/bkcrack .

This requires us to know a 12 byte contiguous plaintext inside the archive. 

RDP Cache files have a fixed 8 byte header (52 44 50 38 62 6D 70 00) followed by 4 bytes that denote the windows version (in our case 06 00 00 00)

Lets put this in HxD into a file

<img width="626" height="55" alt="image" src="https://github.com/user-attachments/assets/7639c2fd-77f3-49fe-90d1-b8bb6a66a77b" />

Then we can use bkcrack to extract the files:
<img width="1368" height="368" alt="image" src="https://github.com/user-attachments/assets/faefd318-4f50-4526-b13f-759b0a656afa" />


Now we have the bin file extracted. We can use bmc tools 

https://github.com/ANSSI-FR/bmc-tools
<img width="1420" height="144" alt="image" src="https://github.com/user-attachments/assets/d089a092-9799-4382-91bc-9d2cc6ad4f7a" />

Open the final collage to find the flag

<img width="889" height="474" alt="image" src="https://github.com/user-attachments/assets/0ab67c4b-d303-4f8d-b102-f49afccfef63" />





