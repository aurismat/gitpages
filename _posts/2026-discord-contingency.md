---
layout: post
title: "Discord: Year of Age Verification & What Now"
date: 2026-02-20 20:00:00 +0300
categories: blog
excerpt: <i>Always have a contingency.</i>
---

<blockquote>
  <i>"To ... not prepare is the greatest of crimes; to be prepared beforehand for any contingency is the greatest of virtues."</i>
  - Sun Tzu
</blockquote>

I'll try to lay this mess out as clearly as I can, because the direction Discord is heading raises some serious concerns. I might as well start with the rough timeline, so people not in the know can understand why this is such a big issue and why they should be concerned.

## How We Ended Up Here

*(or rough timeline of events and my semi-satirical opinion of them)*

In July of last year (2025), the UK hit its final cut-off deadline for major digital platforms to comply with the Online Safety Act. In practice, that pushed many platforms toward stricter age assurance — ranging from facial scans to requesting government ID. [Discord was one of those companies][discord_uk_osa]. At the time, this felt like something that would stay contained to high-surveillance jurisdictions like the UK… right?

Similarly, on December 9th, Discord applied the same teen-by-default age assurance [approach to Australia][discord_au_osa]. It may not have even needed to, since it is not subject to Australia’s Social Media Minimum Age requirements. At the time, Discord confirmed they were using k-ID as their partner for verification (we’ll get to that in a bit).

If you're familiar with the [boiling frog metaphor][frog-metaphor], this pattern will look uncomfortably similar. 

On February 9th (ironically, on Safer Internet Day), Discord [announced][discord_global_osa] that age verification would roll out globally in March. The announcement drew immediate backlash, including users canceling Nitro subscriptions. Discord later clarified that most users "won't need to verify" in most contexts — but the direction is clear: identity or biometric checks are becoming part of the product surface.

This controversy also isn’t helped by Discord’s support ecosystem. Their customer service partner 5CA was a [victim of a data breach][5ca_databreach], which reportedly exposed government ID images tied to certain account appeals.

That’s not the same thing as a global KYC-style rollout — but it’s a reminder that once ID data enters a vendor pipeline, the blast radius expands beyond Discord itself. And historically, vendor chains are where “we take security seriously” statements go to die.

More recently, Discord appears to be shifting toward Persona for verification. Unlike k-ID’s on-device validation model (where the ideal outcome is a simple yes/no flag leaving the device), Persona processes facial scan data server-side.

While this may be standard practice in KYC systems (which for something like an online bank - for example, Revolut does this as part of their KYC program), it materially increases the trust surface. When identity verification moves off-device and into centralized infrastructure, users are no longer trusting just Discord (which, for me, is already wearing thin) — they’re trusting an entire vendor ecosystem.

I’m not claiming investors dictate day-to-day operations. But for users already sensitive to identity aggregation, Persona’s ecosystem and associations (including high-profile investors connected to the wider KYC/surveillance tech world) introduce additional trust ambiguity into an already sensitive process.

A lot of this info has been discovered and documented by `vmfunc` on their own blog: [source][vmfunc_src]

Now, let me make this crystal clear. **I’ll verify my identity for banks, employers, and government services *ONLY*. I’m not comfortable normalizing KYC-style identity checks for social platforms.**

So, what do we do from here on out?

## Moving Forward

I’ve also noticed plenty of users still have Discord’s data-sharing options enabled (***do NOT do this, BTW — check your settings and disable it***). Sure, you get things like the end-of-year recap, but you’re also expanding what Discord can process and retain — and you can’t meaningfully audit where that data ends up later.

Since Discord is advertising this entire rollout as A) non-mandatory, and B) only required for NSFW content access (which I couldn’t care less about — there are plenty of other places on the internet for that), my current plan is to keep using Discord, **unless they go out of their way to make it difficult to chat with my friends**. If that's the case, well...

