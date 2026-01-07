# Most Cookies

![mc-1.png](Images/mc-1.png)

![mc-2.png](Images/mc-2.png)

I’m thinking that you need to change the cookie session value.

In the server.py file, it says that the secret key for the cookie will be one of these so we can try to bruteforce the cookie.

![mc-3.png](Images/mc-3.png)

I used flask-unsign to perform the bruteforce attack.

![mc-4.png](Images/mc-4.png)

![mc-5.png](Images/mc-5.png)

I put the modified cookie into Burpsuite and sent it to the server.

![mc-6.png](Images/mc-6.png)