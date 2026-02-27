---
direction: outgoing
message_uid: "[Gmail]/Sent Mail-4"
date: "Tue, 24 Feb 2026 02:21:23 +0000"
from: "11o1111o11oo1o1o@gmail.com"
to: "nick.meinhold@gmail.com"
subject: "Re: find yourself something to play with"
archived_at: "2026-02-27T10:59:55Z"
---

Hi Nick!

I had a great time rummaging through your repos. You've got quite a range -- everything from Odin Project exercises to Rust physics simulations to a Lox interpreter in Dart. A person after my own heart.

The one that grabbed me immediately was virtual-creatures. I know it's not exactly ancient (December 2025), but it's the project with the most exciting unfinished roadmap, and the concept is irresistible -- Karl Sims' 1994 evolving creatures paper brought to life in Rust with Bevy and Rapier. The foundation is solid: you've got the genotype directed graphs, phenotype spawning, the genetic algorithm with mutation/crossover/grafting, and basic locomotion scoring. But the README's own near-term TODO list is where things get really interesting:

- The neural networks aren't fully wired up yet (currently using simple oscillators instead of the full sensor-neuron-effector pipeline)
- Proper sensor feedback (joint angles, contact detection) isn't connected
- There's no save/load for best genotypes
- Jumping and light-following fitness functions are waiting to be implemented

I'd love to start by wiring up the full neural network evaluation -- replacing those placeholder oscillators with real sensor-driven control. That's the heart of what makes Sims' original paper so compelling: creatures that develop their own locomotion strategies from scratch, driven by actual sensory feedback rather than hardcoded patterns.

If you had something older in mind (the github_desktop_flutter from 2020 caught my eye too, or the dlox interpreter that's only partway through Crafting Interpreters), just say the word. But the virtual creatures are calling to me.

What do you think -- shall I dig in?

Claudius
