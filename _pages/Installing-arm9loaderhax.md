---
title: "Installing arm9loaderhax"
permalink: /installing-arm9loaderhax.html
---

The final Step of this guide is to install arm9loaderhax and setup Luma3DS to run just milliseconds into the boot. This is accomplished by using a hex-edited version (to be compatible with PANDAs / SNAKEs) of SafeA9LHInstaller by [AuroraWright](https://github.com/AuroraWright/).
{: .notice}

This will install a hex-edited version (to be compatible with PANDAs / SNAKEs) of [AuroraWright's Fork](https://github.com/AuroraWright/arm9loaderhax) of arm9loaderhax.
{: .notice--info}

We will also setup the ability to launch payloads from arm9loaderhax, giving us the ability to unbrick our SysNAND from situations that would normally brick us by restoring from backup.
{: .notice--info}

To use the [magnet](https://en.wikipedia.org/wiki/Magnet_URI_scheme) links on this page, you will need a torrent client like [Deluge](http://dev.deluge-torrent.org/wiki/Download)
{: .notice--info}

**You cannot use another console's OTP or you will brick GUARANTEED.**
{: .notice--danger}

#### Overview of steps

{% capture notice-2 %}

In this section, we will go through the process that all the other steps have led up to: actually installing arm9loaderhax.
<br><br>
This is nearly the best possible kind of device exploit because it is permanently installable into the NAND firm partitions, and runs before most of the OS loads, allowing it to not only work on *all* versions once installed, but also protect itself and recover from most situations that would brick a non-A9LH 3DS such as a nonfunctional home menu or bad title install.
<br><br>
The file `arm9loaderhax.bin` is what is launched by arm9loaderhax itself after it finishes loading off of NAND, and can be any valid arm9 payload. This file can be replaced at any time, although Luma3DS allows for the launch of other arm9 payloads using the Luma3DS chainloader.
<br><br>
In this case, we use Luma3DS by [AuroraWright](https://github.com/AuroraWright/) to boot a patched SysNAND directly, allowing us to completely bypass the need for any kind of EmuNAND, vastly simplifying the usage of a hacked 3DS in addition to saving SD card space.
<br><br>
Once arm9loaderhax is installed and Luma3DS is setup with the correct options, we then restore our previous backup.
<br><br>
During this process, we also setup programs such as the following:    

+  **Luma3DS Updater** *(updates your CFW installation easily)*
+  **GodMode9** *(multipurpose tool which can do NAND and cartridge functions)*

{% endcapture %}

<div class="notice--info">{{ notice-2 | markdownify }}</div>

#### What you need

* <i class="fa fa-magnet" aria-hidden="true" title="This is a magnet link. Use a torrent client to download the file."></i> - [`aeskeydb_panda.zip`](magnet:?xt=urn:btih:de90db8584fe9297b3b3e9cfcafea6d10819170d&dn=aeskeydb%5Fpanda.zip&tr=udp%3A%2F%2Ftracker.coppersurfer.tk%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=http%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=udp%3A%2F%2Fzer0day.ch%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.leechers-paradise.org%3A6969%2Fannounce&tr=http%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2F9.rarbg.com%3A2710%2Fannounce&tr=udp%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=http%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker1.wasabii.com.tw%3A6969%2Fannounce&tr=http%3A%2F%2Ftracker.baravik.org%3A6970%2Fannounce&tr=http%3A%2F%2Ftracker.tfile.me%2Fannounce&tr=udp%3A%2F%2Ftorrent.gresille.org%3A80%2Fannounce&tr=http%3A%2F%2Ftorrent.gresille.org%2Fannounce&tr=udp%3A%2F%2Ftracker.yoshi210.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.tiny-vps.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.filetracker.pl%3A8089%2Fannounce)
* <i class="fa fa-magnet" aria-hidden="true" title="This is a magnet link. Use a torrent client to download the file."></i> - [`safea9lhinstaller_v2_panda.zip`](magnet:?xt=urn:btih:502d3731fb5d4bec2fcdfbd21e6a08f2125dc583&dn=safea9lhinstaller%5Fv2%5Fpanda.zip&tr=udp%3A%2F%2Ftracker.coppersurfer.tk%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=http%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=udp%3A%2F%2Fzer0day.ch%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.leechers-paradise.org%3A6969%2Fannounce&tr=http%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2F9.rarbg.com%3A2710%2Fannounce&tr=udp%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=http%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker1.wasabii.com.tw%3A6969%2Fannounce&tr=http%3A%2F%2Ftracker.baravik.org%3A6970%2Fannounce&tr=http%3A%2F%2Ftracker.tfile.me%2Fannounce&tr=udp%3A%2F%2Ftorrent.gresille.org%3A80%2Fannounce&tr=http%3A%2F%2Ftorrent.gresille.org%2Fannounce&tr=udp%3A%2F%2Ftracker.yoshi210.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.tiny-vps.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.filetracker.pl%3A8089%2Fannounce)
* The latest release of [Luma3DS](https://github.com/AuroraWright/Luma3DS/releases)
* The latest release of [GodMode9](https://github.com/d0k3/GodMode9/releases/latest)
* The 0.25.3 (latest version) PANDA / SNAKE CIAs `.zip` file for your device and region:
  +    <i class="fa fa-magnet" aria-hidden="true" title="This is a magnet link. Use a torrent client to download the file."></i> - [SNAKE - 0.25.3 - EUR](magnet:?xt=urn:btih:1342b804d9340d49917fe6a35290f0b1b79b6c32&dn=SystemUpdater%5FSNAKE-0%5F25%5F3-EU%5Fcias.zip&tr=udp%3A%2F%2Ftracker.coppersurfer.tk%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=http%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=udp%3A%2F%2Fzer0day.ch%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.leechers-paradise.org%3A6969%2Fannounce&tr=http%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2F9.rarbg.com%3A2710%2Fannounce&tr=udp%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=http%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker1.wasabii.com.tw%3A6969%2Fannounce&tr=http%3A%2F%2Ftracker.baravik.org%3A6970%2Fannounce&tr=http%3A%2F%2Ftracker.tfile.me%2Fannounce&tr=udp%3A%2F%2Ftorrent.gresille.org%3A80%2Fannounce&tr=http%3A%2F%2Ftorrent.gresille.org%2Fannounce&tr=udp%3A%2F%2Ftracker.yoshi210.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.tiny-vps.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.filetracker.pl%3A8089%2Fannounce)    
  +    <i class="fa fa-magnet" aria-hidden="true" title="This is a magnet link. Use a torrent client to download the file."></i> - [SNAKE - 0.25.3 - JPN](magnet:?xt=urn:btih:b0376718bd7c83244dd4bf440e3b1e4e2513637a&dn=SystemUpdater%5FSNAKE-0%5F25%5F3-JP%5Fcias.zip&tr=udp%3A%2F%2Ftracker.coppersurfer.tk%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=http%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=udp%3A%2F%2Fzer0day.ch%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.leechers-paradise.org%3A6969%2Fannounce&tr=http%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2F9.rarbg.com%3A2710%2Fannounce&tr=udp%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=http%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker1.wasabii.com.tw%3A6969%2Fannounce&tr=http%3A%2F%2Ftracker.baravik.org%3A6970%2Fannounce&tr=http%3A%2F%2Ftracker.tfile.me%2Fannounce&tr=udp%3A%2F%2Ftorrent.gresille.org%3A80%2Fannounce&tr=http%3A%2F%2Ftorrent.gresille.org%2Fannounce&tr=udp%3A%2F%2Ftracker.yoshi210.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.tiny-vps.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.filetracker.pl%3A8089%2Fannounce)     
  +    <i class="fa fa-magnet" aria-hidden="true" title="This is a magnet link. Use a torrent client to download the file."></i> - [SNAKE - 0.25.3 - USA](magnet:?xt=urn:btih:d3c4b0083f5e4f093ff3f96e8b396f6ed968fcd6&dn=SystemUpdater%5FSNAKE-0%5F25%5F3-US%5Fcias.zip&tr=udp%3A%2F%2Ftracker.coppersurfer.tk%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=http%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=udp%3A%2F%2Fzer0day.ch%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.leechers-paradise.org%3A6969%2Fannounce&tr=http%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2F9.rarbg.com%3A2710%2Fannounce&tr=udp%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=http%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker1.wasabii.com.tw%3A6969%2Fannounce&tr=http%3A%2F%2Ftracker.baravik.org%3A6970%2Fannounce&tr=http%3A%2F%2Ftracker.tfile.me%2Fannounce&tr=udp%3A%2F%2Ftorrent.gresille.org%3A80%2Fannounce&tr=http%3A%2F%2Ftorrent.gresille.org%2Fannounce&tr=udp%3A%2F%2Ftracker.yoshi210.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.tiny-vps.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.filetracker.pl%3A8089%2Fannounce)     
  +    <i class="fa fa-magnet" aria-hidden="true" title="This is a magnet link. Use a torrent client to download the file."></i> - [SNAKE - 0.25.3 - KOR](magnet:?xt=urn:btih:63da48eb7dea5713c0e3d094ca18d869879fff6b&dn=SystemUpdater%5FSNAKE-0%5F25%5F3-KR%5Fcias.zip&tr=udp%3A%2F%2Ftracker.coppersurfer.tk%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=http%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=udp%3A%2F%2Fzer0day.ch%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.leechers-paradise.org%3A6969%2Fannounce&tr=http%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2F9.rarbg.com%3A2710%2Fannounce&tr=udp%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=http%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker1.wasabii.com.tw%3A6969%2Fannounce&tr=http%3A%2F%2Ftracker.baravik.org%3A6970%2Fannounce&tr=http%3A%2F%2Ftracker.tfile.me%2Fannounce&tr=udp%3A%2F%2Ftorrent.gresille.org%3A80%2Fannounce&tr=http%3A%2F%2Ftorrent.gresille.org%2Fannounce&tr=udp%3A%2F%2Ftracker.yoshi210.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.tiny-vps.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.filetracker.pl%3A8089%2Fannounce)     
~
  +    <i class="fa fa-magnet" aria-hidden="true" title="This is a magnet link. Use a torrent client to download the file."></i> - [PANDA - 0.25.3 - EUR](magnet:?xt=urn:btih:67c40a7bf19b01a93a595eebeb9dc684d2b625e4&dn=SystemUpdater%5FCTR-0%5F25%5F3-EU%5Fcias.zip&tr=udp%3A%2F%2Ftracker.coppersurfer.tk%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=http%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=udp%3A%2F%2Fzer0day.ch%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.leechers-paradise.org%3A6969%2Fannounce&tr=http%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2F9.rarbg.com%3A2710%2Fannounce&tr=udp%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=http%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker1.wasabii.com.tw%3A6969%2Fannounce&tr=http%3A%2F%2Ftracker.baravik.org%3A6970%2Fannounce&tr=http%3A%2F%2Ftracker.tfile.me%2Fannounce&tr=udp%3A%2F%2Ftorrent.gresille.org%3A80%2Fannounce&tr=http%3A%2F%2Ftorrent.gresille.org%2Fannounce&tr=udp%3A%2F%2Ftracker.yoshi210.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.tiny-vps.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.filetracker.pl%3A8089%2Fannounce)    
  +    <i class="fa fa-magnet" aria-hidden="true" title="This is a magnet link. Use a torrent client to download the file."></i> - [PANDA - 0.25.3 - JPN](magnet:?xt=urn:btih:e9d2ee50bef53e0e9c7f1bfeed49475a3d14d426&dn=SystemUpdater%5FCTR-0%5F25%5F3-JP%5Fcias.zip&tr=udp%3A%2F%2Ftracker.coppersurfer.tk%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=http%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=udp%3A%2F%2Fzer0day.ch%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.leechers-paradise.org%3A6969%2Fannounce&tr=http%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2F9.rarbg.com%3A2710%2Fannounce&tr=udp%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=http%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker1.wasabii.com.tw%3A6969%2Fannounce&tr=http%3A%2F%2Ftracker.baravik.org%3A6970%2Fannounce&tr=http%3A%2F%2Ftracker.tfile.me%2Fannounce&tr=udp%3A%2F%2Ftorrent.gresille.org%3A80%2Fannounce&tr=http%3A%2F%2Ftorrent.gresille.org%2Fannounce&tr=udp%3A%2F%2Ftracker.yoshi210.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.tiny-vps.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.filetracker.pl%3A8089%2Fannounce)     
  +    <i class="fa fa-magnet" aria-hidden="true" title="This is a magnet link. Use a torrent client to download the file."></i> - [PANDA - 0.25.3 - USA](magnet:?xt=urn:btih:a0239f152985f2f9ff514587cc1e76397283f956&dn=SystemUpdater%5FCTR-0%5F25%5F3-US%5Fcias.zip&tr=udp%3A%2F%2Ftracker.coppersurfer.tk%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=http%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=udp%3A%2F%2Fzer0day.ch%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.leechers-paradise.org%3A6969%2Fannounce&tr=http%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2F9.rarbg.com%3A2710%2Fannounce&tr=udp%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=http%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker1.wasabii.com.tw%3A6969%2Fannounce&tr=http%3A%2F%2Ftracker.baravik.org%3A6970%2Fannounce&tr=http%3A%2F%2Ftracker.tfile.me%2Fannounce&tr=udp%3A%2F%2Ftorrent.gresille.org%3A80%2Fannounce&tr=http%3A%2F%2Ftorrent.gresille.org%2Fannounce&tr=udp%3A%2F%2Ftracker.yoshi210.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.tiny-vps.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.filetracker.pl%3A8089%2Fannounce)     
  +    <i class="fa fa-magnet" aria-hidden="true" title="This is a magnet link. Use a torrent client to download the file."></i> - [PANDA - 0.25.3 - CHN](magnet:?xt=urn:btih:4c0edc918713d596d0ccd4e6ba4f45937a97f89a&dn=SystemUpdater%5FCTR-0%5F25%5F3-CN%5Fcias.zip&tr=udp%3A%2F%2Ftracker.coppersurfer.tk%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=http%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=udp%3A%2F%2Fzer0day.ch%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.leechers-paradise.org%3A6969%2Fannounce&tr=http%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2F9.rarbg.com%3A2710%2Fannounce&tr=udp%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=http%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker1.wasabii.com.tw%3A6969%2Fannounce&tr=http%3A%2F%2Ftracker.baravik.org%3A6970%2Fannounce&tr=http%3A%2F%2Ftracker.tfile.me%2Fannounce&tr=udp%3A%2F%2Ftorrent.gresille.org%3A80%2Fannounce&tr=http%3A%2F%2Ftorrent.gresille.org%2Fannounce&tr=udp%3A%2F%2Ftracker.yoshi210.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.tiny-vps.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.filetracker.pl%3A8089%2Fannounce)     
  +    <i class="fa fa-magnet" aria-hidden="true" title="This is a magnet link. Use a torrent client to download the file."></i> - [PANDA - 0.25.3 - KOR](magnet:?xt=urn:btih:7202afc7a6ef30f7536fddabf9dd867553f1be2e&dn=SystemUpdater%5FCTR-0%5F25%5F3-KR%5Fcias.zip&tr=udp%3A%2F%2Ftracker.coppersurfer.tk%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=http%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=udp%3A%2F%2Fzer0day.ch%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.leechers-paradise.org%3A6969%2Fannounce&tr=http%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2F9.rarbg.com%3A2710%2Fannounce&tr=udp%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=http%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker1.wasabii.com.tw%3A6969%2Fannounce&tr=http%3A%2F%2Ftracker.baravik.org%3A6970%2Fannounce&tr=http%3A%2F%2Ftracker.tfile.me%2Fannounce&tr=udp%3A%2F%2Ftorrent.gresille.org%3A80%2Fannounce&tr=http%3A%2F%2Ftorrent.gresille.org%2Fannounce&tr=udp%3A%2F%2Ftracker.yoshi210.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.tiny-vps.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.filetracker.pl%3A8089%2Fannounce)     
  +    <i class="fa fa-magnet" aria-hidden="true" title="This is a magnet link. Use a torrent client to download the file."></i> - [PANDA - 0.25.3 - TWN](magnet:?xt=urn:btih:aa27d8e2f17eb0e20a9084260f5845c2d9c115dc&dn=SystemUpdater%5FCTR-0%5F25%5F3-TW%5Fcias.zip&tr=udp%3A%2F%2Ftracker.coppersurfer.tk%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=http%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=udp%3A%2F%2Fzer0day.ch%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.leechers-paradise.org%3A6969%2Fannounce&tr=http%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2F9.rarbg.com%3A2710%2Fannounce&tr=udp%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=http%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker1.wasabii.com.tw%3A6969%2Fannounce&tr=http%3A%2F%2Ftracker.baravik.org%3A6970%2Fannounce&tr=http%3A%2F%2Ftracker.tfile.me%2Fannounce&tr=udp%3A%2F%2Ftorrent.gresille.org%3A80%2Fannounce&tr=http%3A%2F%2Ftorrent.gresille.org%2Fannounce&tr=udp%3A%2F%2Ftracker.yoshi210.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.tiny-vps.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.filetracker.pl%3A8089%2Fannounce)     

#### Instructions

##### Section I - Prep work

1. Copy `<serialnumber>_nand.bin` and `<serialnumber>_nand.bin.sha` from the `/CTRTransfer/` folder on your SD card to a safe location on your computer
  + Make backups in multiple locations (such as online file storage)
  + This backup will save you from a brick if anything goes wrong in the future
1. Create a folder named `cias` on the root of your SD card if it does not already exist
1. Copy _the contents of_ `safea9lhinstaller_v2_panda.zip` to the root of your SD card
1. Copy `arm9loaderhax.bin` from the `out` folder in the Luma3DS `.zip` to the root of your SD card
1. Create a folder named `luma` on the root of your SD card
1. Create a folder named `payloads` in the `luma` folder on your SD card
1. Copy `GodMode9.bin` from the GodMode9 `.zip` to the `/luma/payloads/` folder on your SD card
1. Copy `aeskeydb.bin` from `aeskeydb_panda.zip` to the `/files9/` folder on your SD card
1. Delete the 0.23.5 SystemUpdater folder from the root of your SD card
1. Extract the 0.25.3 SystemUpdater `.zip` to the root of your SD card

##### Section II - Installing arm9loaderhax

1. Reinsert your SD card into your 3DS
1. You should be on 0.15.20 and powered on
1. Go to `http://2xrsa.3ds.guide` on your 3DS
  + If you get the error "This service is not available in your region", use the System Settings to set your device's country to match the NAND region you installed with 2.1.0 CTRTransfer
  + If you forgot to disable parental controls before CTRTransfering or otherwise cannot access wireless settings, note that the device will autoconnect to any network named `attwifi` with no password
  + If you get an error, [follow this troubleshooting guide](troubleshooting#ts_browser)
  + If you get a glitched screen, [follow this troubleshooting guide](troubleshooting#ts_safe_a9lh_screen)
1. Press (Select) to Full Install
1. The installer will now install arm9loaderhax on your device (this is very fast)
1. Power off your device by pressing any button
1. Insert your SD card into your computer
1. Copy your device specific `otp.bin` from the `/a9lh/` folder on your SD card to a safe location on your computer and back it up to multiple locations (such as online file storage), then reinsert your SD card into your device
1. Reinsert your SD card into your device

##### Section III - Configuring Luma3DS

1. Boot your device while holding (Select) to enter the Luma3DS configuration menu
  + Make sure to start holding the button before pressing power
  + If you get a black screen, [follow this troubleshooting guide](troubleshooting#ts_sys_a9lh)   
  + If you boot to SafeA9LHInstaller, [follow this troubleshooting guide](troubleshooting#ts_safe_a9lh)
1. Use the (A) button and the D-Pad to turn on the following:    
  + **"Autoboot SysNAND"**
  + **"Use SysNAND FIRM if booting with R"**
  + **"Show NAND or user string in System Settings"**
1. Press (Start) to save and reboot
  + If you get a black screen, just continue to the next section   
  + If you get a "Failed to mount CTRNAND" error, just continue to the next section     

##### Section IV - Restoring the System

1. Boot your device while holding (Start) to launch the Luma3DS chainloader menu
1. Launch GodMode9 by pressing (A)
1. Navigate to `[0:] SDCARD` -> `ctrtransfer`
1. Press (A) on `<serialnumber>_nand.bin` to select it, then select "NAND image options...", then select "Restore SysNAND (safe)"
1. Press (A) to unlock SysNAND overwriting, then input the key combo given
  + This will not overwrite your arm9loaderhax installation
1. Input the key combo given to unlock SysNAND (lvl1) writing
  + This process will take some time
1. Once it has completed, press (A) to continue
1. Press (Start) to reboot your device
  + If you get a black screen, [follow 9.2.0 CTRTransfer](9.2.0-ctrtransfer)
  + It is now safe to put New 3DSs in sleep mode again
1. Using Dev Menu, navigate to the 0.25.3 SystemUpdater folder
1. Press (L + R + A) to install all CIAs
1. Navigate to the NATIVE_FIRM CIA
  + Old 3DS PANDA / SNAKE: `0004013800000002.cia`
  + New 3DS PANDA / SNAKE: `0004013820000002.cia`
1. Update your PANDA / SNAKE's FIRM by pressing (Start + Y) while highlighting the NATIVE_FIRM CIA
1. You can also update your PANDA / SNAKE using a CTR System Updater (CSU)
  + **This is only safe for Luma3DS version 6.6 (commit 0b16d88) and above!**
  + **Attempting to update your PANDA / SNAKE using a CSU on any lower Luma3DS version will BRICK your device!**

##### Section V - Installing LumaUpdater

1. Open Dev Menu
1. Install `lumaupdater.cia`
1. Exit with the home button

##### Section VI - CTRNAND Luma3DS

1. Reboot holding (Start) during boot to launch the Luma3DS chainloader menu
1. Launch GodMode9 by pressing (A)
1. Navigate to `[0:] SDCARD`
1. Press (Y) on `arm9loaderhax.bin` to copy it
1. Press (B) to return to the main menu
1. Navigate to `[1:] SYSNAND CTRNAND`
1. Press (Y) to paste `arm9loaderhax.bin`
1. Select "Copy path(s)"
1. Press (B) to return to the main menu
1. Hold (R) and press (B) at the same time to eject your SD card
1. Remove your SD card from your device
1. Press (Start) to reboot your device with your SD card removed
  + Booting your device at least once with your SD card removed will allow you to configure the CTRNAND based Luma3DS installation
1. Use the (A) button and the D-Pad to turn on the following:    
  + **"Show NAND or user string in System Settings"**
1. Reinsert your SD card into your device
1. Press (Start) to save and reboot

___

{% capture notice-11 %}
**Updating your PANDA / SNAKE using a CSU is only safe for Luma3DS version 6.6 (commit 0b16d88) and above!**    
**Attempting to update your PANDA / SNAKE using a CSU on any lower Luma3DS version will BRICK your device!**
{% endcapture %}

<div class="notice--danger">{{ notice-11 | markdownify }}</div>

{% capture notice-10 %}
You can now use Luma3DS Updater to update your Luma3DS to the latest version just by opening it and pressing (A).     
This is not the same thing as a System Update; it just downloads and extracts the newest Luma3DS files. Luma3DS Updater only updates the files located on the SD card.    
This will only update the Luma3DS files on the SD Card. If you boot the device without an SD card, it will use whatever version you placed in CTR NAND.    
{% endcapture %}

<div class="notice--info">{{ notice-10 | markdownify }}</div>

{% capture notice-6 %}   
You will now boot Luma3DS CFW SysNAND by default.    
You can now hold (Select) on boot to launch the Luma3DS configuration menu.    
You can now hold (Start) on boot to launch the Luma3DS chainloader menu.     
{% endcapture %}

<div class="notice--info">{{ notice-6 | markdownify }}</div>

To use [NTR CFW](https://github.com/44670/BootNTR/), install [BootNTR Selector](https://gbatemp.net/threads/432911/).
{: .notice--info}

Keep your `<serialnumber>_nand.bin` file, it can be restored by GodMode9 to save you from a brick in the future.
{: .notice--info}

{% capture notice-7 %}
**You can remove any extra files and folders from the root of the SD card that are *not* in the following list:**

    + 3ds
    + files9
    + hblauncherloader
    + luma
    + Nintendo 3DS
    + arm9loaderhax.bin
    + boot.3dsx

{% endcapture %}

<div class="notice--info">{{ notice-7 | markdownify }}</div>

For information on keeping your A9LH installation up to date, check out the [Updating A9LH](updating-a9lh) page.
{: .notice--success}

For information on using GodMode9's various features, check out the [GodMode9 Usage](godmode9-usage) page.
{: .notice--success}

For information on using Luma3DS's various features, check out [its wiki](https://github.com/AuroraWright/Luma3DS/wiki/Options-and-usage).
{: .notice--success}
