---
title: "Installing a Smart TV the hard way"
date: 2025-07-14
wordcount: true
---

# Installing a Smart TV the hard way

I may be re-inventing the wheel with a bit of this, but I'm trying to build up a Smart TV/FireStick/ChromeCast replacement that I can just run on off of a mini PC. Why? Because fuck data-harvesting tech companies.

## Hardware

This device will serve as the interface for my lobotomized Smart TV. I'm not sure what the appropriate name for this type of device is; it's somewhere between the antiquated "set-top box" and those gumsticks that are jammed into an HDMI port of nearly every living room TV in 2025.

The only television I own is a "SAMSUNG 55-Inch Class Crystal UHD 4K Bed-H Series HDR Business Pro TV (LH55BEDHLG, 2024 Model)". Purchasing a "dumb TV" is a Herculean task in current year. (Those poor tech companies don't get to serve you ads or attempt the usual means of IoT surveillance if you bought a dumb TV.) Indeed, this a smart TV manufactured by a notorious data harvester. However, I will never willingly connect this device to the internet. Moreover, being a business (think of the TVs that show shitty powerpoints in waiting rooms that run 24 hours a day), can reasonably approximately the functions of a dumb TV with enough configuration.

Below is the `fastfetch` for the Beelink Mini PC that I'm using as my poor test subject.

```
          :+ooo/.      ./ooo+:              root@redbox
        :+ooooooo/.  ./ooooooo+:            -----------
      :+ooooooooooo::ooooooooooo+:          OS: LibreELEC (official): 12.0.2 x86_64
    :+ooooooooooo+-  -+ooooooooooo+:        Host: MINI S
  :+ooooooooooo+-  --  -+ooooooooooo+:      Kernel: Linux 6.6.71
.+ooooooooooo+-  :+oo+:  -+ooooooooooo+-    Uptime: 2 hours, 4 mins
-+ooooooooo+-  :+oooooo+:  -+oooooooooo-    Shell: sh
  :+ooooo+-  :+oooooooooo+:  -+oooooo:      
    :+o+-  :+oooooooooooooo+:  -+oo:        Terminal: /dev/pts/0
     ./   :oooooooooooooooooo:   /.         CPU: Intel(R) Celeron(R) N5095 (4) @ 2.90 GHz
   ./oo+:  -+oooooooooooooo+-  :+oo/.       GPU: Intel UHD Graphics @ 0.75 GHz [Integrated]
 ./oooooo+:  -+oooooooooo+-  :+oooooo/.     Memory: 490.05 MiB / 7.42 GiB (6%)
-oooooooooo+:  -+oooooo+-  :+oooooooooo-    Swap: Disabled
.+ooooooooooo+:  -+oo+-  :+ooooooooooo+.    Disk (/): 213.00 MiB / 213.00 MiB (100%) - squashfs [Read-only]
  -+ooooooooooo+:  ..  :+ooooooooooo+-      Disk (/flash): 247.78 MiB / 511.72 MiB (48%) - vfat [Read-only]
    -+ooooooooooo+:  :+ooooooooooo+-        Disk (/storage): 38.18 MiB / 116.32 GiB (0%) - ext4
      -+oooooooooo+::+oooooooooo+-          Disk (/var/media/sdb1-ata-Corsair_Force_LS): 212.40 GiB / 223.57 3
        -+oooooo+:    :+oooooo+-            
          -+oo+:        :+oo+-              Locale: C.UTF-8
            ..            ..
```

Damn, LibreELEC doesn't even use `bash`. (I didn't end up using LibreELEC, but I installed it long enough to grab this.)

## Software
The primary GUI that will serve as my "Smart TV-like interface" is Kodi, a FOSS software media player and entertainment hub. LibreELEC is an extremely minimal linux distro that *just* runs Kodi. This is *almost* the perfect solution, I'll always prefer a lighter software stack. Consquently, however, it doesn't even have a package manager. This is unfortunate because I'm planning to launch a few other things on this device. Instead, I'm going to install a "proper" linux distro (likely Arch) and set up Kodi from there.

The software functionality of this device is broadly obvious: to behave like a Smart TV. Below is a more precise outline of the functions this device must serve:

1. Run linux. It's the best.
2. Provide a user interface that might be found on a typical media center/smart TV
3. Serve YouTube videos (sorry, I'm still gen Z)
4. Serve Twitch stream  (what can I say, I love SM64 speedrunners)
5. Serve videos that might be peddled by Edward Teach 🏴‍☠️
6. Block ads on all video streaming services
7. Run Steam
8. Interface with a local media server

and here are some likely solutions to each of these tasks:

1. Arch Linux. It's the best of the best. (Rocky is a close second.)
2. Kodi, as far as I can tell there's no contest
3. Kodi plugin
4. Kodi plugin
5. Kodi plugin? Will need to do more research.
6. PiHole
7. Just install Steam
8. Jellyfin

1-4: Easy enough.

5: Something something heck yeah. I imagine that this will be tricky, since these are often just media-serving websites without APIs. Never underestimate the open source community, however. I'm sure a solution exists.

6: I do not have a dedicated PiHole machine on my network currently. The Raspberry Pi 3 that I got in high school recently passed on to the great subnet in the sky, and I don't have another machine that would be appropriate. Instead, I plan on just running PiHole from this guy as well through Docker. We'll see how well that works.

7: Apparently you can stream games from another machine on your network with Steam. I.e., I'll be able to play GPU-intensive games on my TV by streaming the game from my desktop to my Mini PC. I've never done this before, but apparently it's pretty easy. My desktop and the Mini PC each have 1Gbps NICs, which should suffice.

8: I've never interfaced with Jellyfin either, but in the next year or so, I plan on setting up a ~100TB media server / archive. You might see me on r/datahoarders. I plan to use Jellyfin to interface with this server.

This is all still very much in the planning stage. There are likely flaws with some of these plans, but that's fantastic. I have a lot to learn.

## Some more thoughts

These are not final thoughts, since I've barely begun this project. I expect to produce a write-up if/once I reasonably complete my goals here.

LibreELEC is a very nice project and it's a shame the scope of `redbox` exceeds the single-responsibility principle as executed by the developers/maintainers of LibreELEC. Also thanks to the developers/maintainers of Kodi, obviously.

This device will also inherit the `___box` naming scheme of all my machine. Thanks to Joe for coming up with `redbox` for my media streaming box.

Dumb TVs are great. Thanks for reading.

GB
