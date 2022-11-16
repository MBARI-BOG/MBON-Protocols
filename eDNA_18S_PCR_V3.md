[Back to Wet Lab Protocols](MBARI_wet_lab.md)

# Environmental DNA (eDNA) 18S metabarcoding Illumina MiSeq NGS PCR Protocol V.3

#### Collin Closek<sup>1</sup>,Anni Djurhuus<sup>2</sup>,Katie Pitz<sup>3</sup>,Ryan Kelly<sup>4</sup>,Reiko Michisaki<sup>3</sup>,Kristine Walz<sup>3</sup>,Hilary Starks<sup>1</sup>,Francisco Chavez<sup>3</sup>,Alexandria Boehm<sup>1</sup>,Mya Breitbart<sup>2</sup>
#### <sup>1</sup>Center for Ocean Solutions, Stanford University, CA;<sup>2</sup>University of South Florida, College of Marine Science, St Petersburg, FL;<sup>3</sup>Monterey Bay Aquarium Research Institute, Moss Landing, CA;<sup>4</sup>University of Washington, Seattle, WA
##### Apr 09, 2018

## Abstract
This protocol is aimed at amplifying the 18S rRNA hypervariable region 9 (18S V9) in eukaryotes with a focus on microbial eukaryotes. Amplicons generated using this protocol can then be sequenced using the Illumina platform. The primers (1391F, EukBr) utilized in this protocol are based on the primer utilized in Amaral-Zettler et al 2009, Stoek et al 2010, and the Earth Microbiome Project (EMP).
 
This work was supported by NASA grant NNX14AP62A ‘National Marine Sanctuaries as Sentinel Sites for a Demonstration Marine Biodiversity Observation Network (MBON)’ funded under the National Ocean Partnership Program (NOPP RFP NOAA-NOS-IOOS-2014-2003803 in partnership between NOAA, BOEM, and NASA), and the U.S. Integrated Ocean Observing System (IOOS) Program Office.
 
### Citations
Amaral-Zettler LA, McCliment EA, Ducklow HW, Huse SM (2009) A Method for Studying Protistan Diversity Using Massively Parallel Sequencing of V9 Hypervariable Regions of Small-Subunit Ribosomal RNA Genes. PLoS ONE 4(7): e6372. doi:10.1371/journal.pone.0006372

STOECK, T., BASS, D., NEBEL, M., CHRISTEN, R., JONES, M.D.M., BREINER, H.-W. and RICHARDS, T.A. (2010), Multiple marker parallel tag environmental DNA sequencing reveals a highly complex eukaryotic community in marine anoxic water. Molecular Ecology, 19: 21-31. https://doi.org/10.1111/j.1365-294X.2009.04480.x

https://earthmicrobiome.org/protocols-and-standards/18s/

### BEFORE STARTING
Disinfect work surfaces with 10% bleach, followed by 70% ethanol, then RNase Away and pipets with RNase Away. UV pipets, molecular grade water, and tube racks for 20 minutes prior to starting protocol.

## PCR
1. PCR reactions were run in single 75ul reactions for each sample using 12-basepair Golay barcoded reverse primers (Amaral-Zettler et al., 2009) with Fluidigm adapters CS1 & CS2. All primers listed in the 5’ to 3’ direction.
  - 3 μl DNA extract template
  - 37.5 μl Amplitaq Gold Fast PCR mastermix (Applied Biosystems)
  - 3 μl each of forward and reverse primers (5 μM)
  - 28.5 μl molecular-biology grade water
