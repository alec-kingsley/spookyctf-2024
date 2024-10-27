# whispers-in-morse

## Description
> Mary got a letter from Maya talking about seeing a cryptid sighting but doesn't want other people to know, the only thing attached is this picture? She wonders if there could be a secret message hidden inside.

## Attachments
### [MaryMorse.jpg](./MaryMorse.jpg)

## Solve

Running `strings` on `MaryMorse.jpg` yields `Password: M.A.__.R.Y` at the bottom. This looks familiar; I read the write-ups for the 2023 SpookyCTF challenges, and
one of them, `Down The Wormhole`, provided a password for a jpg which was able to be used at [this site](https://futureboy.us/stegano/decinput.html). Doing so with
this year's challenge yielded the text 

`NICC{tHe_whIspeRz_iN_Th3_aiR}`
