Mexico City

Description : I managed to scrape this corrupted file from the beacon. I'm not quite sure what it is. I'm sending it over; let me know if you manage to find the containment code.

Category : Steganography

File : Artifact_B.zip


The zip file contains the file name=QR_CODE,permissions=777,size=1000x1000,owner=admin.corrupted

Opening it in HxD we can see that it is made entirely out of 00 and FF . From the file name you can assume the size would be 1000x1000.
Replace all 00 with 0 and FF with 1 and use dcode to make it into a picture.
https://www.dcode.fr/binary-image

Once done it will reveal a QR code that contains the plaintext flag 
<img width="1361" height="995" alt="image" src="https://github.com/user-attachments/assets/00e39919-d793-4f28-9276-29832678ae2a" />
