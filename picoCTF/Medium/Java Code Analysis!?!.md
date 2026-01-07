# Java Code Analysis!?!

![Screenshot 2025-02-15 at 7.27.56 PM.png](Images/Screenshot_2025-02-15_at_7.27.56_PM.png)

I cracked the JWT token using hashcat to find out the secret signing key is “1234” but you can also find it in the source code.

![Screenshot 2025-02-15 at 7.28.17 PM.png](Images/Screenshot_2025-02-15_at_7.28.17_PM.png)

![Screenshot 2025-02-15 at 7.29.46 PM.png](Images/Screenshot_2025-02-15_at_7.29.46_PM.png)

Here we change to role to “Admin” and the userID to “2” (I had set userID to “0” since I thought that the admin account was created before the user but it didn’t work).

![Screenshot 2025-02-15 at 7.33.34 PM.png](Images/Screenshot_2025-02-15_at_7.33.34_PM.png)

The server checks if the user is “Free” or “Admin” based on the “token-payload” so I changed the role to “Admin”

![Screenshot 2025-02-15 at 7.33.10 PM.png](Images/Screenshot_2025-02-15_at_7.33.10_PM.png)

Now when I view the “Flag” book, it shows me the content.

![Screenshot 2025-02-15 at 7.33.52 PM.png](Images/Screenshot_2025-02-15_at_7.33.52_PM.png)