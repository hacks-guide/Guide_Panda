---
title: "0_15_20 ctrtransfer"
permalink: /0_15_20-ctrtransfer.html
---

If you downgrade to 0_15_20 on a New 3DS PANDA or 2DS PANDA and left Wireless Communication off, you can re-enable the wireless by removing the battery for several seconds then booting back up.
{: .notice--info}

Your device may not show some installed titles after the ctrtransfer. This is due to the tickets being removed by the transfer; they will be restored when you restore your NAND backup.
{: .notice--info}

Never format a 2DS while on a version <6.0.0 or you will be unable to complete initial setup and will BRICK!
{: .notice--danger}

#### What you need

* You will need to have booted into Decrypt9
* The 0_15_20 PANDA / SNAKE ctrtransfer image
  +    [ctrtransfer - 0_15_20 - PANDA / SNAKE](https://3ds.guide/torrents/ctrtransfer_CTR-0_15_20-panda_snake.torrent) - <code class="highlighterrouge"><a href="magnet:?xt=urn:btih:2ba74f974d1388c56a08b6abfa8007f45de32595&dn=SecureInfo_B-panda.zip&tr=udp%3A%2F%2Ftracker.leechers-paradise.org%3A6969%2Fannounce&tr=udp%3A%2F%2Ftorrent.gresille.org%3A80%2Fannounce&tr=http%3A%2F%2Ftracker1.wasabii.com.tw%3A6969%2Fannounce&tr=udp%3A%2F%2Fzer0day.ch%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.coppersurfer.tk%3A6969%2Fannounce&tr=udp%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=udp%3A%2F%2F9.rarbg.com%3A2710%2Fannounce&tr=http%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=http%3A%2F%2Ftracker.baravik.org%3A6970%2Fannounce&tr=udp%3A%2F%2Ftracker.tiny-vps.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.filetracker.pl%3A8089%2Fannounce&tr=http%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=http%3A%2F%2Ftracker.tfile.me%2Fannounce&tr=http%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.yoshi210.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftorrent.gresille.org%2Fannounce"><i class="fa fa-magnet" aria-hidden="true"></i></a></code>
* [`SecureInfo_B_panda.zip`](https://3ds.guide/torrents/SecureInfo_B_panda.torrent) - <code class="highlighterrouge"><a href="magnet:?xt=urn:btih:2ba74f974d1388c56a08b6abfa8007f45de32595&dn=SecureInfo_B-panda.zip&tr=udp%3A%2F%2Ftracker.leechers-paradise.org%3A6969%2Fannounce&tr=udp%3A%2F%2Ftorrent.gresille.org%3A80%2Fannounce&tr=http%3A%2F%2Ftracker1.wasabii.com.tw%3A6969%2Fannounce&tr=udp%3A%2F%2Fzer0day.ch%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.coppersurfer.tk%3A6969%2Fannounce&tr=udp%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=udp%3A%2F%2F9.rarbg.com%3A2710%2Fannounce&tr=http%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=http%3A%2F%2Ftracker.baravik.org%3A6970%2Fannounce&tr=udp%3A%2F%2Ftracker.tiny-vps.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.filetracker.pl%3A8089%2Fannounce&tr=http%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=http%3A%2F%2Ftracker.tfile.me%2Fannounce&tr=http%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.yoshi210.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftorrent.gresille.org%2Fannounce"><i class="fa fa-magnet" aria-hidden="true"></i></a></code>

#### Instructions

##### Section I - Prep work

You should be in Decrypt9 for these steps.

1. Press (Select) on the main menu to eject your SD card, then put it in your computer
2. Copy the 0_15_20 `.bin` and `.bin.sha` from the ctrtransfer zip to the `/files9/` folder on your SD card
3. Copy `SecureInfo_B` from `SecureInfo_B-panda.zip` to the `/files9/` folder on your SD card
3. Reinsert your SD card into your 3DS
4. Press (B) to get to the Decrypt9 main menu

##### Section II - ctrtransfer

4. Go to "SysNAND Options", then "CTRNAND Transfer", then "Auto CTRNAND Transfer"
5. Select `ctrtransfer_CTR-0_15_20-panda_snake.bin` when prompted by pressing (A)
6. **Backup SysNAND to `NANDmin.bin` when prompted by pressing (A)**
7. Allow the transfer process to proceed automatically, this may take some time
8. Once the transfer is complete, press (B) and go back to the main menu
9. Go to "SysNAND Options", then "System File Inject", then "Inject SecureInfo_B"
10. Select `SecureInfo_B` when prompted by pressing (A)
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

*(Screen distortions or discolorations are normal for some devices while on 0_15_20, they will go away once you restore your backup)*
{: .notice--info}

Putting a retail 2.1.0 New 3DS into sleep mode is known to cause BRICKS! I cannot be sure if this applies to 0_15_20 PANDA units aswell, but it would be wise to assume it does and continue the installation as soon as possible!
{: .notice--danger}

Continue to [Installing arm9loaderhax](installing-arm9loaderhax).
{: .notice--primary}
