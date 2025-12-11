Pesaro

Description : I see there were exfiltration attempts on this beacon. I'm attaching the network capture. Please identify any exfiltration attempts and send me the containment code.

Category : Forensics

File : dns_exfil.pcap

Opening the file in wireshark we see a lot of requests to fil.trg domain. Use Tshark to print them all out


<img width="1457" height="186" alt="image" src="https://github.com/user-attachments/assets/051472fa-9f41-457a-9672-20614b8b875f" />



Checking the note.ex.fil.trg we can see a little hint. The alphabet.ex.fil.trg contains another hint of A-Z2-7 (which is base32)

<img width="1494" height="257" alt="image" src="https://github.com/user-attachments/assets/89cccc4c-2c8f-49f6-b3c4-5b95adbc840a" />



<img width="774" height="591" alt="image" src="https://github.com/user-attachments/assets/2ad96852-6ec6-45d0-be74-b5b58760e352" />

So the flag could be in the baseX format. Concat the fil.trg requests from 0-3. Put it in CyberChef and add Uppercase (base32 is case sensitive). And you get the flag
<img width="1547" height="293" alt="image" src="https://github.com/user-attachments/assets/9882c9fd-3b7f-42cc-8463-c32217fc7f89" />
