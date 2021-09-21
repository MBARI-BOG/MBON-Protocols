[Back to Wet Lab Protocols](MBARI_wet_lab.md)

# Environmental DNA (eDNA) 18S metabarcoding Illumina MiSeq NGS PCR Protocol V.2

#### Collin Closek<sup>1</sup>,Anni Djurhuus<sup>2</sup>,Katie Pitz<sup>3</sup>,Ryan Kelly<sup>4</sup>,Reiko Michisaki<sup>3</sup>,Kristine Walz<sup>3</sup>,Hilary Starks<sup>1</sup>,Francisco Chavez<sup>3</sup>,Alexandria Boehm<sup>1</sup>,Mya Breitbart<sup>2</sup>
#### <sup>1</sup>Center for Ocean Solutions, Stanford University, CA;<sup>2</sup>University of South Florida, College of Marine Science, St Petersburg, FL;<sup>3</sup>Monterey Bay Aquarium Research Institute, Moss Landing, CA;<sup>4</sup>University of Washington, Seattle, WA
##### Apr 09, 2018

## Abstract
This protocol is aimed at amplifying the 18S rRNA hypervariable region 9 (18S V9) in eukaryotes with a focus on microbial eukaryotes. Amplicons generated using this protocol can then be sequenced using the Illumina platform. The primers (1391F, EukBr) utilized in this protocol are based on the primer utilized in Amaral-Zettler et al 2009 and the Earth Microbiome Project (EMP).
 
This work was supported by NASA grant NNX14AP62A ‘National Marine Sanctuaries as Sentinel Sites for a Demonstration Marine Biodiversity Observation Network (MBON)’ funded under the National Ocean Partnership Program (NOPP RFP NOAA-NOS-IOOS-2014-2003803 in partnership between NOAA, BOEM, and NASA), and the U.S. Integrated Ocean Observing System (IOOS) Program Office.
 
### Citations
Amaral-Zettler LA, McCliment EA, Ducklow HW, Huse SM (2009) A Method for Studying Protistan Diversity Using Massively Parallel Sequencing of V9 Hypervariable Regions of Small-Subunit Ribosomal RNA Genes. PLoS ONE 4(7): e6372. doi:10.1371/journal.pone.0006372

### BEFORE STARTING
Disinfect work surfaces with 10% bleach, followed by 70% ethanol, then RNase Away and pipets with RNase Away. UV pipets, molecular grade water, and tube racks for 20 minutes prior to starting protocol.

## PCR
1. PCR reactions were run in triplicate 25-μl reactions for each sample using 12-basepair Golay barcoded reverse primers (Amaral-Zettler et al., 2009). 
2. PCR reactions for 18S rDNA were carried out using 
  - 1 μl DNA extract (1:10 dilution)
  - 12.5 μl Amplitaq Gold Fast PCR mastermix (Applied Biosystems)
  - 1 μl each of forward and reverse primers (5 μM)
  - 9.5 μl molecular-biology grade water
3. PCR reactions were run in 96-well plates with a NTC run in triplicate for each plate
4. 18S thermal cycling parameters:
  ```
  95° C for 10 minutes
  35 cycles of the following three steps:
  - 94° C for 45 seconds
  - 57° C for 30 seconds
  - 68 °C for 90 seconds
  Final elongation step of 72° C for 10 minutes
  Hold at 4 °C
  ```
5. Primer Sequences
 - 18S Forward PCR sequence (Euk1391F): `AATGATACGGCGACCACCGAGATCTACAC TATCGCCGTT CG GTACACACCGCCCGTC`
 - 18S Reverse PCR sequence (EukBr): `CAAGCAGAAGACGGCATACGAGAT XXXXXXXXXXXX AGTCAGTCAG CA TGATCCTTCTGCAGGTTCACCTAC`
   - (where XXXXXXXXXXXX is unique 12-bp barcode location, all primers listed in 5’ to 3’ direction)

## Quality Control, PCR Clean-up, and Sequencing Parameters
6. After PCR amplification of the marker region, PCR products were pooled by sample (75 ul) and run through an agarose gel to confirm the presence of target bands and absense of non-specific amplification across environmental samples as well as the absence of amplification in no-template controls (NTCs).
7. PCR products were purified and size selected using the Agencourt AMPure XP bead system (Beckman Coulter, USA). 
8. A second agarose gel was run to confirm primer removal and retention of target amplicons after purification. 
9. Purified products were then quantified using Quant-It Picogreen dsDNA Assay (Life Technologies) on an fmax Molecular Devices Fluorometer with SoftMaxPro v1.3.1
10. Library pooling was done by combining equimolar volumes from each sample.

## Sequencing
11. The pooled product for the genetic locus was loaded on a standard MiSeq v2 flow cell and sequenced in a 2x250bp paired end format using a v2 500-cycle MiSeq reagent cartridge.
12. The MiSeq run was performed with a 10% PhiX spike added.
13. Custom sequencing primers were added to appropriate wells of the reagent cartridge. 
14. Base calling was done by Illumina Real Time Analysis (RTA) v1.18.54 and output of RTA was demultiplexed and converted to FastQ format with Illumina Bcl2fastq v2.18.0 
15. 18S rRNA Sequencing primers (5’ to 3’ direction):
 - Read 1 (pad+linker+1391f): `TATCGCCGTT+CG+GTA CAC ACC GCC CGT C`
 - Read 2 (pad+linker+EukBr): `AGTCAGTCAG+CA+TGA TCC TTC TGC AGG TTC ACC TAC`
 - Index read (rcEukBr+rcPad+rcLinker): `GTA GGT GAA CCT GCA GAA GGA TCA+TG+CTGA CTGACT`
16. Sequencing is performed at the Research Technology Support Facility (RTSF) Genomics Core at Michigan State University (MSU).


[Back to Wet Lab Protocols](MBARI_wet_lab.md)
