Plovdiv 

Description : I don't know why the alerts are blaring on this site. The only thing out of place here is this awesome nostalgic game. Seriously, give it a try and see if you can beat my high score. If you manage to beat me, you'll get a containment code. Send it to me, and I'll buy you some kavarma.

Category : Reverse Engineering

File : 




You see a prg file which is most commonly atari / c64 . After loading the file in your emulator of choice (VICE is mine), you will see a clone of flappy bird . The target score is 251, the problem is that after scoring 120 points the score value overflows to -255. So how do we fix this?




We can check in Cyberchef that 251 from decimal > from hex would be FB. Since c64 architecture uses little endian we should be looking for 0x00 0xFB.
Use HxD hex editor to find this sequence.

<img width="891" height="699" alt="image" src="https://github.com/user-attachments/assets/a402c2ef-f0eb-457e-9675-43447105f93f" />


If we change this sequence to 00 01 (1 in dec). You will win the game when scoring your first point


<img width="770" height="636" alt="image" src="https://github.com/user-attachments/assets/b9dba10f-50f5-46be-aaeb-e105678a6a11" />
