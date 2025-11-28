# Flag Hunters

## Description
Lyrics jump from verses to the refrain kind of like a subroutine call. There's a hidden refrain this program doesn't print by default. Can you get it to print it? There might be something in it for you.

## Solution
In the provided code, there is a code injection vulnerability.

```python      elif re.match(r"CROWD.*", line):
        crowd = input('Crowd: ')
        song_lines[lip] = 'Crowd: ' + crowd
        lip += 1
```

The program uses `input()` to get user input for the crowd lines, which is then directly inserted into the `song_lines` list without any sanitization.

To exploit this, I used the payload `;RETURN 0`, which matches the REGEX of `CROWD.*` which then becomes `Crowd: ;RETURN 0`.

The split function splits the line at the semicolon, and the `RETURN 0` matches

```python
elif re.match(r"RETURN [0-9]+", line):
    lip = int(line.split()[1])
```
which sets `lip` to 0, causing the program to jump back to the beginning of the song and print the hidden refrain.
