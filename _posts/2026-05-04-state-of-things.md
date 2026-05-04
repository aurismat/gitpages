---
layout: post
title: "Aurismat: State of Things Mid-2026"
date: 2026-05-04 18:00:00 +0300
categories: blog
excerpt: <i>What's going on in my life(short and long-term).</i>
---

This... is going to be a bit of a rant, but also an announcement post.
Also a 'what the hell have I been doing for the past few years" kind of post.

So, without any further ado, let's get the important part out right away:

**I'm stepping away from livestreaming and shifting my focus towards produced video content.**

Not quitting streaming entirely, mind you - but it's no longer the main thing I'll be building around.

# What happened

If you've been around long enough, you've heard or read me talk about:

- doing video projects & essays;
- reverse engineering experiments;
- VTuber setup upgrades;
- "This will be sick once it's done" ideas;

...and then never heard about those ideas ever again.

So yeah, fair question: where *is* all that?

**Short answer*(tl;dr)*:** I've spread myself too thin and tried to juggle too many things without any of them moving forward.

Long answer is below.

# Twitch - the burnout arc

I won't even sugarcoat this.

I'm burnt out as all hell on streaming.

Not in the 'I hate it' sense - far from it - but more in the "this isn't moving anywhere" sense.

Because the harsh reality of Twitch is this:
- Discoverability is borderline non-existant;
- Twitch constantly pushing ads, both mid-roll and pre-roll is not helping the small streamers;
- The channels' directory is sorted by viewer count(meaning small guys can't punch out to the top);
- So unless you're clip-farming 24/7, you're basically invisible.

And yeah - I've been very vocal about disliking short-form content pipelines in the past. My position hasn't changed on that.
Not because they don't work - they definitely do - but because doing all of that essentially becomes an extra full-time job, for something that's supposed to be a creative hobby.

And after almost 5 years of doing this as a fun, creative outlet, I was expecting to see *something* to click.

Instead, what I got is:
- A small group of regulars(which I genuinely appreciate <3);
- Basically zero meaningful growth;
- Constant loop of "stream did well -> next one doesn't -> motivation tanks"

After so long that one could almost define it as a definition of insanity, it has come to me that this loop is **not sustainable**.

So instead of pretending that it is:
- Streams will slow down even more;
- I'll still go live whenever I feel like it (birthday stream at May 13th is a highly likely);
- But the Twitch channel is no longer the core focus.

Primary focus now will be creating content that exists *even while I'm off-air*.

# The project backlog
<h5> <i>yeah, I never finished these</i> edition</h5>

Let's go through this graveyeard.

## Scavenger SV-4 Camera Modding - Part 2

