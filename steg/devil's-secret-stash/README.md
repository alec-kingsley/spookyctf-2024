# devil's-secret-stash
## Description
> In the depths of the Pine Barrens, a cryptic legend whispers of the Jersey Devil guarding a picture. Tales speak of forgotten knowledge sealed within, but only those sharp enough to see the truth can unlock its secrets. The key? The key hiding in plain sight, woven into the eerie folklore itself, waiting for the chosen few to discover and reveal the dark treasures within.

## Attachment
### [devil.jpg](./devil.jpg)

## Solve
This challenge took me a long time. I quickly found after running
```sh
binwalk -e devil.jpg
```
a zip file containing a file called `flag`, but it was password-protected.

The description said `The key? The key hiding in plain sight, woven into the eerie folklore itself`, which led me to believe that the key related to the folklore surrounding the Jersey Devil. After reading
about this creature, I guessed many passwords such as `Leeds Devil` (another name for him) `Mother Leeds` (the mother of the Jersey Devil), etc. From the `hiding in plain sight` clue, I guessed every word in
the description, the title, and the author.

Finally, it turned out the key was the decimal offset of the zip file within the original jpg file. Here's the binwalk output I got:
```
DECIMAL       HEXADECIMAL     DESCRIPTION
--------------------------------------------------------------------------------
0             0x0             JPEG image data, EXIF standard
12            0xC             TIFF image data, big-endian, offset of first image directory: 8
15196         0x3B5C          Copyright string: "Copyright (c) 1998 Hewlett-Packard Company"
250250        0x3D18A         Zip archive data, encrypted compressed size: 55, uncompressed size: 27, name: flag
250447        0x3D24F         End of Zip archive, footer length: 22
```

And the password was `250250`.

`NICC{J3rS3y_D3v1l_Arch1V3}`
