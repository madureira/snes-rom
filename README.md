# snes-rom
This is a try to write a simple game to run in some SNES Emulator.


## Dependencies
- [snes9x](http://www.mediafire.com/?io0aok7857twdop)
- [WLA Executables](http://www.mediafire.com/?t0x21wi3htiko19)


## Building
**1.** Extract the WLA Executables;

**2.** Put `wlalink.exe` and `wla683993.exe` in your `C:/Windows/System32` directory;

**3.** Open the Windows Command-line in the project directory and type:
```sh
C:\snes-rom> wla-65816 -vo main.asm main.obj
```
```sh
C:\snes-rom> wlalink -vr main.link main.smc
```
**4.** In your root folder you should now have a `main.smc` file, this is the finished ROM;

**5.** Test `main.smc` in a SNES emulator;

**6.** If you see a green screen, this works!


## Structure
The basic structure of this application is given in the following way:

- `main.asm` The game source code;
- `main.link` This file will help build the ROM;
- `header.inc` The header contains assembler directives for WLA which do things like define the ROM's name, size, vectors, etc;
- `Snes_Init.asm` An initialization routine, it's a piece of code that clears/resets system values and sets the SNES up for use;
