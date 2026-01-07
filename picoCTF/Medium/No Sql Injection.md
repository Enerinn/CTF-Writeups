# No Sql Injection

There’s a login page, and I assume we are going to use no SQL injection to login.

![Screenshot 2025-02-03 at 6.44.41 PM.png](Images/Screenshot_2025-02-03_at_6.44.41_PM.png)

I used `{ "$ne": null }` on email and password field and was able to get in.

In the code, it shows that the flag is returned in something like a cookie when the user logs in.

![Screenshot 2025-02-03 at 6.45.07 PM.png](Images/Screenshot_2025-02-03_at_6.45.07_PM.png)

In the storage tab of inspect element, I found the token.

![Screenshot 2025-02-03 at 6.45.20 PM.png](Images/Screenshot_2025-02-03_at_6.45.20_PM.png)

Using base64 decryption, I got the flag.

![Screenshot 2025-02-03 at 6.45.31 PM.png](Images/Screenshot_2025-02-03_at_6.45.31_PM.png)