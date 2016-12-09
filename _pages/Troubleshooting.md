---
title: "Troubleshooting"
permalink: /troubleshooting.html
---

If you are unable to boot your 3DS, please look for the section relevant to you, and follow the instructions. Once a solution works for you, you can proceed on with the main guide
(The section is fairly long, try using Ctrl+F to search for your issue.)
{: .notice--primary}

**If you still cannot solve your issue and need to reach out for help, please paste the contents of all relevant .log files from the root of your SD card into a [Gist](https://gist.github.com/), then come for help prepared with a detailed description of your problem and what you've tried.**
{: .notice--info}

## <a name="ts_browser" />A browser based exploit is not working
Browser based exploits (such as browserhax or 2xrsa) are often unstable and crash frequently, but they can sometimes be fixed by doing the following steps

1. Open the browser, then open the browser settings
    1. Scroll to the bottom and Initialize Savedata (it also may be called Clear All Save Data)
    2. Try the exploit again

## <a name="ts_safe_a9lh" />System boots directly SafeA9LHInstaller
You copied the wrong `arm9loaderhax.bin` file to your SD card (you were only supposed to copy the `3ds` folder and `SafeA9LHInstaller.dat` file from the SafeA9LHInstaller zip)    

1. Use the correct `arm9loaderhax.bin`
    1. Copy `arm9loaderhax.bin` from the Luma3DS `.zip` to the root of your SD card
    2. Reboot holding select and continue

## <a name="ts_safe_a9lh_screen" />SafeA9LHInstaller shows a glitched screen
This happens occasionally, but the reason is unknown. The buttons will still work, but the screen will be glitched looking

1. Follow instructions as normal
    1. Press (Select) and arm9loaderhax will be installed
    2. The console will reboot
        + If the console does not reboot, wait 10 seconds, then power off your 3DS by holding down the power button

## <a name="ts_d9_backup" />Decrypt9 or Hourglass9 won't restore / can't find my NAND backup

1. Make sure you do not have any folder named "Decrypt9" on **the root** of your SD card
3. Try checking your SD card file system with something like `fsck.vfat <sd partition path>` (on *nix) or `CHKDSK <sd drive letter> /F` (on Windows)
4. Try backing up your SD card files, then formatting it and copying them back
5. Try a different SD card

## <a name="ts_sys_down" />Black screen on SysNAND boot

1. Try booting with your SD card out, and then reinserting it after booting.
    1. Power off your 3DS by holding down the power button.
    2. Take out the SD card.
    3. Power on the 3DS.
    4. When the home menu appears, reinsert your SD card.
    5. If this worked, you should Clear Home Menu's extdata by navigating to the following folder on your SD card: `/Nintendo 3DS/(32 Character ID)/(32 Character ID)/extdata/00000000/`
        + EUR Region: Delete `00000098`
        + JPN Region: Delete `00000082`
        + USA Region: Delete `0000008f`
        + CHN Region: Delete `000000A1`
        + KOR Region: Delete `000000A9`
        + TWN Region: Delete `000000B1`
1. Try booting without any cartridges inserted (including flashcarts)
2. If you have a hardmod and a NAND backup, flash the backup back to SysNAND.
3. Try booting into recovery mode and updating your system.    
    *This probably will not work for an Old 3DS downgraded to 0_15_20*    
    **This will BRICK a New 3DS downgraded to 0_15_20**
    1. Power off your 3DS by holding down the power button.
    2. Hold L+R+A+Up.
    3. Power on the 3DS.
    4. If you enter safe mode, update your 3DS *only if you have an entrypoint for the latest FW version and it is possible to downgrade from it* and attempt the downgrade again.
4. Your 3DS may be bricked. For support, ask for help at [#Cakey on Freenode](http://webchat.freenode.net/?channels=%23Cakey).

## <a name="ts_sys_a9lh" />Black screen on SysNAND boot after installing arm9loaderhax

1. Ensure you have a working payload.
    1. Check for the existence of `arm9loaderhax.bin` in the root of your SD card.
2. Try resetting Luma's config and fix options
    1. Delete `/luma/config.bin` from your SD card
    2. Set your options when it boots
3. Test booting Hourglass9
    1. On Luma3DS, hold Start on boot
4. Try deleting home menu's extdata
    1. Clear Home Menu's extdata by navigating to the following folder on your SD card: `/Nintendo 3DS/(32 Character ID)/(32 Character ID)/extdata/00000000/`
        + EUR Region: Delete `00000098`
        + JPN Region: Delete `00000082`
        + USA Region: Delete `0000008f`
        + CHN Region: Delete `000000A1`
        + KOR Region: Delete `000000A9`
        + TWN Region: Delete `000000B1`
5. Try booting without any cartridges inserted (including flashcarts)
7. Try [this test payload](https://mega.nz/#!YxMiGDhB!VZLv2XPSqFFzEhf4kGMXAdQtSpIGvnp2vu2W1j4o7cc/) .
    1. Rename `/arm9loaderhax.bin`, if it exists, to something else.
    2. Place the `arm9loaderhax.bin` from the archive linked above in your SD root.
    3. Insert your SD card into your 3DS and power on.
    4. Press (A). Your 3DS should power off; this means arm9loaderhax is working and something else is broken; your device is **not** bricked.
10. Ask for help at [#Cakey on Freenode](http://webchat.freenode.net/?channels=%23Cakey).

## <a name="ts_sys_blue" />Blue screen on boot (bootrom error)

1. Your 3DS is bricked
2. You will need to get a [hardmod](https://gbatemp.net/threads/414498/) or repair / replace the device
