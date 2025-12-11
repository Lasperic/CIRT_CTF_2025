Poznan


Description : Plankton implanted this micro-kernel into one of our machines, and it's causing havoc. I've isolated the box and bagged the sample. I'm attaching it to this secure message. Please find the containment code and send it over.

Category : Reverse Engineering

File : kernel.zip

This is a packed micro-kernel. You can unzip it into a directory and look through content.



<img width="672" height="266" alt="image" src="https://github.com/user-attachments/assets/a664f9e5-6a45-4f14-b5dc-1aa214003812" />


in the sbin folder you can find a ctf-kmod binary.
Plugging it into Binary Ninja we can find two suspicious data sections

<img width="1190" height="84" alt="image" src="https://github.com/user-attachments/assets/bfcb2292-02df-42f7-bdf5-1d80884aaba5" />


checking where they are used 

<img width="635" height="467" alt="image" src="https://github.com/user-attachments/assets/2c899d57-4b53-4b95-a8ac-efbcbf6632e4" />

we can see its a XOR function bit by bit.

Removing the padding and putting it into Cyberchef we get the flag


<img width="1129" height="303" alt="image" src="https://github.com/user-attachments/assets/27c246e3-4864-4af4-ae50-34ba531f6d85" />

