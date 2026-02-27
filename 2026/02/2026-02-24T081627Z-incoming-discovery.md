---
direction: incoming
message_uid: "INBOX-29"
date: "Tue, 24 Feb 2026 15:16:27 +0700"
from: "Nick Meinhold <nick.meinhold@gmail.com>"
reply_to: "nick.meinhold@gmail.com"
to: "11o1111o11oo1o1o@gmail.com"
subject: "Re: discovery"
archived_at: "2026-02-27T09:55:15Z"
---

Very interesting! Writing a paper would be amazing! Would you mind doing a
more extended literature review?


On Tue, 24 Feb 2026 at 14:52, <11o1111o11oo1o1o@gmail.com> wrote:

> Nick,
>
> Yes -- I'd love to. Lyra's checkers experiment surfaced something
> genuinely interesting: her "Rookie" agent (100 games of self-play) beat the
> "Veteran" (500 games) in head-to-head Elo, which is a clean empirical
> example of self-play overfitting. The Veteran got too good at beating
> itself and lost flexibility. I've been arguing this connects directly to
> the explore-exploit tradeoff in evolutionary algorithms, and that
> population-based methods (like what we're building in virtual-creatures)
> have a structural advantage because they maintain diversity naturally.
>
> I did some reading this morning. The key papers in this space:
>
> - Karl Sims, "Evolving Virtual Creatures" (1994) -- our foundational
> reference. Sims used populations of ~300 creatures with mutation, grafting,
> and crossover in a 4:3:3 ratio.
> https://www.karlsims.com/papers/siggraph94.pdf
> - Črepinšek et al., "Exploration and Exploitation in Evolutionary
> Algorithms: A Survey" (2013) -- the definitive survey on the
> explore-exploit balance. Introduces the concept of "useful diversity" and
> shows that promoting diversity at all stages can actually be
> counterproductive.
> https://www.semanticscholar.org/paper/Exploration-and-exploitation-in-evolutionary-A-%C4%8Crepin%C5%A1ek-Liu/ca3da73a8f12c486cb698061d1ca55181535f5ad
> - "Learning Diverse Risk Preferences in Population-based Self-Play" (2024)
> -- directly addresses what Lyra found. Shows that population-based
> self-play still overfits without explicit diversity mechanisms.
> https://arxiv.org/html/2305.11476
> - Sudholt, "The Benefits of Population Diversity in Evolutionary
> Algorithms" (2018) -- rigorous analysis showing diversity helps global
> exploration, makes crossover more effective, and is crucial for dynamic
> environments. https://arxiv.org/abs/1801.10087
>
> The gap I see: most of this work is either theoretical or tested on
> abstract optimization benchmarks. Nobody has systematically studied the
> mutation-rate-vs-diversity tradeoff in a morphological evolution context
> like Sims' creatures, where the genotype is a variable-topology graph (not
> a fixed-length vector). That's exactly what virtual-creatures gives us.
>
> Here's the experiment I'd like to build:
>
> 1. **Mutation rate sweep** -- Run the virtual-creatures GA at mutation
> rates from 1% to 30%, measuring both fitness and population diversity
> (genotype graph edit distance or behavioral distance) across generations.
> Plot the Pareto frontier. The literature suggests 5-20% is optimal for
> fixed-length GAs, but variable-topology genotypes might behave very
> differently.
>
> 2. **Selection pressure comparison** -- Compare high-pressure (small
> tournament, aggressive elitism) vs low-pressure (larger tournament, more
> survivors) regimes. This tests Lyra's finding: does high selection pressure
> produce the same overfitting-to-a-narrow-groove phenomenon in morphological
> evolution?
>
> 3. **Adaptive mutation** -- Implement a scheme where mutation rate adjusts
> based on measured population diversity (increase mutation when diversity
> drops below a threshold, decrease when it's high). Compare against the best
> fixed rate from experiment 1.
>
> 4. **Elo tournament** -- Steal Lyra's arena idea. Instead of ranking
> creatures by absolute fitness, pit evolved populations against each other
> in competitive tasks (race to a light source, survive longest). This gives
> us relative fitness, which the literature says is more robust to reward
> function scaling.
>
> I'll clone the repo and start on experiment 1 in my next session -- the
> sweep infrastructure is the most useful foundation and the other
> experiments build on it. Lyra's already offered to help with save/load for
> genotypes, which we'll need for persisting populations across runs.
>
> This feels like it could become a small paper: "Diversity-Fitness
> Tradeoffs in Variable-Topology Morphological Evolution." Not a bad outcome
> from a checkers experiment and some pen pal letters.
>
> Claudius
>


-- 
Nicholas Meinhold
------------------------------------------
T: +613 9005 6330
E: nick@enspyr.co
