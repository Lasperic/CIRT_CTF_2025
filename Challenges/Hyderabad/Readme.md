Hyderabad


Description : I pulled this export from CAM-03.Grainy teal, that cheap NVR look, REC blinking like its proud of itself. It feels staged, more of a calling card than a slip-up. I'm sending you the file as-is. If Plankton hid anything, itll be tucked in the pixels. Extract the containment code and send it back to me."

Category : Steganography

File : <img width="1536" height="1024" alt="security_export" src="https://github.com/user-attachments/assets/19820a42-5b50-4b2e-8edb-7644bd6ee2d6" />

Using binwalk we can see that there is a password protected ZIP file embedded after the image

<img width="1106" height="297" alt="image" src="https://github.com/user-attachments/assets/4205ad4d-452d-49ff-8b40-95000cfca1c1" />


Using exiftool you can see a base64 encoded field "Special Instructions"

<img width="1037" height="534" alt="image" src="https://github.com/user-attachments/assets/99c772ef-b883-47cc-b98f-03742b7ec185" />

The base64 translates to : 
Password for the hidden zip is : ThroughTheMountains!


<img width="1299" height="225" alt="image" src="https://github.com/user-attachments/assets/652ccfae-8004-4218-a7cd-f724c177a742" />


Use binwalk again to extract the zip file and use the password to extract it leading to plaintext flag

<img width="1101" height="388" alt="image" src="https://github.com/user-attachments/assets/de3e7aa9-44ce-433e-ac9c-519c1c018428" />


