# DISKO 2

*Category:* Forensics

---

# Description
> Can you find the flag in this disk image? The right one is Linux! One wrong step and its all gone! Download the disk image here.
---

# Attachment

[disko-2.dd.gz](./disko-2.dd.gz)

---
# Solution

I noticed it was a compressed file so i unzipped with `gzip -d disko-2.dd.gz`.
Then I tried to extract the partitions using binwalk.

The extracted folder contians a FAT and Linux partition. In the description of the challenge, it said that the Linux partition is the correct one. I ran `strings Linux_partition.0 | grep pico` and found the flag.
