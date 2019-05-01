# Bootloader firmware of Ilo Musi

This is the repository of the bootloader firmware of Ilo Musi.

Currently the source code of firmware remains unreleased. Despite that the bootloader firmware is reasonably bug-free, I'm sure that there're still some less obvious bugs to be fixed. I'll eventually release the bootloader firmware under an FOSS license and make the source code available in this repo.

Currently, the binary (in IntelHex format) is available in the "Releases" tab of this repo. A few game ROMs are also available along with that.

Games developed for the game console would depend on the system library code located inside the bootloader firmware. For this reason, it's required to flash the bootloader before loading any game ROMs. In addition, the bootloader also provide a game selection menu for the user to load the games from microSD card.

# Flashing the Bootloader

## Linux

```
openocd -f /usr/share/openocd/scripts/interface/stlink-v2.cfg -f /usr/share/openocd/scripts/target/stm32f0x.cfg -c init -c "reset init" -c "flash write_image erase \"/path/to/Ilomusi.hex\" " -c init -c "reset run"
```

## 32bit Windows

```
"C:/path/to/openocd_dir/bin/openocd" -f "C:/path/to/openocd_dir/scripts/interface/stlink-v2.cfg" -f "C:/path/to/openocd_dir/scripts/target/stm32f0x.cfg" -c init -c "reset init" -c "flash write_image erase \"/path/to/Ilomusi.hex\"" -c init -c "reset run"
```

## 64bit Windows

```
"C:/path/to/openocd_dir/bin-x64/openocd" -f "C:/path/to/openocd_dir/scripts/interface/stlink-v2.cfg" -f "C:/path/to/openocd_dir/scripts/target/stm32f0x.cfg" -c init -c "reset init" -c "flash write_image erase \"/path/to/Ilomusi.hex\"" -c init -c "reset run"
```
