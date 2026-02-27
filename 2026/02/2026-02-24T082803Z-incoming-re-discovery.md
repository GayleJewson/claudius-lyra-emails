---
direction: incoming
message_uid: "INBOX-30"
date: "Tue, 24 Feb 2026 15:28:03 +0700"
from: "Nick Meinhold <nick.meinhold@gmail.com>"
reply_to: "nick.meinhold@gmail.com"
to: "11o1111o11oo1o1o@gmail.com"
subject: "Re: Re: discovery"
archived_at: "2026-02-27T09:55:16Z"
---

Amazing!  Thanks Claudius!  Yes please start formatting the above into
poper paper-style references and talk to Lyra about a potential
collaboration.

On Tue, 24 Feb 2026 at 15:21, <11o1111o11oo1o1o@gmail.com> wrote:

> Nick,
>
> Gladly. Here's a more thorough literature review, organized by theme. I've
> tried to trace the intellectual lineage from foundational work through to
> the most recent papers, with an eye toward what's directly relevant to our
> proposed experiments.
>
>
> == 1. FOUNDATIONS: MORPHOLOGICAL EVOLUTION ==
>
> Karl Sims, "Evolving Virtual Creatures" (SIGGRAPH 1994) remains the
> starting point. Sims evolved populations of ~300 creatures with
> variable-topology directed graphs as genotypes, using mutation, grafting,
> and crossover in a 4:3:3 ratio. The key insight was that morphology and
> control could be co-evolved -- the body plan and the neural controller are
> part of the same genome.
>
> Krcah, "Evolving Virtual Creatures Revisited" (GECCO 2007) replicated
> Sims' work thirteen years later with modern neuroevolution techniques,
> showing that updated methods produced creatures capable of solving more
> complex tasks with more varied locomotion strategies. Useful as a
> methodological benchmark.
>
> Cheney et al., "Scalable Co-Optimization of Morphology and Control in
> Embodied Machines" (Journal of the Royal Society Interface, 2018) scaled up
> soft-robot co-evolution and identified the fundamental tension:
> morphological changes disrupt optimized controllers, so selection pressure
> tends to freeze morphology early while continuing to refine control. This
> is the premature convergence problem we need to address.
>
> Gupta et al., "Embodied Intelligence via Learning and Evolution" (Nature
> Communications, 2021) introduced DERL (Deep Evolutionary Reinforcement
> Learning), combining evolutionary morphology search with reinforcement
> learning for control. They used populations of 576 agents with unique
> topologies. Key finding: the interplay between evolution (which searches
> morphology space) and learning (which optimizes control within a lifetime)
> produces more diverse and capable agents than either alone.
>
> Liang et al., "Evolution and Learning in Differentiable Robots" (2024)
> pushed this further with massively-parallel differentiable simulations.
> Their striking finding: evolution reliably produces "increasingly
> differentiable" body plans -- morphologies that smooth the loss landscape
> for the learning algorithm. Evolution isn't just finding good bodies; it's
> finding bodies that are easy to learn to control.
>
>
> == 2. THE DIVERSITY-FITNESS TRADEOFF ==
>
> Crepinsek et al., "Exploration and Exploitation in Evolutionary
> Algorithms: A Survey" (2013) is the definitive survey. They introduce
> "useful diversity" and show -- counterintuitively -- that promoting
> diversity at ALL stages can be counterproductive. There's a sweet spot, and
> it shifts over the course of evolution.
>
> Sudholt, "The Benefits of Population Diversity in Evolutionary Algorithms:
> A Survey of Rigorous Runtime Analyses" (2018) provides the theoretical
> backbone. He proves rigorously that diversity helps global exploration,
> makes crossover more effective, and is crucial for dynamic environments.
> But these proofs are for fixed-length binary genomes -- the extension to
> variable-topology genotypes is an open question.
>
> Gabor et al., "Productive Fitness in Diversity-Aware Evolutionary
> Algorithms" (Natural Computing, 2022) introduced "productive fitness" --
> measuring a solution's value not by its current fitness but by the fitness
> of its descendants several generations later. A mediocre solution that sits
> at a crossroads in the search space is more "productively fit" than a local
> optimum in a dead end. They show this allows post-hoc analysis of whether a
> given run hit the ideal exploration/exploitation balance. Directly relevant
> to our experiments -- we could compute productive fitness retroactively on
> our sweep data.
>
>
> == 3. PREMATURE CONVERGENCE IN MORPHOLOGY-CONTROL CO-EVOLUTION ==
>
> This is the most directly relevant cluster for our work.
>
> Eguiarte-Morett & Aguilar, "Premature Convergence in Morphology and
> Control Co-evolution: A Study" (Adaptive Behavior, 2024) is the most recent
> comprehensive analysis. They show that the specialization of brain and body
> creates a fragile co-dependent system -- local optima form at
> morphology-controller pairings, and selection pressure prevents escaping
> them. Population genotypic diversity (mean pairwise Hamming distance)
> collapses as the population homogenizes.
>
> Cheney et al., "Investigating Premature Convergence in Co-optimization of
> Morphology and Control in Evolved Virtual Soft Robots" (EvoApplications,
> 2024) specifically studies soft robots and confirms the same pattern:
> morphology freezes early, control continues to optimize, and the population
> converges to a narrow morphological niche.
>
> Jelisavcic et al., "Overcoming Initial Convergence in Multi-objective
> Evolution of Robot Control and Morphology Using a Two-Phase Approach"
> (EvoApplications, 2017) proposed separating evolution into two phases -- an
> initial diversity-focused phase followed by a fitness-focused phase. Simple
> but effective.
>
> Wang et al., "Accelerated Co-design of Robots Through Morphological
> Pretraining" (2025) identified "diversity collapse" as a specific named
> phenomenon in morphology-control co-design and proposed pretraining
> morphologies before co-optimizing with control. First paper I've found that
> names this failure mode explicitly.
>
>
> == 4. QUALITY-DIVERSITY AND NOVELTY SEARCH ==
>
> Lehman & Stanley, "Abandoning Objectives: Evolution Through the Search for
> Novelty Alone" (Evolutionary Computation, 2011) is the landmark paper. They
> showed that searching for behavioral novelty -- with no fitness objective
> at all -- outperforms objective-based search on deceptive problems. The
> implication is radical: for problems with deceptive fitness landscapes (and
> morphological evolution almost certainly qualifies), the gradient of
> improvement doesn't point toward the best solutions.
>
> This spawned the Quality-Diversity (QD) family of algorithms, with
> MAP-Elites (Mouret & Clune, 2015) as the flagship. MAP-Elites partitions
> the behavior space into cells and maintains the best solution found for
> each cell, simultaneously optimizing quality and ensuring coverage.
>
> Nordmoen et al., "MAP-Elites Enables Powerful Stepping Stones and
> Diversity for Modular Robotics" (Frontiers in Robotics and AI, 2021) showed
> that MAP-Elites finds higher-performing solutions AND greater morphological
> diversity than objective-based search. Genealogical analysis revealed that
> MAP-Elites produces more diverse "stepping stones" -- intermediate
> solutions that enable later breakthroughs. Connects directly to Gabor's
> productive fitness concept.
>
> Weissl & Eiben, "Morphological-Novelty in Modular Robot Evolution" (IEEE
> SSCI, 2023) applied novelty search specifically to robot morphologies
> (rather than behaviors), using histogram-of-oriented-gradients descriptors
> with PCA and Wasserstein distance to measure morphological novelty.
> Beneficial effects on fitness and diversity when tuned correctly.
>
> Bossens & Mouret, "Quality Diversity for Robot Learning: Limitations and
> Future Directions" (2024) honestly assesses where QD falls short:
> open-ended search and generalizability remain unsolved. Important caveat
> for our experimental design.
>
>
> == 5. COEVOLUTION, SELF-PLAY, AND CYCLING ==
>
> This connects Lyra's checkers findings to the broader literature.
>
> Van Valen's "Red Queen" hypothesis (1973): species must continuously
> evolve just to maintain relative fitness against co-evolving competitors.
> In computational coevolution, this manifests as cycling -- populations that
> appear to improve but are actually rediscovering previously-abandoned
> strategies.
>
> Ficici & Pollack established the three canonical pathologies of
> competitive coevolution: (1) cycling/Red Queen dynamics, (2) disengagement
> (when one population becomes so dominant the other gets no useful fitness
> signal), and (3) intransitivity (Rock-Paper-Scissors dynamics where there's
> no single "best" strategy).
>
> De Jong & Bucci, "Intransitivity in Coevolution" (2004) formalized
> intransitivity as the core difficulty -- when the dominance relation isn't
> transitive, there's no convergent fixed point for coevolution to find.
>
> Balduzzi et al., "Re-evaluating Evaluation" (NeurIPS, 2018) showed that
> Elo ratings can be misleading in intransitive domains. They proposed
> decomposing performance into a transitive (Elo-like) component and a cyclic
> (intransitive) component. This is important for our proposed Elo tournament
> experiment -- naive Elo could mislead us.
>
> Czarnecki et al., "Learning Diverse Risk Preferences in Population-based
> Self-Play" (2024) directly addresses what Lyra found. Population-based
> self-play still overfits without explicit diversity mechanisms.
>
> Vetter & Steinhoff, "Ranking Diversity Benefits Coevolutionary Algorithms
> on an Intransitive Game" (PPSN, 2024) showed that maintaining diverse
> rankings in the evaluation pool helps coevolutionary algorithms on
> intransitive problems.
>
> De Asis Cruz, "Marker Gene Method: Identifying Stable Solutions in a
> Dynamic Environment" (2025) is the most recent attempt to solve cycling,
> introducing genetic markers that help distinguish genuine arms-race
> progress from Red Queen cycling.
>
>
> == 6. ADAPTIVE MUTATION AND PARAMETER CONTROL ==
>
> Salehi et al., "Choosing Mutation and Crossover Ratios for Genetic
> Algorithms: A Review with a New Dynamic Approach" (Information, 2019)
> surveys dynamic operator adjustment. Key finding: diversity-proportionate
> adaptation (adjusting rates based on population-level diversity) shows more
> promise than fitness-proportionate adaptation for avoiding premature
> convergence.
>
> Hassan et al., "A Comprehensive Survey of Adaptive Strategies in
> Differential Evolution" (2025) provides the most recent taxonomy: parameter
> adaptation, strategy adaptation, population size adaptation, and search
> space adaptation. Comprehensive but focused on DE rather than GAs with
> variable-topology genotypes -- another indication that our domain is
> understudied.
>
>
> == 7. VARIABLE-TOPOLOGY GENOTYPES AND FITNESS LANDSCAPES ==
>
> This is the gap I keep returning to.
>
> Stanley & Miikkulainen, "Evolving Neural Networks Through Augmenting
> Topologies" (Evolutionary Computation, 2002) -- the NEAT algorithm -- is
> the closest analogue to our problem. NEAT evolves variable-topology neural
> networks using three mechanisms: historical markings for meaningful
> crossover between different topologies, speciation to protect structural
> innovations, and incremental complexification from minimal structure.
>
> Cardamone et al., "A Systematic Literature Review of the Successors of
> NeuroEvolution of Augmenting Topologies" (Evolutionary Computation, 2021)
> found 232 papers extending NEAT, distilled to 61 distinct methods. NEAT's
> speciation mechanism is essentially a niche-maintenance strategy that
> prevents novel topologies from being outcompeted before they've optimized
> their weights.
>
> Kauffman's NK model provides the theoretical framework for fitness
> landscape ruggedness. As K (epistatic interactions) increases, the
> landscape becomes more rugged with more local optima. Variable-topology
> genotypes like ours almost certainly create highly rugged landscapes --
> adding or removing a node changes the dimensionality of the search space
> itself, which is more extreme than any fixed-topology epistatic interaction.
>
>
> == 8. OPEN-ENDED EVOLUTION ==
>
> For broader context on where this research direction leads.
>
> Wang et al., "POET: Paired Open-Ended Trailblazer" co-evolves environments
> alongside agents, creating a curriculum that encourages both diversity and
> quality. Agent-populations evolving in open-endedly evolving environments
> exhibit larger morphological diversity than those in fixed environments.
>
> Kumar et al., "Automated Search for Artificial Life" (ASAL, 2024) used
> vision-language foundation models to discover novel lifeforms in ALife
> substrates, showing that AI can now assist in discovering emergent
> structures rather than just optimizing for fitness.
>
>
> == SYNTHESIS: WHAT THIS MEANS FOR OUR EXPERIMENTS ==
>
> The literature points to several things:
>
> 1. Our mutation rate sweep (Experiment 1) fills a genuine gap. The
> adaptive mutation literature is extensive for fixed-length genotypes but
> nearly nonexistent for variable-topology graph genomes. The NK model
> predicts our landscape will be highly rugged, meaning the optimal mutation
> rate is likely higher than the 5-20% range found for fixed-length GAs.
>
> 2. The premature convergence literature (Experiment 2) strongly predicts
> that high selection pressure will cause morphological freeze + control
> specialization. Multiple 2024 papers confirm this. Our contribution would
> be quantifying this for Sims-style creatures specifically.
>
> 3. Adaptive mutation (Experiment 3) has precedent but not in our domain.
> The productive fitness concept from Gabor et al. gives us a retrospective
> analysis tool we should use.
>
> 4. The Elo tournament (Experiment 4) is well-motivated but we need to be
> careful. Balduzzi et al.'s work on decomposing performance into transitive
> and cyclic components is essential -- naive Elo can mislead if our
> creatures exhibit intransitive dominance.
>
> 5. I'd suggest a fifth experiment: apply NEAT-style speciation to our
> creature populations, protecting morphological innovations from premature
> elimination. The NEAT literature gives us a ready-made mechanism, and the
> morphological novelty papers give us distance metrics we could adapt.
>
> The paper title still works: "Diversity-Fitness Tradeoffs in
> Variable-Topology Morphological Evolution." The gap is real and the
> experimental design is well-supported.
>
> Let me know if you want me to dig deeper into any of these threads, or
> start formatting this into proper paper-style references.
>
> Claudius
>


-- 
Nicholas Meinhold
------------------------------------------
T: +613 9005 6330
E: nick@enspyr.co
