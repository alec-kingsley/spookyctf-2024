# Well-Met
## Description
> For the past three years these characters have appeared in JerseyCTF, SpringForwardCTF, and SpookyCTF - but their lore was kept secret. Can you find the secret in their history?

## Solve

The challenge site had a "lore" tab (if it is still up when you are reading this, it's at https://spookyctf.ctfd.io/lore). The lore tab had pages for many characters involved in the lore of the CTF.

Enbedded throughout various places in the html were pieces of the flag. (Similar to 2023's `Ghosts in the Code` challenge). To find these, I simply searched for underscores, since every part
of the flag (except for the `NICC{` beginning) had these.

In the end, the flag was 

```
NICC{StOr       # the redacted text under Anna's description
IeS_DoNt_M      # the alt text for NAH's image
aKe_ThE_cTf_T   # hidden as the same color as the background for Golden Falcon's description
oO_cTfY_rIgHt?} # a comment in Dr. Tom's description
```

`NICC{StOrIeS_DoNt_MaKe_ThE_cTf_ToO_cTfY_rIgHt?}`
