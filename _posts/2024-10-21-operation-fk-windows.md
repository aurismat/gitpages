---
layout: post
title:  "Operation: Fuck Windows"
date:   2024-10-21 16:25:00 +0300
categories: blog
excerpt: <i>When Windows 10 couldn’t… Windows 10 LTSC could.</i>
---

***warning:** huge amounts of OS installation autism ahead. Casual readers, proceed with caution!*

Before even contemplating this operation, my previous Windows 10 installation had been ***rock solid***: no random crashes, no random driver crashes, no nothing really!
Only instance of it going belly up had been when I had installed Riot’s Vanguard and it kept disconnecting my network adapter, which was a bummer - but ultimately I didn’t stick around to see them add that shitty AC to [League with patch 14.9][league-ac-patch], and Valorant wasn’t really my cup of tea either, so… rock solid!

However, since I had bought a budget M.2 to SATA SSD to get me by when I had purchased parts to build my main PC back in 2019, it had served me well for what it was, but it’s age and speed and lack of storage space had started to show over the years(mostly storage space).
512 gigabytes of storage for system + a handful of games + a fuckton of software + a VM or two??? Yeah that was never going to work out.

And as such, **Operation: Fuck Windows** had started to take shape. Now, why the hell would I ever want to bin Windows 10 if it had been working so well?

For one, I really wanted to upgrade my SSD for both storage space and speed reasons - as much as SATA M.2 SSDs are great, your usual PCIe Gen 3.0 NVMe SSD runs **circles** around them!
And seeing that the storage space is becoming a lot more affordable([Moore’s law][moore], but twice as slow in this case), I could now get two terabytes of blazing fast SSD storage for ~150 euros.

For another reason, Windows 10 *consumer* editions would see End-of-Life at October 2025, which is a move I really don’t get, seeing that Windows 11 is still experiencing feature creep and [keeps constantly breaking for users][win11-kernel-failure]; but whatever.
Not a huge deal to me, since I had plans to install Linux as a daily driver for my main PC for a while now, and I had been using [Manjaro][manjaro], a fork of [Arch Linux (btw)][archlinux] on my work laptop and it’s been very usable for a lean, mean coding machine over there!

So, I had taken the past week or so(as of writing of this blog post) to set up this plan, I ended up purchasing a [Western Digital SN850X 2TB SSD][sn850x], a speedy boi with plenty of space and most importantly, a dedicated DRAM cache - I had heard of horror stories of DRAM-less SSD’s that utilize host’s memory buffer(ELI5: use RAM as a DRAM cache for the SSD) [crash out on Windows 11][win11-ssd-crash], so I didn’t want that to happen.
Probably not something that *would* occur on Linux, but didn’t want to take my chances.
Additionally, I had heard of stories of SSD’s starting to throttle their read/write performance while under high loads to a point where they overheat, so I had also ordered a [beQuiet! MC1 Pro SSD cooler][mc1] in order to keep those temps under control.

And as such, last Friday, I had received all the parts in the mail, and Operation: Fuck Windows could really go underway. Arch Linux installer was hungry for some action.

## Friday: The Night of the Reckoning

So, after getting home from a long-ass day at work, I was eager to install my new SSD and give it a spin in some Arch Linux. But, *not so fast!*

Initially I had thought I’d be able to easily swap it in and out of my case in the cramped space I had between the tower CPU cooler and my GPU - but that plan flopped really quickly. So I had to remove my PC from my shitty plastic shelf that keeps it behind my desk, and tear it down - and oh boy should I have cleaned my PC from dust sooner! Also, one interesting problem location I had never seen as an issue was the lower bit - where the power supply goes! That part between the case and PSU isn’t reachable, but I saw it should be cleaned, and oh lordy - dismount your PSUs when cleaning your PC, people! That poor PSU fan does a lot of work to keep your PC alive! Give it the best chance you can! *Please.*

Anyway, after all those shenanigans, Arch Linux was ready to be installed. Now, don’t tell the ‘*archlunix elitists*’ that I told you this - but `archinstall` is a perfectly usable installer for those too lazy to set up Arch the [old way][archinstall].
Sure, it’s nowhere near Ubuntu Server’s ncurses-based installer GUI, but it’s perfectly serviceable to get people to a functional Arch install!

Initially I was confused as to why the installer dedicated 53 gigabytes of space for root(`/`) when you set it to auto-partition with a `/home` partition and not a nice number like 64 - but I solved that quickly. Some hiccups later(which may or may not involve manual partitioning bullshit) and before the end of an hour I was up and running in Arch with the KDE Plasma desktop! YIPPEE!🥳

Aaaand this is where all the small issues began. Especially issues that, working with Windows 10 for nearly a decade, would just trigger my undiagnosed ADHD:
- Logon screen(called desktop manager greeters in Linux) would not only use the wrong display, but also show the greeter on all screens in their landscape orientation;
- VSync between my main monitor with 144Hz refresh rate and side monitors with 60Hz refresh rate felt really wonky, making the overall desktop experience feel a little off;
- I couldn’t get window zones, like Windows with [PowerToys][powertoys] does it with [FancyZones][fancyzones] - a really big deal breaker for me, but I found a serviceable substitute so that has somewhat curbed my type of autism…

> Never mind that, I can run all of my games now!

