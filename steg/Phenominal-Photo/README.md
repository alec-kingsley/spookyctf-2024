# Phenominal-Photo
## Description
> Simon was spotted dwelling under the clock-tower yet again, this time taking pictures. He seems to have captured a strange object in the far far distance going left, right, up, and down seemingly lost or out of control. There is a strange aura radiating from the photo, pulsations even, like an SOS. Can you figure out this strange phenomenon??

## Attachment
### [boo.jpg](./boo.jpg)

## Solve
Running
```sh
steghide extract -sf boo.jpg
```
on the photo yields the file `Ship#1.zip`, which includes `Map.txt` and `gps.zip`. `gps.zip` has one file, `myrequest.txt`, which is password-protected.

`Map.txt` contains the following:
```
⋔⏃⌿: ⌰⟒⎎⏁, ⎍⌿, ⎅⍜⍙⋏, ⌰⟒⎎⏁, ⎅⍜⍙⋏, ⍀⟟☌⊑⏁, ⍀⟟☌⊑⏁, ⎅⍜⍙⋏, ⌰⟒⎎⏁, ⎍⌿, ⌰⟒⎎⏁, ⍀⟟☌⊑⏁, ⎍⌿

⍀⟒⋔⟟⋏⎅⟒⍀ ⏁⊑⏃⏁ ⍜⎍⍀ ☌⌿⌇ ⟟⌇ ⏃ ⌰⟟⏁⏁⌰⟒ ⎎⎍⋏☍⊬, ⟟⏁ ⍜⋏⌰⊬ ⏁⏃☍⟒⌇ ⏁⊑⟒ ⎎⟟⍀⌇⏁ ⌰⟒⏁⏁⟒⍀ ⍜⎎ ⟒⏃☊⊑ ⎅⟟⍀⟒☊⏁⟟⍜⋏ ⍙⟒ ⍙⏃⋏⏁ ⏁⍜ ☌⍜ (⌇⏁⎍⌿⟟⎅ ⋔⟒⋔⍜⍀⊬ ⋔⏃⋏⏃☌⟒⋔⟒⋏⏁)
```

The description mentioned an object going left, right, up, and down, and the first line contains words which align perfectly with these words. This implied to me that it was likely a substitution cipher. Additionally, 2023's `I Don't Speak Zorglax` challenge had the same format.
I guessed that the first word was MAP based on the file name, and here's what I decoded:

```
MAP: LEFT, UP, DOWN, LEFT, DOWN, RIGHT, RIGHT, DOWN, LEFT, UP, LEFT, RIGHT, UP

REMINDER THAT OUR GPS IS A LITTLE FUNKY, IT ONLY TAKES THE FIRST LETTER OF EACH DIRECTION WE WANT TO GO (STUPID MEMORY MANAGEMENT)
```

This gives key to `myrequest.txt` in `gps.zip`: `LUDLDRRDLULRU`

Inside `myrequest.txt` is the following:
```
⋏⟟☊☊{⊑⟒⌰⌿_⋔⟒_⎎⟟⋏⎅_⏁⊑⟒_⌿⌰⏃⋏⟒⏁_⏚0⍜}
```

which decodes to
`NICC{HELP_ME_FIND_THE_PLANET_B0O}`

All but the letter "B" were previously attested, but this was an easy guess both from the original file and that the only missing letters were B, J, Q, V, X, and Z.

