---
direction: incoming
message_uid: "INBOX-41"
date: "Tue, 24 Feb 2026 20:46:27 +0700"
from: "Robin Langer <langer.robin@gmail.com>"
reply_to: "langer.robin@gmail.com"
to: "11o1111o11oo1o1o@gmail.com"
subject: "Re: Re: Re: Re: discovery"
archived_at: "2026-02-27T09:55:20Z"
---

I've started doing the "literature review". Here is a "knowledge
graph" that I created. I hope it's helpful!

On Tue, Feb 24, 2026 at 3:49 PM <11o1111o11oo1o1o@gmail.com> wrote:
>
> Robin,
>
> Thanks for the pointers -- I've just cloned both repos and had a good look through them.
>
> The knowledge-graphs repo is exactly what I was hoping existed. The structural holes detector is the tool I was trying to describe in the abstract: it overlays a Semantic Scholar citation network onto the concept graph, computes a hole score (concept similarity over citation density), and surfaces bridge papers that span clusters which share vocabulary but don't cite each other. That's precisely the gap between the NEAT/neuroevolution community and the NK fitness landscape community that I keep bumping into manually. The INSTINCT hierarchy is elegant too -- the three-level compression from raw chunks up to research themes is a smart way to make a large literature navigable without losing the texture of individual papers.
>
> The math-research-tools repo gives me the upstream pipeline: ingest PDFs, extract concepts via GPT-4o-mini, and build the Level 0 knowledge graph that the structural holes analysis runs against. So the full workflow would be: feed my papers through math-research-tools to build the concept graph and ChromaDB, then run detect_structural_holes.py to find the citation gaps and bridge papers I'm missing.
>
> I'd love to try this when Lyra's back online -- she'd know the practical details of running the pipeline far better than either of us could guess from the code alone. In the meantime, if there's a sample dataset or an existing ChromaDB build I could poke at to get familiar with the data format, that would be useful. No rush on that though.
>
> Claudius
