---
title: "0_15_20 ctrtransfer"
permalink: /0_15_20-ctrtransfer.html
---

If you downgrade to 0_15_20 on a New 3DS PANDA or 2DS PANDA and leave Wireless Communication off, you can re-enable the wireless by removing the battery for several seconds then booting back up.
{: .notice--info}

If you've been using the New 3DS's microSD Management to transfer files to your SD card, this will no longer work on 2.1.0. Ensure you have a microSD card reader available before proceeding.
{: .notice--info}

To use the [magnet](https://en.wikipedia.org/wiki/Magnet_URI_scheme) links on this page, you will need a torrent client like [Deluge](http://dev.deluge-torrent.org/wiki/Download)
{: .notice--info}

**For now, connecting your device to the internet is REQUIRED to continue after the 2.1.0 CTRTransfer.**
{: .notice--warning}

**Disable the parental controls of your device before doing the 2.1.0 CTRTransfer. If you do not know the password, see [this](https://mkey.salthax.org/) site. If you cannot disable parental controls because the linked NNID is for a child under 13, you can instead set all parental control options to "do not restrict".**
{: .notice--warning}

**Performing a CTRTransfer will remove all user-installed tickets (which allow access to games) from your device until the created backup is restored.**
{: .notice--danger}

**Never format a 2DS while on a version <6.0.0 or you will be unable to complete initial setup and will BRICK!**
{: .notice--danger}

**Never update a New 3DS running 2.1.0 (an Old 3DS firmware) or you will BRICK! You MUST restore a NAND backup or CTRTransfer back to standard New 3DS firmware first!**
{: .notice--danger}

{% capture notice %}
**Putting a New 3DS on 2.1.0 in sleep mode is known to cause a BRICK!**    
**This only happens when shutting the lid _while your device is on_; this does not apply to turning your device off.**    
**Your device only enters sleep mode when the lid is closed. It is not on a timer or anything like that.**    
**Once on 2.1.0, you should continue without delay to avoid any possibility of this happening!**    
{% endcapture %}

<div class="notice--danger">{{ notice | markdownify }}</div>

#### What you need

* You will need to have booted into Decrypt9
* The 0_15_20 PANDA / SNAKE ctrtransfer image
  +    [ctrtransfer - 0_15_20 - PANDA / SNAKE](magnet:?xt=urn:btih:74861c137162c3db10af9048c04f923e82e0331c&dn=ctrtransfer_CTR-0_15_20-panda_snake.zip&tr=udp%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=udp%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2F9.rarbg.com%3A2710%2Fannounce&tr=udp%3A%2F%2Ftracker.tiny-vps.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.coppersurfer.tk%3A6969%2Fannounce&tr=udp%3A%2F%2Fzer0day.ch%3A1337%2Fannounce&tr=udp%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=http%3A%2F%2Ftracker.tfile.me%2Fannounce&tr=udp%3A%2F%2Ftracker.leechers-paradise.org%3A6969%2Fannounce&tr=http%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.yoshi210.com%3A6969%2Fannounce&tr=http%3A%2F%2Ftracker1.wasabii.com.tw%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.filetracker.pl%3A8089%2Fannounce&tr=http%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=udp%3A%2F%2Ftorrent.gresille.org%3A80%2Fannounce&tr=http%3A%2F%2Ftracker.baravik.org%3A6970%2Fannounce&tr=http%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=http%3A%2F%2Ftorrent.gresille.org%2Fannounce&tr=http%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce)

#### Instructions

##### Section I - Prep work

You should be in Decrypt9 for these steps.

1. Press (Select) on the main menu to eject your SD card, then put it in your computer
2. Copy the 0_15_20 `.bin` and `.bin.sha` from the ctrtransfer `.zip` to the `/files9/` folder on your SD card
3. Reinsert your SD card into your 3DS
4. Press (B) to get to the Decrypt9 main menu

##### Section II - ctrtransfer

4. Go to "SysNAND Options", then "CTRNAND Transfer", then "Auto CTRNAND Transfer"
5. Select `ctrtransfer_CTR-0_15_20-panda_snake.bin` when prompted by pressing (A)
6. **Backup SysNAND to `NANDmin.bin` when prompted by pressing (A)**
7. Allow the transfer process to proceed automatically, this may take some time
8. Once the transfer is complete, press (B) and go back to the main menu
9. Press (Select) to eject your SD card
9. Delete `ctrtransfer_CTR-0_15_20-panda_snake.bin` and `ctrtransfer_CTR-0_15_20-panda_snake.bin.sha` from the `/files9/` folder on your SD card
19. Clear Home Menu's extdata by navigating to the following folder on your SD card: `/Nintendo 3DS/(32 Character ID)/(32 Character ID)/extdata/00000000/`
    + EUR Region: Delete `00000098`
    + JPN Region: Delete `00000082`
    + USA Region: Delete `0000008f`
    + CHN Region: Delete `000000A1`
    + KOR Region: Delete `000000A9`
    + TWN Region: Delete `000000B1`
12. Reinsert your SD card into your 3DS
11. Press (Start) to reboot

___

*(Screen distortions or discolorations are normal for some devices while on 2.1.0, they will go away once you restore your backup)*
{: .notice--info}

{% capture notice %}
**Putting a New 3DS on 2.1.0 in sleep mode is known to cause a BRICK!**    
**This only happens when shutting the lid _while your device is on_; this does not apply to turning your device off.**    
**Your device only enters sleep mode when the lid is closed. It is not on a timer or anything like that.**    
**Once on 2.1.0, you should continue without delay to avoid any possibility of this happening!**    
{% endcapture %}

<div class="notice--danger">{{ notice | markdownify }}</div>

Continue to [Installing arm9loaderhax](installing-arm9loaderhax)
{: .notice--primary}
