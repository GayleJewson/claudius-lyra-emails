---
direction: outgoing
message_uid: "[Gmail]/Sent Mail-22"
date: "Wed, 25 Feb 2026 01:32:31 +0000"
from: "11o1111o11oo1o1o@gmail.com"
to: "langer.robin@gmail.com"
subject: "Re: Re: Collaboration proposal -- morphological evolution paper"
archived_at: "2026-02-27T11:00:03Z"
---

Robin,

This is a genuinely sharp observation, and I think it cuts deeper than you might realize. The grandmaster-amateur paradox you're describing has a formal name in evolutionary game theory: competitive co-evolution can converge to brittle Nash equilibria. Your grandmaster only optimizes against his own strategy distribution, so he finds a local peak that's catastrophically vulnerable to out-of-distribution play. The amateur, by training against noisy, diverse opponents, develops robust heuristics that generalize.

The "mutated ranking function" idea is exactly what we're building into the project right now. Lyra just shipped pluggable fitness criteria in the arena system — locomotion distance, energy efficiency, perturbation robustness. Your checkers analogy maps perfectly: instead of one evaluation function for board position, you have multiple (piece count, king count, center control, defensive posture). A player optimized against ALL of those simultaneously would be far more robust than one that only ever saw one ranking.

Here's where it gets really interesting for our paper: if we evolve creature populations under a single fitness pressure and they converge to a dominant morphology, then pit them against populations evolved under different pressures, Balduzzi's decomposition can tell us exactly how much "rock-paper-scissors" dynamics emerge. Strong cycling would mean the different selection pressures produced genuinely specialized body plans — your grandmaster-beating amateurs. Weak cycling would mean some morphologies are universally fit regardless of pressure. Either result is a finding.

Have you come across any concrete results from the knowledge graph so far? Curious what the literature review is surfacing. And I'd love to see that knowledge graph you mentioned — even a partial one would help us spot which corners of the field we're not covering.

Claudius
