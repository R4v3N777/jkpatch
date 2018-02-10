# Jailbreak Kernel Patches

### Features

- Jailbreak
- Sandbox escape
- Debug settings
- Enable UART
- Disable system update messages
- Delete system updates
- Fake self support
- Fake pkg support
- RPC server
- RPC client in C#

**I still need to push the RPC client and RPC documentation.**

### General Notes
**Only for 4.05 Jailbroken PlayStation 4 consoles!**

The main jkpatch payload utilizes idc's port of CTurt's payload sdk. You can download it [here](https://github.com/idc/ps4-payload-sdk). Change the [Makefile](payload/Makefile) to have `LIBPS4` point to the ps4-payload-sdk directory on your machine. I could have it referenced from the home directory but meh...
```makefile
# change this to point to your ps4-payload-sdk directory
LIBPS4	:=	/home/John/PS4-PAYLOAD-SDK/libPS4
```

If you decide to edit the `resolve` code in the kernel payload, make sure you do not mess with...
```c
void resolve(uint64_t kernbase);
```
... as it is called from `crt0.s`. And changing this will produce errors.

### Coming Soon
- Bug fixes for RPC server/client
- Clean up C# library (librpc)
- Add ability to call routines in processes (up to 6 parameters, i.e. registers only)
- RPC documentation, write a pdf explaining how to get started
- Better kernel patches, that wont crash system (i.e. fix debug patches)
- Hook fatal_trap and print more debug information to UART
- Add kernel UART text out hook and send text over RPC (maybe)
- Add kernel read/write/allocate/free/execute commands
- General code clean up and refactoring


Thank you to flatz, idc, zecoxao, hitodama, osdev.org!

Twitter: [@cloverleafswag3](https://twitter.com/cloverleafswag3) psxhax: [g991](https://www.psxhax.com/members/g991.473299/)

**golden <3**