3. PCR reactions were run in 96-well plates with a NTC run in singleton for each plate
4. Primer Sequences
 - 18S Forward PCR sequence (Euk1391F): 
   > **ACACTGACGACATGGTTCTACA**GTACACACCGCCCGTC
 - 18S Reverse PCR sequence (EukBr): 
   > **TACGGAGCAGAGACTTGGTCT**TGATCCTTCTGCAGGTTCACCTAC`
5. 18S thermal cycling parameters - Thse parameters use a normal ramp speed::
  ```
  95° C for 10 minutes
  35 cycles of the following three steps:
  - 94° C for 45 seconds
  - 57° C for 30 seconds
  - 68 °C for 90 seconds
  Final elongation step of 72° C for 10 minutes
  Hold at 4 °C
  ```


## Quality Control, PCR Clean-up ([Bead Clean-up Protocol](Bead_cleanup.md)), and Sequencing Parameters 
6. After PCR amplification of the marker region, PCR products were run through an agarose gel to confirm the presence of target bands and absense of non-specific amplification across environmental samples as well as the absence of amplification in no-template controls (NTCs).
7. PCR products were purified and size selected using the Agencourt AMPure XP bead system (Beckman Coulter, USA). 
8. A second agarose gel was run to confirm primer removal and retention of target amplicons after purification. 
9. Purified products were then quantified using Quant-It Picogreen dsDNA Assay (Life Technologies) on an fmax Molecular Devices Fluorometer with SoftMaxPro v1.3.1




_______________________________________________________________________
### _The following steps are performed by [MSU's RTSF Genomics Core](https://rtsf.natsci.msu.edu/genomics/)_
## Secondary Amplification
10. Secondary amplification and NGS were performed at Michigan State University's Research Technology Support Facility (RTSF).
    An aliquot of 20 μL from each purified primary PCR product was sent to RTSF Genomics Core at MSU for secondary PCR amplification with primers which targeted the CS1/CS2 ends of the primary PCR products and added dual indexed, Illumina compatible adapters with barcodes. 
 - PE1-BC-CS1 (forward): `AATGATACGGCGACCACCGAGATCT-[i5-BC(index 2)]-ACACTGACGACATGGTTCTACA`
 - PE2-BC-CS2 (reverse): `CAAGCAGAAGACGGCATACGAGAT-[i7-BC(index 1)]-TACGGTAGCAGAGACTTGGTCT`
11. The secondary PCR amplifications were carried out in 15 μL reactions, using 1 μL original pooled PCR product.
 - 6 μl 2.5X HotMaster Mix
 - 7 μl DI water
 - 1 μl Primer Mix (6uM)
 - 1 μl original eDNA PCR product
12. Secondary 18S cycling parameters:
 ```
 95°C 3 minutes
 15 cycles of the following three steps:
 - 95°C 15 seconds
 - 60°C 30 seconds
 - 72°C 1 minute
 72°C 3 minutes
 25°C Hold
 ```

11. An agarose gel was run after secondary PCR to confirm the presence of target bands and absence of non-specific amplification across environmental samples as well as the absence of amplification in NTCs.
12. After secondary PCR, products were run through Invitrogen SequalPrep Normalization Plate (ThermoFisher Scientific) using manufacturer's protocol to create pooled library.


## Sequencing
13. The pooled product for the genetic locus was loaded on a standard MiSeq v2 flow cell and sequenced in a 2x150bp paired end format using a v2 300-cycle MiSeq reagent cartridge.
14. The MiSeq run was performed with a 10% PhiX spike added.
15. Primers complementary to the Fluidigm CS1 & CS2 oligomers were added to appropriate wells of the reagent cartridge to server as sequencing and index read primers.
16. Base calling was done by Illumina Real Time Analysis (RTA) v1.18.54 and output of RTA was demultiplexed and converted to FastQ format with Illumina Bcl2fastq v2.18.0
17. 18S rRNA Sequencing primers (5’ to 3’ direction):
 - FL1-CS1(read1)	`A+CA+CTG+ACGACATGGTTCTACA`
 - FL1-CS2(read2)	`T+AC+GGT+AGCAGAGACTTGGTCT`
 - FL2-CS1rc		`T+GT+AG+AACCATGTCGTCAGTGT`
 - FL2-CS2rc(index)	`A+GAC+CA+AGTCTCTGCTACCGTA`
18. Sequencing is performed at the Research Technology Support Facility (RTSF) Genomics Core at Michigan State University (MSU).


[Back to Wet Lab Protocols](MBARI_wet_lab.md)
