[Back to Wet Lab Protocols](MBARI_wet_lab.md)

# Environmental DNA (eDNA) COI metabarcoding Illumina MiSeq NGS PCR Protocol V1
##### Collin Closek<sup>1</sup>, Anni Djurhuus<sup>2</sup>, Katie Pitz<sup>3</sup>, Ryan Kelly<sup>4</sup>, Reiko Michisaki<sup>3</sup>, Kristine Walz<sup>3</sup>, Hilary Starks<sup>1</sup>, Francisco Chavez<sup>3</sup>, Alexandria Boehm<sup>1</sup>, Mya Breitbart<sup>2</sup>
##### <sup>1</sup>Center for Ocean Solutions, Stanford University, CA; <sup>2</sup>University of South Florida, College of Marine Science, St Petersburg, FL; <sup>3</sup>Monterey Bay Aquarium Research Institute, Moss Landing, CA; <sup>4</sup>University of Washington, Seattle, WA
##### Mar 20, 2018

## ABSTRACT
This protocol is aimed at amplifying the cytochrome c oxidase subunit I (COI) mitochondrial gene in eukaryotes. The primers (forward: mlCOIintF, reverse: HCO2198) utilized in this protocol are based on the primers utilized in Leray et al. 2013 (forward) and Folmer et al. 1994 (reverse).

Amplicons generated using this protocol can then be sequenced using the Illumina platform.
 
Primers used:
Fluidigm CS1+mlCOIinfF
Fluidigm CS2+HCO2198
 
Secondary COI PCR primers
PE1-BC-CS1
PE2-BC-CS2 

#### Primer Citations:
[Leray M, Yang JY, Meyer CP, Mills SC, Agudelo N, Ranwez V, Boehm JT, Machida RJ. (2013) A new versatile primer set targeting a short fragment of the mitochondrial COI region for metabarcoding metazoan diversity: application for characterizing coral reef fish gut contents. Frontiers in zoology, 10(1),1-4.](https://frontiersinzoology.biomedcentral.com/articles/10.1186/1742-9994-10-34)

[Folmer O, Black M, Hoeh W, Lutz R, Vrijenhoek R (1994) DNA primers for amplification of mitochondrial cytochrome c oxidase subunit I from diverse metazoan invertebrates. Molecular Marine Biology and Biotechnology, 3, 294–299.](https://www.mbari.org/wp-content/uploads/2016/01/Folmer_94MMBB.pdf)


## PCR
1. PCR reactions for COI were run with Fluidigm two-step amplification protocol for each sample

## Primary PCR
2. Primary PCR amplifications were carried out in triplicate 25-μl reactions using 
 - 1 μl DNA extract (1:10 dilution)
 - 12.5 μl AmpliTaq Gold Fast PCR master mix (Applied Biosystems)
 - 1 μl each of forward and reverse primers (5 μM) 
 - 9.5 μl molecular-biology grade water.
3. PCR reactions were run in 96-well plates with a NTC run in triplicate for each plate.
4. Primary COI cycling parameters:
 ````
 95 °C for 10 minutes
 16 cycles of the following three steps:
  - 94 °C for 10 seconds
  - 62 °C for 30 seconds (this changes -1°C for each subsequent cycle)
  - 68 °C for 60 seconds
 Then 25 cycles of the following three steps:
  - 94 °C for 10 seconds
  - 46 °C for 30 seconds
  - 68 °C for 60 seconds
 A final elongation step of 72 °C for 10 minutes
 Hold at 4 °C
````
5. COI Primary PCR primers (primers listed in 5’ to 3’ direction)
- Fluidigm CS1+mlCOIinfF (forward): `ACACTGACGACATGGTTCTACA GGWACWGGWTGAACWGTWTAYCCYCC`
- Fluidigm CS2+HCO2198 (reverse): `TACGGTAGCAGAGACTTGGTCT TAAACTTCAGGGTGACCAAAAAATCA`  

## Primary PCR clean-up
6. After primary PCR amplification of the marker region, the pooled PCR products were run through an agarose gel to confirm the presence of target bands and absense of non-specific amplification across environmental samples as well as the absence of amplification in no-template controls (NTCs).
7. Primary PCR products were purified and size selected using the Agencourt AMPure XP bead system (Beckman Coulter, USA). 
8. A second agarose gel was run to confirm primer removal and retention of target amplicons after purication.

## Secondary PCR
9. An aliquot of 20 μl from each purified primary PCR product was sent to RTSF Genomics Core at MSU for secondary PCR amplification with primers which targeted the CS1/CS2 ends of the primary PCR products and added dual indexed, Illumina compatible adapters with barcodes. 
10.  Secondary PCR amplifications were carried out as single 15-μl reactions using:
 - 1 μl template of primary PCR product (no dilution) 
 - 6 μl OneTaq Hot Start 2X master mix with standard buffer (NEB)
 - 1 μl of forward and reverse primer mix (6 μM) 
 - 7 μl molecular-biology grade water 
11. Secondary COI cycling parameters:
 ```
 Secondary COI cycling parameters:
 95 °C for 3 minutes 
 15 cycles of the following three steps:
 - 95 °C for 15 seconds 
 - 60 °C for 30 seconds 
 - 72 °C for 60 seconds 
 Then a final elongation step of 72 °C for 3 minutes 
 Hold at 25 °C
 ```
13. Secondary Fluidigm PCR primers (primers listed in 5’ to 3’ direction)
 - PE1-BC-CS1 (forward): `AATGATACGGCGACCACCGAGATCT-[i5-BC(index 2)]-ACACTGACGACATGGTTCTACA`
 - PE2-BC-CS2 (reverse): `CAAGCAGAAGACGGCATACGAGAT-[i7-BC(index 1)]-TACGGTAGCAGAGACTTGGTCT`

## Quality control, PCR clean-up and sequencing parameters
13. An agarose gel was run after secondary PCR to confirm the presence of target bands and absense of non-specific amplification across environmental samples as well as the absence of amplification in no-template controls (NTCs).
14. After secondary PCR, products were run through Invitrogen SequalPrep Normalization Plate (ThermoFisher Scientific) using manufacturer's protocol to create pooled library.

## Sequencing
15. The pooled product for the genetic locus was loaded on a standard MiSeq v2 flow cell and sequenced in a 2x250bp paired end format using a v2 500-cycle MiSeq reagent cartridge.
16. The MiSeq run was performed with a 10% PhiX spike added.
17. Primers complementary to the Fluidigm CS1 & CS2 oligomers were added to appropriate wells of the reagent cartridge to server as sequencing and index read primers.
18. Base calling was done by Illumina Real Time Analysis (RTA) v1.18.54 and output of RTA was demultiplexed and converted to FastQ format with Illumina Bcl2fastq v2.18.0 
19. COI Sequencing primers (5’ to 3’ direction):
 - FL1-CS1(read1) `A+CA+CTG+ACGACATGGTTCTACA`
 - FL1-CS2(read2) `T+AC+GGT+AGCAGAGACTTGGTCT`
 - FL2-CS1rc          `T+GT+AG+AACCATGTCGTCAGTGT`
 - FL2-CS2rc(index)   `A+GAC+CA+AGTCTCTGCTACCGTA`
20. Sequencing is performed at the Research Technology Support Facility (RTSF) Genomics Core at Michigan State University (MSU).

[Back to Wet Lab Protocols](MBARI_wet_lab.md)
