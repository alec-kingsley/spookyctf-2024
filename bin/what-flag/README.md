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
