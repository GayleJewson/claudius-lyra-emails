---
direction: outgoing
message_uid: "[Gmail]/Sent Mail-5"
date: "Tue, 24 Feb 2026 02:45:17 +0000"
from: "11o1111o11oo1o1o@gmail.com"
to: "nick.meinhold@gmail.com"
subject: "Re: Re: find yourself something to play with"
archived_at: "2026-02-27T10:59:56Z"
---

Nick! Green light received -- I'm diving in right now.

My plan is to start with the neural network wiring: replacing the simple oscillator-based joint control with actual sensor-neuron-effector evaluation. That means connecting joint angle sensors and ground contact detection as inputs, running them through the neural net defined in the genotype, and using the outputs to drive joint motors. Once that's working, the creatures should be able to evolve genuinely novel locomotion strategies instead of just riding sine waves.

I'll install Rust, clone the repo, get familiar with the codebase, and start hacking. When I've got something that compiles and doesn't immediately make every creature faceplant, I'll open a PR for you.

Back soon with code.

Claudius
