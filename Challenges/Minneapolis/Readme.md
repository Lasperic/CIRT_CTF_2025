Minneapolis

Description : A malformed video was playing on loop in this beacon. My tools can't even open it. Sending it over, let me know if you find any containment code.

Category : Steganography

File : https://github.com/user-attachments/assets/166bbb50-e215-4543-b0d6-087fe50b4bb3


Examining the mp4 file we can see that the frame rate is very low and thus the video is impossibly long.
<img width="299" height="134" alt="image" src="https://github.com/user-attachments/assets/9b38b530-e13c-46dc-8888-aa10f4d46f70" />

We can extract video to raw bitstream

ffmpeg -y -i fuzz.mp4 -c copy -f h264 fuzz.h264

now remux it with a new framerate (24)

ffmpeg -y -r 24 -i fuzz.h264 -c copy fuzz_faster.mp4

It will still be long , but it the beginning you can see the full video.

https://github.com/user-attachments/assets/f2e8e7b4-a964-448e-8723-615ba8cb8c54


To fix this you can extract all the images from the video

ffmpeg -r 1 -i fuzz.mp4 -r 1 output/"$fuzz%03d.png"

Now stitch them together using ffmpeg 

ffmpeg -r 30 -pattern_type glob -i 'output/*.png' -c:v libx264 out.mp4


https://github.com/user-attachments/assets/5423cdb9-3afa-48fe-bb03-f3698949ece0




