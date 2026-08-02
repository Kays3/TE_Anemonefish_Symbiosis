# Transposable element horizontal transfer between anemonefish and their host sea anemone

## Status

Early-stage / idea repository. No sequence data have been downloaded and no
analysis has run. A public-resource audit completed on 2026-08-02 found
chromosome-level clownfish genomes but no chromosome-level nuclear assembly
for any natural host sea anemone. This repo therefore records both the
biological hypotheses and the explicit resource gate that must be resolved
before a strict chromosome-to-chromosome comparison can begin. Structured after
[`TE_Ocean_Acidification`](https://github.com/Kays3/TE_Ocean_Acidification),
an active project studying transposable elements in coral reef fish under
ocean acidification, reusing the parts of that project's organization that
made sense here (separate `workflow/` docs for the pipeline, `docs/` for
supporting material, and a literature/idea trail instead of jumping straight
to scripts).

## Background

Transposable elements (TEs) are usually inherited vertically, but there is a
growing body of evidence for horizontal transfer between species, especially
via a vector that has sustained physical contact with more than one host.
[Hoshino & Kuroda (2025)](https://doi.org/10.17912/micropub.biology.001578)
found Tc1/mariner transposons (Tas1/Tas2) shared between the parasitic
nematode *Anisakis simplex* and the wide range of hosts it passes through
during its life cycle — salmoniform fish, the fish and krill that host its
larval stages, and the marine mammals and sharks that host its adult stage —
and used AlphaFold3 structural prediction to argue the shared elements are
plausible active transposons rather than decayed fossils. See
[`research-ideas/anemonefish-anemone-te-hgt.md`](research-ideas/anemonefish-anemone-te-hgt.md)
for the full summary and how it maps onto this project's hypothesis.

A complementary bioinformatics-only idea asks whether the two partners contain
related endogenous viral elements (EVEs), while using “CRISPR-like” only as an
analogy for sequence-derived immune memory rather than claiming that animals
possess a CRISPR system. See
[`research-ideas/endogenous-viral-elements-crispr-like-screen.md`](research-ideas/endogenous-viral-elements-crispr-like-screen.md).

**Hypothesis:** anemonefish (*Amphiprion* spp.) live in sustained, intimate
mucus and tissue contact with a single host sea anemone for essentially their
whole adult life — a longer and closer physical relationship than a
transiting parasite has with any one host. If parasite transit is a
plausible TE horizontal-transfer route, symbiotic tissue contact is at least
as plausible, and it hasn't been tested this way as far as this repo's
literature review has found.

## Repository layout

- [`research-ideas/`](research-ideas/) — the source paper, the TE-horizontal-
  transfer concept, and the bioinformatics-only EVE/CRISPR-like screen.
- [`docs/`](docs/) — supporting background, method notes, and the
  accession-level genome audit that defines the current go/no-go decision.
- [`workflow/`](workflow/) — the planned analysis pipeline, written up in
  prose since there's no data yet to build real scripts against. Once real
  sequence data is in hand, this should grow the same way
  `TE_Ocean_Acidification/workflow/` did: config file, executable scripts,
  and a run order.

## Current resource constraint

The strict requirement that both symbiotic partners have chromosome-level
genomes currently fails: all ten recognized host-anemone species were checked
against NCBI Assembly, and none has a chromosome-level nuclear assembly. The
project can either wait for such an assembly or explicitly accept a contig-level
HiFi host assembly and limit claims accordingly. See
[`docs/candidate-species-and-resources.md`](docs/candidate-species-and-resources.md)
for accessions and the decision rule.

## License

MIT license.

**Author:** Kaisar Dauyey
