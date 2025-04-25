## CTF BIOS - Bt_Root

So here the file which contains flag is `.pcapng`. And opened the file through Wireshark.  
And had no idea what to do. Then I decided to check every file which is somewhat different.  

I got several files like:
- `.png` (some malformed format)
- an `.mp4` file  
- and a `.txt` file  

So I checked every file and at last I checked the `.txt` file which contained some values which was understandable:  
**"all hail king bluetooth"**

I just checked it in Google and got a useful thing called **HARALD BLUETOOTH**.  
Then I entered it in the Python flag translator, in which I got the flag.
