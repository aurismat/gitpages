---
layout: post
title: "Operation Fuck Windows 2: Electric Boogaloo"
date: 2026-10-27 09:45:00 +0200
categories: blog
excerpt: <i>The 8 month conclusion.</i>
---
Man, a little over two years has passed since my last attempt to dabble with Linux, huh? Crazy.

A lot has changed, both in my personal home setup and in the market, so I think it's time to put it out there: I've been running Linux successfully, as a Windows power-user, for well over eight months now, and I couldn't be happier.

But this begs the question - why, in the year of 2026, did I decide to try Linux all over again after the relative failure of the first Operation: Fuck Windows back in October of 2024?

## My main PC

Relatively to the launch of Monster Hunter: Wilds(which, for the record - despite it's shortcomings in terms of PC performance is still an amazing game IMHO), I had finally felt the need to upgrade my main rig to be able to play more newer games at better settings - besides, I was a grown ass man at the time with a JOB; so I could treat myself. Unfortunately I had run into the moment of dilemma - do I get the shiny new RX 9070 XT and get FSR4 support right out of the gate, or do I trust AMD to eventually release it for RDNA3 cards and get the best-in-slot for raster graphics of RX 7900 XTX? Well, those who know me - they know which one I went for. And oh boy, what a card is the 7900 XTX! However, the memes of AMD hardware being stupendously powerful and the drivers being a bit of a goofball proved to be true, as official AMD drivers would find ways to rear their ugly head and cause crashes. With enough tuning with the Adrenaline software and using [community-run R.ID patched drivers][r-id-drivers] I was able to highly mitigate the issue, but every now and then it'd reoccur, which was a pretty big pain point. Overall it worked - but it could be better. *Do better, AMD - instead of trying to sell us the new shiny thing.*

That tangent aside - Windows 10 consumer editions have officially ended their support(even though you can get another year of extended security updates, or ESUs, or up to three if you know how) - I cannot rely on an operating system left on life support, and I cannot rely on AI-riddled slop that even [NASA engineers cannot tame][nasa-outlook]. So I was looking for a good solution to get Windows out of my life for good, and after a good motivation from a friend to just "take the plunge. You won't die.", I decided to go fully through planning and execution of this plan. As such, Operation: Fuck Windows 2 the Electric Boogaloo had begun to take shape.

Note, this was well before I was even *aware* of Linus Tech Tips deciding to make another [Linux daily driver video][ltt-challenge], so a lot of my choices were self-researched and informed. The biggest problem I wanted to get through is to reduce my own friction of making the switch. While a lot of the software I already use is cross-platform(I use Krita/KDEnlive for photo/video editing, LibreOffice has been a mainstay for a while, even during my university stint), I had to look out for some gotchas - and I will cover some of these for those who may be looking for a way into the Linux rabbit hole that they may never want to climb back out of - at least from the POV of a washed up VTuber who wants his stuff working yet also wants it to *not* break.

So then, the OS choice. I knew I'd be going with Arch-based distro since I'm well familiar with the ecosystem of pacman and AUR, but which one? [Manjaro seems to be undergoing some internal changes][manjaro-takeover] so I can't expect it to be as well-maintained as I'd want(hell, I'm considering even reinstalling my work laptop to something else!); [Omarchy][omarchy] seemed like a good contender, but it's Hyprland-first approach increased the friction factor(plus the AI-forward development which I wasn't too fond of for an OS) so it was out. [Garuda Linux][garuda-linux] seemed like a good contender but it felt like it was a touch less supported, which left me with either bothering to go through installing pure Arch(doable but lots of pain points), or...

CachyOS!

The rationale for utilizing what at first glance is a gamer-first distro with performance optimizations is not insane. Now, normal Arch works fine, generally - but a lot of setup and maintenance work falls under the user, which is not what I want to do on my computer - I want to keep it in a place where I can have my cake and eat it too - by which I mean that I wanted a distro that is maintainable with good performance, but still has the bleeding-edge software that Arch is known for.

And, after running this distro for about eight months, I want to say that results are in.

So - what did it take to get a Linux main PC running with all the production software that I'd want, including my VTubing stack and perfect OBS running?

A fair bit - but a lot of it is solved already. There's a really fair saying that LTT's Linus has stated - if something doesn't work, it's because someone hasn't been pissed at it enough to fix it. Case in point - I thought I was going to be SOL with VNyan, since I rely on Spout2 to pass through an alpha render of it to OBS - but a kind soul named `hoshinolina` made a wrapper that pipes Spout2 into a Pipewire video stream named [`spout2pw`][spout2pw](which has since been taken over by `tasokait`'s fork - [repo][spout2pw-fork]), and that was essentially a godsent. Initial builds when I had first deployed my install was lacking - I had to make my own scripted workarounds to bind to the correct Spout2 streams to get proper video - but modern versions are really mature and easy to work with, to a point it's seamless once you sic the wrapper.

Likewise, I was expecting my Elgato Stream deck to be another non-starter, since Elgato historically hasn't been good with Linux support. But where vendor refuses to support, community comes through - with a tool like [OpenDeck][opendeck] being a complete-enough solution that I no longer need anything else to keep it around! Granted not all plugins are available, but stopgaps are easily filled by the OpenDeck's capacity to execute scripts, and Windows-based plugins being capable of running via Wine with mixed results!

Likewise, I was expecting Linux to need a bunch of virtual audio cabling to set up stuff for streaming - but Linux builds of OBS support Pipewire capture natively, and very nicely differentiate between multiple apps for multiple streams, which allowed me to keep the setups very clean!

Now, a bit onto the bad, and the ugly. Is it all sunshine and rainbows? Hell no, far from it - due to the fact the X11 and Wayland changes are still in progress, apps like Discord that rely on XWayland as fallbacks are caught in the crossfire and suffer penalties - namely, while the vanilla Discord's screenshare works, more times than not it goes to capture entire system audio rather than just the target window's; other clients have a mitigation for this in a custom screenshare wrapper, but most of those clients run on a web-based version of Discord, meaning they cannot take advantage of proper screenshare encoding properly, causing screenshare quality issues.

Another issue I had encountered was that my computer would hang when I'd put it to sleep. I primarily chalked this up to AMDGPU drivers having some crap in low-power states that caused issues with my chungus RDNA3 card, but over time it seems to have fixed itself by driver firmware updates. Similarly to displays - my Dell U2412M monitor would give some crap with resolutions on boot, but some EDID pinning later I was able to get it back in order.

Now then, the overall experience. Do I miss Windows, or it's boring consistency that works with everything? *In a way* - however, with Linux the same kind of boring consistency is there too, and there are still some growing pains, but overall it's a really rewarding computing experience if you give it an honest try. Is it for everyone? Not at all; I think if you're happy with what Windows gives you right now and you hate to break that comfort zone, or you want/need some software that is 100% borked on Linux - then you should stay(though consider hardening the OS so it stops invading your privacy and gets out of your way); otherwise, if you're willing to adapt, want to do a bit more scripting, and have an OS that respects you and your privacy? Linux might just be for you.

Ultimately, I see no reason to roll back to Windows so I'll be staying for the time being; and with how more and more fixes come in to Linux, with even other platforms like [GOG starting to bring in Linux developers][gog-linux-news] - the experience will just keep improving for all. And in that sense - Operation: Fuck Windows is a resounding success!

Thank you all for reading this blogpost about my personal Linux experience; I'll put out more technical blogposts as well as my long-term Steam Controller review out soon, and along with some videos actually being worked on in the background - y'all got something to look forward to; But until then...

***see you space cowboy...***

[id-id-drivers]: https://rdn-id.com/
[nasa-outlook]: https://www.techspot.com/news/111933-humanity-returns-moon-but-outlook-doesnt-work.html
[ltt-challenge]: https://www.youtube.com/watch?v=kluoZ9RhmVo
[manjaro-takeover]:https://forum.manjaro.org/t/manjaro-2-0-manifesto/186171/2
[omarchy]:https://omarchy.org/
[garuda-linux]: https://garudalinux.org/
[spout2pw]:https://spout2pw.lina.yt/
[spout2pw-fork]:https://github.com/tasokait/spout2pw
[opendeck]: https://github.com/nekename/OpenDeck
[gog-linux-news]: https://www.linuxjournal.com/content/gog-moves-toward-native-linux-support-major-shift-drm-free-gaming
