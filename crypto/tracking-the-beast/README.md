# tracking-the-beast
## Description
> NICC is hot on the trail of bigfoot! He has been following a path equivalent to the curve y^2 = x^3 + 73x + 42 mod 251. Each point along this curve represents one of Bigfoot's hideouts. NICC dicovered in his cave located at (26,38), many references to Green Lantern comics. A large depiction of Green Lantern with 13 rings on his fingers was drawn on the cave wall. I think this is the cover to an old issue of Green Lantern, could something about the issue point to how many more hideouts Bigfoot will travel through before stopping again?

> Flag Format: NICC{(##,##)}

## Solve
I did not understand this challenge, but I recognized the format from last year's `Strange Monuments` challenge. The only differences were that the numbers were changed around and this challenge gave the points passed, but not the final point. `Strange Monuments` gave the final point and asked how many points were passed.

After looking up Green Lantern with 13 rings on his fingers, I found that that was issue #49, so I figured that Bigfoot traveled through 49 hideouts. 

After reading some write-ups for `Strange Monuments` and messing around with their solve scripts, I got a nice one-liner in [SageMath](https://www.sagemath.org/):
```
EllipticCurve(GF(251),[73,42])(26,38)*49
```
which output this: `(72 : 17 : 1)`

`NICC{(72, 17)}`
