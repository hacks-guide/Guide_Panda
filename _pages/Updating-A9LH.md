---
title: "Updating A9LH"
permalink: /updating-a9lh.html
---

### Last Update: 11 Nov 2016

The actual installation of arm9loaderhax itself consists of payload files installed into the NFIRM partitions on your device's NAND chip, which is soldered to the motherboard itself. These payloads are updated rarely and only really serve the purpose of launching `arm9loaderhax.bin` from the SD Card, which is, in our case, Luma3DS.
{: .notice}

If you do not know what version of arm9loaderhax you are running, just install the latest version with these steps. Installing the latest version while already on the latest version will have no effect.
{: .notice--info}

If you have a PIN set on Luma, you must temporarily turn it off to do these steps. You can re-enable the PIN after the update.
{: .notice--info}

If you are using a payload that does not init the screen on its own (such as Bootanim9), you will need to rename it to `arm9loaderhax_si.bin` instead of `arm9loaderhax.bin`
{: .notice--info}

These steps will also update your various payloads and the AES key database.
{: .notice--success}

**If you attempt these steps on a retail console, you will BRICK!**
{: .notice--danger}

#### What you need

* [`aeskeydb_panda.zip`](../Guide/torrents/aeskeydb_panda.torrent) - <code class="highlighterrouge"><a href="magnet:?xt=urn:btih:8409379ff4f495e53be1032e539f07fad05e0874"><i class="fa fa-magnet" aria-hidden="true"></i></a></code>
* [`safea9lhinstaller_v2_panda.zip`](../Guide/torrents/safea9lhinstaller_v2_panda.torrent) - <code class="highlighterrouge"><a href="magnet:?xt=urn:btih:502d3731fb5d4bec2fcdfbd21e6a08f2125dc583"><i class="fa fa-magnet" aria-hidden="true"></i></a></code>
* The latest release of [Luma3DS](https://github.com/AuroraWright/Luma3DS/releases/latest)
* The latest release of [Decrypt9WIP](https://github.com/d0k3/Decrypt9WIP/releases/latest)
* The latest release of [GodMode9](https://github.com/d0k3/GodMode9/releases/latest)

#### Instructions

**For all of these instructions, OVERWRITE any existing files on your SD card.**

##### Section I - Prep work

4. Delete the `a9lh` folder from the root of your SD card if it exists
5. Copy _the contents of_ `safea9lhinstaller_v2_panda.zip` to the root of your SD card
16. Copy `aeskeydb.bin` from `aeskeydb_panda.zip` to the `/files9/` folder on your SD card
15. Copy `Decrypt9WIP.bin` from the Decrypt9WIP zip to the `/luma/payloads/` folder on your SD card and rename `Decrypt9WIP.bin` to `start_Decrypt9WIP.bin`
16. Copy `GodMode9.bin` from the GodMode9 zip to the `/luma/payloads/` folder on your SD card and rename `GodMode9.bin` to `up_GodMode9.bin``
5. Copy `arm9loaderhax.bin` from the SafeA9LHInstaller zip to the `/luma/payloads` folder on your SD card
6. Rename `arm9loaderhax.bin` in `/luma/payloads` to `down_safea9lhinstaller.bin`
8. Copy `arm9loaderhax.bin` from the Luma3DS zip to the root of your SD card, overwrite existing files
9. Reinsert your SD card into your 3DS

##### Section II - Payload update

10. Boot the device while holding D-Pad down
11. Press (Select) to update arm9loaderhax
12. Power off the device and put your SD card back in your computer
13. Delete the `a9lh` folder from the root of your SD card
14. Delete `down_safea9lhinstaller.bin` from `/luma/payloads`

##### Section III - Configuring Luma3DS

15. Reinsert your SD card into your 3DS and boot holding (Select)
16. Use the (A) button and the D-Pad to turn on the following:    
  + **"Autoboot SysNAND"**
  + **"Use SysNAND FIRM if booting with R (A9LH)"**
  + **"Show NAND or user string in System Settings"**
3. If you are using a **New 3DS**, you should *also* enable the following:
  + **"New 3DS CPU" to "Clock+L2(x)"**
    + This will increase the framerate of many games, but may cause instability in others
    + If some games do not work properly, disable this option and try again
4. Press Start to save and reboot

##### Section IV - CTRNAND Luma3DS

1. Open GodMode9 from arm9loaderhax by holding (Start) on boot
2. Navigate to `SDCARD`
3. Press (Y) on `arm9loaderhax.bin` to copy it
4. Press (B) to go back to the main menu
4. Navigate to `SYSNAND CTRNAND`
5. Press (Y) to paste a copy of `arm9loaderhax.bin`
6. Select "Copy path(s)"
6. Press (A) to unlock SysNAND writing, then input the key combo given
7. Press Start to reboot
15. Reboot with the SD card removed
  + Booting the device at least once with the SD card removed will allow you to configure the CTRNAND based luma installation
16. Use the (A) button and the D-Pad to turn on the following:    
  + **"Show NAND or user string in System Settings"**
3. If you are using a **New 3DS**, you should *also* enable the following:
  + **"New 3DS CPU" to "Clock+L2(x)"**
    + This will increase the framerate of many games, but may cause instability in others
    + If some games do not work properly, disable this option and try again
14. Reinsert your SD card, then press Start to save and reboot!

{% capture notice-11 %}
**Updating your PANDA using a CSU is only safe for Luma3DS version 6.6 (commit 0b16d88) and above!**    
**Attempting to update your PANDA on any lower Luma3DS version will BRICK your device!**
{% endcapture %}

<div class="notice--danger">{{ notice-11 | markdownify }}</div>
