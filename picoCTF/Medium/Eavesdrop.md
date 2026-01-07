# Eavesdrop

![eav-1.png](Images/eav-1.png)

In Wireshark, there was this tcp stream.

![eav-2.png](Images/eav-2.png)

I filtered by `tcp.port == 9002` and followed the TCP stream. I changed “Show data as” to “Raw” and saved the file.

![eav-3.png](Images/eav-3.png)

Then I used the command that we saw earlier `openssl des3 -d -salt -in file.des3 -out file.txt -k supersecretpassword123` to get the flag.