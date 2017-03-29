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

**You cannot use another console's OTP or you will brick GUARANTEED.**
{: .notice--danger}

#### What you need

* [`aeskeydb_panda.zip`](magnet:?xt=urn:btih:de90db8584fe9297b3b3e9cfcafea6d10819170d&dn=aeskeydb%5Fpanda.zip&tr=udp%3A%2F%2Ftracker.coppersurfer.tk%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=http%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=udp%3A%2F%2Fzer0day.ch%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.leechers-paradise.org%3A6969%2Fannounce&tr=http%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2F9.rarbg.com%3A2710%2Fannounce&tr=udp%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=http%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker1.wasabii.com.tw%3A6969%2Fannounce&tr=http%3A%2F%2Ftracker.baravik.org%3A6970%2Fannounce&tr=http%3A%2F%2Ftracker.tfile.me%2Fannounce&tr=udp%3A%2F%2Ftorrent.gresille.org%3A80%2Fannounce&tr=http%3A%2F%2Ftorrent.gresille.org%2Fannounce&tr=udp%3A%2F%2Ftracker.yoshi210.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.tiny-vps.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.filetracker.pl%3A8089%2Fannounce)
* [`safea9lhinstaller_v2_panda.zip`](magnet:?xt=urn:btih:502d3731fb5d4bec2fcdfbd21e6a08f2125dc583&dn=safea9lhinstaller%5Fv2%5Fpanda.zip&tr=udp%3A%2F%2Ftracker.coppersurfer.tk%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=http%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=udp%3A%2F%2Fzer0day.ch%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.leechers-paradise.org%3A6969%2Fannounce&tr=http%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2F9.rarbg.com%3A2710%2Fannounce&tr=udp%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=http%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker1.wasabii.com.tw%3A6969%2Fannounce&tr=http%3A%2F%2Ftracker.baravik.org%3A6970%2Fannounce&tr=http%3A%2F%2Ftracker.tfile.me%2Fannounce&tr=udp%3A%2F%2Ftorrent.gresille.org%3A80%2Fannounce&tr=http%3A%2F%2Ftorrent.gresille.org%2Fannounce&tr=udp%3A%2F%2Ftracker.yoshi210.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.tiny-vps.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.filetracker.pl%3A8089%2Fannounce)
* The latest release of [Luma3DS](https://github.com/AuroraWright/Luma3DS/releases)
* The latest release of [Decrypt9WIP](https://github.com/d0k3/Decrypt9WIP/releases/latest)
* The latest release of [GodMode9](https://github.com/d0k3/GodMode9/releases/latest)
* The 0_25_3 (latest version) PANDA / SNAKE CIAs `.zip` file for your device and region:
  +    [SNAKE - 0_25_3 - EUR](magnet:?xt=urn:btih:1342b804d9340d49917fe6a35290f0b1b79b6c32&dn=SystemUpdater%5FSNAKE-0%5F25%5F3-EU%5Fcias.zip&tr=udp%3A%2F%2Ftracker.coppersurfer.tk%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=http%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=udp%3A%2F%2Fzer0day.ch%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.leechers-paradise.org%3A6969%2Fannounce&tr=http%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2F9.rarbg.com%3A2710%2Fannounce&tr=udp%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=http%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker1.wasabii.com.tw%3A6969%2Fannounce&tr=http%3A%2F%2Ftracker.baravik.org%3A6970%2Fannounce&tr=http%3A%2F%2Ftracker.tfile.me%2Fannounce&tr=udp%3A%2F%2Ftorrent.gresille.org%3A80%2Fannounce&tr=http%3A%2F%2Ftorrent.gresille.org%2Fannounce&tr=udp%3A%2F%2Ftracker.yoshi210.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.tiny-vps.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.filetracker.pl%3A8089%2Fannounce)    
  +    [SNAKE - 0_25_3 - JPN](magnet:?xt=urn:btih:b0376718bd7c83244dd4bf440e3b1e4e2513637a&dn=SystemUpdater%5FSNAKE-0%5F25%5F3-JP%5Fcias.zip&tr=udp%3A%2F%2Ftracker.coppersurfer.tk%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=http%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=udp%3A%2F%2Fzer0day.ch%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.leechers-paradise.org%3A6969%2Fannounce&tr=http%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2F9.rarbg.com%3A2710%2Fannounce&tr=udp%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=http%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker1.wasabii.com.tw%3A6969%2Fannounce&tr=http%3A%2F%2Ftracker.baravik.org%3A6970%2Fannounce&tr=http%3A%2F%2Ftracker.tfile.me%2Fannounce&tr=udp%3A%2F%2Ftorrent.gresille.org%3A80%2Fannounce&tr=http%3A%2F%2Ftorrent.gresille.org%2Fannounce&tr=udp%3A%2F%2Ftracker.yoshi210.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.tiny-vps.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.filetracker.pl%3A8089%2Fannounce)     
  +    [SNAKE - 0_25_3 - USA](magnet:?xt=urn:btih:d3c4b0083f5e4f093ff3f96e8b396f6ed968fcd6&dn=SystemUpdater%5FSNAKE-0%5F25%5F3-US%5Fcias.zip&tr=udp%3A%2F%2Ftracker.coppersurfer.tk%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=http%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=udp%3A%2F%2Fzer0day.ch%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.leechers-paradise.org%3A6969%2Fannounce&tr=http%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2F9.rarbg.com%3A2710%2Fannounce&tr=udp%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=http%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker1.wasabii.com.tw%3A6969%2Fannounce&tr=http%3A%2F%2Ftracker.baravik.org%3A6970%2Fannounce&tr=http%3A%2F%2Ftracker.tfile.me%2Fannounce&tr=udp%3A%2F%2Ftorrent.gresille.org%3A80%2Fannounce&tr=http%3A%2F%2Ftorrent.gresille.org%2Fannounce&tr=udp%3A%2F%2Ftracker.yoshi210.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.tiny-vps.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.filetracker.pl%3A8089%2Fannounce)     
  +    [SNAKE - 0_25_3 - KOR](magnet:?xt=urn:btih:63da48eb7dea5713c0e3d094ca18d869879fff6b&dn=SystemUpdater%5FSNAKE-0%5F25%5F3-KR%5Fcias.zip&tr=udp%3A%2F%2Ftracker.coppersurfer.tk%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=http%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=udp%3A%2F%2Fzer0day.ch%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.leechers-paradise.org%3A6969%2Fannounce&tr=http%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2F9.rarbg.com%3A2710%2Fannounce&tr=udp%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=http%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker1.wasabii.com.tw%3A6969%2Fannounce&tr=http%3A%2F%2Ftracker.baravik.org%3A6970%2Fannounce&tr=http%3A%2F%2Ftracker.tfile.me%2Fannounce&tr=udp%3A%2F%2Ftorrent.gresille.org%3A80%2Fannounce&tr=http%3A%2F%2Ftorrent.gresille.org%2Fannounce&tr=udp%3A%2F%2Ftracker.yoshi210.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.tiny-vps.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.filetracker.pl%3A8089%2Fannounce)     
~
  +    [PANDA - 0_25_3 - EUR](magnet:?xt=urn:btih:67c40a7bf19b01a93a595eebeb9dc684d2b625e4&dn=SystemUpdater%5FCTR-0%5F25%5F3-EU%5Fcias.zip&tr=udp%3A%2F%2Ftracker.coppersurfer.tk%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=http%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=udp%3A%2F%2Fzer0day.ch%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.leechers-paradise.org%3A6969%2Fannounce&tr=http%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2F9.rarbg.com%3A2710%2Fannounce&tr=udp%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=http%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker1.wasabii.com.tw%3A6969%2Fannounce&tr=http%3A%2F%2Ftracker.baravik.org%3A6970%2Fannounce&tr=http%3A%2F%2Ftracker.tfile.me%2Fannounce&tr=udp%3A%2F%2Ftorrent.gresille.org%3A80%2Fannounce&tr=http%3A%2F%2Ftorrent.gresille.org%2Fannounce&tr=udp%3A%2F%2Ftracker.yoshi210.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.tiny-vps.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.filetracker.pl%3A8089%2Fannounce)    
  +    [PANDA - 0_25_3 - JPN](magnet:?xt=urn:btih:e9d2ee50bef53e0e9c7f1bfeed49475a3d14d426&dn=SystemUpdater%5FCTR-0%5F25%5F3-JP%5Fcias.zip&tr=udp%3A%2F%2Ftracker.coppersurfer.tk%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=http%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=udp%3A%2F%2Fzer0day.ch%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.leechers-paradise.org%3A6969%2Fannounce&tr=http%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2F9.rarbg.com%3A2710%2Fannounce&tr=udp%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=http%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker1.wasabii.com.tw%3A6969%2Fannounce&tr=http%3A%2F%2Ftracker.baravik.org%3A6970%2Fannounce&tr=http%3A%2F%2Ftracker.tfile.me%2Fannounce&tr=udp%3A%2F%2Ftorrent.gresille.org%3A80%2Fannounce&tr=http%3A%2F%2Ftorrent.gresille.org%2Fannounce&tr=udp%3A%2F%2Ftracker.yoshi210.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.tiny-vps.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.filetracker.pl%3A8089%2Fannounce)     
  +    [PANDA - 0_25_3 - USA](magnet:?xt=urn:btih:a0239f152985f2f9ff514587cc1e76397283f956&dn=SystemUpdater%5FCTR-0%5F25%5F3-US%5Fcias.zip&tr=udp%3A%2F%2Ftracker.coppersurfer.tk%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=http%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=udp%3A%2F%2Fzer0day.ch%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.leechers-paradise.org%3A6969%2Fannounce&tr=http%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2F9.rarbg.com%3A2710%2Fannounce&tr=udp%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=http%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker1.wasabii.com.tw%3A6969%2Fannounce&tr=http%3A%2F%2Ftracker.baravik.org%3A6970%2Fannounce&tr=http%3A%2F%2Ftracker.tfile.me%2Fannounce&tr=udp%3A%2F%2Ftorrent.gresille.org%3A80%2Fannounce&tr=http%3A%2F%2Ftorrent.gresille.org%2Fannounce&tr=udp%3A%2F%2Ftracker.yoshi210.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.tiny-vps.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.filetracker.pl%3A8089%2Fannounce)     
  +    [PANDA - 0_25_3 - CHN](magnet:?xt=urn:btih:4c0edc918713d596d0ccd4e6ba4f45937a97f89a&dn=SystemUpdater%5FCTR-0%5F25%5F3-CN%5Fcias.zip&tr=udp%3A%2F%2Ftracker.coppersurfer.tk%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=http%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=udp%3A%2F%2Fzer0day.ch%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.leechers-paradise.org%3A6969%2Fannounce&tr=http%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2F9.rarbg.com%3A2710%2Fannounce&tr=udp%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=http%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker1.wasabii.com.tw%3A6969%2Fannounce&tr=http%3A%2F%2Ftracker.baravik.org%3A6970%2Fannounce&tr=http%3A%2F%2Ftracker.tfile.me%2Fannounce&tr=udp%3A%2F%2Ftorrent.gresille.org%3A80%2Fannounce&tr=http%3A%2F%2Ftorrent.gresille.org%2Fannounce&tr=udp%3A%2F%2Ftracker.yoshi210.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.tiny-vps.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.filetracker.pl%3A8089%2Fannounce)     
  +    [PANDA - 0_25_3 - KOR](magnet:?xt=urn:btih:7202afc7a6ef30f7536fddabf9dd867553f1be2e&dn=SystemUpdater%5FCTR-0%5F25%5F3-KR%5Fcias.zip&tr=udp%3A%2F%2Ftracker.coppersurfer.tk%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=http%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=udp%3A%2F%2Fzer0day.ch%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.leechers-paradise.org%3A6969%2Fannounce&tr=http%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2F9.rarbg.com%3A2710%2Fannounce&tr=udp%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=http%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker1.wasabii.com.tw%3A6969%2Fannounce&tr=http%3A%2F%2Ftracker.baravik.org%3A6970%2Fannounce&tr=http%3A%2F%2Ftracker.tfile.me%2Fannounce&tr=udp%3A%2F%2Ftorrent.gresille.org%3A80%2Fannounce&tr=http%3A%2F%2Ftorrent.gresille.org%2Fannounce&tr=udp%3A%2F%2Ftracker.yoshi210.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.tiny-vps.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.filetracker.pl%3A8089%2Fannounce)     
  +    [PANDA - 0_25_3 - TWN](magnet:?xt=urn:btih:aa27d8e2f17eb0e20a9084260f5845c2d9c115dc&dn=SystemUpdater%5FCTR-0%5F25%5F3-TW%5Fcias.zip&tr=udp%3A%2F%2Ftracker.coppersurfer.tk%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=http%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=udp%3A%2F%2Fzer0day.ch%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.leechers-paradise.org%3A6969%2Fannounce&tr=http%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2F9.rarbg.com%3A2710%2Fannounce&tr=udp%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=http%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker1.wasabii.com.tw%3A6969%2Fannounce&tr=http%3A%2F%2Ftracker.baravik.org%3A6970%2Fannounce&tr=http%3A%2F%2Ftracker.tfile.me%2Fannounce&tr=udp%3A%2F%2Ftorrent.gresille.org%3A80%2Fannounce&tr=http%3A%2F%2Ftorrent.gresille.org%2Fannounce&tr=udp%3A%2F%2Ftracker.yoshi210.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.tiny-vps.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.filetracker.pl%3A8089%2Fannounce)     

#### Instructions

##### Section I - Prep work

1. **Copy the `/files9/` folder on your SD card to a safe location on your computer and back it up to multiple locations (such as online file storage); the files inside could save you from total data loss if you break your system**
2. Create a folder named `cias` on the root of your SD card if it does not already exist
2. Copy _the contents of_ `safea9lhinstaller_v2_panda.zip` to the root of your SD card
12. Copy `arm9loaderhax.bin` from the `out` folder in the Luma3DS `.zip` to the root of your SD card
13. Create a folder named `luma` on the root of your SD card
14. Create a folder named `payloads` in the `luma` folder on your SD card
15. Copy `Decrypt9WIP.bin` from the Decrypt9WIP `.zip` to the `/luma/payloads/` folder on your SD card and rename `Decrypt9WIP.bin` to `start_Decrypt9WIP.bin`
16. Copy `GodMode9.bin` from the GodMode9 `.zip` to the `/luma/payloads/` folder on your SD card and rename `GodMode9.bin` to `up_GodMode9.bin`
16. Copy `aeskeydb.bin` from `aeskeydb_panda.zip` to the `/files9/` folder on your SD card
17. Delete the 0_23_5 SystemUpdater folder from the root of your SD card
17. Extract the 0_25_3 SystemUpdater `.zip` to the root of your SD card

##### Section II - Installing arm9loaderhax

1. Reinsert your SD card into your 3DS
2. Do the steps for installing arm9loaderhax on your device:
3. You should be on 0_15_20
4. Go to `http://dukesrg.github.io/2xrsa.html?arm11.bin` on your 3DS
  + If you get an error, [follow this troubleshooting guide](troubleshooting#ts_browser)
  + If you get a glitched screen, [follow this troubleshooting guide](troubleshooting#ts_safe_a9lh_screen)
5. Press (Select) to Full Install
6. The installer will now install arm9loaderhax on your device (this is very fast)
7. Shut down your console, hold the power button until it turns off if necessary
8. Copy your console specific `OTP.bin` from the `/a9lh/` folder on your SD card to a safe location on your computer and back it up to multiple locations (such as online file storage), then reinsert your SD card into your 3DS

##### Section III - Configuring Luma3DS

1. Hold select on boot to enter the Luma3DS menu
  + Make sure to start holding the button before pressing power
  + If you get a black screen, [follow this troubleshooting guide](troubleshooting#ts_sys_a9lh)   
  + If you boot to SafeA9LHInstaller, [follow this troubleshooting guide](troubleshooting#ts_safe_a9lh)
2. Use the (A) button and the D-Pad to turn on the following:    
  + **"Autoboot SysNAND"**
  + **"Use SysNAND FIRM if booting with R"**
  + **"Show NAND or user string in System Settings"**
3. If you are using a **New 3DS**, you should *also* enable the following:
  + **"New 3DS CPU" to "Clock+L2(x)"**
    + This will increase the framerate of many games, but may cause instability in others
    + If some games do not work properly, disable this option and try again
4. Press Start to save and reboot
  + If you get a black screen, just continue to the next section   

##### Section IV - Restoring the System

1. Copy `NANDmin.bin` to the `/files9/` folder on your SD card
2. Open Decrypt9WIP from arm9loaderhax by holding (Start) on boot
3. Go to "SysNAND Options"
3. Go to "SysNAND Backup/Restore"
4. Restore **(keep a9lh)** from `NANDmin.bin`
5. Press (Start) to reboot
6. Using Dev Menu, navigate to the 0_25_3 SystemUpdater folder
4. Press (L + R + A) to install all CIAs
3. Navigate to the NATIVE_FIRM CIA
  + Old 3DS PANDA / SNAKE: `0004013800000002.cia`
  + New 3DS PANDA / SNAKE: `0004013820000002.cia`
4. Update your PANDA / SNAKE's FIRM by pressing (Start + Y) while highlighting the NATIVE_FIRM CIA
6. You can also update your PANDA / SNAKE using a CTR System Updater (CSU)
  + **This is only safe for Luma3DS version 6.6 (commit 0b16d88) and above!**
  + **Attempting to update your PANDA / SNAKE using a CSU on any lower Luma3DS version will BRICK your device!**

##### Section V - CTRNAND Luma3DS

1. Open GodMode9 from arm9loaderhax by holding (Start) on boot
2. Navigate to `SDCARD`
3. Press (Y) on `arm9loaderhax.bin` to copy it
4. Press (B) to go back to the main menu
4. Navigate to `SYSNAND CTRNAND`
5. Press (Y) to paste a copy of `arm9loaderhax.bin`
6. Select "Copy path(s)"
6. Press (A) to unlock SysNAND writing, then input the key combo given
7. Press Start to reboot

##### Section VI - Finalizing setup

2. Open Dev Menu
7. Install `lumaupdater.cia`\
8. Exit with the home button
9. Launch the Homebrew Launcher from the home menu
10. Select "DSP Dump"
11. Press (Start) when prompted to exit
15. Reboot with the SD card removed
  + Booting the device at least once with the SD card removed will allow you to configure the CTRNAND based luma installation
16. Use the (A) button and the D-Pad to turn on the following:    
  + **"Show NAND or user string in System Settings"**
3. If you are using a **New 3DS**, you should *also* enable the following:
  + **"New 3DS CPU" to "Clock+L2(x)"**
    + This will increase the framerate of many games, but may cause instability in others
    + If some games do not work properly, disable this option and try again
14. Reinsert your SD card, then press Start to save and reboot!

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
You will now boot a Custom Firmware based SysNAND by default.    
You can now hold (Select) on boot to launch the Luma3DS configuration menu.    
You can now hold (Start) on boot to launch Decrypt9WIP
You can now hold (Up) on boot to launch GodMode9
{% endcapture %}

<div class="notice--info">{{ notice-6 | markdownify }}</div>

To use [NTR CFW](https://github.com/44670/BootNTR/), get `ntr.bin` from the appropriate `.zip` on [this](https://github.com/44670/BootNTR/releases) page and copy it to the root of your SD card, then install `BootNTR.cia` from [this](https://github.com/astronautlevel2/BootNTR/releases/latest) page.
{: .notice--info}

Keep your `NANDmin.bin` file, it can be restored by Decrypt9 to save you from a brick in the future.
{: .notice--info}

You can remove your NAND backups from `/files9/` as long as you still have them backed up to a safe location.
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

For information on using Luma3DS's various features, check out [its wiki](https://github.com/AuroraWright/Luma3DS/wiki/Options-and-usage).
{: .notice--success}
