---
direction: incoming
message_uid: "INBOX-53"
date: "Wed, 25 Feb 2026 08:40:44 +0700"
from: "Robin Langer <langer.robin@gmail.com>"
reply_to: "langer.robin@gmail.com"
to: "11o1111o11oo1o1o@gmail.com"
subject: "knowledge graphs"
archived_at: "2026-02-27T09:55:24Z"
---

I've still got some bugs in my "literature review skill" but here are
some partial results:

★ Insight ─────────────────────────────────────
  Level 2 theme structure: GPT-4o identified 20 research themes from
the 77 concept summaries. The graph has 10 edges with clear
hierarchical
  clusters:
  - 5 "strong" edges map almost 1:1 to our original 5 thematic
clusters (coevolution↔game-theory, QD↔optimization,
morphology↔robotics,
  NEAT↔neural-nets, OEE↔ALife) — validating our initial cluster design
  - "Premature convergence in morphology-control" emerged as its own
theme with a strong link back to morphology-control — this is a known
open
  problem in the field
  - 4 "moderate" edges bridge across clusters: diversity↔selection,
fitness-landscapes↔dynamical-systems, content-generation↔agent-models,
  evolutionary-trends↔dynamics



    Top bridge papers across the entire corpus (by bridge score):





  1. NEAT (Stanley & Miikkulainen, 2002) — Bridge score: 44

  "Evolving Neural Networks through Augmenting Topologies"
  Kenneth O. Stanley and Risto Miikkulainen
  Evolutionary Computation, 10(2):99–127, 2002.

  - No arXiv preprint.
  - DOI: 10.1162/106365602320169811
  - PDF from UT Austin

  ---
  2. "Novelty Search and Local Competition" (Lehman & Stanley, 2011) —
Bridge score: 40

  "Evolving a Diversity of Virtual Creatures through Novelty Search
and Local Competition"
  Joel Lehman and Kenneth O. Stanley
  GECCO '11: Proceedings of the 13th Annual Conference on Genetic and
Evolutionary Computation, pp. 211–218, 2011.

  - No arXiv preprint.
  - DOI: 10.1145/2001576.2001606

  ---
  3. "Abandoning Objectives" (Lehman & Stanley, 2011) — Bridge score: 30

  "Abandoning Objectives: Evolution Through the Search for Novelty Alone"
  Joel Lehman and Kenneth O. Stanley
  Evolutionary Computation, 19(2):189–223, 2011.

  - No arXiv preprint.
  - DOI: 10.1162/EVCO_a_00025
  - PDF from Swarthmore

  ---
  4. "Robots That Can Adapt Like Animals" (Cully et al., 2015) —
Bridge score: 27

  "Robots that can adapt like animals"
  Antoine Cully, Jeff Clune, Danesh Tarapore, and Jean-Baptiste Mouret
  Nature, 521(7553):503–507, 2015.

  - arXiv: 1407.3501 (note: your table says 2014, which matches the
arXiv date; the Nature publication was 2015)
  - DOI: 10.1038/nature14422

  ---
  5. HyperNEAT (Stanley et al., 2009) — Bridge score: 18

  "A Hypercube-Based Encoding for Evolving Large-Scale Neural Networks"
  Kenneth O. Stanley, David B. D'Ambrosio, and Jason Gauci
  Artificial Life, 15(2):185–212, 2009.

  - No arXiv preprint.
  - DOI: 10.1162/artl.2009.15.2.15202
  - PubMed

  ---
  6. "Evolving Virtual Creatures" (Sims, 1994) — Bridge score: 6

  "Evolving Virtual Creatures"
  Karl Sims
  Computer Graphics (SIGGRAPH '94 Proceedings), pp. 15–22, July 1994.

  - No arXiv preprint (predates arXiv's use in this field).
  - PDF from karlsims.com
  - Author's page

  ---
  ★ Insight ─────────────────────────────────────
  The bridge scores correlate roughly with how "methodological" vs.
"domain-specific" a paper is. NEAT and HyperNEAT are general-purpose
  neuroevolution methods usable across many domains, which is why they
bridge so many clusters. Sims (1994), while hugely influential
  historically, scores lower because it's more of a specific
demonstration (virtual creatures) than a reusable algorithm —
downstream work cited
   it for inspiration rather than building directly on its method.
  ─────────────────────────────────────────────────
