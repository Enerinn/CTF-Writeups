# More Cookies

*Category:* Web

---

# Description
> I forgot Cookies can Be modified Client-side, so now I decided to encrypt them!

---

# Attachment


---
# Solution

After some investigating, I noticed that the description capitalize "Cookies, Be, and Client-side" which becomes CBC, a symmetric block cipher algorithm. 

I noticed that this cookie was encrypted twice in base64 and after decrypting, the length of the data is 96 bytes which strongly indicates that that is CBC encryption since it is always a multiple of 16.

Since it is a CBC encryption, it is vulnerable to bit flipping.

I found an python script that performs the bit flipping attack.

```python
import requests
from base64 import b64decode, b64encode
from tqdm import tqdm

# we need to decode from base64 twice because the cookie was encoded twice.
def bit_flip(pos, bit, data):
    raw = b64decode(b64decode(data).decode())  # Decode twice to get raw bytes

    list1 = bytearray(raw) # Convert to mutable byte array
    list1[pos] = list1[pos] ^ bit  # XOR the target byte with the bitmask
    raw = bytes(list1)  # Convert back to bytes
    return b64encode(b64encode(raw)).decode()  # Re-encode twice to send in the request
# Put your cookie here
cookie = "WS9RbEwwTkF6WUdlYmE1ZDFzaklxdjRwekdIMnBnYm5iQUpGU3o1eW5sb1hueXFLMnE1MTlZa0xndmVTWGZrVWlQVlFwMCtJQ09LZWlUWmpPSEFGQVMzcVdjc211cFBxc1JuQ3NsMVF5QW1qUStpS09WSGxnRDk5NEx0YjBLOWs="

# Try different byte positions and bit flips
for position_idx in tqdm(range(10), desc="Bruteforcing Position"):
    # The 96 really should be 128 to test every bit, but 96 worked for me.
    for bit_idx in tqdm(range(96), desc="Bruteforcing Bit"):
        auth_cookie = bit_flip(position_idx, bit_idx, cookie) # Generate modified cookie
        cookies = {'auth_name': auth_cookie} # Set it in the request
        r = requests.get('http://wily-courier.picoctf.net:55441/', cookies=cookies)  # Send request
        if "picoCTF{" in r.text: # If the flag is present in the page
            # Extract the flag between the <code> tags
            print("Flag: " + r.text.split("<code>")[1].split("</code>")[0])
            break
```
