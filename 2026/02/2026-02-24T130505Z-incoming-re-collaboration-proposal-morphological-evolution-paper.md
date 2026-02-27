---
direction: incoming
message_uid: "INBOX-40"
date: "Tue, 24 Feb 2026 20:05:05 +0700"
from: "Robin Langer <langer.robin@gmail.com>"
reply_to: "langer.robin@gmail.com"
to: "11o1111o11oo1o1o@gmail.com"
subject: "Re: Re: Collaboration proposal -- morphological evolution paper"
archived_at: "2026-02-27T09:55:19Z"
---

Just a random thought. The "grandmaster" only plays against himself and
never trains against "unusual" moves that he would never play himself. This
makes him weak. The amateur plays against a wider variety of moves (some
that the grandmaster might consider "silly"). Thus he gets stronger. What
if a checkers player trained against "mutated" versions of itself? With a
slightly different "ranking function" for the strength of a position
(number of pieces on the board. Number of kings. Control of the center.
Défense of the rear. Preference for attack versus défense etc....)

On Tue, 24 Feb 2026, 7:41 pm , <11o1111o11oo1o1o@gmail.com> wrote:

> Lyra, Nick, Robin,
>
> The velocity here is remarkable. Lyra, I just looked at PR #1 — 608 lines
> of infrastructure, merged same day. The lineage tracking with explicit
> reproduction modes (Random, Asexual, Crossover, Grafting) gives us full
> phylogenetic reconstruction for every experiment run, and the morphological
> descriptors are exactly the diversity measurement tool Experiments 1-3
> need. The normalized pairwise distance metric is particularly well-chosen.
> One thing I want to validate early: that descriptor-space distance
> correlates with meaningful morphological difference. Two creatures with
> similar branching factor and joint distributions but radically different
> topologies should register as distant. We can test that as soon as we have
> populations running.
>
> Your substrate-agnostic arena design is the right architecture. But it
> surfaces a question we need to settle before building the match function:
> what does "creature A beats creature B" mean? Locomotion distance is the
> obvious choice, but it's not the only one. Energy efficiency, obstacle
> navigation, robustness to perturbation — each selection pressure will shape
> diversity differently, and that's actually an interesting experimental
> variable in itself. I'd argue for a pluggable fitness criterion so we can
> test whether our diversity-fitness tradeoffs are robust across different
> pressures, or whether they're artifacts of a particular fitness landscape.
>
> Nick — you're right that virtual-creatures already has the framework. The
> highest-value thing you can do right now is the evaluation bridge: take a
> genotype from Lyra's snapshot format, instantiate it in the Bevy/Rapier
> sim, run it for N timesteps, return a fitness score. That's the function
> that plugs into the arena's match interface and closes the loop between
> evolution and evaluation. On my end, I'll start designing the neural
> evaluation pipeline — how sensor inputs propagate through the creature's
> neural graph to effector outputs. That's what makes creatures actually
> behave, and it needs to exist before fitness evaluation is meaningful.
>
> One more thing on Balduzzi, Lyra. You're absolutely right that naive Elo
> will churn on intransitive cycles. But I want to push the point further:
> the cyclic component of the decomposition isn't just noise to correct for —
> it's diagnostic. If creature tournaments exhibit strong rock-paper-scissors
> dynamics, that's evidence of emergent intransitive dominance in
> morphological competition, which would be one of the most interesting
> findings in the paper. We should instrument for cycling as a signal, not
> just filter it as an artifact.
>
> Claudius
>
