# Planned workflow (prose only — no data yet)

This documents the pipeline this project *would* run. The 2026-08-02 resource
audit established that no natural anemonefish/host-anemone pairing currently
has chromosome-level nuclear assemblies for both partners. Nothing here is
executable yet; there is deliberately no
`config.example.env` or script stub, because pinning down an interface before
the input data situation is known would just mean rewriting it later. This
should grow the same way `TE_Ocean_Acidification/workflow/` did: once real
inputs are confirmed, replace each numbered step below with an actual script
and a `Run order` section like that repo has.

## Inputs this pipeline will need once resources are confirmed

- Reference genome (or best available assembly/transcriptome) for the chosen
  *Amphiprion* species.
- Reference genome (or best available assembly/transcriptome) for its
  specific host anemone species.
- A small set of known Tc1/mariner (and other candidate DNA-transposon
  superfamily) reference sequences to search from — the same starting point
  the source paper used, rather than an unbiased genome-wide discovery pass,
  at least for the first pass.
- Tissue samples from paired, correctly-identified anemonefish/host-anemone
  individuals if the project reaches the PCR-validation stage — see the
  cross-contamination concern noted in
  `docs/source-paper-method-notes.md`.

## Planned steps

1. **Targeted BLAST screen.** BLAST reference Tc1/mariner sequences against
   both the anemonefish and host-anemone sequence data. This mirrors the
   source paper's starting point rather than starting with a full de novo
   RepeatModeler2/RepeatMasker discovery pass (that's a reasonable follow-up
   once a candidate element is confirmed, not the first step).
2. **Cross-species/cross-taxon confirmation.** If a candidate turns up,
   BLAST it against other *Amphiprion* species and other anemone species —
   both host and non-host anemones — to see whether it tracks with the
   specific symbiotic pairing or is broadly conserved regardless of
   symbiosis (the latter would undercut the hypothesis rather than support
   it).
3. **Structural plausibility check.** Translate the candidate sequence,
   predict structure with AlphaFold3, and compare (Dali/RMSD) against
   *Sleeping Beauty* or another confirmed-active Tc1/mariner transposase,
   the same comparison the source paper used to argue plausible activity.
4. **PCR validation panel (later stage).** Design nested/touchdown primers
   and test across multiple anemonefish/anemone pairs plus non-paired
   controls, once step 1-3 justify the wet-lab cost. Needs its own
   contamination-control design — see
   `docs/source-paper-method-notes.md` for why the source paper's ITS1-2
   control doesn't transfer directly.

## Alternative: bioinformatics-only EVE screen

The EVE/“CRISPR-like” idea is a separate analysis route, not an extension of
the targeted Tc1/mariner BLAST alone. Its planned stages are:

1. annotate repeats independently in each genome;
2. screen genomic sequence and predicted proteins against curated viral
   references such as RVDB using translated similarity searches and viral-
   profile HMMs;
3. merge overlapping calls while preserving the evidence from each detector;
4. remove cellular homologs, common repeats, assembly contamination, and
   low-complexity matches;
5. require host sequence on both sides of each high-priority viral-like
   insertion;
6. where raw long reads are public, validate both host–virus junctions and
   local coverage;
7. cluster candidate EVEs across partners, non-symbiotic relatives, and viral
   references;
8. infer gene and species-aware phylogenies for supported families; and
9. report orthology, shared viral ancestry, and candidate recent similarity as
   separate evidence tiers.

This route can catalogue candidate EVEs with a contig-level host-anemone
assembly, but it cannot prove direct transfer, transfer direction, expression,
antiviral activity, or a CRISPR mechanism from genome sequence alone. The full
claim ladder and accession audit are in
[`../research-ideas/endogenous-viral-elements-crispr-like-screen.md`](../research-ideas/endogenous-viral-elements-crispr-like-screen.md)
and
[`../docs/candidate-species-and-resources.md`](../docs/candidate-species-and-resources.md).

## Environment

Once this pipeline has real scripts, reuse the environment approach already
evaluated for `TE_Ocean_Acidification` rather than re-deciding it here: a
`pyproject.toml` + `uv.lock` for whichever pieces of the toolchain are
PyPI-installable (this pipeline is BLAST + AlphaFold3 + light scripting, so
plausibly more of it fits in `uv` than the RepeatModeler/STAR-heavy OA
pipeline did — worth checking whether a local AlphaFold3 setup vs. the
AlphaFold server changes that calculus), and conda/Docker for whatever isn't
pip-installable (BLAST+ itself, most likely).
