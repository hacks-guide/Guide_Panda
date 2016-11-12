---
layout: splash
permalink: /
header:
  overlay_color: "#5e616c"
  overlay_image: home-page-feature.jpg
  overlay_filter: 0.5
  cta_label: "Get Started"
  cta_url: "/get-started"
  caption:
excerpt: 'A complete guide to developer 3DS custom firmware, <br /> from stock to arm9loaderhax.<br />'
---

**This guide is for developer ("PANDA") consoles _only_!**
{: .notice--danger}

**This guide needs *your* help to seed [these](https://plailect.github.io/Guide/rss.xml) torrents!**
{: .notice--info}

**To use the [torrent](https://en.wikipedia.org/wiki/Torrent_file) files in this guide, you will need a torrent client like [Transmission](https://sourceforge.net/projects/trqtw/files/latest/download)**
{: .notice--info}

**Read all of the introductory pages before proceeding.**
{: .notice--warning}

## What is Homebrew?

[**Homebrew**](https://en.wikipedia.org/wiki/List_of_homebrew_video_games) usually refers to software that is not authorized by Nintendo. It allows you to run homebrew games, tools like save editing and backup, and emulators for various older systems.

In most cases, running homebrew on your console is 100% free using just the Internet Browser. There are also various other exploits in commercial games to get homebrew running.

## What is Custom Firmware?

**Custom Firmware** ("CFW") enables you to use more advanced hacks that userland homebrew can't easily do. For instance, signature patches let you install unsigned titles that appear right on your HOME Menu.

CFW can be easily set up on any console that is on 9.2.0-20 or lower. Other versions can be downgraded, most for free or with just an exploit game.

## What does this guide install?

This guide has the end goal of taking a completely unmodified 3DS from stock
firmware to arm9loaderhax powered Custom Firmware.

Arm9loaderhax is the newest and best method of launching Custom Firmware that gives us nearly full control of the system only milliseconds into boot, which is similar to the effect of BootMii for the Wii.

The benefits of arm9loaderhax over other Custom Firmware launch methods are numerous, and as such it is recommended to use this guide over any other that relies on outdated software (such as menuhax or rxTools).

## What do I need to know before starting?

+ **Before beginning the guide, you must know the risks of 3DS hacking: EVERY time you modify your system, there is always the potential for an UNRECOVERABLE brick. They're rare, but still a possibility so make sure you follow ALL directions EXACTLY.**
+ This guide will work on New 3DS, Old 3DS, and 2DS in all regions on on all firmwares (except for Old 3DS JPN).
+ If everything goes according to plan, you will lose no data and end up with everything that you started with.
+ A large part of this guide is lengthy NAND dumps and downgrades, so the entire process can take *several* hours thanks to the 3DS's slow processor.
+ **Keep the device plugged in and charged throughout the entire process to avoid data loss or damage from an unexpected power-off!**
+ Your SD card should be [MBR, not GPT](http://www.howtogeek.com/245610/) (the SD card that comes with the device will be MBR by default).
+ If you need to format a brand new SD card, you can use [`guiformat`](http://www.ridgecrop.demon.co.uk/index.htm?guiformat.htm) and set to an Allocation Unit Size of 32K.
+ The 2DS is essentially identical to the Old 3DS in terms of software, and that any steps which say "Old 3DS" also apply to 2DS.