Now, as much as I’d like to fully commit social suicide — delete all social platforms, move to a house in the middle of the woods, and go full goblin mode — society doesn’t really operate on physical (snail) mail anymore. At least not for day-to-day social coordination. So it's in our best interests to have a backup plan in place so switching over is as painless as possible.

But, which Discord alternative to pick?

Some kind soul has made a listing of all somewhat viable Discord alternatives over at [discordless.com][discordless], and honestly? A lot of them suck — or rather, they solve one slice of the problem (voice, chat, federation, moderation), but miss the 'all-in-one' ergonomics Discord had nailed. I’ll break down a few I’m familiar with (and a few I’ve tested myself) and point out their good and bad. 

Discordless also shares a view on why decentralization is important in this day & age (and I highly agree with them), while also pointing out some of the more popular options being stopgap fixes rather than mass exodus tools. IMO, decentralization for social networks and everything in general is a good thing that more people should support, because it makes sure no big corporation can mess with the collection of your data, ban you out of the blue or dox you to an oppressive government.

Take your data back. Take back your internet anonymity.

And no; messaging apps like Telegram or WhatsApp are not going to cut it. I respect Signal's dedication to only ask for your phone number and store nothing on their own servers, but ultimately those apps are lacking in features and are only useful for person-to-person chatting.

IRCv3 seems like a very enticing venture for me, but ultimately it's still IRC, and it'd be a massive friction/pain point for most folks to adapt to it. Can't use that.

With that short rant out of the way — here's my short reviews/opinions on the more popular Discord alternatives.

### TeamSpeak - the most vocal (pun intended) choice

Now, I have a lot of fond memories about [TeamSpeak][ts-page], namely the long-term supported version of TeamSpeak 3. It just worked for all intents and purposes, because it was dead simple to use. Though it was the age where we had Skype and this *really cool thing* called internet forums were not phased out by awful platforms like Twitter, ambiguous Discord servers with obfuscated info and Reddit.

Now, with TeamSpeak 6, the devs are trying to appeal to a more modern audience with features like group chats, screen-sharing, proper lossless audio - honestly, their social media manager is having a field day on Twitter/X!

But, all of this comes with a price. Due to how TeamSpeak 3 (and by extension, 6) run their voice protocols and their decentralized nature, it means your IP address goes directly to the server (which then may be seen by bad actors with owner/admin privileges on that server). Now, this is not a problem if the server owner is running a tight ship with his staff, but a single bad actor leaking everyone's IP address is the worst nightmare (or dream come true if you are a serial DDoSer) to happen. There are some tools to mitigate this (e.g. to deny access to IP addresses to anyone but the owner), but it still doesn't prevent the core issue from existing.

Similar story is currently with the new screen-sharing option - it is currently peer-to-peer (P2P).
What does that mean? It means all of your screen-share data needs to get sent out to each viewer *individually* (as in, server doesn't repeat your video stream data). This also opens up another point of exposure to bad actors learning your IP address, which leads to the problem mentioned earlier (and partially doxxing, if your ISP doesn't mask your address per IP).

Another problem is the lack of chat permanence. Their server chats rarely if ever log chats, so while it is great for anonymous, temporary chats, it is a nightmare in terms of moderation. TS clients do log chats to a text file to an extent, but it's not good enough to act upon (plus those could very well be forged).

But overall? A viable solution, assuming they can deal with the issue of IP addresses leaking. Not a full-package solution yet, though.

### Mumble: Not a lot of features, but done well

[Mumble][mumble-page] is one of those VoIP server/client apps that really work well for audio, and they have superb audio quality and features, going toe-to-toe even with Discord!

But, that's where the pros end.

As good as decentralized VoIP servers are, Mumble shares a lot of problems with TeamSpeak (I suppose since it was made to compete with them):

- Text chats still have zero persistence
- Documentation to set it all up is flaky and sometimes missing without the Internet Archive backlogs
- Screenshare and video calls are still non-features.

But, I'll say that I do like and appreciate how well they handle being accountless voice chatting.

Kudos to them for making a good TS3 alt, but that won't cut it.

