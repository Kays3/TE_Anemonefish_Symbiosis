# Idea: shared endogenous viral elements and CRISPR-like antiviral memory

## Status

Feasibility-screen idea. A genome-only discovery analysis is possible with
public data, but no natural clownfish-hosting sea anemone currently has a
chromosome-level assembly. Any first pass using the available host-anemone
HiFi assemblies must therefore be described as exploratory and
contig-resolved, not chromosome-resolved.

## Question

Do anemonefish and their natural host sea anemones contain homologous
endogenous viral elements (EVEs) that are unexpectedly similar given the deep
divergence between vertebrates and cnidarians?

An unexpected fish-anemone EVE relationship could be consistent with a shared
viral reservoir, independent infection by related viruses, or horizontal
transfer. It would not, by itself, establish direct transfer during symbiosis
or identify the direction of transfer.

## What "CRISPR-like" means here

This is not a search for CRISPR repeats or PAM motifs in the animal genomes.
The analogy is functional: in some animals, virus-derived genomic sequences
can generate PIWI-interacting RNAs (piRNAs) that provide heritable,
sequence-specific antiviral activity. Demonstrating that mechanism in
anemonefish or sea anemones would require appropriate small-RNA data and,
ultimately, functional experiments.

The STAR Protocols workflow, "Extraction of CRISPR-targeted sequences from
the metagenome" (Sugimoto et al. 2022), instead mines bacterial and archaeal
CRISPR spacers from shotgun metagenomes to recover targeted phages, plasmids,
and other mobile genetic elements. It could become a complementary mucus-
microbiome/virome arm, but it cannot detect animal EVEs from the two reference
genomes. Published 16S amplicon datasets are also insufficient for that
workflow; it requires shotgun metagenomic reads.

## Public-genome constraint, audited 2026-08-02

The fish side is suitable. For example, the published chromosome-level
*Amphiprion clarkii* assembly is `GCA_027123335.1`, and the telomere-to-
telomere maroon clownfish *Premnas biaculeatus* assembly is
`GCA_053813585.1`.

The host-anemone side does not meet a strict chromosome-level requirement:

- *Stichodactyla haddoni*: `GCA_049996035.1`, NCBI level `Contig`.
- *Entacmaea quadricolor*: `GCA_050437185.1`, NCBI level `Contig`.
- *Heteractis doreensis*: `GCA_050437215.1`, NCBI level `Contig`.
- Other published natural host-anemone assemblies are scaffold-level.

The 2025 PacBio HiFi assemblies are valuable because they provide megabase-
scale contigs and raw long reads, but they are not chromosome-scale. Under a
strict rule that both partners must have chromosome-level genomes, no natural
clownfish-host-anemone pair is currently eligible.

## Bioinformatics-only pilot if contig-level host assemblies are accepted

### Candidate pairings

1. *P. biaculeatus*--*E. quadricolor*: a T2T clownfish genome paired with a
   natural host that has a recent HiFi contig assembly.
2. *A. clarkii*--*S. haddoni*: a chromosome-scale clownfish genome paired
   with a natural host that has a recent HiFi contig assembly.

These are species-level comparisons. The sequenced fish and anemone
individuals were not collected as matched cohabiting pairs.

### Discovery and validation

1. Download the assemblies, annotations, raw long reads, and available RNA-
   seq data; record exact accession versions and checksums.
2. Audit taxonomic purity and assembly structure before EVE discovery,
   including contamination from bacteria and Symbiodiniaceae.
3. Annotate transposable elements independently with
   RepeatModeler2/RepeatMasker so viral hits overlapping retrotransposon
   domains are not overinterpreted.
4. Search for non-retroviral EVEs with `detectEVE`, translated similarity
   searches against RVDB-Prot, and HMMER searches against RVDB-Prot-HMM.
5. Identify endogenous retrovirus candidates using LTR structure plus
   family-consistent `gag`, `pol`, and `env` evidence. A reverse
   transcriptase, integrase, or helicase hit alone is ambiguous.
6. Merge overlapping hits, extract candidate sequences and 10--20 kb host
   flanks, and cluster candidate proteins across focal and control genomes.
7. Require raw long reads that cross virus-host junctions, normal local
   coverage, and animal sequence on both sides before accepting an
   integration.
8. Build viral-family-specific alignments and phylogenies with related
   clownfish, host and non-host anemones, non-anemonefish damselfish, and
   viral references.

### Evidence tiers

- **Screening hit:** reproducible viral protein or profile-HMM match.
- **Probable EVE:** viral evidence plus credible animal flanks and no strong
  contamination signal.
- **High-confidence EVE:** both integration junctions supported by raw long
  reads and coherent viral-family annotation.
- **Shared viral lineage:** independently validated fish and anemone EVEs
  that cluster together in a viral phylogeny.
- **HGT candidate:** a shared lineage whose sequence relationships are
  inconsistent with ordinary host vertical inheritance and remain robust to
  broad taxon sampling and contamination checks.

The final tier is evidence consistent with HGT, not proof of direct transfer
through clownfish-anemone contact.

## What a genome-only study can and cannot claim

It can produce high-confidence EVE catalogs, validate integration boundaries,
identify shared viral lineages, estimate relative insertion ages in some
cases, and nominate candidates for population or experimental follow-up.

It cannot demonstrate direct ecological transfer, determine transfer
direction from two reference genomes, establish viral activity, or establish
piRNA-mediated immunity. Those claims require population sampling, matched
host-pair material, small-RNA data, and/or functional validation.

## Decision gate

- If chromosome-level assemblies for both partners are mandatory, pause this
  direct pair analysis until a host-anemone Hi-C/Omni-C assembly is published
  or generated.
- If megabase-scale HiFi contigs plus raw junction-spanning reads are
  acceptable, proceed with a clearly labeled exploratory pilot and avoid
  chromosome-position, long-range synteny, and pair-specific transfer claims.

Reference-guided pseudochromosome scaffolding against a distant non-host sea
anemone should not be presented as a substitute for experimental Hi-C/Omni-C
scaffolding.

## Key references

- De Jode A, Titus BM. 2025. The first de novo HiFi genome assemblies for
  three clownfish-hosting sea anemone species. *Genome Biology and Evolution*
  17:evaf064. <https://doi.org/10.1093/gbe/evaf064>
- Brait N, et al. 2025. detectEVE: fast, sensitive and precise detection of
  endogenous viral elements in genomic data. *Molecular Ecology Resources*.
  <https://doi.org/10.1111/1755-0998.14083>
- Bigot T, et al. 2020. RVDB-prot, a reference viral protein database and its
  HMM profiles. *F1000Research* 8:530.
  <https://doi.org/10.12688/f1000research.18776.2>
- Sugimoto R, et al. 2022. Extraction of CRISPR-targeted sequences from the
  metagenome. *STAR Protocols* 3:101525.
  <https://doi.org/10.1016/j.xpro.2022.101525>
- Suzuki Y, et al. 2020. Non-retroviral endogenous viral element limits
  cognate virus replication in *Aedes aegypti* ovaries. *Current Biology*
  30:3495--3506.e6. <https://doi.org/10.1016/j.cub.2020.06.057>
