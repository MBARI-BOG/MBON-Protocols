[Back to Wet Lab Protocols](MBARI_wet_lab.md)

# Environmental DNA (eDNA) 16S metabarcoding Illumina MiSeq NGS PCR Protocol V.2

#### Collin Closek<sup>1</sup>,Anni Djurhuus<sup>2</sup>,Katie Pitz<sup>3</sup>,Ryan Kelly<sup>4</sup>,Reiko Michisaki<sup>3</sup>,Kristine Walz<sup>3</sup>,Hilary Starks<sup>1</sup>,Francisco Chavez<sup>3</sup>,Alexandria Boehm<sup>1</sup>,Mya Breitbart<sup>2</sup>
#### <sup>1</sup>Center for Ocean Solutions, Stanford University, CA;<sup>2</sup>University of South Florida, College of Marine Science, St Petersburg, FL;<sup>3</sup>Monterey Bay Aquarium Research Institute, Moss Landing, CA;<sup>4</sup>University of Washington, Seattle, WA
##### Apr 09, 2018

## ABSTRACT
This protocol is aimed at amplifying the 16S rRNA hypervariable region 4 (16S V4) in prokaryotes. The primers (515fB and 806rB, 926R) used in this protocol are based on the primer utilized in Apprill et al 2015 and the Earth Microbiome Project (EMP).
 
This work was supported by NASA grant NNX14AP62A ‘National Marine Sanctuaries as Sentinel Sites for a Demonstration Marine Biodiversity Observation Network (MBON)’ funded under the National Ocean Partnership Program (NOPP RFP NOAA-NOS-IOOS-2014-2003803 in partnership between NOAA, BOEM, and NASA), and the U.S. Integrated Ocean Observing System (IOOS) Program Office.
 
Citation
Apprill, A., McNally, S., Parsons, R. & Weber, L. Minor revision to V4 region SSU rRNA 806R gene primer greatly increases detection of SAR11 bacterioplankton. Aquat Microb Ecol 75, 129–137 (2015). doi:10.3354/ame01753
 
Earth Microbiom Project
http://press.igsb.anl.gov/earthmicrobiome/protocols-and-standards/16s/
### BEFORE STARTING
Disinfect work surfaces with 10% bleach, followed by 70% ethanol, then RNase Away and pipets with RNase Away. UV pipets, molecular grade water, and tube racks for 20 minutes prior to starting protocol.

## PCR
1. Both forward (515F-Y) and reverse (926R) primers for the 16S rRNA gene, targeting microorganisms, were tagged yielding dual-indexed reads (Apprill et al., 2015; Kozich et al., 2013; Parada et al., 2016). 
2. PCR reactions were carried out in triplicate according to Apprill et al. (2015) with 1:10 dilutions on all extracts on a two-step fluidigm PCR protocol. 
3. For general amplification (without barcodes) 1 μl DNA template was added to the master mix consisting of 
  - 4.9 μl sterile water
  - 5.0 μl 2.0X Hot Master Mix (Qiagen)
  - 6.05 μl of each primer
  
    Final concentration of 5 μM 

4. PCR reactions were run in 96-well plates with a NTC run in triplicate for each plate.
5. Cycling parameters:
  ```
  95 °C for 3 minutes
  Thirty cycles of 95 °C for 45 seconds
  - 50 °C for 45 seconds
  - 68 °C for 90 seconds
  - 68 °C for 5 minutes
  ```
6. For the secondary PCR step to attach barcodes to individual samples, 1 μl DNA template was added to the master mix consisting of 
  - 7.0 μl sterile water
  - 6.0 μl 2.5X Hot Master Mix (Qiagen)
  - 0.5 μl of each primer
 
    A final concentration of 6 μM

7. Secondary PCR cycling parameters:
  ```
  95 °C for 3 minutes
  Fifteen cycles of 95 °C for 15 seconds
  - 60 °C for 30 seconds
  - 72 °C for 1 minite
  - 72 °C for 3 minutes.
  ```

## Quality Control, PCR Clean-up
8. After PCR amplification of the marker region, the pooled PCR products were run through an agarose gel to confirm the presence of target bands and absense of non-specific amplification across environmental samples as well as the absence of amplification in no-template controls (NTCs).
9. PCR products were purified and size selected using the Agencourt AMPure XP bead system (Beckman Coulter, USA). 
10. A second agarose gel was run to confirm primer removal and retention of target amplicons after purification. 
11. Purified products were then quantified using Quant-It Picogreen dsDNA Assay (Life Technologies) on an fmax Molecular Devices Fluorometer with SoftMaxPro v1.3.1. 
12. Equimolar pools were constructed and quantified with Qubit dsDNA HS kit to confirm pool concentration prior to library preparation
13. One library was constructed for each location sampled in using the KAPA HyperPrep and Library Quantification kits following manufacturer’s protocol.

## Sequencing
14. Sequencing was performed at the Research Technology Support Facility (RTSF) Genomics Core at Michigan State University (MSU). 
15. The pooled product was loaded on a standard MiSeq v2 flow cell and sequenced in a 2x250bp paired end format using a v2 500-cycle MiSeq reagent cartridge. 
16. The MiSeq run was performed with a 10% PhiX spike. 
17. Custom sequencing primers were added to appropriate wells of the reagent cartridge.
18. Base calling was done by Illumina Real Time Analysis (RTA) v1.18.54 and output of RTA was demultiplexed and converted to FastQ format with Illumina Bcl2fastq v2.18.0. 


[Back to Wet Lab Protocols](MBARI_wet_lab.md)
