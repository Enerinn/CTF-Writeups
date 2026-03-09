# SansAlpha

*Category:* General 

---

# Description
> The Multiverse is within your grasp! Unfortunately, the server that contains the secrets of the multiverse is in a universe where keyboards only have numbers and (most) symbols.

---

# Attachment


---
# Solution

`**` represents any number of characters. In this case, it finds the first file or subdirectory that is at least 3 characters.

`$_` refers to the most recent output!

![sansalpha-2.png](Images/sansalpha-2.png)

`${_:3:2}${_:8:1}` concats the most recent output, in this case “cat”
`${_:x:y}` takes the most recent output, start at x position, and concat y letters

![sansalpha-3.png](Images/sansalpha-3.png)