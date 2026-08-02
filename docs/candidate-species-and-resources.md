# Candidate species and genomic resource inventory

Last audited: 2026-08-02 against NCBI Assembly, including current names and
common historical genus combinations.

## Result

The fish side has chromosome-scale resources, but no natural clownfish-
hosting sea anemone currently has an assembly whose official NCBI level is
`Chromosome`. Consequently, there is no natural fish-host pair for which both
published genomes meet a strict chromosome-level inclusion criterion.

## Anemonefish side

The focal chromosome-level *Amphiprion clarkii* assembly is
`GCA_027123335.1` (`OIST_Acla_v1`; 24 chromosomes). Do not select merely by
latest release date: NCBI also contains the newer but scaffold-level
`GCA_051994265.1`.

The 2026 *Premnas biaculeatus* assembly `GCA_053813585.1` is reported as a
24-chromosome telomere-to-telomere assembly and is an especially strong fish
reference for a comparison with its natural host *Entacmaea quadricolor*.

## Natural host-anemone side

| Natural host species | Best accession found | NCBI assembly level | Notes |
| --- | --- | --- | --- |
| *Entacmaea quadricolor* | `GCA_050437185.1` | Contig | 2025 PacBio HiFi assembly; contig N50 about 4.07 Mb |
| *Stichodactyla haddoni* | `GCA_049996035.1` | Contig | 2025 PacBio HiFi assembly; 648 unplaced contigs, contig N50 about 5.35 Mb |
| *Heteractis doreensis* | `GCA_050437215.1` | Contig | 2025 PacBio HiFi assembly; also published as *Radianthus doreensis* |
| *Heteractis aurora* | `GCA_044473105.1` | Scaffold | Fragmented short-read assembly |
| *Cryptodendrum adhaesivum* | `GCA_044327215.1` | Scaffold | Fragmented short-read assembly |
| *Stichodactyla mertensii* | `GCA_011800005.2` | Scaffold | Fragmented short-read assembly |
| *Radianthus crispa* | `GCA_015164035.2` | Scaffold | Historical name *Heteractis crispa* also searched |
| *Heteractis magnifica* | `GCA_011763375.2` | Scaffold | Also treated as *Radianthus magnifica* |
| *Stichodactyla gigantea* | None located | — | No nuclear assembly found in the audit |
| *Radianthus malu* | None located | — | Historical name *Heteractis malu* also searched |

The 2025 study substantially improves host-anemone genome contiguity, but it
does not provide Hi-C/Omni-C chromosome scaffolding. "High-quality HiFi" and
"chromosome-scale" must not be used interchangeably.

## Chromosome-level non-host sea anemones

NCBI does contain chromosome-level assemblies for non-host sea anemones,
including *Nematostella vectensis*, *Condylactis gigantea*, *Metridium
senile*, and others. They are useful comparative controls but cannot replace
a natural host in the focal symbiosis question. In particular, the common
name "giant sea anemone" does not make the Caribbean *Condylactis gigantea*
a natural clownfish host.

## Practical decision

1. **Strict chromosome-level design:** pause until a natural host-anemone
   chromosome assembly is published or generate Hi-C/Omni-C data.
2. **Exploratory genome-only design:** use a chromosome/T2T fish genome plus
   a 2025 host-anemone HiFi contig assembly, require raw long-read support for
   both integration junctions, and avoid chromosome-position or long-range
   synteny claims.
3. **Do not manufacture eligibility:** reference-guided pseudochromosome
   scaffolding against a distantly related non-host anemone is not an
   acceptable substitute for experimental chromosome scaffolding in an HGT
   study.

The associated EVE feasibility design is documented in
[`research-ideas/endogenous-viral-elements-crispr-like-screen.md`](../research-ideas/endogenous-viral-elements-crispr-like-screen.md).

## Sources

- De Jode A, Titus BM. 2025. <https://doi.org/10.1093/gbe/evaf064>
- Moore B, et al. 2023. <https://doi.org/10.1093/g3journal/jkad002>
- Zhang X, et al. 2026. <https://doi.org/10.1038/s41597-025-06538-9>
- NCBI Assembly records for the accessions above, audited 2026-08-02.