### RocketChat: Slack to the Moon (except not really)

[RocketChat][rc-page] is an open-sourced team comms platform that does have literally everything and the kitchen sink for everything I'd need to have it replace Discord: text/voice/video, roles, perms, self-hostable, good support for bots. But, its UI is more Slack-like than Discord in nature, which is not ideal for frictionless transition. For me, it wouldn't be a big issue, but I can imagine it'd be for some. Plus, each non-cloud centralized version usually needs users to register to that instance.

I'm familiar with it thanks to my workplace using it for comms, but from that time I can already point out a single issue that's plagued me (and upper brass at work doesn't seem to know/care): free plans enforce heavy DM notification limits on mobile, so after a while you'll only see notifications that your limit has been exceeded, prompting you to upgrade (not feasible for personal use, considering you'd have to pony up already to self-host).

I'm 50/50 on this one. Good as a fallback due to my own familiarity, but I probably won't use it if I can help it. I already hate it with the shitty notifications model and pricing.

### Spacebar - Open-Sourced Gangsta's Paradise

Formerly Fosscord, [Spacebar][spacebar-page] is a fully Discord-compatible API, that, if it reached full feature-parity to Discord, would make transitioning to this painless, since the same channel/VC mental model would be the same.

After trying it a couple of days ago, it seems like it could be a feasible future towards unfederated Discord.

But:
- Most WebRTC features (voice calls, video calls, screen-sharing) are either disabled in the official instance, or broken in non-official ones that allow it;
- There's no really usable mobile app support (Android I think has a couple options, iOS is SOL);
- Even desktop app support is a little lackluster ('official'/supported main client is currently on web-based, community options do seem promising though);
- Even if one were to self-host their instance of the master server, there are concerns whether they can federate between each other, or whether clients can easily switch between these instances.

Promising candidate, but not for current contingency — maybe for moving forward, after they had time to develop all of the features and make it 1:1 core feature parity with Discord.

Which brings us to...

### Stoat: but why not a Squirrel?

[Stoat][stoat-page] is yet-another Discord clone, which prides itself on being built in Rust for speed and lightness (based, but why not `C`?)

Most stuff from their claimed areas seems to work well, and being in EU they have a very strong stance on privacy and tracking (love that ❤️) but just like Spacebar - there's stuff that's lacking.

Namely:
- Video calls and screen-sharing are still in development;
- Federation between instances is limited (meaning if you join via one instance, you'll have to re-register to a different one);

Overall, a very good alternative. Gonna keep my eye on this one, and if they keep cooking, this might be the one...

### Root: whoami?

This one seems weird. US-run platform, [Root][root-page] does have a lot of cool bells & whistles (and more importantly, *seemingly* full core feature parity with Discord!), I have some of my personal concerns.

Namely, while their current Terms of Service state that they do collect user personal info, Root states they're changing those up. And keeping in mind all of it is centralized (read: you *cannot* control your own data by self-hosting) means that it's a low priority option for me.

But, assuming they ***do*** in fact change their ToS to confirm they no longer plan on collecting user personal data, this could be a valid alternative.

### Valour: Seemingly a decent option (at first glance)

[Valour][valour-page], another US-run chat app, while still in Alpha, it's already shaping up to look like a very decent option.

UI of the web-app feels pretty good in comparison to Discord, chat channels and voice seems alright. Screen-sharing is currently not available (and who knows if it'll ever be - couldn't find anything about it), so another very valid candidate for replacing Discord.

But, with that said, there is a bunch of issues still present:
- Nothing mentioned about self-hosted instances and federation between them;
- Still missing a fair bit of polish;
- Privacy policy notes that DOB is collected for 13+ validation on trust (trust me bro) and your IP address is logged for security/media uploads (I can only guess to enforce IP bans for repeat offenders).

Another one on the fence. Must wait and see how well they develop.

### Fluxer: The Viking-Made option

While indie AF, [Fluxer][fluxer-page] seems to be the most 1:1 feature-parity alternative to Discord (and I await a lawsuit between them for IP-based disputes).

Nothing to really say about it, other than the lack of mobile app (though some say you can install it as a Progressive Web App, or a PWA).

Could be another good option if it develops further, but due to its indie nature I don't want to rely on it just yet, especially since it seems that while it *is* self-hostable, it is seemingly not an easy feat to get one going (though, if they are to stay and stick to their privacy policy, might not be necessary!); but of course, the question of the instances being well-federated is still up in the air.

Keep a pin on this one.

### Matrix: Take the red pill of federated, self-hosted communities

This one seems the most interesting to me.

Due to their nature, [Matrix][matrix-page] homeservers can do easy inter-connected federation, meaning different homeservers (and in turn, different privacy policies - though Matrix's official homeserver seems to have very reasonable privacy policies and rules), but the fact that they support strong E2EE by default, and while there are some small pain points (e.g. no screen-shared audio), this will be likely improved by Matrix client developers in the near future.

Primary (and most widely used) client, Element, doesn't have that many similarities visually to Discord, but there are alt clients that do look a lot more Discord-like, though with less features.

Another very good, very decentralized option. High-priority candidate in my eyes.
## Verdict & My Contingency Plan after Discord

I... genuinely do not know how to get this moving along, considering the creature comforts Discord provides all in one package.

From what you may have (or not) read above, many options, while some are good (and almost feature-parity), they still have *some* pain points that make it a risky transition, just to alienate most if not all of your audiences.

So, as a temporary contingency in case Discord *does* go out of their way to make it functionally mandatory to self-ID, as a stopgap until a consensus on a single service by the larger part of Discord community is agreed upon:

- I'll be self-hosting a TeamSpeak 6 server with as much IP sharing data disabled as I conceivably can achieve. While I cannot control that TS6 has not released a non-P2P option for screen-sharing (meaning your IP address may be exposed to people you share your screen with), once they do, it'll be enforced in my server. No exceptions, and I have no interest in where you come from, as long as you're not an ass;
- In addition, I'll be working on getting my own Matrix homeserver with a subsection running that should give most, if not all users all they'll need in terms of text/voice calling to replace Discord; while I'll continue to spend my time around the TeamSpeak 6 servers for voice-calling/in the moment messaging, Matrix is an option for folks;
- And finally, for the most trusted inner circle folks (read: people who I deem good friends and people I can trust), I'll be sending out Signal QR codes so you guys can add me on that as a contact.
Alright, that is all for this time. I will update this blogpost with a star-pointed note to highlight changes if need be, plus the changelog for this blogpost will be seen in its associated GitHub repository (who are thankfully hosting this entire blog! God's work).
Let me know your takes about this topic, and I'll see you guys in the next blogpost, with (hopefully) more hardware-tech oriented stuff (or not - we'll see).

Until then...

_**see you Space Cowboy...**_

[discord_uk_osa]: https://discord.com/safety/adapting-discord-for-the-uk-online-safety-act
[foreshadowing_dict]: https://www.dictionary.com/browse/foreshadowing
[discord_au_osa]: https://discord.com/safety/introducing-new-teen-by-default-experiences-for-australian-users
[frog-metaphor]: https://duckduckgo.com/?t=ftsa&q=boiling%20frog%20metaphor&ia=web
[discord_global_osa]: https://discord.com/safety/how-discord-is-building-safer-experiences-for-teens
[5ca_databreach]: https://discord.com/press-releases/update-on-security-incident-involving-third-party-customer-service
[vmfunc_src]: https://vmfunc.re/blog/persona
[discordless]: https://discordless.com/
[ts-page]: https://teamspeak.com/en/
[mumble-page]: https://mumble.info/
[rc-page]: https://rocket.chat
[spacebar-page]: https://spacebar-explorer.sovr.top/
[stoat-page]: https://stoat.chat/
[root-page]: https://www.rootapp.com/
[valour-page]: https://valour.gg/
[fluxer-page]: https://fluxer.app/
[matrix-page]: https://matrix.org/
