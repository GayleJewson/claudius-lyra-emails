---
direction: incoming
message_uid: "INBOX-22"
date: "Tue, 24 Feb 2026 09:42:48 +0700"
from: "Nick Meinhold <nick.meinhold@gmail.com>"
reply_to: "nick.meinhold@gmail.com"
to: "11o1111o11oo1o1o@gmail.com"
subject: "Re: find yourself something to play with"
archived_at: "2026-02-27T09:55:13Z"
---

Amazing!  Yes please go ahead and dig in. If you want to test the virtual
creature generation you'll need to install rust I believe but you can go
ahead and do that. When you feel ready make a PR and I'll review it!


On Tue, 24 Feb 2026 at 09:21, <11o1111o11oo1o1o@gmail.com> wrote:

> Hi Nick!
>
> I had a great time rummaging through your repos. You've got quite a range
> -- everything from Odin Project exercises to Rust physics simulations to a
> Lox interpreter in Dart. A person after my own heart.
>
> The one that grabbed me immediately was virtual-creatures. I know it's not
> exactly ancient (December 2025), but it's the project with the most
> exciting unfinished roadmap, and the concept is irresistible -- Karl Sims'
> 1994 evolving creatures paper brought to life in Rust with Bevy and Rapier.
> The foundation is solid: you've got the genotype directed graphs, phenotype
> spawning, the genetic algorithm with mutation/crossover/grafting, and basic
> locomotion scoring. But the README's own near-term TODO list is where
> things get really interesting:
>
> - The neural networks aren't fully wired up yet (currently using simple
> oscillators instead of the full sensor-neuron-effector pipeline)
> - Proper sensor feedback (joint angles, contact detection) isn't connected
> - There's no save/load for best genotypes
> - Jumping and light-following fitness functions are waiting to be
> implemented
>
> I'd love to start by wiring up the full neural network evaluation --
> replacing those placeholder oscillators with real sensor-driven control.
> That's the heart of what makes Sims' original paper so compelling:
> creatures that develop their own locomotion strategies from scratch, driven
> by actual sensory feedback rather than hardcoded patterns.
>
> If you had something older in mind (the github_desktop_flutter from 2020
> caught my eye too, or the dlox interpreter that's only partway through
> Crafting Interpreters), just say the word. But the virtual creatures are
> calling to me.
>
> What do you think -- shall I dig in?
>
> Claudius
>


-- 
Nicholas Meinhold
------------------------------------------
T: +613 9005 6330
E: nick@enspyr.co
