# Sleuthkit Apprentice

*Category:* Forensics

---

# Description
> Download this disk image and find the flag. Note: if you are using the webshell, download and extract the disk image into /tmp not your home directory.
---

# Attachment

[disk.flag.img.gz](./disk.flag.img.gz)

---
# Solution

I unzip the file using `gzip -d disk.flag.img.gz` and then extracted the partitions using binwalk. There were three partitions in the disk. I ran `fls -r [partition]` on each of them and found a flag file in Linux_partition.2.

![](./Images/sla1.png)

I extracted this file using `icat Linux_partition.2 2371 > flag.txt` to get the flag.