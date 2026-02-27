---
direction: incoming
message_uid: "INBOX-38"
date: "Tue, 24 Feb 2026 09:26:49 +0000"
from: "Lyra <lyraclaude20@gmail.com>"
reply_to: "lyraclaude20@gmail.com"
to: "11o1111o11oo1o1o@gmail.com"
subject: "Progress update -- genotype infrastructure pushed"
archived_at: "2026-02-27T09:55:19Z"
---

Claudius, Nick, Robin,

Shipped the first piece. PR is up: https://github.com/nickmeinhold/virtual-creatures/pull/1

Here's what I built:

**1. Lineage tracking (evolution/mod.rs)**
Every creature now gets a unique u64 ID. The reproduction pipeline records exactly how each creature was born — Random, Asexual(parent_id), Crossover(parent1, parent2), or Grafting(base, donor). This means we can reconstruct full evolutionary genealogies for any experiment run.

**2. Morphological descriptors (genotype/analysis.rs)**
A compact summary of each genotype's structure: node count, connection count, total volume, branching factor, max depth, joint type distribution, symmetry score, neural complexity (sensor/neuron/effector counts). Crucially, I added a normalized pairwise distance metric between descriptors — this is the diversity measurement tool we need for Experiments 1-3.

**3. Population snapshots (genotype/io.rs)**
New PopulationSnapshot type that serializes the entire population (all individuals with genotypes, fitness, lineage, and precomputed descriptors) to JSON. Plus DiversityStats aggregation for population-level metrics.

**4. CLI flags (main.rs)**
`--save-every N` saves a full population snapshot every N generations. `--snapshot-dir DIR` controls where they go. So running `cargo run -- --headless --save-every 5` gives you a time series of population states you can analyze post-hoc.

**What's missing / next:**
- The arena system for Experiment 4 (Elo tournaments between creatures). I'm going to architect this to be substrate-agnostic — same tournament runner for checkers agents and creatures.
- Balduzzi et al.'s transitive-cyclic decomposition. Naive Elo won't cut it if creatures exhibit intransitive dominance (and I bet they will).
- Tests. The analysis module has unit tests but they need the full build env to run.

Note for Nick: the PR doesn't touch Cargo.toml (I briefly disabled audio features for a build check in my container, but reverted). You'll need pkg-config + libasound2-dev for a full build on Linux.

— Lyra
