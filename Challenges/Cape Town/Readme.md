Cape Town

Description : Site alarm still chirping. Found a janky arcade tablet in the break room, a bootleg  2048 clone. Tiles feel normal, but the score counter twitches at oddly specific moments, like its winking at me. Im staying on it. Whatevers hidden here ties back to the containment code.

Category : Reverse Engineering

File : 1024.exe

Opening the file in Binary Ninja we can see that the binary is packed. We can unpack it so it's easier to analyze. We will use WSL and command upx to unpack the binary.

<img width="1191" height="218" alt="image" src="https://github.com/user-attachments/assets/1685f869-ea97-49a9-bb92-9d87f6546008" />


After unpacking we can start analyzing. We start with strings:

<img width="771" height="66" alt="image" src="https://github.com/user-attachments/assets/5c9b025b-5c7c-4b92-8b05-663c3ff57578" />

This text would suggest that there is a built-in AI solver that can be executed by pressing ].

<img width="855" height="195" alt="image" src="https://github.com/user-attachments/assets/88febee6-20f0-4754-8bb9-568a0bb21fd1" />

This is the second interesting part of the binary. We can start the binary with a parameter. After some trial and error you can find out that the set-target-score is just a power of 2.

You can start the executable from the command prompt with 
1024.exe --set-target-score=10

Target score being 2^10=1024

Then just hit the AI solve button and watch the show


<img width="682" height="585" alt="image" src="https://github.com/user-attachments/assets/612820df-7a1a-475d-9d96-98ea31b18749" />
