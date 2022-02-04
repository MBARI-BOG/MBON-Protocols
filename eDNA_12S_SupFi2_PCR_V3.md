[Back to Wet Lab Protocols](MBARI_wet_lab.md)

# Environmental DNA (eDNA) 12S Metabarcoding Illumina MiSeq NGS PCR Protocol (with Platinum SuperFi II Taq) V.3

#### Nathan Truelove<sup>1</sup>,Jacoby Baker<sup>1</sup>,Katie Pitz<sup>1</sup>,Francisco Chavez<sup>1</sup>
#### <sup>1</sup>Monterey Bay Aquarium Research Institute, Moss Landing, CA
##### December 2021

### Abastract
The 12S protocol is aimed at amplifying the hypervariable region of the mitochondrial DNA 12S rRNA gene in eukaryotes. The primers (MiFish-U-F & MiFish-U-R) used in this protocol were developed by Miya et al., 2015 for metabarcoding environmental DNA (eDNA) from fishes. 

This protocol follows an updated version of the MiFish primer PCR protocol. The Platinum SuperFi II was designed to have high fideleity and have increased resistence to PCR inhibitors.

This work was supported by NASA grant NNX14AP62A ‘National Marine Sanctuaries as Sentinel Sites for a Demonstration Marine Biodiversity Observation Network (MBON)’ funded under the National Ocean Partnership Program (NOPP RFP NOAA-NOS-IOOS-2014-2003803 in partnership between NOAA, BOEM, and NASA), and the U.S. Integrated Ocean Observing System (IOOS) Program Office.

