# no-access
## Description
> Mary hid a little surprise for everyone in the SpookyCTF Discord. Can you find it?

## Solve
Based on the title and description, I figured there was a hidden Discord channel.

I found a Discord plugin manager called [Vencord](https://vencord.dev/) and got the plugin `ShowHiddenChannels`, then navigated back to the discord server where I found a channel called `#super-secret`
in the category "TKLDQ3T3AFLF" with the description "ZDAzU19kSVNjMFJkXzRMbDBXX3RIaVo/fQ=="

The description was base64 for `d03S_dISc0Rd_4Ll0W_tHiZ?}`, but since categories must be all caps, that part was distorted a bit. I knew it had to start with `NICC{`, so I found that that was `TklDQ3s=`, 
so I just had to fix the capitalization of `T3AFLF`. After messing around with it a bit, I found `TklDQ3t3aFlfZDAzU19kSVNjMFJkXzRMbDBXX3RIaVo/fQ==`

which decodes to

`NICC{whY_d03S_dISc0Rd_4Ll0W_tHiZ?}`
