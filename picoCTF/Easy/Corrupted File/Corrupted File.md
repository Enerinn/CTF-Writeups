# Corrupted File

*Category:* Forensics

---

# Description
> This file seems broken... or is it? Maybe a couple of bytes could make all the difference. Can you figure out how to bring it back to life? Download the file here.

---

# Attachment

[file](./file)

---
# Solution

Using command `head file`, I noticed that the file header looks similar to a JPEG header.
![](./images/corruptedFile2.png)

Using hexedit, I matched the header to the standard JPEG header and got the flag.

![](./images/corruptedFile3.png)
