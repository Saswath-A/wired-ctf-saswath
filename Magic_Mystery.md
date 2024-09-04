## CTF BIOS - Magic_Mystery

    So basically in this challenge, the given PNG file shows a error while opening it i.e it is not a PNG file. So after googling a lot i came to know that for the first 8 bytes should be filled with specific magic number i.e hex digits which denotes .PNG (89 50 4E 47 0D 0A 1A 0A). Then I checked the head of file through hexdump using the command " xxd chall.png | head " after which it clearly showed that the first 8 bytes are empty. So I manually filled with the hex digit through hex editor. After that I had another error that it has invaild IHDR length. Then I found that the length was also blank.


![alt text](https://i.sstatic.net/hcIIO.png)

    After viewing this image i had a clear idea what i have to do. Then as same i entered the hex digits in the right space and got the flag in Imageviewer.