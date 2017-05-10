---
title: "Updating A9LH"
permalink: /updating-a9lh.html
---

### Last Update: 11 Nov 2016

The actual installation of arm9loaderhax itself consists of payload files installed into the NFIRM partitions on your device's NAND chip, which is soldered to the motherboard itself. These payloads are updated rarely and only really serve the purpose of launching `arm9loaderhax.bin` from your SD card, which is, in our case, Luma3DS.
{: .notice}

If you do not know what version of arm9loaderhax you are running, just install the latest version with these steps. Installing the latest version while already on the latest version will have no effect.
{: .notice--info}

If you have a PIN set on Luma, you must temporarily turn it off to do these steps. You can re-enable the PIN after the update.
{: .notice--info}

If you are using a payload that does not init the screen on its own (such as Bootanim9), you will need to rename it to `arm9loaderhax_si.bin` instead of `arm9loaderhax.bin`
{: .notice--info}

To use the [magnet](https://en.wikipedia.org/wiki/Magnet_URI_scheme) links on this page, you will need a torrent client like [Deluge](http://dev.deluge-torrent.org/wiki/Download)
{: .notice--info}

These steps will also update your various payloads and the AES key database.
{: .notice--success}

#### What you need

* <i class="fa fa-magnet" aria-hidden="true" title="This is a magnet link. Use a torrent client to download the file."></i> - [`aeskeydb_panda.zip`](magnet:?xt=urn:btih:de90db8584fe9297b3b3e9cfcafea6d10819170d&dn=aeskeydb%5Fpanda.zip&tr=udp%3A%2F%2Ftracker.coppersurfer.tk%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=http%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=udp%3A%2F%2Fzer0day.ch%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.leechers-paradise.org%3A6969%2Fannounce&tr=http%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2F9.rarbg.com%3A2710%2Fannounce&tr=udp%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=http%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker1.wasabii.com.tw%3A6969%2Fannounce&tr=http%3A%2F%2Ftracker.baravik.org%3A6970%2Fannounce&tr=http%3A%2F%2Ftracker.tfile.me%2Fannounce&tr=udp%3A%2F%2Ftorrent.gresille.org%3A80%2Fannounce&tr=http%3A%2F%2Ftorrent.gresille.org%2Fannounce&tr=udp%3A%2F%2Ftracker.yoshi210.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.tiny-vps.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.filetracker.pl%3A8089%2Fannounce)
* <i class="fa fa-magnet" aria-hidden="true" title="This is a magnet link. Use a torrent client to download the file."></i> - [`safea9lhinstaller_v2_panda.zip`](magnet:?xt=urn:btih:502d3731fb5d4bec2fcdfbd21e6a08f2125dc583&dn=safea9lhinstaller%5Fv2%5Fpanda.zip&tr=udp%3A%2F%2Ftracker.coppersurfer.tk%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=http%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=udp%3A%2F%2Fzer0day.ch%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.leechers-paradise.org%3A6969%2Fannounce&tr=http%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2F9.rarbg.com%3A2710%2Fannounce&tr=udp%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=http%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker1.wasabii.com.tw%3A6969%2Fannounce&tr=http%3A%2F%2Ftracker.baravik.org%3A6970%2Fannounce&tr=http%3A%2F%2Ftracker.tfile.me%2Fannounce&tr=udp%3A%2F%2Ftorrent.gresille.org%3A80%2Fannounce&tr=http%3A%2F%2Ftorrent.gresille.org%2Fannounce&tr=udp%3A%2F%2Ftracker.yoshi210.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.tiny-vps.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.filetracker.pl%3A8089%2Fannounce)
* The latest release of [GodMode9](https://github.com/d0k3/GodMode9/releases/latest)

#### Instructions

**For all of these instructions, OVERWRITE any existing files on your SD card.**
{: .notice--info}

##### Section I - Prep work

1. Power off your device
1. Insert your SD card into your computer
1. Delete any existing `aeskeydb.bin` from the root of your SD card
1. Delete the `a9lh` folder from the root of your SD card if it exists
1. Copy `aeskeydb.bin` from `aeskeydb_panda.zip` to the `/files9/` folder on your SD card
1. Copy _the contents of_ `safea9lhinstaller_v2_panda.zip` to the root of your SD card
1. Copy `GodMode9.bin` from the GodMode9 `.zip` to the `/luma/payloads/` folder on your SD card
1. Copy `arm9loaderhax.bin` from the SafeA9LHInstaller `.zip` to the `/luma/payloads` folder on your SD card
1. Rename `arm9loaderhax.bin` in `/luma/payloads` to `down_safea9lhinstaller.bin`
1. Copy `arm9loaderhax.bin` from the Luma3DS `.zip` to the root of your SD card, overwrite existing files
1. Reinsert your SD card into your 3DS

##### Section II - Payload update

1. Boot your device while holding (Start) to launch the Luma3DS chainloader menu
1. Launch SafeA9LHInstaller by pressing (A)
1. Press (Select) to update arm9loaderhax
1. Power off your device
1. Insert your SD card into your computer
1. Delete the `a9lh` folder from the root of your SD card
1. Delete `safea9lhinstaller.bin` from `/luma/payloads/`
1. Reinsert your SD card into your device

##### Section III - Configuring Luma3DS

1. Boot your device while holding (Select) to enter the Luma3DS configuration menu
1. Use the (A) button and the D-Pad to turn on the following:    
  + **"Autoboot SysNAND"**
  + **"Use SysNAND FIRM if booting with R"**
  + **"Show NAND or user string in System Settings"**
1. Press (Start) to save and reboot

##### Section IV - CTRNAND Luma3DS

1. Reboot holding (Start) during boot to launch the Luma3DS chainloader menu
1. Launch GodMode9 by pressing (A)
1. Navigate to `[0:] SDCARD`
1. Press (Y) on `arm9loaderhax.bin` to copy it
1. Press (B) to return to the main menu
1. Navigate to `[1:] SYSNAND CTRNAND`
1. Press (Y) to paste `arm9loaderhax.bin`
1. Select "Copy path(s)"
  + Overwrite any existing `arm9loaderhax.bin` if prompted
1. Press (A) to unlock SysNAND (lvl1) writing, then input the key combo given
1. Press (B) to return to the main menu
1. Hold (R) and press (B) at the same time to eject your SD card
1. Remove your SD card from your device
1. Press (Start) to reboot your device with your SD card removed
  + Booting your device at least once with your SD card removed will allow you to configure the CTRNAND based Luma3DS installation
1. Use the (A) button and the D-Pad to turn on the following:    
  + **"Show NAND or user string in System Settings"**
1. Reinsert your SD card into your device
1. Press (Start) to save and reboot

{% capture notice-11 %}
**Updating your PANDA / SNAKE using a CSU is only safe for Luma3DS version 6.6 (commit 0b16d88) and above!**    
**Attempting to update your PANDA / SNAKE using a CSU on any lower Luma3DS version will BRICK your device!**
{% endcapture %}

<div class="notice--danger">{{ notice-11 | markdownify }}</div>
