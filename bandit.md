## Bandit - Saswath A

As of in the website of bandit game, they said to connect to their IP server through SSH (Secure Shell). So I searched some about SSH in Google to know about it and how it works. After knowing some things, I tried to enter the bandit server with the user given and entered successfully.

### Level 0

So after entering the level 0, I read the `readme` text file through the `cat` command and got the password for the first level. Then exited from the server and logged in again to the server as bandit1. Entered the server successfully.

**Password**: `ZjLjTmM6FvvyRnrb2rfNWOZOTa6ip5If`

### Level 1

For entering level 2, I needed a password from a file in level 1 named `-`. Since `-` is treated as an argument or command, it can't be opened directly. I Googled how to handle it and found that using `./-` deactivates the special meaning and treats it as a file name.

**Password**: `263JGJPfgU6LtdEvgfWU1XP5yac29mFx`

### Level 2

In level 2, the password is in a file name with spaces. Terminals interpret space as separator, so using `"file name with spaces"` or escaping it helps. I just typed `cat` and used tab completion to get:
`cat "spaces in this filename"`

**Password**: `MNk8KNH3Usiio41PRUEoDFPqfxLPlSmx`

### Level 3

The password file was in the `inhere` directory. But the file was hidden, so `ls` didn’t show it. I learned to use `ls -a` to list hidden files. Then I used `cat` to read the password.

**Password**: `2WmrDFRmJIq3IPxneAaMGhap0pFhF3NJ`

### Level 4

Inside the `inhere` directory were multiple files. The hint said it’s a human-readable file. I found out that only ASCII and Unicode files are human-readable. I used the `file` command to filter and found the ASCII text file.

**Password**: `4oQYVPkxZOOEOO5pTW81FB8j8lxXGUQw`

### Level 5

This level had additional criteria: human-readable, 1033 bytes, non-executable. I used:
`du -a -b | grep 1033`  
Then I opened the found file and got the password.

**Password**: `HWasnPhtq9AVKe0dmk45nxy20cvUa6EG`

### Level 6

No filename is given, but we’re told how to identify it. I used `find` with multiple flags: `-type`, `-user`, `-group`, and `-size`. Found the file, read it, and got the password.

**Password**: `morbNTDkSW6jIlUc0ymOdMaLnOlFVAaj`

### Level 7

The password was next to the word `millionth` in `data.txt`. I used:
`grep millionth data.txt`  
It printed the whole line with the password.

**Password**: `dfwvzFQi4mU0wfNbFOe9RoWskMLg7eEc`

### Level 8

The file had many repeated lines. Only one line (the password) was unique. I used:
`sort data.txt | uniq -u`

**Password**: `4CKMh1JI91bUIZZPXDqGanal4xvAg0JM`

### Level 9

The password was hidden in human-readable strings and preceded by `=` characters. I used:
`strings data.txt | grep =`

**Password**: `FGUW5ilLVJrxX9kMYMmlN4MgbpfMiqey`

### Level 10

The data was Base64 encoded. I used:
`base64 -d data.txt`

**Password**: `dtR173fZKb0RRsDFSGsg2RWnpNVj3qRr`

### Level 11

The content had characters rotated by 13. I used:
`cat data.txt | tr 'A-Za-z' 'N-ZA-Mn-za-m'`

**Password**: `7x16WNeHIi5YkIhWsfFIqoognUTyj9Q4`

### Level 12

The file was a hexdump of a repeatedly compressed file. I:
1. Reverted the hexdump
2. Identified formats using `file`
3. Decompressed with `gzip`, `bzip2`, `tar`, etc.
This level took the most time.

**Password**: `FO5dwFsc0cbaIiH0h8J2eUks2vdTDwAn`

### Level 13

I had to use `scp` to get the private key. Changed file permissions with `chmod 700`. Then logged in using the key.

**Password**: `MU4VWeTyJk8ROof1qqmcBPaLh7lDCPvS`

### Level 14

Used `telnet` to connect to a port and input the previous password to receive the next one.

**Password**: `8xCjnmgoKbGLhHFAZlGE5Tmu4M2tKJQo`

### Level 15

Used:
`openssl s_client -connect localhost:30001`  
Then pasted the password to get the next one.

**Password**: `kSkvUpMQ7lBYyCM4GBPvCvT1BfWRy0Dx`

### Level 16

Scanned ports with:
`nmap -sV localhost -p 31000-32000`  
Filtered out echo services. Found port 31790. Used:
`openssl s_client -connect localhost:31790 -quiet`

**Password**: `EReVavePLFHtFlFsjn3hyzMlvSuSAcRD`

### Level 17

Used:
`diff passwords.old passwords.new`  
Got the changed line.

**Password**: `x2gLTTjFwMOhQ8oWNbMN362QKxfRqGlO`

### Level 18

Login instantly logs you out. Used:
`ssh bandit18@bandit.labs.overthewire.org -p 2220 cat readme`

**Password**: `cGWpMaKXVwDUNgPAVJbWYuGHVn9zl3j8`

### Level 19

Used:
`./bandit20-do cat /etc/bandit_pass/bandit20`

**Password**: `0qXahG8ZjOVMN9Ghs7iOWsCfZyXOUbYO`

### Level 20

Used:
`echo -n 'password' | nc -l -p 1234`  
Then the program sent it.

**Password**: `EeoULMCra2q0dSkYj561DX7s1CpBuOBt`

### Level 21

Checked `/etc/cron.d/cronjob_bandit22`, found a script writing the password to `/tmp`. Used `cat` on that file.

**Password**: `tRae0UfB9v0UzbCdn9cY0gQnds9GF58Q`

### Level 22

**Password**: `0Zf11ioIjMVN551jX3CmStKLYqjk54Ga`

### Level 23

**Password**: `gb8KRRCsshuZXI0tUuR6ypOFjiZbf3G8`

### Level 24

**Password**: `iCi86ttT4KSNe1armKiwbQNmB3YJP3q4`

### Level 26

**Password**: `s0773xxkk0MXfdqOfPRVr9L3jJBUOgCZ`
