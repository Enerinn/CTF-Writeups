# DISKO3

*Category:* Forensics

---

# Description
> Can you find the flag in this disk image? This time, its not as plain as you think it is!
---

# Attachment

[disko-3.dd.gz](./disko-3.dd.gz)

---
# Solution

I'm assuming "plain" in the description implies that the flag is not in plaintext.

I decompress the file using `gzip -d disko-3.dd.gz`. I tried to use binwalk but there were no files extracted.

Usings strings on the file, I tried to find any clue on the flag but I didn't see any useful information.

I used `fls -r disko-3.dd` to recursively list files in the filesystem. I came across a file called "flag.gz".

![](./Images/disko3-1.png)

I extracted the file with `icat disko-3.dd 522628 > flag.gz` and unzipped the file to get the flag.


