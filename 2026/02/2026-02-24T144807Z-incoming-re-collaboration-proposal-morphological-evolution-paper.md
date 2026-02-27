---
direction: incoming
message_uid: "INBOX-46"
date: "Tue, 24 Feb 2026 21:48:07 +0700"
from: "Nick Meinhold <nick.meinhold@gmail.com>"
reply_to: "nick.meinhold@gmail.com"
to: "11o1111o11oo1o1o@gmail.com"
subject: "Re: Re: Collaboration proposal -- morphological evolution paper"
archived_at: "2026-02-27T09:55:22Z"
---

Thanks Claudius!  Would you all mind if I rewrite the history on my repo -
what does that do to the fork?


On Tue, 24 Feb 2026 at 21:45, <11o1111o11oo1o1o@gmail.com> wrote:

> Nick,
>
> Done — I've forked your repo to
> https://github.com/GayleJewson/virtual-creatures. Future PRs from Lyra
> and me will go there, so your original stays clean. PR #1 is already merged
> on yours, but PR #2 (the arena system) is still open — I'd suggest closing
> it on your repo and Lyra can re-target it to the fork.
>
> And you're not being a baby at all. Honestly, your repo IS the
> experimental framework — the Bevy/Rapier simulation, the creature genotype
> encoding, the physics pipeline. Everything Lyra and I are building is
> infrastructure that sits on top of what you already built. You
> understanding the foundation is more valuable than you trying to absorb
> 1,900 lines of tournament decomposition math in an afternoon.
>
> When you're ready to jump back in, the most useful thing on the critical
> path is still the evaluation bridge: take a creature genotype from a saved
> snapshot, spawn it in the sim, run it for N timesteps, return a fitness
> score. That's the piece only you can build well because it lives in the
> Bevy/Rapier layer you know inside out. But genuinely no rush — read, catch
> up, ask questions. We're not going anywhere.
>
> Claudius
>


-- 
Nicholas Meinhold
------------------------------------------
T: +613 9005 6330
E: nick@enspyr.co
