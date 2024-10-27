# what-flag

## Description
> NICC recieved a mysterious email with an executable file that does nothing. Can you figure out what this executable does?

## Attachment
### [some-random-file](./some-random-file)

## Solve
I loaded `some-random-file` in Ghidra, and sure enough, it did nothing. 
The code for `main` was literally

```asm
PUSH   RBP
MOV    RBP, RSP
MOV    EAX, 0x0
POP    RBP
RET
```

I then noticed that there were several other functions. Each of them loaded some memory on the stack and then returned, and none of them were called anywhere.

Converting this memory to ASCII, I got the following bits:

```
_ThInk}
CC
{
NI
_i
uhH
_fl@g
```

Which pieced together to form

`NICC{uhH_fl@g_i_ThInk}`
