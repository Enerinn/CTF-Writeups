# JAuth

Once login with test account, server gives us a JWT cookie:

`eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJhdXRoIjoxNzM5NTcxMTkzODIzLCJhZ2VudCI6Ik1vemlsbGEvNS4wIChYMTE7IExpbnV4IGFhcmNoNjQ7IHJ2OjEwOS4wKSBHZWNrby8yMDEwMDEwMSBGaXJlZm94LzExNS4wIiwicm9sZSI6InVzZXIiLCJpYXQiOjE3Mzk1NzExOTR9.Pb-YiMW5Wx9-th_Yd5qft6-P4Nx9x3mnR64Khskvmjc`

This decodes to:

![Screenshot 2025-02-14 at 5.18.06 PM.png](Images/Screenshot_2025-02-14_at_5.18.06_PM.png)

I tried just changing role to admin but it didn’t work so I changed the alg to “none” as well and removed the signature.

`eyJ0eXAiOiJKV1QiLCJhbGciOiJub25lIn0.eyJhdXRoIjoxNzM5NTcxMTkzODIzLCJhZ2VudCI6Ik1vemlsbGEvNS4wIChYMTE7IExpbnV4IGFhcmNoNjQ7IHJ2OjEwOS4wKSBHZWNrby8yMDEwMDEwMSBGaXJlZm94LzExNS4wIiwicm9sZSI6ImFkbWluIiwiaWF0IjoxNzM5NTcxMTk0fQ.` 

![Screenshot 2025-02-14 at 5.20.47 PM.png](Images/Screenshot_2025-02-14_at_5.20.47_PM.png)

I did this in Burpsuite because when I modified the cookie in the web application, it still didn’t work (haven’t figured out why).

![Screenshot 2025-02-14 at 5.22.26 PM.png](Images/Screenshot_2025-02-14_at_5.22.26_PM.png)