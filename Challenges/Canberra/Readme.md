Canberra

Description : There appears to be a disputed charge with one of our vendors. The finance department says the CEO called them. I've pulled the network logs for that period. Can you analyze them?

Category : Forensics

File : asterisk.pcap

Open the pcap file in WireShark for initial investigation. From the protocol, you can see it's a voip call


<img width="1356" height="374" alt="image" src="https://github.com/user-attachments/assets/b55388f0-309e-4883-8715-7bdfe3a50734" />


In wireshark navigate into Telephony > VOIP calls


<img width="558" height="175" alt="image" src="https://github.com/user-attachments/assets/b2a7b213-a083-4250-92a4-854db54cf8f8" />



After that you can see and hear the whole spoofed call and extract the flag

<img width="1534" height="730" alt="image" src="https://github.com/user-attachments/assets/f3e895e6-be45-4efd-a47c-fea0135b2778" />



