# Java Code Analysis!?!

*Category:* Web

---

# Description
> BookShelf Pico, my premium online book-reading service. I believe that my website is super secure. I challenge you to prove me wrong by reading the 'Flag' book!

---

# Attachment


---
# Solution

I cracked the JWT token using hashcat to find out the secret signing key is “1234” but you can also find it in the source code.

![jca1.png](Images/jca1.png)

![jca2.png](Images/jca2.png)

Here we change to role to “Admin” and the userID to “2” (I had set userID to “0” since I thought that the admin account was created before the user but it didn’t work).

![jca3.png](Images/jca3.png)

The server checks if the user is “Free” or “Admin” based on the “token-payload” so I changed the role to “Admin”

![jca4.png](Images/jca4.png)

Now when I view the “Flag” book, it shows me the content.

![jca5.png](Images/jca5.png)