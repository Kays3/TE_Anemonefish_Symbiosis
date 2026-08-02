# Idea and source: TE horizontal gene transfer between anemonefish and their host sea anemone

This is the founding idea for this repository, carried over from the
`TE_Ocean_Acidification` research-ideas note this project was split out of.

## Source

Hoshino N, Kuroda H. 2025. "Possible Horizontal Gene Transfer of Novel
Transposable Elements in *Anisakis simplex* between Hosts and Parasites."
microPublication Biology. DOI:
[10.17912/micropub.biology.001578](https://doi.org/10.17912/micropub.biology.001578).
Open access (CC BY 4.0). PDF archived at
`research-ideas/sources/hoshino-kuroda-2025-micropub-biology-001578.pdf`.
A step-by-step method breakdown is in
[`../docs/source-paper-method-notes.md`](../docs/source-paper-method-notes.md).

### What the paper found, briefly

BLAST search turned up two Tc1/mariner-family transposon sequences (Tas1,
Tas2) in the genome of *Anisakis simplex*, a parasitic nematode that
migrates through multiple hosts over its life cycle. These elements are
homologous to Tc1/mariner elements already abundant in salmoniform fish, and
structurally similar (AlphaFold3 + Dali/RMSD) to the *Sleeping Beauty*
transposase, a known-active reconstructed Tc1/mariner element. PCR for
Tas1/2 came back positive across a wide, taxonomically scattered set of
species that all sit somewhere on *Anisakis*'s documented host list —
intermediate hosts, definitive hosts, and other TE-rich vertebrates — while
a parallel PCR for the parasite's own marker gene stayed negative in all of
them, ruling out simple contamination. Their argument: a parasite that
physically transits a chain of hosts is a plausible vector for horizontal
transfer of transposons between those hosts.

## The adapted hypothesis for this repository

Anemonefish (*Amphiprion* spp.) live embedded in the tentacles of a single
host anemone for essentially their whole adult life, mucus-coated by it,
through a slow acclimation process that itself involves exchanging mucus
with the anemone. That is a longer and more intimate tissue-contact
relationship than a parasite passing through a host's gut. If parasite
transit is a plausible HGT vector, sustained epidermal/mucus contact between
an obligate symbiotic fish and its cnidarian host is at least as plausible a
route, and — as far as the (informal, non-exhaustive) literature check
behind this idea found — hasn't been tested this way.

**Hypothesis:** TE families found in anemonefish genomes and TE families
found in their specific host anemone's genome/transcriptome show sequence
and/or structural similarity beyond what shared ancestry alone would
predict, consistent with horizontal transfer through the symbiosis.

See [`../workflow/README.md`](../workflow/README.md) for the planned
pipeline and [`../docs/candidate-species-and-resources.md`](../docs/candidate-species-and-resources.md)
for the open question this whole idea currently hinges on: whether a
specific anemonefish/host-anemone pair actually has enough public sequence
data to start from.

## What would need to happen before this is a real study, not just an idea

- Confirm the resource-availability question in
  `docs/candidate-species-and-resources.md` — this is the actual gate.
- A literature check for whether anemonefish TE content has already been
  characterized, and whether anyone has already looked at anemonefish/
  anemone HGT specifically.
- A check for known ectoparasites or pathogens shared between anemonefish
  and their host anemones — if one exists, it's a second, more direct
  analogy to the *Anisakis* vector story and worth testing alongside the
  direct-contact hypothesis.
- A resolved contamination-control design for the eventual PCR stage (see
  `docs/source-paper-method-notes.md`), since the obvious cross-species
  tissue contamination risk here is different from the source paper's.
