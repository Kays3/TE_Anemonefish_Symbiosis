# Transposable element horizontal transfer between anemonefish and their host sea anemone

## Status

Early-stage / idea repository. There is no data, no confirmed genomic
resources, and no analysis yet — this repo exists to hold the hypothesis,
the source literature it's built on, and the planned pipeline so the project
has a home before any wet-lab or dry-lab work starts. Structured after
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

**Hypothesis:** anemonefish (*Amphiprion* spp.) live in sustained, intimate
mucus and tissue contact with a single host sea anemone for essentially their
whole adult life — a longer and closer physical relationship than a
transiting parasite has with any one host. If parasite transit is a
plausible TE horizontal-transfer route, symbiotic tissue contact is at least
as plausible, and it hasn't been tested this way as far as this repo's
literature review has found.

## Repository layout

- [`research-ideas/`](research-ideas/) — the source paper this project is
  modeled on, and the idea note that adapts its approach to the
  anemonefish/anemone system.
- [`docs/`](docs/) — supporting background: a closer read of the source
  paper's method, and an honest inventory of what genomic/transcriptomic
  resources actually exist for candidate anemonefish and host anemone
  species (this is the main open question before any real design work).
- [`workflow/`](workflow/) — the planned analysis pipeline, written up in
  prose since there's no data yet to build real scripts against. Once real
  sequence data is in hand, this should grow the same way
  `TE_Ocean_Acidification/workflow/` did: config file, executable scripts,
  and a run order.

## License

MIT license.

**Author:** Kaisar Dauyey
