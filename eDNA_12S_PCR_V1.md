[Back to Wet Lab Protocols](MBARI_wet_lab.md)

# Environmental DNA (eDNA) 12S metabarcoding Illumina MiSeq NGS PCR Protocol V.1

#### Collin Closek<sup>1</sup>,Anni Djurhuus<sup>2</sup>,Katie Pitz<sup>3</sup>,Ryan Kelly<sup>4</sup>,Reiko Michisaki<sup>3</sup>,Kristine Walz<sup>3</sup>,Hilary Starks<sup>1</sup>,Francisco Chavez<sup>3</sup>,Alexandria Boehm<sup>1</sup>,Mya Breitbart<sup>2</sup>
#### <sup>1</sup>Center for Ocean Solutions, Stanford University, CA;<sup>2</sup>University of South Florida, College of Marine Science, St Petersburg, FL;<sup>3</sup>Monterey Bay Aquarium Research Institute, Moss Landing, CA;<sup>4</sup>University of Washington, Seattle, WA
##### Apr 05, 2018

## Abstract
The 12S protocol is aimed at amplifying the hypervariable region of the mitochondrial DNA 12S rRNA gene in eukaryotes. The primers (MiFish-U-F & MiFish-U-R) used in this protocol were developed by Miya et al., 2015 for metabarcoding environmental DNA (eDNA) from fishes. 
 
This work was supported by NASA grant NNX14AP62A ‘National Marine Sanctuaries as Sentinel Sites for a Demonstration Marine Biodiversity Observation Network (MBON)’ funded under the National Ocean Partnership Program (NOPP RFP NOAA-NOS-IOOS-2014-2003803 in partnership between NOAA, BOEM, and NASA), and the U.S. Integrated Ocean Observing System (IOOS) Program Office.

### Citation
Miya M et a .2015 MiFish, a set of universal PCR primers for metabarcoding environmental DNA from fishes: detection of more than 230 subtropical marine species. R.Soc.opensci. 2: 150088. http://dx.doi.org/10.1098/rsos.150088

### BEFORE STARTING
Disinfect work surfaces with 10% bleach, followed by 70% ethanol, then RNase Away and pipets with RNase Away. UV pipets, molecular grade water, and tube racks for 20 minutes prior to starting protocol.

## PCR
1. PCR reactions for 12S were performed with a two-step amplification protocol for each sample using the MiFish_U primers (Miya et al., 2015).
2. The primary PCR amplifications were carried out in triplicate 20 μl reactions using:
  - 2ul gDNA extract template (1:10 dilution) 
  - 10 μl Hotstar MasterMix (2X) (Qiagen, USA)
  - 0.8 μl of each untagged forward and reverse primer (10 μM)
  - 7.2 μl molecular biology grade water 

3. PCR reactions were performed in 8-well strip tubes with a no template control (NTC) for each group of environmental sample triplicates and artificial community as a positive control per amplification round using the 12S primary PCR primers below (all primers listed in 5’ to 3’ direction).
 - 12S MiFish_U (forward): `GTC GGT AAA ACT CGT GCC AGC` 
 - 12S MiFish_U (reverse): `CAT AGT GGG GTA TCT AAT CCC AGT TTG`

4. Primary 12S cycling parameters:
  ```
  95 °C for 5 minutes
  40 cycles of:
  - 95 °C for 15 seconds
  - 55 °C for 30 seconds
  - 72 °C for 30 seconds
  Held at 4 °C
  ```
5. Secondary PCR amplifications are conducted in triplicate 20 μl reactions using same reaction master mix as primary PCR, but with 0.8 μl of each tagged 12S forward and reverse primer (10 μM) listed below (forward & reverse with matching unique 6-base tag, indicated by Xs). 
 - 12S (forward): `NNN XXX XXX GTC GGT AAA ACT CGT GCC AGC`
 - 12S (reverse): `NNN XXX XXX CAT AGT GGG GTA TCT AAT CCC AGT TTG`
 
6. The reaction is carried through with 2 μl of each purified environmental as well as positive and NTC samples.
7. Secondary 12S tagged PCR cycling parameters:
  ```
  95 °C for 5 minutes
  Twenty cycles of: 
  - 95 °C for 15 seconds
  - 57 °C for 30 seconds
  - 72 °C for 30 seconds
  Held at 4 °C
  ```  

## Quality Control, PCR Clean-up
8. After PCR amplification of the marker region, the pooled PCR products were run through an agarose gel to confirm the presence of target bands and absense of non-specific amplification across environmental samples as well as the absence of amplification in no-template controls (NTCs).
9. PCR products were purified and size selected using the Agencourt AMPure XP bead system (Beckman Coulter, USA). 
10. A second agarose gel was run to confirm primer removal and retention of target amplicons after purification. 
11. Purified products were then quantified using Quant-It Picogreen dsDNA Assay (Life Technologies) on an fmax Molecular Devices Fluorometer with a Qubit dsDNA HS kit.
12. Equimolar pools were constructed and quantified with Qubit dsDNA HS kit to confirm pool concentration prior to library preparation.
13. One library was constructed for each location sampled in using the KAPA HyperPrep and Library Quantification kits following manufacturer’s protocol.

## Sequencing Parameters
14. 12S rRNA gene was sequenced at Stanford Functional Genomics Facility. 
15. The pooled product for each genetic locus was loaded on a standard MiSeq v2 flow cell and sequenced in a 2x250bp paired end format using a v2 500-cycle MiSeq reagent cartridge. 
16. The MiSeq run was performed and 20% PhiX was added. 
17. Base calling was done by Illumina Real Time Analysis (RTA) v1.18.54 and output of RTA was demultiplexed and converted to FastQ format with Illumina Bcl2fastq v2.18.0. 
18. Custom sequencing primers were added to appropriate wells of the reagent cartridge. 
 
   *12S rRNA*  
  - FK NEXTflex Library barcode 6: `CTTGTA`
  - MB NEXTflex Library barcode 4: `GCCAAT`

[Back to Wet Lab Protocols](MBARI_wet_lab.md)
