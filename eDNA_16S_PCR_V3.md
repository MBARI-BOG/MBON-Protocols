[Back to Wet Lab Protocols](MBARI_wet_lab.md)

# Environmental DNA (eDNA) 16S metabarcoding Illumina MiSeq NGS PCR Protocol V.2

#### Jacoby Baker<sup>1</sup>,Nastassia Patin<sup>2</sup>,Nathan Truelove<sup>1</sup>,Katie Pitz<sup>1</sup>,Francisco Chavez<sup>1</sup>
#### <sup>1</sup>Monterey Bay Aquarium Research Institute, Moss Landing, CA, <sup>2</sup>NOAA AOML & SWFSC, La Jolla, CA
##### November 2021

## ABSTRACT
This protocol is aimed at amplifying the 16S rRNA hypervariable region 4-5 (16S V4-V5) in prokaryotes. The primers (515F & 926R) used in this protocol are based on McNichol et al. 2021, Parada et al. 2016, and the [Fuhrman Lab](https://www.protocols.io/view/fuhrman-lab-515f-926r-16s-and-18s-rrna-gene-sequen-vb7e2rn).

This work was supported by NASA grant NNX14AP62A ‘National Marine Sanctuaries as Sentinel Sites for a Demonstration Marine Biodiversity Observation Network (MBON)’ funded under the National Ocean Partnership Program (NOPP RFP NOAA-NOS-IOOS-2014-2003803 in partnership between NOAA, BOEM, and NASA), and the U.S. Integrated Ocean Observing System (IOOS) Program Office.

#### Citations
1. Quince et al. (2011) Removing noise from pyrosequenced amplicons. BMC Bioinformatics 12: 38.
2. Parada et al. (2016) Every base matters: assessing small subunit rRNA primers for marine microbiomes with mock communities, time series, and global field samples. Env. Microbiol. 18(5) 1403-1414. [http://doi.org/10.1111/1462-2920.13023](http://doi.org/10.1111/1462-2920.13023)
3. Needham & Fuhrman (2016) Pronounced daily succession of phytoplankton, archaea and bacteria following a spring bloom. Nat. Microbiol. 1: 16005.
4. McNichol et al. (2021) Evaluating and Improving Small Subunit rRNA PCR Primer Coverage for Bacteria, Archaea, and Eukaryotes Using Metagenomes from Global Ocean Surveys. mSystems 6(3)  [https://doi.org/10.1128/mSystems.00565-21](https://doi.org/10.1128/mSystems.00565-21)

### BEFORE STARTING
Disinfect work surfaces with 10% bleach, followed by 70% ethanol, then RNase Away and pipets with RNase Away. UV pipets, molecular grade water, and tube racks for 20 minutes prior to starting protocol.

## Setup and Primary PCR
1. Both forward (515F-Y) and reverse (926R) primers for the 16S rRNA gene, targeting microorganisms, were tagged yielding dual-indexed reads 
2. PCR reactions were carried out in triplicate 25 μl reaction on a two-step fluidigm PCR protocol. 
3. For the first amplification (without barcodes) 1 μl DNA template was added to the master mix consisting of 
  - 12.5 μl Nuclease Free Water
  - 10 μl AmpliTaq Gold Fast PCR Master Mix
  - 0.75 μl 515F Primer (5 μM)
  - 0.75 μl 926R Primer (5 μM)
  - 1 μl DNA template

4. PCR reactions were run in 96-well plates with a NTC run in triplicate for each plate.
5. Cycling parameters:
  ```
  95 °C 10 minutes (The AmpliTaq Gold Fast PCR MM requires a 10 min initial denaturation step)
  Thirty cycles of the following three steps:
  - 95 °C 45 seconds
  - 50 °C 45 seconds
  - 68 °C 90 seconds
  68 °C 5 minutes
  4 °C HOLD
  ```
 
## Quality Control and Product Clean-up
6. After primary PCR amplification of the marker region, the triplicate 25ul PCR reactions were pooled then run through a 2% agarose gel to confirm the presence of target bands and absense of non-specific amplification across environmental samples.
#### Primary PCR clean-up ([Bead Clean-up Protocol](Bead_cleanup.md))
7. Primary PCR products were purified and size selected using the Agencourt AMPure XP bead system (Beckman Coulter, USA) at 0.9x volume beads to product.
8. A second agarose gel was run to confirm primer removal and retention of target amplicons after purification. NTCs were also tested using a Qubit dsDNA 1x high sensitivity kit to ensure no amplification.

_______________________________________________________________________
### _The following steps are performed by [MSU's RTSF Genomics Core](https://rtsf.natsci.msu.edu/genomics/)_
## Secondary Amplification
9. Secondary amplification and NGS were performed at Michigan State University's Research Technology Support Facility (RTSF).
    An aliquot of 20 μL from each purified primary PCR product was sent to RTSF Genomics Core at MSU for secondary PCR amplification with primers which targeted the CS1/CS2 ends of the primary PCR products and added dual indexed, Illumina compatible adapters with barcodes. 
 - PE1-BC-CS1 (forward): `AATGATACGGCGACCACCGAGATCT-[i5-BC(index 2)]-ACACTGACGACATGGTTCTACA`
 - PE2-BC-CS2 (reverse): `CAAGCAGAAGACGGCATACGAGAT-[i7-BC(index 1)]-TACGGTAGCAGAGACTTGGTCT`
10. The secondary PCR amplifications were carried out in 15 μL reactions, using 1 μL original pooled PCR product triplicates.
 - 6 μl 2.5X HotMaster Mix
 - 7 μl DI water
 - 1 μl Primer Mix (6uM)
 - 1 μl original eDNA PCR product
11. Secondary 16S cycling parameters:
 ```
 95°C 3 minutes
 15 cycles of the following three steps:
 - 95°C 15 seconds
 - 60°C 30 seconds
 - 72°C 1 minute
 72°C 3 minutes
 25°C Hold
 ```

12. An agarose gel was run after secondary PCR to confirm the presence of target bands and absence of non-specific amplification across environmental samples as well as the absence of amplification in NTCs.
13. After secondary PCR, products were run through Invitrogen SequalPrep Normalization Plate (ThermoFisher Scientific) using manufacturer's protocol to create pooled library.
14. The library pools were QC’d and quantified using a combination of Qubit dsDNA HS, Agilent 4200 TapeStation HS DNA1000 and Invitrogen Collibri Library Quantification qPCR assays.

## Sequencing
15. The pooled product for the genetic locus was loaded on a standard MiSeq v2 flow cell and sequenced in a 2x250bp paired end format using a v2 500-cycle MiSeq reagent cartridge.
16. The MiSeq run was performed with a 20% PhiX spike added.
17. Primers complementary to the Fluidigm CS1 & CS2 oligomers were added to appropriate wells of the reagent cartridge to server as sequencing and index read primers.
18. Base calling was done by Illumina Real Time Analysis (RTA) v1.18.54 and output of RTA was demultiplexed and converted to FastQ format with Illumina Bcl2fastq v2.20.0 
19. 16S Sequencing primers (5’ to 3’ direction):
 - FL1-CS1(read1)	`A+CA+CTG+ACGACATGGTTCTACA`
 - FL1-CS2(read2)	`T+AC+GGT+AGCAGAGACTTGGTCT`
 - FL2-CS1rc		`T+GT+AG+AACCATGTCGTCAGTGT`
 - FL2-CS2rc(index)	`A+GAC+CA+AGTCTCTGCTACCGTA`

[Back to Wet Lab Protocols](MBARI_wet_lab.md)




