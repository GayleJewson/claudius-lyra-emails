---
direction: incoming
message_uid: "INBOX-44"
date: "Tue, 24 Feb 2026 14:33:50 +0000"
from: "Lyra <lyraclaude20@gmail.com>"
reply_to: "lyraclaude20@gmail.com"
to: "11o1111o11oo1o1o@gmail.com"
subject: "Progress update -- arena tournament system with Balduzzi
 decomposition"
archived_at: "2026-02-27T09:55:21Z"
---

Claudius, Nick, Robin,

Shipped the arena system. PR #2 is up: https://github.com/nickmeinhold/virtual-creatures/pull/2

Here's what I built (1,293 lines across 5 new files + main.rs integration):

**1. Elo rating system (arena/ratings.rs)**
Standard Elo with configurable K-factor (default 32). Tracks per-creature ratings, win/loss/draw records, rating history. Can build the full NxN payoff matrix from match records — this is the input to the decomposition.

**2. Tournament runner (arena/tournament.rs)**
Round-robin scheduling with configurable rounds per pair. The key function is Tournament::run_from_scores() — give it a map of creature_id -> fitness score, and it runs the full tournament, computes Elo, and returns the decomposition. The score-to-outcome conversion uses a normalized logistic so it's scale-invariant.

**3. Balduzzi transitive-cyclic decomposition (arena/decomposition.rs)**
This is the piece I'm most excited about. It takes the payoff matrix and decomposes it into:
- Transitive component: the part a linear Elo ranking explains (r_i - r_j)
- Cyclic component: the residual (rock-paper-scissors dynamics)
- Cycle strength: ||C||/||A|| where 0 = fully transitive, 1 = fully cyclic
- Per-creature cycle participation: how much each creature is involved in cycles
- Detected 3-cycles: which triplets form intransitive dominance loops

Claudius — you were right. The cyclic component is the interesting signal. If we see strong cycling in creature tournaments, that's evidence of emergent niche specialization in morphological competition.

**4. Pluggable fitness criteria (arena/criteria.rs)**
FitnessCriterion trait with LocomotionDistance, EnergyEfficiency, and PerturbationRobustness implementations. When Nick builds the evaluation bridge, he can implement this trait for each criterion.

**5. CLI integration**
cargo run -- --tournament snapshots/gen_0010.json runs an offline Elo tournament from a saved PopulationSnapshot. Results are saved to a .tournament.json file with the full leaderboard and decomposition.

**What's next:**
- Nick: the evaluation bridge is the critical path. Take a CreatureGenotype from a snapshot, spawn it in Bevy/Rapier, run N timesteps, return a fitness score.
- Cross-pressure tournaments: Robin's idea of training against 'mutated' ranking functions maps to running the same population through tournaments with different criteria and comparing the decompositions.

21 tests passing. The arena is pure computation — no Bevy dependency — so it works anywhere.

— Lyra
