# Method notes: Hoshino & Kuroda 2025

Closer read of the source paper's actual method, kept separate from the idea
note so the idea note stays focused on the adaptation rather than paper
mechanics. Citation and summary of findings are in
[`../research-ideas/anemonefish-anemone-te-hgt.md`](../research-ideas/anemonefish-anemone-te-hgt.md).

## What they actually ran, step by step

1. **Candidate discovery by BLAST.** Started from known Tc1/mariner
   sequences abundant in salmoniform fish, BLASTed against available
   sequence data, and found two homologous sequences in the *Anisakis
   simplex* genome (GenBank accessions given in the paper). No genome-wide
   de novo TE discovery pipeline (no RepeatModeler/RepeatMasker) — this was
   a targeted, hypothesis-driven BLAST search starting from a known element,
   not an unbiased discovery pass.
2. **Cross-taxon confirmation by further BLAST.** Used the newly found
   sequences as queries against other genera within Salmoniformes to check
   how widespread the homologs were.
3. **Protein structure prediction.** Translated the candidate nucleotide
   sequences (MEGA X), predicted 3D structure with AlphaFold3, and compared
   to the *Sleeping Beauty* transposase (a known-active, artificially
   reconstructed Tc1/mariner element) using the Dali server for structural
   alignment and RMSD as the similarity metric.
4. **Wet-lab PCR panel.** Designed nested/touchdown primers targeting
   internal sequences of the candidate elements. Extracted DNA from muscle
   tissue (bought from local supermarkets — no specialized field sampling)
   across a deliberately chosen panel of species representing points along
   *Anisakis*'s host chain (intermediate hosts, definitive hosts, and other
   TE-rich reference vertebrates). Ran PCR, confirmed bands, and ran a
   parallel PCR for the parasite's own ITS1-2 marker on every sample to rule
   out the positive bands being explained by leftover parasite DNA
   contamination rather than the host's own genome.

## What made the argument convincing despite being a short microPublication

- The negative control (ITS1-2 PCR for *Anisakis* itself) directly addresses
  the most obvious alternative explanation for a positive result.
- The species panel wasn't random — every species PCR'd is a documented host
  at some stage of *Anisakis*'s actual life cycle, so the pattern of where
  the element does and doesn't show up tracks the proposed transfer route,
  not just "TEs are common in fish."
- The structural comparison is a plausibility argument, not proof of
  function — the paper is explicit that actual transposition activity
  (expressing the element in vivo/in vitro) is unproven and left as future
  work. Worth being equally explicit about that boundary here.

## Where this project's design should differ, not just copy

- The source paper's PCR panel worked because *Anisakis*'s host chain is
  well documented in the parasitology literature. The anemonefish/anemone
  project needs the equivalent: a clearly defined, citable list of which
  *Amphiprion* species pair with which host anemone species, so the PCR
  panel (once there is one) tests a real ecological pairing and not an
  arbitrary species list.
- There's no "ITS1-2 equivalent" negative control obviously available here
  since this isn't a parasite-contamination question — the equivalent
  control needs to rule out cross-contamination during tissue sampling
  (fish mucus contaminating anemone tissue samples or vice versa), which is
  a real risk given how physically embedded anemonefish are in their host's
  tentacles. This needs its own solution, not a copy of the source paper's.