Original video: [https://www.youtube.com/watch?v=n847QNmGF34][sv4-vid]<br>
Repo: [https://github.com/aurismat/sv4-camera-mods][sv4-patches]

The first Scavenger SV-4 video was essentially shader surgery where I:
- stripped out noise layers;
- disabled UV passes;
- simplified the post-processing chain;

All of which resulted in a really clean game video feed, and all of that worked because SV-4's developer, Khallis, conveniently exposed a lot of that stuff in plaintext in the game files.

So natureally, the next step was to try to make this as useful as I could, with more options/better cleanup, maybe even a runtime injection option.

That's where things went sideways, because going from editing shader files to reverse-engineering a game binary with no previous experience is not a small feat.

In the end, I tried to pivot into a user-friendly patcher program, but in hindsight making a .NET GUI program that wraps PowerShell to run Git commands to make patches turned out to be a compatiblity nightmare.
Between pathing issues, environment differences and Windows being a pissy fuck that it is, it was never gonna be plug-and-play.

So I scrapped the video. What's left of the attempted patches is in the repo.

Could I revisit this project *at some point* with actual runtime injection, using an overlay with a library like Imgui and having toggleable effects? Probably - but that'd require me to dive deep into reverse engineering than I ever have.

So:
This project is on ice - not dead per se - but I cannot promise anything either.

## Gromada: Revenge - modern patching

This one for the most part has the opposite problem.

Technically? It's essentially solved.

The game originally expected hyper-specific old libraries that break on modern Windows, so:

- I ended up patching it to run cleanly on Windows 10, no CD crap required(not that it was a difficult DRM check, it literally checked for CD presence in that partition);
- Verified it across my own systems as well as my mate Hwaldar's to make sure it all works;
- Even did an one-shot streamed playthrough without issues;

Which would make you think this will *surely* get to work.

Then comes the stupid part: audio.
The game streams music from CD Audio stream session of the game CD.

My solution around this was to rip the tracks, stitch them up where necessary to not need file transitions, and patch up game files where needed.

Which works on paper; but this also means *I'd be redistributing copyrighted audio*, and that's where I hit the crossroads.

Do I put it out in anyway and risk a DMCA takedown, potentially a lawsuit?

There was a workaround I had come up that I would make the user provide their own CD rips, but then I'd need to find a good way to implement making the user hand-feed the music files to stitching scripts via ffmpeg to reconstruct what the game expects, which *could* be doable - I just haven't gotten around to it.

Meanwhile, on the content side - script was already written, voiceover is recorded, B-roll and footage is ready.

So this one is generally **blocked by polish and legal paranoia**.
It'll very likely become a video once I figure out what to do with the game music.

## Intravenous video essay

This is another one of those projects that got put on almost-permanent limbo.

I went into this one pretty ambitiously:

- Recording gameplay footage;
- Starting to write a full essay;
- Breaking the game down level-by-level, Pyrocynical-essay-style;

And then... I just shelved it halfway through.

Part of the issue with this is timing.

Explosive Squat Games has since reworked the original story in Intravenous 2, and with a third game on the way, trying to do a deep-dive essay without fully covering everything feels incomplete.

I still want to revisit this - but it needs a better approach than what I had originally planned.

## VTuber 3D stream room

This one died the most predictable death possible: I just got bored halfway in.

The idea/vision itself was really solid: a full 3D environment that the camera would move and pan around as pseudo-scenes, some TV screens [similar to this(YouTube link)][yt-tv-wall] that I could change the content of on-the-fly;

Technically, even I wasn't sure whether this could work and whether VNyan, my VTubing program of choice, would be up to snuff for this kind of crazy.

In reality:

- Spout2 was a little too inconsistent for my liking to render them as CRT TV screens;
- asset sourcing was a pain in the ass(though that was recently resolved as the asset pack's I really wanted author, Sean Nicolas, has [re-published them on Fab][80s-tech-pack]);
- Consistency between my own sourced models was awful(also why I wanted to use assets from one vendor);

Which in combination really put this project at a halt. But at this point I'm on Linux now and the entire pipeline needs a solid workaround before I can commit to it, and motivation these days is definitely not there.

As such, this project is **indefinitely shelved unless I find a clean path forward for my tech stack to make this room a reality.**

## My VTuber model re-design/lore

This one has somewhat similar reasons to the VTuber 3D stream room, but they're more oriented towards a creative block:

- I have multiple lore drafts, none were ever finalized to be cleaned up into something that would be useable;
- I want an outfit design that's both distint, yet still mine and reuseable (thumbnails, animation etc.);
- April Fools bit, while promising, it was more of experimentation with the funny than any actual progress.

In short; creative block & no real time to push it further.

## Operation: Fuck Windows - Part 2

This one is actually alive, and surprisingly - quite successful!

I've switched over to CachyOS for good for a couple of months now, and so far:
- Gaming works better than expected;
- Environment for development is way cleaner;
- And a lot less of "WTF Windows???" moments.

I really wanted to document this and get it out there, but doing it properly is another story.

What's missing:
- Reproducible setup steps - I want to essentially make a cheat-sheet playbook for other curious parties to follow;
- Cleaned up scripts of irritations that I had to fix myself by scripting;
- Turn the random notes I have into proper guides;
- Document my stream setup, which is a rabbit hole in of itself on Linux.

There's easily a detailed blogpost and maybe even a video sitting there; so what's stopping it?

Work, gaming and not wanting to half-ass this.

This is the project I *do* want to finish, for sustainable future post-Windows 10 death.

## The (possible) game reviews channel

Very recent and still in the works idea, but I figured I'd share it.

The core concept of it is this:
- There'd be less corporate journalist-reviewer nonsense;
- More actual player-focused analysis, by actual players;
- Potentially guest contributors;

Which all sounds amazing for networking and reach on paper.

In practice, because of the three people who'd be co-hosting that channel with me I'm the most technical-savy person on there, it'd mean that I'd have to be the lead editor, which means more responsibility and deadlines, which I don't want to take on while my own backlog is still sitting there, like some sort of a rhethorical noose around my neck.

I'm not shaking this responsibility, far from it - I'm certainly interested, but I haven't commited to it yet. However, if it does happen, I intend to mirror the reviews here with a written version.

# So what now?

Everything written above boils down to one realization: I've been doing a lot, but none of it pushed me forward.

Streaming has been the biggest, and the longest-running example of that.

So the shift is simple: I'll be streaming less, but I'll be silently working in the background on more produced content and do my best to finish things that actually last.

No hard promises, no fake schedules that I stop following mid-week.

Direction is locked in clearly: **crafting content that doesn't stop being relevant after I stop being live.**

That being said, streams will happen - just not as the main pillar anymore.

I'll do my best to push out the blogpost about Operation: Fuck Windows Part 2.
But until then...

_**see you Space Cowboy...**_

[sv4-vid]: https://www.youtube.com/watch?v=n847QNmGF34
[sv4-patches]: https://github.com/aurismat/sv4-camera-mods
[yt-tv-wall]: https://www.youtube.com/watch?v=QkNPt9j3vs4
[80s-tech-pack]: https://sketchfab.com/3d-models/80s-tech-pack-is-back-29fa666b6ef04e7abaf9d467c41706e5