*famous last words*

## Saturday: Where it all came crashing down

So on Saturday, seeing the last night's success that Elden Ring loading was, among with a couple other games, I had decided I’d try to tackle VR support for my setup - which, if failed would be a huge deal breaker for me.
Now, natively Meta doesn’t support anything for Linux(which is a huge untapped market - Meta, *please* do this at some day!), nor does SteamVR streaming to their app already on Meta Marketplace work *yet* - so we’re left on uncharted waters - or are we?
There has been a project that’s trying to bring a lot of headsets to open-sourced wireless streaming called ALVR, and it has been a project I’ve been keeping my eye on for a while - but never required using it because Steam’s own VR streaming works a treat and wired connections work without a hitch on Windows 10 anyways!

So, after some hiccups with installing the correct AUR package(for Nvidia users - install `alvr-nvidia` with your favourite AUR helper), I got it up and working - but it was awful performance! No matter how much I had attempted to fix it(by switching around quality settings, encoder presets, everything else) - I could not get it to work reliably to a point where it’s just ‘here ya go, it just works’ ideology. Now sure, that’s never going to happen on Linux - UNLESS Valve actually pioneers it, as they have seemingly pioneered Linux gaming, handheld hardware and much more. But alas, knowing that this would be a huge deal-breaker for me, even though I play VR about once per week - the dream of an open-sourced OS running on my PC would have to be put on hold, at least for now.

Now, after doing some research, I had found that Windows 10 has more versions than just your good old consumer editions - there’s some Enterprise editions, including LTSC IoT(abbr: Long Term Support Channel Internet of Things) edition of Windows 10 2021(which is years old by now, I know); but, the most important bit is that those versions will [keep receiving security patches up until 2032!][ltsc-notice] Of course, those versions are meant for enterprise use and God forbid, if the consumers would get their hands on these it’d be madness!

***\*cough\*** look up ‘windows 10 activation scripts github massgravel’ and you’ll find what you need*

So yeah, in the future, will I reinstall back to Linux? ***Probably**.* Here’s the catches that stop me from using it fully *for now*:
- Previous gripes with KDE Plasma(listed in bullet list above);
- VR support is shoddy and takes a long time to get right at best, and outright unusable at worst;
- Audio routing is a bit of a nightmare(maybe I wasn’t accustomed to creating virtual audio devices and routing them, i don’t know - but it’d be neat if Pipewire-capable frontend apps would support creating dummy audio sinks for easier routing purposes);
- Doesn’t feel like a ‘just works’ package just yet - the pipe dream of that is long from a reality.
- Not a huge deal breaker for me since I rarely play any offenders in this case - but many anti-cheats and some DRM outright deny Linux, most notably EA, Riot’s Vanguard, Activision and many more; [too many to list here][areweacyet].

So for now, I will continue using Windows 10 LTSC IoT on my main PC until either it goes EOL, or features start breaking on it, like the crazy decision to deprecate Windows Mixed Reality on Windows 11 24H2([[Windows deprecated features list]][win-deprecate] [[Redditors dropping PSAs WMR stops working]][reddit-wmr-remove]).
If anything, I reckon Windows 11 is a skip version - just how Windows Vista and 8 were(as in, Windows XP, 7 and 10 were great, but versions in between were just… awful).

Anyway, thanks for reading, put up your current gripes with Windows(or Linux, if you’re using it!) in the comments so I can mald with you(or laugh at something silly breaking orz). I’m still working on my Meta Quest 2 review in the background, but it’s a low priority on my list so it might still take a while. Video production is a little higher priority now, which at my pace might enter production by the end of October(or not idfk, game retrospective video scripts take long to write orz)

[league-ac-patch]: https://www.reddit.com/r/leagueoflegends/comments/1civ4l7/update_from_riot_on_vanguard/
[moore]: https://en.wikipedia.org/wiki/Moore's_law
[win11-kernel-failure]: https://answers.microsoft.com/en-us/windows/forum/all/windows-24h2-causing-kernal-power-failure/81c2379e-44d7-49c6-a97c-27aaf086d635
[manjaro]: https://manjaro.org/
[sn850x]: https://www.westerndigital.com/en-in/products/internal-drives/wd-black-sn850x-nvme-ssd
[archlinux]: https://archlinux.org/
[win11-ssd-crash]: https://www.tomshardware.com/pc-components/ssds/western-digital-releases-fix-for-windows-11-24h2-bsods-users-are-strongly-advised-to-update-their-ssd-firmware
[mc1]: https://www.bequiet.com/en/accessories/2252
[archinstall]: https://wiki.archlinux.org/title/Installation_guide
[powertoys]: https://learn.microsoft.com/en-us/windows/powertoys/
[fancyzones]: https://learn.microsoft.com/en-us/windows/powertoys/fancyzones
[ltsc-notice]: https://learn.microsoft.com/en-us/windows/whats-new/ltsc/whats-new-windows-10-2021#lifecycle
[areweacyet]: https://areweanticheatyet.com/
[win-deprecate]: https://learn.microsoft.com/en-us/windows/whats-new/deprecated-features
[reddit-wmr-remove]: https://www.reddit.com/r/virtualreality/comments/1ftrjmf/warning_windows_11_24h2_update_removes_wmr_support/
