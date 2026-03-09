# SOAP

*Category:* Web

---

# Description
> The web project was rushed and no security assessment was done. Can you read the /etc/passwd file?

---

# Attachment


---
# Solution

I noticed that the packet contains xml data.

![image.png](Images/soap1.png)

I modified the xml by adding an xxe payload.

![image.png](Images/soap2.png)
