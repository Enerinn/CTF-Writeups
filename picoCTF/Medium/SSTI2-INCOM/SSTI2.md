# SSTI2

# Challenge Name

*Category:* Web

---

# Description
> I made a cool website where you can announce whatever you want! I read about input sanitization, so now I remove any kind of characters that could be a problem :) I heard templating is a cool and modular way to build web apps! Check out my website here!

---

# Attachment


---
# Solution

There was a simple web form that took in user input and displayed it back to the user. I tried {{7*7}} and got 49 back, indicating a Server-Side Template Injection (SSTI) vulnerability.

Using the payload `{{ self._TemplateReference__context.cycler.__init__.__globals__.os.popen('ls').read() }}`, I got

![](Images/ssti2-1.png)

which confirmed that there is input sanitization in place.

