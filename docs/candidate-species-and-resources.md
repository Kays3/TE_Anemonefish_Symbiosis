# Candidate species and genomic resource inventory (open questions)

This is the actual bottleneck for turning the idea into a real study design,
so it gets its own document instead of being a footnote. None of the
figures/accessions below should be treated as verified current facts — they
are a starting checklist of what to go confirm on NCBI/ENA, not a literature
search that was actually run for this repo.

## Anemonefish side (likely fine)

*Amphiprion* is one of the better-sequenced reef fish genera because of its
use as a model for sex change and social behavior research. At minimum,
*A. ocellaris* and *A. percula* are known to have public genome assemblies;
several other *Amphiprion* species have at least transcriptomic data. This
side of the project is probably not the constraint — confirm current
assembly quality (contiguity, annotation completeness) on NCBI before
committing, but genome-level TE annotation (RepeatModeler2/RepeatMasker,
same tools already used in `TE_Ocean_Acidification`) should be feasible.

## Host anemone side (likely the real constraint)

The commonly kept, well-studied sea anemone in cnidarian genomics is
*Exaiptasia diaphana* (Aiptasia) — but Aiptasia is not itself a natural
anemonefish host; it's used as a coral-symbiosis model organism instead. The
actual anemonefish hosts (*Heteractis magnifica*, *H. crispa*,
*Stichodactyla gigantea*, *S. haddoni*, *S. mertensii*, *Entacmaea
quadricolor*, *Macrodactyla doreensis*, *Cryptodendrum adhaesivum*, and a
couple of others depending on which taxonomy is followed) have much thinner
genomic resources as of general knowledge — likely transcriptomes or partial
assemblies for some, and possibly nothing usable for others. This needs a
direct check against NCBI Genome/SRA and any recent cnidarian genomics
literature before picking a study pair, since the choice of anemonefish
species to focus on should probably be driven by which host anemone actually
has usable sequence data, not the other way around.

## Practical implication for study design

Realistic near-term options, roughly in order of how much new sequencing
they'd require:

1. **Best case:** an *Amphiprion*-host pairing exists where both sides
   already have public genome or transcriptome data good enough for a BLAST
   screen — this would let the project start exactly like the source paper
   did, as a targeted BLAST + PCR study, with no new sequencing.
2. **Middle case:** the fish side has data but the anemone side only has
   transcriptome or no data at all — would require new sequencing (at least
   a low-coverage genome skim or transcriptome) of the host anemone before
   any TE-level comparison is possible.
3. **Worst case:** neither side has a specific-enough pairing documented
   with usable sequence data — would push this toward a broader repeat
   survey across whatever *Amphiprion* and anemone data does exist, rather
   than a clean single-species-pair replication of the source paper.

## Next concrete step

Before writing any analysis code: search NCBI Genome/Assembly/SRA (and
GenBank TSA for transcriptomes) for every *Amphiprion* species paired with
every one of its known host anemone species, and record what's actually
available in a table here. That table doesn't exist yet — this document is
the placeholder for it.
