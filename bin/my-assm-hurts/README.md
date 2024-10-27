# my-assm-hurts

## Description
> As Mary was attempting to time travel, she slipped on a patch of ice and landed on her butt. While getting up from the ice, she found a cool-looking USB flash drive containing a file with some system code. Can you help Mary decrypt what information the file has?

## Attachment 
### [freezingprogram.txt](./freezingprogram.txt)

## Solve
After looking through the assembly program, I saw that there were several interesting one-character strings being used, such as "{" and many letters.

I realized that these put together were the flag. Here's a one-liner to print it.

```sh
grep -o \".\" freezingprogram.txt | grep -o [^\"] | tr -d '\n' && echo
```

`NICC{hEy_th1s-is_Co0L}`