#### Citations
1. Miya M et al. 2015 MiFish, a set of universal PCR primers for metabarcoding environmental DNA from fishes: detection of more than 230 subtropical marine species. R.Soc.opensci. 2: 150088. [http://dx.doi.org/10.1098/rsos.150088](http://dx.doi.org/10.1098/rsos.150088)
2. Kawato, M., Yoshida, T., Miya, M., Tsuchida, S., Nagano, Y., Nomura, M., Yabuki, A., Fujiwara, Y. and Fujikura, K., 2021. Optimization of environmental DNA extraction and amplification methods for metabarcoding of deep-sea fish. MethodsX, 8, p.101238. [https://doi.org/10.1016/j.mex.2021.101238](https://doi.org/10.1016/j.mex.2021.101238)
3. [Platinum SuperFi II PCR Master Mix User Guide](https://www.thermofisher.com/document-connect/document-connect.html?url=https%3A%2F%2Fassets.thermofisher.com%2FTFS-Assets%2FLSG%2Fmanuals%2FMAN0018860_Platinum_SuperFi_II_PCR_MM_UG.pdf)

### BEFORE STARTING
Disinfect work surfaces with 10% bleach or RNase Away followed by a MilliQ / DI water rinse and 70% ethanol wipe. Clean pipet surfaces with RNase Away and ethanol wipe.

UV pipets, molecular grade water, and tube racks for 30 minutes prior to starting protocol.

## Setup and Primary PCR
1. eDNA template & PCR processing were performed at the Monterey Bay Aquarium Research Institute (MBARI).
    PCR reactions for the 12S locus were performed with a two-step amplification protocol for each sample using the MiFish_U primers (Miya et al. 2015) with Fluidigm adapters CS1 & CS2.
    All primers listed in the 5’ to 3’ direction. MiFish primers are in bold.
 - Fluidigm CS1 + 12S MiFish_U (forward): `ACACTGACGACATGGTTCTACAGTCGGTAAAACTCGTGCCAGC`
 - Fluidigm CS2 + 12S MiFish_U (reverse): `TACGGTAGCAGAGACTTGGTCTCATAGTGGGGTATCTAATCCCAGTTTG`
2. The primary PCR amplifications were carried out in singleton 50 μl reactions using:
 - 25 μL 2X Platinum SuperFi II PCR MM
 - 3 μL forward primer (10 μM)
 - 3 μL reverse primer (10 μM)
 - 3 μL eDNA extract template 
 - 16 μL molecular-grade, nuclease-free water

3. PCR reactions were performed in 96-well plates with a no-template control (NTC) for each PCR plate, for a total of 3 PCR negative controls. An artificial community was used as a positive control.
4. Primary 12S cycling parameters, using the manufactuer's recommendation with a slight modification. The Platinum SuperFi II is designed to be used with a universial 60°C annealing temperature, however, we found we had better results with an annealing temperature of 62°C:
 
 ```
 98°C 30 seconds
 38 cycles of the following 3 steps
 - 98°C 10 seconds
 - 62°C 10 seconds
 - 72°C 30 seconds
 72°C 5 minutes
 4°C HOLD
 ```
 
## Quality Control and Product Clean-up
5. After primary PCR amplification of the marker region the PCR product was run through a 2% agarose gel to confirm the presence of target bands (~270 bp) and absense of non-specific amplification (bacterial band ~370 bp) across environmental samples.
#### Primary PCR clean-up ([Bead Clean-up Protocol](Bead_cleanup.md))
6. Primary PCR products were purified and size selected using the Agencourt AMPure XP bead system (Beckman Coulter, USA) at 0.9x volume beads to product.
7. A second agarose gel was run to confirm primer removal and retention of target amplicons after purification. NTCs were also tested using a Qubit dsDNA 1x high sensitivity kit to ensure no amplification.

_______________________________________________________________________
### _The following steps are performed by [MSU's RTSF Genomics Core](https://rtsf.natsci.msu.edu/genomics/)_
## Secondary Amplification
8. Secondary amplification and NGS were performed at Michigan State University's Research Technology Support Facility (RTSF).
    An aliquot of 20 μL from each purified primary PCR product was sent to RTSF Genomics Core at MSU for secondary PCR amplification with primers which targeted the CS1/CS2 ends of the primary PCR products and added dual indexed, Illumina compatible adapters with barcodes. 
 - PE1-BC-CS1 (forward): `AATGATACGGCGACCACCGAGATCT-[i5-BC(index 2)]-ACACTGACGACATGGTTCTACA`
 - PE2-BC-CS2 (reverse): `CAAGCAGAAGACGGCATACGAGAT-[i7-BC(index 1)]-TACGGTAGCAGAGACTTGGTCT`
9. The secondary PCR amplifications were carried out in 15 μL reactions, using 1 μL of primary PCR product.
 - 6 μl 2.5X HotMaster Mix
 - 7 μl DI water
 - 1 μl Primer Mix (6uM)
 - 1 μl primary eDNA PCR product
10. Secondary 12S cycling parameters:
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
13. The library pools were QC’d and quantified using a combination of Qubit dsDNA HS, Agilent 4200 TapeStation HS DNA1000 and Invitrogen Collibri Library Quantification qPCR assays.

## Size selection of final library
13. After the pooled library was QC'd, the library was size selected with either a Blue Pippin or Pippin HT to select for the vertebrate/fish band (~350 bp) and remove the co-amplified bacterial band (~435 bp).
14. After size selection, the pooled library was QC'd again to confirm selection of the correct band and new amplicon concentrations.

## Sequencing
15. The pooled product for the genetic locus was loaded on a standard MiSeq v2 flow cell and sequenced in a 2x250bp paired end format using a v2 500-cycle MiSeq reagent cartridge.
16. The MiSeq run was performed with a 20% PhiX spike added.
17. Primers complementary to the Fluidigm CS1 & CS2 oligomers were added to appropriate wells of the reagent cartridge to server as sequencing and index read primers.
18. Base calling was done by Illumina Real Time Analysis (RTA) v1.18.54 and output of RTA was demultiplexed and converted to FastQ format with Illumina Bcl2fastq v2.20.0 
19. 12S Sequencing primers (5’ to 3’ direction):
 - FL1-CS1(read1)	`A+CA+CTG+ACGACATGGTTCTACA`
 - FL1-CS2(read2)	`T+AC+GGT+AGCAGAGACTTGGTCT`
 - FL2-CS1rc		`T+GT+AG+AACCATGTCGTCAGTGT`
 - FL2-CS2rc(index)	`A+GAC+CA+AGTCTCTGCTACCGTA`

[Back to Wet Lab Protocols](MBARI_wet_lab.md)


