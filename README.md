# DXA Data Xtraction Assistant 
A software used to convert DXA output from xps format into csv files.

[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.3974993.svg)](https://doi.org/10.5281/zenodo.3974993)

***

# Content
*[Preparation](#Preparation)
  - [Installation](#Installation)
  - [DXA Outputs](#DXA-Outputs)

*[Usage](#Usage)
  - [Select Type of DXA Scanner](#Select-Type-of-DXA-Scanner)
  - [Select Input and Output Paths](#Select-Input-and-Output-Paths)
  - [Scan Type Selection](#Scan-Type-Selection)

*[Output Details](#Output-Details)
  - [Hologic](#Hologic)
    - [Hologic: Single Type](#Hologic-Single-Type)
      - [Hologic: Demographic](#Hologic-Demographic)
      - [Hologic: Total Body Bone](#Hologic-Total-Body-Bone)
      - [Hologic: Total Body Composition](#Hologic-Total-Body-Composition)
      - [Hologic: Total Body Ext](#Hologic-Total-Body-Ext)
      - [Hologic: Lumbar Spine](#Hologic-Lumbar-Spine)
      - [Hologic: Total Hip Ext](#Hologic-Total-Hip-Ext)
      - [Hologic: Radius Scan](#Hologic-Radius-Scan)
    - [Hologic: Merged Output](#Hologic-Merged-Output)
  - [Lunar Prodigy](#Lunar-Prodigy)
    - [Lunar Prodigy: Single Type](#Lunar-Prodigy-Single-Type)
      - [Lunar Prodigy: Demographic](#Lunar-Prodigy-Demographic)
      - [Lunar Prodigy: Total Body Bone Ext](#Lunar-Prodigy-Total-Body-Bone-Ext)
      - [Lunar Prodigy: Total Body Ext](#Lunar-Prodigy-Total-Body-Ext)
      - [Lunar Prodigy: Lumbar Spine Ext](#Lunar-Prodigy-Lumbar-Spine-Ext)
      - [Lunar Prodigy: Total Hip Ext](#Lunar-Prodigy-Total-Hip-Ext)
      - [Lunar Prodigy: Radius Scan](#Lunar-Prodigy-Radius-Scan)
    - [Lunar Prodigy: Merged Output](#Lunar-Prodigy-Merged-Output)
  - [MG](#MG)
    - [MG: Single Type](#MG-Single-Type)
      - [MG: Demographic](#MG-Demographic)
      - [MG: Total Body Bone Ext](#MG-Total-Body-Bone-Ext)
      - [MG: Total Body Ext](#MG-Total-Body-Ext)
      - [MG: Lumbar Spine Ext](#MG-Lumbar-Spine-Ext)
      - [MG: Total Hip Ext](#MG-Total-Hip-Ext)
      - [MG: Radius Scan](#MG-Radius-Scan)
    - [MG: Merged Output](#MG-Merged-Output)
  - [iDXA](#iDXA)
    - [iDXA: Single Type](#iDXA-Single-Type)
      - [iDXA: Demographic](#iDXA-Demographic)
      - [iDXA: Total Body Bone](#iDXA-Total-Body-Bone)
      - [iDXA: Total Body Ext](#iDXA-Total-Body-Ext)
      - [iDXA: Lumbar Spine](#iDXA-Lumbar-Spine)
      - [iDXA: Total Hip](#iDXA-Total-Hip)
      - [iDXA: Radius Scan](#iDXA-Radius-Scan)
    - [iDXA: Merged Output](#iDXA-Merged-Output)


###### <p dir='rtl' align='right'>[Back to Top](#Content)</p>

# Preparation
## Installation
The DXA Data Xtraction Assistant is a standalone application constructed by Python 3.7, which does not require installation. Just double click to run. It may take couple of minutes to load, the first time it is used. 
## DXA Outputs
The objective of the DXA Data Xtraction Assistant is to automate conversion for DXA output with “.xps” or ".pdf" format into “.csv” files. Input files should be named as following:
(Patient ID)\_(Number of Visit)\_(Scan Type).xps
* Patient ID: used to index patients, which must be unique and identical for each patient, and composed of only letters and numbers. There is no length limit. 
* Number of Visit: a number which denotes the ith visit of a patient. This must be a number but there is no length limit for this number. 
* Scan Type: a sequence of abbreviations that denotes the type of scan (Table 1).

*Table 1: Abbreviation of Scan Types*

|Scan Type|DXA Output|
|---|---|
|BC|Body Composition|
|BCext|Body Composition Extension|
|Bone|Total Body Bone|
|Boneext|Total Body Bone Extension|
|LS|Lumbar Spine|
|LSext|Lumbar Spine Extension|
|DH|Dual Hip|
|DHext|Dual Hip Extension|
|Radius|Radius Scan|

For example, a patient indexed as SSSH0001 went for a DXA scan at the 2nd time, then the Body Composition scan output should be saved as SSSH0001\_2\_BC.xps (do not include any other characters). 

![Figure 1: DXA outputs example](/FIG/FIG1.png)

*Figure 1: DXA outputs example*


###### <p dir='rtl' align='right'>[Back to Top](#Content)</p>
# Usage
The DXA Data Xtraction Assistant allows users to choose the input and output file paths. It also allows users to customize the output DXA data, to streamline “.csv” file outputs. In this section, we will introduce the User Interface of the Converter.

###### <p dir='rtl' align='right'>[Back to Top](#Content)</p>
## Select Type of DXA Scanner
A user interface will appear when you double click and run this application ([Figure 2: User Interface – Selecting Type of DXA Scanners](#DXA-Scanner)). Three DXA manufactures, Hologic, GE, and Norland are supported. 
* The Hologic button works for Horizon model with Apex software v5.5
* The Norland button works for both ELITE and XR-800 models, both of which use the same Illuminatus v 4.7.5 software.
* The GE button navigates to a new page ([Figure 3: User Interface – GE scanners](#GE-Scanner)). 
	* The MG button supports GE Lunar Prodigy enCORE software v12, 
	* The Lunar Prodigy button supports enCORE v.16
	* The iDXA button works for enCORE v17 and 18. 

## Select Input and Output Paths
After selecting the type of DXA scanner, users can select the input and output folders ([Figure 4: Input Interface – Selecting Input and Output Paths](#Path-Setting)). 
The input folder should be the folder that contains all DXA outputs (see [DXA Outputs](#DXA-Outputs)). The output folder is the folder where the output “.csv” files will be saved. Both input and output folders can be located anywhere on your computer or in an accessible cloud storage location. 

* Click the Input Folder and Output Folder buttons to select the file path for these locations. 
* Once both of these have been assigned, click the Transform button.  This will start the DXA Data Xtraction Assistant conversion process. 
* Click Step 2 to enter the next process.

![Figure 4: Input Interface – Selecting Input and Output Paths](/FIG/FIG2.png)

*Figure 4: Input Interface – Selecting Input and Output Paths*

###### <p dir='rtl' align='right'>[Back to Top](#Content)</p>
## Scan Type Selection
DXA Data Xtraction Assistant provides several options for the users to customize their output files ([Figure 5: Output Interface – Selecting the Interested Outcomes](#Scan-Type-Selection)). 
* Check all data that should be included in the DXA Data Xtraction Assistant output “.csv” file.  
* Then, click the Merge button. 
The “.csv” files with the chosen data will then be saved in the assigned output file path.

![Figure 5: Output Interface – Selecting the Interested Outcomes](/FIG/FIG3.png)

*Figure 5: Output Interface – Selecting the Interested Outcomes*

###### <p dir='rtl' align='right'>[Back to Top](#Content)</p>
# Output Details
The created “.csv” output files will be saved in the provided file path.  Output files are automatically provided using two types of output formats: (1) the first separates out information into one “.csv” file for participant information and a separate “.csv” file for each DXA scan type; (2) the second output format results in a large, merged table containing all information (participant information and scan type). Details of this process are introduced in the following sections.
The output “.csv” files include a merged file, named “MergedOutput.csv”, in the selected output file path, as well as a subfolder named as “SingleType” ([Figure 6: Merged Output](#Output-Details)), which contains the participant information in one file, “Demographic.csv” and the information for each requested DXA scan type as separate “.csv” file ([Figure 7: Schematic for the “.csv” output files in the “SingleType” Subfolder for the DXA Data Xtraction Assistant](#Output-Details)).

![Figure 6: Merged Output](/FIG/FIG4.png)

*Figure 6: Merged Output*

![Figure 7: Schematic for the “.csv” output files in the “SingleType” Subfolder for the DXA Data Xtraction Assistant](/FIG/FIG5.png)

*Figure 7: Schematic for the “.csv” output files in the “SingleType” Subfolder for the DXA Data Xtraction Assistant *

###### <p dir='rtl' align='right'>[Back to Top](#Content)</p>

## Hologic
### Hologic: Single Type
#### Hologic: Demographic
The “Demographic.csv” file is a default file which is automatically generated when using the DXA Data Xtraction Assistant.  This file contains each patients’ demographic information, collected from each DXA output. This file includes 8 columns (Table 2). 

*Table 2: Demographic output*

|Variables|Description|
|---|---|
|Patients_ID|Patient ID, from the input file name|
|Patients_Visit|Visit Number, from the input file name|
|Name	|Patient name, as it appears in the DXA scan |
|Age	|Patient age, as it appears in the DXA scan |
|DOB	|Patient date of birth, as it appears in the DXA scan |
|Sex	|Patient sex, as it appears in the DXA scan |
|Ethnicity	|Patient Ethnicity, as it appears in the DXA scan |
|Height	|Patient Height, as it appears in the DXA scan |

###### <p dir='rtl' align='right'>[Back to Top](#Content)</p>
#### Hologic: Total Body Bone
If the Total Body Bone option was selected, a “TotalBodyBone.csv” would be generated in “SingleType” subfolder ([Figure 7: Schematic for the “.csv” output files in the “SingleType” Subfolder for the DXA Data Xtraction Assistant](#Output-Details)). Table 5 introduced the meaning of each column.

*Table 5: Total Body Bone output*

|Variables	|Explanation|
|---|---|
|Patients_ID	|Patient ID, from the input file name|
|Patients_Visit	|Visit Number, from the input file name|
|Region	|Region of DXA measurement|
|Area_cm2	|Area (cm2)|
|BMC_g	|Bone Mineral Content (g)|
|BMD_g/cm2	|Areal Bone Mineral Density (g/cm2)|
|T_score	|T-score|
|Z_score	|Z-score|


###### <p dir='rtl' align='right'>[Back to Top](#Content)</p>
#### Hologic: Total Body Composition
If the Total Body Composition option was selected, three outputs files will be created in the “SingleType” subfolder ([Figure 7: Schematic for the “.csv” output files in the “SingleType” Subfolder for the DXA Data Xtraction Assistant](#Output-Details)): (1) “TotalBodyComp_Adipose.csv”, (2) “TotalBodyComp_Composition.csv”, and (3) “TotalBodyComp_Lean.csv. 
Table 7 introduced the meaning of each column for “TotalBodyComp_Adipose.csv”

*Table 7: Total Body Composition - Adipose output*

|Patients_ID	|Patient ID, from the input file name|
|---|---|
|Patients_Visit	|Visit Number, from the input file name|
|Measure	|Measurement names|
|Result	|Measurement values|
|Tscore	|T-scores|
|Zscore	|Z-scores|

Table 8 introduced the meaning of each column for “TotalBodyComp_Composition.csv”

*Table 8: Total Body Composition - Composition output*

|Variables	|Explanation|
|---|---|
|Patients_ID	|Patient ID, from the input file name|
|Patients_Visit	|Visit Number, from the input file name|
|Region	|Region of DXA measurement|
|Fat_Mass_g	|Fat Mass (g)|
|Lean_Mass_g	|Lean Mass (g)|
|Total_Mass_g	|Total Mass (g)|
|Fat_Percent	|Fat Percent (%)|
|Fat_Percent_Tscore	|T-score of Fat Percent (%)|
|Fat_Percent_Zscore	|Z-score of Fat Percent|

Table 9 introduced the meaning of each column for “TotalBodyComp_Lean.csv”

*Table 9: Total Body Composition - Lean output*

|Variables	|Explanation|
|--|--|
|Patients_ID	|Patient ID, from the input file name|
|Patients_Visit	|Visit Number, from the input file name|
|Measure	|Measurement names|
|Result	|Measurement values|
|Tscore	|T-scores|
|Zscore	|Z-scores|


###### <p dir='rtl' align='right'>[Back to Top](#Content)</p>
#### Hologic: Total Body Ext
If the Total Body Ext option was selected, a “TotalBodyExt.csv” would be generated in “SingleType” subfolder ([Figure 7: Schematic for the “.csv” output files in the “SingleType” Subfolder for the DXA Data Xtraction Assistant](#Output-Details)). Table 6 introduced the meaning of each column.

*Table 6: Total Body Ext output*

|Variables	|Explanation|
|---|---|
|Patients_ID	|Patient ID, from the input file name|
|Patients_Visit	|Visit Number, from the input file name|
|Region	|Region of DXA measurement|
|BMC_g	|Bone Mineral Content (g)|
|Fat_Mass_g	|Fat Mass (g)|
|Lean_Mass_g	|Lean Mass (g)|
|Lean_BMC_g	|Lean Bone Mineral Content (g)|
|Total_Mass_g	|Total Mass (g)|
|Fat_Percent	|Fat Percent (%)|


###### <p dir='rtl' align='right'>[Back to Top](#Content)</p>
#### Hologic: Lumbar Spine
If the Lumbar Spine option was selected, a “LumbarSpine.csv” would be generated in “SingleType” subfolder ([Figure 7: Schematic for the “.csv” output files in the “SingleType” Subfolder for the DXA Data Xtraction Assistant](#Output-Details)). Table 4 introduced the meaning of each column.

*Table 4: Lumbar Spine output*

|Variables	|Explanation|
|---|---|
|Patients_ID	|Patient ID, from the input file name|
|Patients_Visit	|Visit Number, from the input file name|
|Region	|Region of DXA measurement|
|Area_cm2	|Area (cm2)|
|BMC_g	|Bone Mineral Content (g)|
|BMD_g/cm2	|Areal Bone Mineral Density (g/cm2)|
|T_score	|T-score|
|Z_score	|Z-score|

###### <p dir='rtl' align='right'>[Back to Top](#Content)</p>
#### Hologic: Total Hip Ext
If the Total Hip Ext option was selected, a “TotalHipExt.csv” would be generated in the “SingleType” subfolder of the output file path ([Figure 7: Schematic for the “.csv” output files in the “SingleType” Subfolder for the DXA Data Xtraction Assistant](#Output-Details)). Table 3 introduced the meaning of each column.

*Table 3: Total Hip Ext output*

|Variables	|Explanation|
|---|---|
|Patients_ID	|Patient ID, from the input file name|
|Patients_Visit	|Visit Number, from the input file name|
|Region	|Region of DXA measurement|
|Area_cm2	|Area (cm2)|
|BMC_g	|Bone Mineral Content (g)|
|BMD_g/cm2	|Areal Bone Mineral Density (g/cm2)|
|T_score	|T-score|
|Z_score	|Z-score|

###### <p dir='rtl' align='right'>[Back to Top](#Content)</p>
#### Hologic: Radius Scan
If the Radius Scan option was selected, a “Rad.csv” would be generated in “SingleType” subfolder ([Figure 7: Schematic for the “.csv” output files in the “SingleType” Subfolder for the DXA Data Xtraction Assistant](#Output-Details)). Table 10 introduced the meaning of each column.

*Table 10: Radius Scan output*

|Variables	|Explanation|
|---|---|
|Patients_ID	|Patient ID, from the input file name|
|Patients_Visit	|Visit Number, from the input file name|
|Radius+Ulna |Region of DXA measurement|
|Area_cm2	|Area (cm2)|
|BMC_g	|Bone Mineral Content (g)|
|BMD_g/cm2	|Areal Bone Mineral Density (g/cm2)|
|Z_score	|Z-score|


###### <p dir='rtl' align='right'>[Back to Top](#Content)</p>
### Hologic: Merged Output
A “MergedOutput.csv” would be generated in the output path ([Figure 6: Merged Output](#Output-Details)). It would only contain the interested outcomes as selected ([Figure 5: Output Interface – Selecting the Interested Outcomes](#Scan-Type-Selection)). Table 11 introduced the meaning of each column when all options were picked up.

*Table 11: Merged Output*

|Options	|Variables	|Explanation|
|---|---|---|
|Demographic	|Patients_ID	|Patient ID, from the input file name|
|	|Visit	|Visit Number, from the input file name|
|	|Name	|Patient name appeared in the scan report|
|	|Age	|Patient age|
|	|DOB	|Patient date of birth|
|	|Sex	|Patient sex|
|	|Ethnicity	|Patient Ethnicity|
|	|Height	|Patient Height|
|Total Body Bone	|LArmBMD	|Left Arm Areal Bone Mineral Density (g/cm2)|
|	|RArmBMD	|Right Arm Areal Bone Mineral Density (g/cm2)|
|	|LRibBMD	|Left Rib Areal Bone Mineral Density (g/cm2)|
|	|RRibBMD	|Right Rib Areal Bone Mineral Density (g/cm2)|
|	|LLegBMD	|Left Leg Areal Bone Mineral Density (g/cm2)|
|	|RLegBMD	|Right Leg Areal Bone Mineral Density (g/cm2)|
|	|TotBMC	|Total Body Bone Mineral Content (g)|
|	|TotBMD	|Total Body Areal Bone Mineral Density (g/cm2)|
|	|TotTScr	|Total Body T-score|
|	|TotZScr	|Total Body Z-score|
|Total Body Composition - Composition	|AndroidFM	|Android Fat Mass (g)|
|	|AndroidLM+BMC	|Android Mass (g) + Bone Mineral Content (g)|
|	|AndroidTotM	|Android Total Mass (g)|
|	|AndroidBF%	|Android Body Fat (%)|
|	|GynoidFM	|Gynoid Fat Mass (g)|
|	|GynoidLM+BMC	|Gynoid Mass (g) + Bone Mineral Content (g)|
|	|GynoidTotM	|Gynoid Total Mass (g)|
|	|GynoidBF%	|Gynoid Body Fat (%)|
|Total Body Composition - Adipose	|A/G	|Android/Gynoid Ratio|
|	|VATm	|Est. VAT Mass (g)|
|	|VATv	|Est. VAT Volume (cm2)|
|	|VATa	|Est. VAT Area (cm2)|
|Total Body Composition - Lean	|Ln/Ht	|Lean/Height² (kg/m2)|
|	|AppLn/Ht	|Appen. Lean/Height² (kg/m²)|
|Total Body Ext	|LArmBMC	|Left Arm Bone Mineral Content (g)|
|	|LArmFM*	|Left Arm Fat Mass (g)|
|	|LArmLM	|Left Arm Lean Mass (g)|
|	|LArmLM+BMC*	|Left Arm Lean Mass (g) + Bone Mineral Content (g)|
|	|LArmTotM*	|Left Arm Total Mass (g)|
|	|LArmBF%*	|Left Arm Body Fat (%)|
|	|RArmBMC	|Right Arm Bone Mineral Content (g)|
|	|RArmFM*	|Right Arm Fat Mass (g)|
|	|RArmLM	|Right Arm Lean Mass (g)|
|	|RArmLM+BMC*	|Right Arm Lean Mass (g) + Bone Mineral Content (g)|
|	|RArmTotM*	|Right Arm Total Mass (g)|
|	|RArmBF%*	|Right Arm Body Fat (%)|
|	|TrunkBMC	|Trunk Arm Bone Mineral Content (g)|
|	|TrunkFM*	|Trunk Arm Fat Mass (g)|
|	|TrunkLM	|Trunk Arm Lean Mass (g)|
|	|TrunkLM+BMC*	|Trunk Arm Lean Mass (g) + Bone Mineral Content (g)|
|	|TrunkTotM*	|Trunk Arm Total Mass (g)|
|	|TrunkBF%*	|Trunk Arm Body Fat (%)|
|	|LLegBMC	|Left Leg Bone Mineral Content (g)|
|	|LLegFM*	|Left Leg Fat Mass (g)|
|	|LLegLM	|Left Leg Lean Mass (g)|
|	|LLegLM+BMC*	|Left Leg Lean Mass (g) + Bone Mineral Content (g)|
|	|LLegTotM*	|Left Leg Total Mass (g)|
|	|LLegBF%*	|Left Leg Body Fat (%)|
|	|RLegBMC	|Right Leg Bone Mineral Content (g)|
|	|RLegFM*	|Right Leg Fat Mass (g)|
|	|RLegLM	|Right Leg Lean Mass (g)|
|	|RLegLM+BMC*	|Right Leg Lean Mass (g) + Bone Mineral Content (g)|
|	|RLegTotM*	|Right Leg Total Mass (g)|
|	|RLegBF%*	|Right Leg Body Fat (%)|
|	|SubTotalBMC	|Subtotal Bone Mineral Content (g)|
|	|SubTotalFM*	|Subtotal Fat Mass (g)|
|	|SubTotalLM	|Subtotal Lean Mass (g)|
|	|SubTotalLM+BMC*	|Subtotal Lean Mass (g) + Bone Mineral Content (g)|
|	|SubTotalTotM*	|Subtotal Total Mass (g)|
|	|SubTotalBF%*	|Subtotal Body Fat (%)|
|	|HeadBMC	|Head Bone Mineral Content (g)|
|	|HeadFM*	|Head Fat Mass (g)|
|	|HeadLM	|Head Lean Mass (g)|
|	|HeadLM+BMC*	|Head Lean Mass (g) + Bone Mineral Content (g)|
|	|HeadTotM*	|Head Total Mass (g)|
|	|HeadBF%*	|Head Body Fat (%)|
|	|TotalBMC	|Total Bone Mineral Content (g)|
|	|TotalFM*	|Total Fat Mass (g)|
|	|TotalLM	|Total Lean Mass (g)|
|	|TotalLM+BMC*	|Total Lean Mass (g) + Bone Mineral Content (g)|
|	|TotalTotM*	|Total Total Mass (g)|
|	|TotalBF%*	|Total Body Fat (%)|
|Lumbar Spine	|L1L4BMC	|L1-L4 Bone Mineral Content (g)|
|	|L1L4BMD	|L1-L4 Areal Bone Mineral Density (g/cm2)|
|	|L1L4TScr	|L1-L4 T-score|
|	|L1L4ZScr	|L1-L4 Z-score|
|Total Hip Ext  |LFNBMC	|Left Femoral Neck Bone Mineral Content (g)|
|	|LFNBMD	|Left Femoral Neck Areal Bone Mineral Density (g/cm2)|
|	|LFNTScr	|Left Femoral Neck T-score|
|	|LFNZScr	|Left Femoral Neck Z-score|
|	|RFNBMC	|Right Femoral Neck Bone Mineral Content (g)|
|	|RFNBMD	|Right Femoral Neck Areal Bone Mineral Density (g/cm2)|
|	|RFNTScr	|Right Femoral Neck T-score|
|	|RFNZScr	|Right Femoral Neck Z-score|
|	|LGTBMC	|Left Greater Trochanter Neck Bone Mineral Content (g)|
|	|LGTBMD	|Left Greater Trochanter Neck Areal Bone Mineral Density (g/cm2)|
|	|LGTTScr	|Left Greater Trochanter Neck T-score|
|	|LGTZScr	|Left Greater Trochanter Neck Z-score|
|	|RGTBMC	|Right Greater Trochanter Neck Bone Mineral Content (g)|
|	|RGTBMD	|Right Greater Trochanter Neck Areal Bone Mineral Density (g/cm2)|
|	|RGTTScr	|Right Greater Trochanter Neck T-score|
|	|RGTZScr	|Right Greater Trochanter Neck Z-score|
|	|LTHBMC	|Left Total Hip Neck Bone Mineral Content (g)|
|	|LTHBMD	|Left Total Hip Neck Areal Bone Mineral Density (g/cm2)|
|	|LTHTScr	|Left Total Hip Neck T-score|
|	|LTHZScr	|Left Total Hip Neck Z-score|
|	|RTHBMC	|Right Total Hip Neck Bone Mineral Content (g)|
|	|RTHBMD	|Right Total Hip Neck Areal Bone Mineral Density (g/cm2)|
|	|RTHTScr	|Right Total Hip Neck T-score|
|	|RTHZScr	|Right Total Hip Neck Z-score|
|	|MeanTHTScr	|Mean Total Hip Neck T-score|
|	|MeanTHBMC	|Mean Total Hip Neck Bone Mineral Content (g)|
|	|MeanTHBMD	|Mean Total Hip Neck Areal Bone Mineral Density (g/cm2)|
|Radius Scan |Rad1/3Area	|Third-distal Area (cm2)|
| |Rad1/3BMC |Third-distal Bone Mineral Content (g)|
| |Rad1/3BMD |Third-distal Areal Bone Mineral Density (g/cm2)|
| |Rad1/3Zsc |Third-distal  Z-score|
| |RadMIDArea	|Mid-distal Area (cm2)|
| |RadMIDBMC |Mid-distal Bone Mineral Content (g)|
| |RadMIDBMD |Mid-distal Areal Bone Mineral Density (g/cm2)|
| |RadMIDZsc |Mid-distal Z-score|
| |RadUDArea	|Ultradistal Area (cm2)|
| |RadUDBMC |Ultradistal Bone Mineral Content (g)|
| |RadUDBMD |Ultradistal Areal Bone Mineral Density (g/cm2)|
| |RadUDZsc |Ultradistal Z-score|
| |RadTotArea	|Total distal Area (cm2)|
| |RadTotBMC |Total distal Bone Mineral Content (g)|
| |RadTotBMD |Total distal Areal Bone Mineral Density (g/cm2)|
| |RadTotZsc |Total distal Z-score|
									

###### <p dir='rtl' align='right'>[Back to Top](#Content)</p>

## Lunar Prodigy
### Lunar Prodigy: Single Type
#### Lunar Prodigy: Demographic
The “Demographic.csv” file is a default file which is automatically generated when using the DXA Data Xtraction Assistant.  This file contains each patients’ demographic information, collected from each DXA output. This file includes 8 columns (Table 2). 

*Table 2: Demographic output*

|Variables|Description|
|---|---|
|Patients_ID|Patient ID, from the input file name|
|Patients_Visit|Visit Number, from the input file name|
|Name	|Patient name, as it appears in the DXA scan |
|Age	|Patient age, as it appears in the DXA scan |
|DOB	|Patient date of birth, as it appears in the DXA scan |
|Sex	|Patient sex, as it appears in the DXA scan |
|Ethnicity	|Patient Ethnicity, as it appears in the DXA scan |
|Height	|Patient Height, as it appears in the DXA scan |
|Weight	|Patient Weight, as it appears in the DXA scan |

###### <p dir='rtl' align='right'>[Back to Top](#Content)</p>
#### Lunar Prodigy: Total Body Bone Ext
If the Total Body Bone Ext option was selected, a “TotalBodyBoneExt.csv” would be generated in “SingleType” subfolder ([Figure 7: Schematic for the “.csv” output files in the “SingleType” Subfolder for the DXA Data Xtraction Assistant](#Output-Details)). Table 5 introduced the meaning of each column.

*Table 5: Total Body Bone Ext output*

|Variables	|Explanation|
|---|---|
|Patients_ID	|Patient ID, from the input file name|
|Patients_Visit	|Visit Number, from the input file name|
|Region	|Region of DXA measurement|
|BMD_g/cm2	|Areal Bone Mineral Density (g/cm2)|
|YA_Percent	|The mean of a young adult reference|
|YA_T_score	|T-score|
|AM_Percent	|The mean of an age-matched reference|
|AM_Z_score	|Z-score|
|BMC_g	|Bone Mineral Content (g)|
|Area_cm2	|Area (cm2)|


###### <p dir='rtl' align='right'>[Back to Top](#Content)</p>
#### Lunar Prodigy: Total Body Ext
If the Total Body Ext option was selected, a “TotalBodyExt.csv” would be generated in “SingleType” subfolder ([Figure 7: Schematic for the “.csv” output files in the “SingleType” Subfolder for the DXA Data Xtraction Assistant](#Output-Details)). Table 6 introduced the meaning of each column.

*Table 6: Total Body Ext output*

|Variables	|Explanation|
|---|---|
|Patients_ID	|Patient ID, from the input file name|
|Patients_Visit	|Visit Number, from the input file name|
|Region	|Region of DXA measurement|
|Tissue_Percent_Fat	|Tissue Fat (%)|
|Region_Percent_Fat	|Region Fat (%)|
|Tissue_g	|Tissue Mass (g)|
|Fat_g	|Fat Mass (g)|
|Lean_g	|Lean Mass (g)|
|BMC_g	|Bone Mineral Content (g)|
|Total_Mass_kg	|Total Mass (kg)|



###### <p dir='rtl' align='right'>[Back to Top](#Content)</p>
#### Lunar Prodigy: Lumbar Spine Ext
If the Lumbar Spine Ext option was selected, a “LumbarSpineExt.csv” would be generated in “SingleType” subfolder ([Figure 7: Schematic for the “.csv” output files in the “SingleType” Subfolder for the DXA Data Xtraction Assistant](#Output-Details)). Table 4 introduced the meaning of each column.

*Table 4: Lumbar Spine Ext output*

|Variables	|Explanation|
|---|---|
|Patients_ID	|Patient ID, from the input file name|
|Patients_Visit	|Visit Number, from the input file name|
|Region	|Region of DXA measurement|
|BMD_g/cm2	|Areal Bone Mineral Density (g/cm2)|
|YA_Percent	|The mean of a young adult reference|
|YA_T_score	|T-score|
|AM_Percent	|The mean of an age-matched reference|
|AM_Z_score	|Z-score|
|BMC_g	|Bone Mineral Content (g)|
|Area_cm2	|Area (cm2)|
|Width_cm	|Width (cm)|
|Height_cm	|Height (cm)|

###### <p dir='rtl' align='right'>[Back to Top](#Content)</p>
#### Lunar Prodigy: Total Hip Ext
If the Total Hip Ext option was selected, a “TotalHipExt.csv” would be generated in the “SingleType” subfolder of the output file path ([Figure 7: Schematic for the “.csv” output files in the “SingleType” Subfolder for the DXA Data Xtraction Assistant](#Output-Details)). Table 3 introduced the meaning of each column.

*Table 3: Total Hip Ext output*

|Variables	|Explanation|
|---|---|
|Patients_ID	|Patient ID, from the input file name|
|Patients_Visit	|Visit Number, from the input file name|
|Region	|Region of DXA measurement|
|BMD_g/cm2	|Areal Bone Mineral Density (g/cm2)|
|YA_Percent	|The mean of a young adult reference|
|YA_T_score	|T-score|
|AM_Percent	|The mean of an age-matched reference|
|AM_Z_score	|Z-score|
|BMC_g	|Bone Mineral Content (g)|
|Area_cm2	|Area (cm2)|

###### <p dir='rtl' align='right'>[Back to Top](#Content)</p>
#### Lunar Prodigy: Radius Scan
If the Radius Scan option was selected, a “Rad.csv” would be generated in “SingleType” subfolder ([Figure 7: Schematic for the “.csv” output files in the “SingleType” Subfolder for the DXA Data Xtraction Assistant](#Output-Details)). Table 10 introduced the meaning of each column.

*Table 10: Radius Scan output*

|Variables	|Explanation|
|---|---|
|Patients_ID	|Patient ID, from the input file name|
|Patients_Visit	|Visit Number, from the input file name|
|Region	|Region of DXA measurement|
|BMD_g/cm2	|Areal Bone Mineral Density (g/cm2)|
|YA_Percent	|The mean of a young adult reference|
|YA_T_score	|T-score|
|AM_Percent	|The mean of an age-matched reference|
|AM_Z_score	|Z-score|


###### <p dir='rtl' align='right'>[Back to Top](#Content)</p>
### Lunar Prodigy: Merged Output
A “MergedOutput.csv” would be generated in the output path ([Figure 6: Merged Output](#Output-Details)). It would only contain the interested outcomes as selected ([Figure 5: Output Interface – Selecting the Interested Outcomes](#Scan-Type-Selection)). Table 11 introduced the meaning of each column when all options were picked up.

*Table 11: Merged Output*

|Options	|Variables	|Explanation|
|---|---|---|
|Demographic	|Patients_ID	|Patient ID, from the input file name|
|	|Visit	|Visit Number, from the input file name|
|	|Name	|Patient name appeared in the scan report|
|	|Age	|Patient age|
|	|DOB	|Patient date of birth|
|	|Sex	|Patient sex|
|	|Ethnicity	|Patient Ethnicity|
|	|Height	|Patient Height|
|	|Weight	|Patient Weight|
|Total Body Bone Ext	|LArmBMD	|Left Arm Areal Bone Mineral Density (g/cm2)|
|	|RArmBMD	|Right Arm Areal Bone Mineral Density (g/cm2)|
|	|RibBMD	|Rib Areal Bone Mineral Density (g/cm2)|
|	|LLegBMD	|Left Leg Areal Bone Mineral Density (g/cm2)|
|	|RLegBMD	|Right Leg Areal Bone Mineral Density (g/cm2)|
|	|TotBMC	|Total Body Bone Mineral Content (g)|
|	|TotBMD	|Total Body Areal Bone Mineral Density (g/cm2)|
|	|TotTScr	|Total Body T-score|
|	|TotZScr	|Total Body Z-score|
|Total Body Ext	|ArmsRegPerFat	|Arms Region Fat Percent(%)|
|	|ArmsTissue	|Arms Tissue Mass (g)|
|	|ArmsFat	|Arms Fat Mass (g)|
|	|ArmsLean	|Arms Lean Mass (g)|
|	|ArmsBMC	|Arms Bone Mineral Content (g)|
|	|ArmsTotalMass	|Arms Total Mass (kg)|
|	|ArmRRegPerFat	|Right Arm Region Fat Percent(%)|
|	|ArmRTissue	|Right Arm Tissue Mass (g)|
|	|ArmRFat	|Right Arm Fat Mass (g)|
|	|ArmRLean	|Right Arm Lean Mass (g)|
|	|ArmRBMC	|Right Arm Bone Mineral Content (g)|
|	|ArmRTotalMass	|Right Arm Total Mass (kg)|
|	|ArmLRegPerFat	|Left Arm Region Fat Percent(%)|
|	|ArmLTissue	|Left Arm Tissue Mass (g)|
|	|ArmLFat	|Left Arm Fat Mass (g)|
|	|ArmLLean	|Left Arm Lean Mass (g)|
|	|ArmLBMC	|Left Arm Bone Mineral Content (g)|
|	|ArmLTotalMass	|Left Arm Total Mass (kg)|
|	|ArmDRegPerFat	|Left Arm Region Fat Percent Difference (%)|
|	|ArmDTissue	|Arm Tissue Mass Difference (g)|
|	|ArmDFat	|Arm Fat Mass Difference (g)|
|	|ArmDLean	|Arm Lean Mass Difference (g)|
|	|ArmDBMC	|Arm Bone Mineral Content Difference (g)|
|	|ArmDTotalMass	|Arm Total Mass Difference (kg)|
|	|LegsRegPerFat	|Legs Region Fat Percent(%)|
|	|LegsTissue	|Legs Tissue Mass (g)|
|	|LegsFat	|Legs Fat Mass (g)|
|	|LegsLean	|Legs Lean Mass (g)|
|	|LegsBMC	|Legs Bone Mineral Content (g)|
|	|LegsTotalMass	|Legs Total Mass (kg)|
|	|LegRRegPerFat	|Right Leg Region Fat Percent(%)|
|	|LegRTissue	|Right Leg Tissue Mass (g)|
|	|LegRFat	|Right Leg Fat Mass (g)|
|	|LegRLean	|Right Leg Lean Mass (g)|
|	|LegRBMC	|Right Leg Bone Mineral Content (g)|
|	|LegRTotalMass	|Right Leg Total Mass (kg)|
|	|LegLRegPerFat	|Left Leg Region Fat Percent(%)|
|	|LegLTissue	|Left Leg Tissue Mass (g)|
|	|LegLFat	|Left Leg Fat Mass (g)|
|	|LegLLean	|Left Leg Lean Mass (g)|
|	|LegLBMC	|Left Leg Bone Mineral Content (g)|
|	|LegLTotalMass	|Left Leg Total Mass (kg)|
|	|LegDRegPerFat	|Left Leg Region Fat Percent Difference (%)|
|	|LegDTissue	|Legs Tissue Mass Difference (g)|
|	|LegDFat	|Legs Fat Mass Difference (g)|
|	|LegDLean	|Legs Lean Mass Difference (g)|
|	|LegDBMC	|Legs Bone Mineral Content Difference (g)|
|	|LegDTotalMass	|Legs Total Mass Difference (kg)|
|	|TrunkRegPerFat	|Trunk Region Fat Percent(%)|
|	|TrunkTissue	|Trunk Tissue Mass (g)|
|	|TrunkFat	|Trunk Fat Mass (g)|
|	|TrunkLean	|Trunk Lean Mass (g)|
|	|TrunkBMC	|Trunk Bone Mineral Content (g)|
|	|TrunkTotalMass	|Trunk Total Mass (kg)|
|	|TrunkRRegPerFat	|Right Trunk Region Fat Percent(%)|
|	|TrunkRTissue	|Right Trunk Tissue Mass (g)|
|	|TrunkRFat	|Right Trunk Fat Mass (g)|
|	|TrunkRLean	|Right Trunk Lean Mass (g)|
|	|TrunkRBMC	|Right Trunk Bone Mineral Content (g)|
|	|TrunkRTotalMass	|Right Trunk Total Mass (kg)|
|	|TrunkLRegPerFat	|Left Trunk Region Fat Percent(%)|
|	|TrunkLTissue	|Left Trunk Tissue Mass (g)|
|	|TrunkLFat	|Left Trunk Fat Mass (g)|
|	|TrunkLLean	|Left Trunk Lean Mass (g)|
|	|TrunkLBMC	|Left Trunk Bone Mineral Content (g)|
|	|TrunkLTotalMass	|Left Trunk Total Mass (kg)|
|	|TrunkDRegPerFat	|Left Trunk Region Fat Percent Difference (%)|
|	|TrunkDTissue	|Trunk Tissue Mass Difference (g)|
|	|TrunkDFat	|Trunk Fat Mass Difference (g)|
|	|TrunkDLean	|Trunk Lean Mass Difference (g)|
|	|TrunkDBMC	|Trunk Bone Mineral Content Difference (g)|
|	|TrunkDTotalMass	|Trunk Total Mass Difference (kg)|
|	|AndroidRegPerFat	|Android Region Fat Percent(%)|
|	|AndroidTissue	|Android Tissue Mass (g)|
|	|AndroidFat	|Android Fat Mass (g)|
|	|AndroidLean	|Android Lean Mass (g)|
|	|AndroidBMC	|Android Bone Mineral Content (g)|
|	|AndroidTotalMass	|Android Total Mass (kg)|
|	|GynoidRegPerFat	|Gynoid Region Fat Percent(%)|
|	|GynoidTissue	|Gynoid Tissue Mass (g)|
|	|GynoidFat	|Gynoid Fat Mass (g)|
|	|GynoidLean	|Gynoid Lean Mass (g)|
|	|GynoidBMC	|Gynoid Bone Mineral Content (g)|
|	|GynoidTotalMass	|Gynoid Total Mass (kg)|
|	|TotalRegPerFat	|Total Region Fat Percent(%)|
|	|TotalTissue	|Total Tissue Mass (g)|
|	|TotalFat	|Total Fat Mass (g)|
|	|TotalLean	|Total Lean Mass (g)|
|	|TotalBMC	|Total Bone Mineral Content (g)|
|	|TotalTMass	|Total Mass (kg)|
|	|TotalRRegPerFat	|Right Total Region Fat Percent(%)|
|	|TotalRTissue	|Right Total Tissue Mass (g)|
|	|TotalRFat	|Right Total Fat Mass (g)|
|	|TotalRLean	|Right Total Lean Mass (g)|
|	|TotalRBMC	|Right Total Bone Mineral Content (g)|
|	|TotalRTotalMass	|Right Total Total Mass (kg)|
|	|TotalLRegPerFat	|Left Total Region Fat Percent(%)|
|	|TotalLTissue	|Left Total Tissue Mass (g)|
|	|TotalLFat	|Left Total Fat Mass (g)|
|	|TotalLLean	|Left Total Lean Mass (g)|
|	|TotalLBMC	|Left Total Bone Mineral Content (g)|
|	|TotalLTotalMass	|Left Total Total Mass (kg)|
|	|TotalDRegPerFat	|Left Total Region Fat Percent Difference (%)|
|	|TotalDTissue	|Total Tissue Mass Difference (g)|
|	|TotalDFat	|Total Fat Mass Difference (g)|
|	|TotalDLean	|Total Lean Mass Difference (g)|
|	|TotalDBMC	|Total Bone Mineral Content Difference (g)|
|	|TotalDTotalMass	|Total Mass Difference (kg)|
|Lumbar Spine Ext	|L1L4BMC	|L1-L4 Bone Mineral Content (g)|
|	|L1L4BMD	|L1-L4 Areal Bone Mineral Density (g/cm2)|
|	|L1L4TScr	|L1-L4 T-score|
|	|L1L4ZScr	|L1-L4 Z-score|
|Total Hip Ext  |LFNBMC	|Left Femoral Neck Bone Mineral Content (g)|
|	|LFNBMD	|Left Femoral Neck Areal Bone Mineral Density (g/cm2)|
|	|LFNTScr	|Left Femoral Neck T-score|
|	|LFNZScr	|Left Femoral Neck Z-score|
|	|RFNBMC	|Right Femoral Neck Bone Mineral Content (g)|
|	|RFNBMD	|Right Femoral Neck Areal Bone Mineral Density (g/cm2)|
|	|RFNTScr	|Right Femoral Neck T-score|
|	|RFNZScr	|Right Femoral Neck Z-score|
|	|LGTBMC	|Left Greater Trochanter Neck Bone Mineral Content (g)|
|	|LGTBMD	|Left Greater Trochanter Neck Areal Bone Mineral Density (g/cm2)|
|	|LGTTScr	|Left Greater Trochanter Neck T-score|
|	|LGTZScr	|Left Greater Trochanter Neck Z-score|
|	|RGTBMC	|Right Greater Trochanter Neck Bone Mineral Content (g)|
|	|RGTBMD	|Right Greater Trochanter Neck Areal Bone Mineral Density (g/cm2)|
|	|RGTTScr	|Right Greater Trochanter Neck T-score|
|	|RGTZScr	|Right Greater Trochanter Neck Z-score|
|	|LTHBMC	|Left Total Hip Neck Bone Mineral Content (g)|
|	|LTHBMD	|Left Total Hip Neck Areal Bone Mineral Density (g/cm2)|
|	|LTHTScr	|Left Total Hip Neck T-score|
|	|LTHZScr	|Left Total Hip Neck Z-score|
|	|RTHBMC	|Right Total Hip Neck Bone Mineral Content (g)|
|	|RTHBMD	|Right Total Hip Neck Areal Bone Mineral Density (g/cm2)|
|	|RTHTScr	|Right Total Hip Neck T-score|
|	|RTHZScr	|Right Total Hip Neck Z-score|
|	|MeanTHTScr	|Mean Total Hip Neck T-score|
|	|MeanTHBMC	|Mean Total Hip Neck Bone Mineral Content (g)|
|	|MeanTHBMD	|Mean Total Hip Neck Areal Bone Mineral Density (g/cm2)|
|Radius Scan |Rad1/3BMD |Third-distal Areal Bone Mineral Density (g/cm2)|
| |Rad1/3TScr |Third-distal  T-score|
| |Rad1/3ZScr |Third-distal  Z-score|

									

###### <p dir='rtl' align='right'>[Back to Top](#Content)</p>

## MG
### MG: Single Type
#### MG: Demographic
The “Demographic.csv” file is a default file which is automatically generated when using the DXA Data Xtraction Assistant.  This file contains each patients’ demographic information, collected from each DXA output. This file includes 8 columns (Table 2). 

*Table 2: Demographic output*

|Variables|Description|
|---|---|
|Patients_ID|Patient ID, from the input file name|
|Patients_Visit|Visit Number, from the input file name|
|Name	|Patient name, as it appears in the DXA scan |
|Age	|Patient age, as it appears in the DXA scan |
|DOB	|Patient date of birth, as it appears in the DXA scan |
|Sex	|Patient sex, as it appears in the DXA scan |
|Ethnicity	|Patient Ethnicity, as it appears in the DXA scan |
|Height	|Patient Height, as it appears in the DXA scan |
|Weight	|Patient Weight, as it appears in the DXA scan |

###### <p dir='rtl' align='right'>[Back to Top](#Content)</p>
#### MG: Total Body Bone Ext
If the Total Body Bone Ext option was selected, a “TotalBodyBoneExt.csv” would be generated in “SingleType” subfolder ([Figure 7: Schematic for the “.csv” output files in the “SingleType” Subfolder for the DXA Data Xtraction Assistant](#Output-Details)). Table 5 introduced the meaning of each column.

*Table 5: Total Body Bone Ext output*

|Variables	|Explanation|
|---|---|
|Patients_ID	|Patient ID, from the input file name|
|Patients_Visit	|Visit Number, from the input file name|
|Region	|Region of DXA measurement|
|BMD_g/cm2	|Areal Bone Mineral Density (g/cm2)|
|YA_Percent	|The mean of a young adult reference|
|YA_T_score	|T-score|
|AM_Percent	|The mean of an age-matched reference|
|AM_Z_score	|Z-score|
|BMC_g	|Bone Mineral Content (g)|
|Area_cm2	|Area (cm2)|


###### <p dir='rtl' align='right'>[Back to Top](#Content)</p>
#### MG: Total Body Ext
If the Total Body Ext option was selected, a “TotalBodyExt.csv” would be generated in “SingleType” subfolder ([Figure 7: Schematic for the “.csv” output files in the “SingleType” Subfolder for the DXA Data Xtraction Assistant](#Output-Details)). Table 6 introduced the meaning of each column.

*Table 6: Total Body Ext output*

|Variables	|Explanation|
|---|---|
|Patients_ID	|Patient ID, from the input file name|
|Patients_Visit	|Visit Number, from the input file name|
|Region	|Region of DXA measurement|
|Tissue_Percent_Fat	|Tissue Fat (%)|
|Region_Percent_Fat	|Region Fat (%)|
|Tissue_g	|Tissue Mass (g)|
|Fat_g	|Fat Mass (g)|
|Lean_g	|Lean Mass (g)|
|BMC_g	|Bone Mineral Content (g)|
|Total_Mass_kg	|Total Mass (kg)|



###### <p dir='rtl' align='right'>[Back to Top](#Content)</p>
#### MG: Lumbar Spine Ext
If the Lumbar Spine Ext option was selected, a “LumbarSpineExt.csv” would be generated in “SingleType” subfolder ([Figure 7: Schematic for the “.csv” output files in the “SingleType” Subfolder for the DXA Data Xtraction Assistant](#Output-Details)). Table 4 introduced the meaning of each column.

*Table 4: Lumbar Spine Ext output*

|Variables	|Explanation|
|---|---|
|Patients_ID	|Patient ID, from the input file name|
|Patients_Visit	|Visit Number, from the input file name|
|Region	|Region of DXA measurement|
|BMD_g/cm2	|Areal Bone Mineral Density (g/cm2)|
|YA_Percent	|The mean of a young adult reference|
|YA_T_score	|T-score|
|AM_Percent	|The mean of an age-matched reference|
|AM_Z_score	|Z-score|
|BMC_g	|Bone Mineral Content (g)|
|Area_cm2	|Area (cm2)|
|Width_cm	|Width (cm)|
|Height_cm	|Height (cm)|

###### <p dir='rtl' align='right'>[Back to Top](#Content)</p>
#### MG: Total Hip Ext
If the Total Hip Ext option was selected, a “TotalHipExt.csv” would be generated in the “SingleType” subfolder of the output file path ([Figure 7: Schematic for the “.csv” output files in the “SingleType” Subfolder for the DXA Data Xtraction Assistant](#Output-Details)). Table 3 introduced the meaning of each column.

*Table 3: Total Hip Ext output*

|Variables	|Explanation|
|---|---|
|Patients_ID	|Patient ID, from the input file name|
|Patients_Visit	|Visit Number, from the input file name|
|Region	|Region of DXA measurement|
|BMD_g/cm2	|Areal Bone Mineral Density (g/cm2)|
|YA_Percent	|The mean of a young adult reference|
|YA_T_score	|T-score|
|AM_Percent	|The mean of an age-matched reference|
|AM_Z_score	|Z-score|
|BMC_g	|Bone Mineral Content (g)|
|Area_cm2	|Area (cm2)|

###### <p dir='rtl' align='right'>[Back to Top](#Content)</p>
#### MG: Radius Scan
If the Radius Scan option was selected, a “Rad.csv” would be generated in “SingleType” subfolder ([Figure 7: Schematic for the “.csv” output files in the “SingleType” Subfolder for the DXA Data Xtraction Assistant](#Output-Details)). Table 10 introduced the meaning of each column.

*Table 10: Radius Scan output*

|Variables	|Explanation|
|---|---|
|Patients_ID	|Patient ID, from the input file name|
|Patients_Visit	|Visit Number, from the input file name|
|Region	|Region of DXA measurement|
|BMD_g/cm2	|Areal Bone Mineral Density (g/cm2)|
|YA_Percent	|The mean of a young adult reference|
|YA_T_score	|T-score|
|AM_Percent	|The mean of an age-matched reference|
|AM_Z_score	|Z-score|
|BMC_g	|Bone Mineral Content (g)|
|Area_cm2	|Area (cm2)|


###### <p dir='rtl' align='right'>[Back to Top](#Content)</p>
### MG: Merged Output
A “MergedOutput.csv” would be generated in the output path ([Figure 6: Merged Output](#Output-Details)). It would only contain the interested outcomes as selected ([Figure 5: Output Interface – Selecting the Interested Outcomes](#Scan-Type-Selection)). Table 11 introduced the meaning of each column when all options were picked up.

*Table 11: Merged Output*

|Options	|Variables	|Explanation|
|---|---|---|
|Demographic	|Patients_ID	|Patient ID, from the input file name|
|	|Visit	|Visit Number, from the input file name|
|	|Name	|Patient name appeared in the scan report|
|	|Age	|Patient age|
|	|DOB	|Patient date of birth|
|	|Sex	|Patient sex|
|	|Ethnicity	|Patient Ethnicity|
|	|Height	|Patient Height|
|	|Weight	|Patient Weight|
|Total Body Bone Ext	|HeadBMD	|Head Areal Bone Mineral Density (g/cm2)|
|	|HeadBMC	|Head Bone Mineral Content (g)|
|	|HeadArea	|Head Area (cm2)|
|	|ArmLBMD	|Left Arm Areal Bone Mineral Density (g/cm2)|
|	|ArmLBMC	|Left Arm Bone Mineral Content (g)|
|	|ArmLArea	|Left Arm Area (cm2)|
|	|LegLBMD	|Left Leg Areal Bone Mineral Density (g/cm2)|
|	|LegLBMC	|Left Leg Bone Mineral Content (g)|
|	|LegLArea	|Left Leg Area (cm2)|
|	|TrunkLBMD	|Left Trunk Areal Bone Mineral Density (g/cm2)|
|	|TrunkLBMC	|Left Trunk Bone Mineral Content (g)|
|	|TrunkLArea	|Left Trunk Area (cm2)|
|	|TotalLBMD	|Left Total Body Areal Bone Mineral Density (g/cm2)|
|	|TotalLBMC	|Left Total Body Bone Mineral Content (g)|
|	|TotalLArea	|Left Total Body Area (cm2)|
|	|ArmRBMD	|Right Arm Areal Bone Mineral Density (g/cm2)|
|	|ArmRBMC	|Right Arm Bone Mineral Content (g)|
|	|ArmRArea	|Right Arm Area (cm2)|
|	|LegRBMD	|Right Leg Areal Bone Mineral Density (g/cm2)|
|	|LegRBMC	|Right Leg Bone Mineral Content (g)|
|	|LegRArea	|Right Leg Area (cm2)|
|	|TrunkRBMD	|Right Trunk Areal Bone Mineral Density (g/cm2)|
|	|TrunkRBMC	|Right Trunk Bone Mineral Content (g)|
|	|TrunkRArea	|Right Trunk Area (cm2)|
|	|TotalRBMD	|Right Total Body Areal Bone Mineral Density (g/cm2)|
|	|TotalRBMC	|Right Total Body Bone Mineral Content (g)|
|	|TotalRArea	|Right Total Body Area (cm2)|
|	|ArmsBMD	|Arms Areal Bone Mineral Density (g/cm2)|
|	|ArmsBMC	|Arms Bone Mineral Content (g)|
|	|ArmsArea	|Arms Area (cm2)|
|	|LegsBMD	|Legs Areal Bone Mineral Density (g/cm2)|
|	|LegsBMC	|Legs Bone Mineral Content (g)|
|	|LegsArea	|Legs Area (cm2)|
|	|TrunkBMD	|Trunk Areal Bone Mineral Density (g/cm2)|
|	|TrunkBMC	|Trunk Bone Mineral Content (g)|
|	|TrunkArea	|Trunk Area (cm2)|
|	|RibsBMD	|Ribs Areal Bone Mineral Density (g/cm2)|
|	|RibsBMC	|Ribs Bone Mineral Content (g)|
|	|RibsArea	|Ribs Area (cm2)|
|	|PelvisBMD	|Pelvis Areal Bone Mineral Density (g/cm2)|
|	|PelvisBMC	|Pelvis Bone Mineral Content (g)|
|	|PelvisArea	|Pelvis Area (cm2)|
|	|SpineBMD	|Spine Areal Bone Mineral Density (g/cm2)|
|	|SpineBMC	|Spine Bone Mineral Content (g)|
|	|SpineArea	|Spine Area (cm2)|
|	|TotalBMD	|Total Body Areal Bone Mineral Density (g/cm2)|
|	|TotalBMC	|Total Body Bone Mineral Content (g)|
|	|TotalArea	|Total Body Area (cm2)|
|	|TotalTScr	|Total Body T-score|
|	|TotalZScr	|Total Body Z-score|
|Total Body Ext	|ArmLTissuePerFat	|Left Arm Tissue Fat Percent(%)|
|	|ArmLRegPerFat	|Left Arm Region Fat Percent(%)|
|	|ArmLTissue	|Left Arm Tissue Mass (g)|
|	|ArmLFat	|Left Arm Fat Mass (g)|
|	|ArmLLean	|Left Arm Lean Mass (g)|
|	|ArmLBMC	|Left Arm Bone Mineral Content (g)|
|	|ArmLTotalMass	|Left Arm Total Mass (kg)|
|	|LegLTissuePerFat	|Left Leg Tissue Fat Percent(%)|
|	|LegLRegPerFat	|Left Leg Region Fat Percent(%)|
|	|LegLTissue	|Left Leg Tissue Mass (g)|
|	|LegLFat	|Left Leg Fat Mass (g)|
|	|LegLLean	|Left Leg Lean Mass (g)|
|	|LegLBMC	|Left Leg Bone Mineral Content (g)|
|	|LegLTotalMass	|Left Leg Total Mass (kg)|
|	|TrunkLTissuePerFat	|Left Trunk Tissue Fat Percent(%)|
|	|TrunkLRegPerFat	|Left Trunk Region Fat Percent(%)|
|	|TrunkLTissue	|Left Trunk Tissue Mass (g)|
|	|TrunkLFat	|Left Trunk Fat Mass (g)|
|	|TrunkLLean	|Left Trunk Lean Mass (g)|
|	|TrunkLBMC	|Left Trunk Bone Mineral Content (g)|
|	|TrunkLTotalMass	|Left Trunk Total Mass (kg)|
|	|TotalLTissuePerFat	|Left Total Tissue Fat Percent(%)|
|	|TotalLRegPerFat	|Left Total Region Fat Percent(%)|
|	|TotalLTissue	|Left Total Tissue Mass (g)|
|	|TotalLFat	|Left Total Fat Mass (g)|
|	|TotalLLean	|Left Total Lean Mass (g)|
|	|TotalLBMC	|Left Total Bone Mineral Content (g)|
|	|TotalLTotalMass	|Left Total Total Mass (kg)|
|	|ArmRTissuePerFat	|Right Arm Tissue Fat Percent(%)|
|	|ArmRRegPerFat	|Right Arm Region Fat Percent(%)|
|	|ArmRTissue	|Right Arm Tissue Mass (g)|
|	|ArmRFat	|Right Arm Fat Mass (g)|
|	|ArmRLean	|Right Arm Lean Mass (g)|
|	|ArmRBMC	|Right Arm Bone Mineral Content (g)|
|	|ArmRTotalMass	|Right Arm Total Mass (kg)|
|	|LegRTissuePerFat	|Right Leg Tissue Fat Percent(%)|
|	|LegRRegPerFat	|Right Leg Region Fat Percent(%)|
|	|LegRTissue	|Right Leg Tissue Mass (g)|
|	|LegRFat	|Right Leg Fat Mass (g)|
|	|LegRLean	|Right Leg Lean Mass (g)|
|	|LegRBMC	|Right Leg Bone Mineral Content (g)|
|	|LegRTotalMass	|Right Leg Total Mass (kg)|
|	|TrunkRTissuePerFat	|Right Trunk Tissue Fat Percent(%)|
|	|TrunkRRegPerFat	|Right Trunk Region Fat Percent(%)|
|	|TrunkRTissue	|Right Trunk Tissue Mass (g)|
|	|TrunkRFat	|Right Trunk Fat Mass (g)|
|	|TrunkRLean	|Right Trunk Lean Mass (g)|
|	|TrunkRBMC	|Right Trunk Bone Mineral Content (g)|
|	|TrunkRTotalMass	|Right Trunk Total Mass (kg)|
|	|TotalRTissuePerFat	|Right Total Tissue Fat Percent(%)|
|	|TotalRRegPerFat	|Right Total Region Fat Percent(%)|
|	|TotalRTissue	|Right Total Tissue Mass (g)|
|	|TotalRFat	|Right Total Fat Mass (g)|
|	|TotalRLean	|Right Total Lean Mass (g)|
|	|TotalRBMC	|Right Total Bone Mineral Content (g)|
|	|TotalRTotalMass	|Right Total Total Mass (kg)|
|	|ArmsTissuePerFat	|Arms Tissue Fat Percent(%)|
|	|ArmsRegPerFat	|Arms Region Fat Percent(%)|
|	|ArmsTissue	|Arms Tissue Mass (g)|
|	|ArmsFat	|Arms Fat Mass (g)|
|	|ArmsLean	|Arms Lean Mass (g)|
|	|ArmsBMC	|Arms Bone Mineral Content (g)|
|	|ArmsTotalMass	|Arms Total Mass (kg)|
|	|LegsTissuePerFat	|Legs Tissue Fat Percent(%)|
|	|LegsRegPerFat	|Legs Region Fat Percent(%)|
|	|LegsTissue	|Legs Tissue Mass (g)|
|	|LegsFat	|Legs Fat Mass (g)|
|	|LegsLean	|Legs Lean Mass (g)|
|	|LegsBMC	|Legs Bone Mineral Content (g)|
|	|LegsTotalMass	|Legs Total Mass (kg)|
|	|TrunkTissuePerFat	|Trunk Tissue Fat Percent(%)|
|	|TrunkRegPerFat	|Trunk Region Fat Percent(%)|
|	|TrunkTissue	|Trunk Tissue Mass (g)|
|	|TrunkFat	|Trunk Fat Mass (g)|
|	|TrunkLean	|Trunk Lean Mass (g)|
|	|TrunkBMC	|Trunk Bone Mineral Content (g)|
|	|TrunkTotalMass	|Trunk Total Mass (kg)|
|	|AndroidTissuePerFat	|Android Tissue Fat Percent(%)|
|	|AndroidRegPerFat	|Android Region Fat Percent(%)|
|	|AndroidTissue	|Android Tissue Mass (g)|
|	|AndroidFat	|Android Fat Mass (g)|
|	|AndroidLean	|Android Lean Mass (g)|
|	|AndroidBMC	|Android Bone Mineral Content (g)|
|	|AndroidTotalMass	|Android Total Mass (kg)|
|	|GynoidTissuePerFat	|Gynoid Tissue Fat Percent(%)|
|	|GynoidRegPerFat	|Gynoid Region Fat Percent(%)|
|	|GynoidTissue	|Gynoid Tissue Mass (g)|
|	|GynoidFat	|Gynoid Fat Mass (g)|
|	|GynoidLean	|Gynoid Lean Mass (g)|
|	|GynoidBMC	|Gynoid Bone Mineral Content (g)|
|	|GynoidTotalMass	|Gynoid Total Mass (kg)|
|	|TotalTissuePerFat	|Total Tissue Fat Percent(%)|
|	|TotalRegPerFat	|Total Region Fat Percent(%)|
|	|TotalTissue	|Total Tissue Mass (g)|
|	|TotalFat	|Total Fat Mass (g)|
|	|TotalLean	|Total Lean Mass (g)|
|	|TotalBMC	|Total Bone Mineral Content (g)|
|	|TotalMass	|Total Body Mass (kg)|
|Lumbar Spine Ext	|L1L4BMC	|L1-L4 Bone Mineral Content (g)|
|	|L1L4BMD	|L1-L4 Areal Bone Mineral Density (g/cm2)|
|	|L1L4TScr	|L1-L4 T-score|
|	|L1L4ZScr	|L1-L4 Z-score|
|	|L1L4Width	|L1-L4 Width|
|	|L1L4Height	|L1-L4 Height|
|Total Hip Ext  |LFNBMC	|Left Femoral Neck Bone Mineral Content (g)|
|	|LFNBMD	|Left Femoral Neck Areal Bone Mineral Density (g/cm2)|
|	|LFNTScr	|Left Femoral Neck T-score|
|	|LFNZScr	|Left Femoral Neck Z-score|
|	|RFNBMC	|Right Femoral Neck Bone Mineral Content (g)|
|	|RFNBMD	|Right Femoral Neck Areal Bone Mineral Density (g/cm2)|
|	|RFNTScr	|Right Femoral Neck T-score|
|	|RFNZScr	|Right Femoral Neck Z-score|
|	|LGTBMC	|Left Greater Trochanter Neck Bone Mineral Content (g)|
|	|LGTBMD	|Left Greater Trochanter Neck Areal Bone Mineral Density (g/cm2)|
|	|LGTTScr	|Left Greater Trochanter Neck T-score|
|	|LGTZScr	|Left Greater Trochanter Neck Z-score|
|	|RGTBMC	|Right Greater Trochanter Neck Bone Mineral Content (g)|
|	|RGTBMD	|Right Greater Trochanter Neck Areal Bone Mineral Density (g/cm2)|
|	|RGTTScr	|Right Greater Trochanter Neck T-score|
|	|RGTZScr	|Right Greater Trochanter Neck Z-score|
|	|LTHBMC	|Left Total Hip Neck Bone Mineral Content (g)|
|	|LTHBMD	|Left Total Hip Neck Areal Bone Mineral Density (g/cm2)|
|	|LTHTScr	|Left Total Hip Neck T-score|
|	|LTHZScr	|Left Total Hip Neck Z-score|
|	|RTHBMC	|Right Total Hip Neck Bone Mineral Content (g)|
|	|RTHBMD	|Right Total Hip Neck Areal Bone Mineral Density (g/cm2)|
|	|RTHTScr	|Right Total Hip Neck T-score|
|	|RTHZScr	|Right Total Hip Neck Z-score|
|	|MeanTHTScr	|Mean Total Hip Neck T-score|
|	|MeanTHBMC	|Mean Total Hip Neck Bone Mineral Content (g)|
|	|MeanTHBMD	|Mean Total Hip Neck Areal Bone Mineral Density (g/cm2)|
|Radius Scan |RadUDBMD |Ultradistal Areal Bone Mineral Density (g/cm2)|
| |RadUDBMC |Ultradistal Bone Mineral Content (g)|
| |RadUDArea	|Ultradistal Area (cm2)|
| |UlnaUDBMD |Ultradistal Ulna Areal Bone Mineral Density (g/cm2)|
| |UlnaUDBMC |Ultradistal Ulna Bone Mineral Content (g)|
| |UlnaUDArea	|Ultradistal Ulna Area (cm2)|
| |Rad1/3BMD |Third-distal Areal Bone Mineral Density (g/cm2)|
| |Rad1/3BMC |Third-distal Bone Mineral Content (g)|
| |Rad1/3Area	|Third-distal Area (cm2)|
| |Ulna1/3BMD |Third-distal Ulna Areal Bone Mineral Density (g/cm2)|
| |Ulna1/3BMC |Third-distal Ulna Bone Mineral Content (g)|
| |Ulna1/3Area	|Third-distal Ulna Area (cm2)|
| |BothUDBMD |Ultradistal Radius + Ulna Areal Bone Mineral Density (g/cm2)|
| |BothUDBMC |Ultradistal Radius + Ulna Bone Mineral Content (g)|
| |BothUDArea	|Ultradistal Radius + Ulna Area (cm2)|
| |Both1/3BMD |Third-distal Radius + Ulna Areal Bone Mineral Density (g/cm2)|
| |Both1/3BMC |Third-distal Radius + Ulna Bone Mineral Content (g)|
| |Both1/3Area	|Third-distal Radius + Ulna Area (cm2)|
| |RadTotalBMD |Total Areal Bone Mineral Density (g/cm2)|
| |RadTotalBMC |Total Bone Mineral Content (g)|
| |RadTotalArea	|Total Area (cm2)|
| |UlnaTotalBMD |Total Ulna Areal Bone Mineral Density (g/cm2)|
| |UlnaTotalBMC |Total Ulna Bone Mineral Content (g)|
| |UlnaTotalArea	|Total Ulna Area (cm2)|
| |BothTotalBMD |Total Radius + Ulna Areal Bone Mineral Density (g/cm2)|
| |BothTotalBMC |Total Radius + Ulna Bone Mineral Content (g)|
| |BothTotalArea	|Total Radius + Ulna Area (cm2)|
| |RadUDTScr |Ultradistal T-score|
| |RadUDZScr |Ultradistal Z-score|
| |Rad1/3TScr |Third-distal T-score|
| |Rad1/3ZScr |Third-distal Z-score|
| |RadTotalTScr |Total T-score|
| |RadTotalZScr |Total Z-score|
		

###### <p dir='rtl' align='right'>[Back to Top](#Content)</p>

## iDXA
### iDXA: Single Type
#### iDXA: Demographic
The “Demographic.csv” file is a default file which is automatically generated when using the DXA Data Xtraction Assistant.  This file contains each patients’ demographic information, collected from each DXA output. This file includes 8 columns (Table 2). 

*Table 2: Demographic output*

|Variables|Description|
|---|---|
|Patients_ID|Patient ID, from the input file name|
|Patients_Visit|Visit Number, from the input file name|
|Name	|Patient name, as it appears in the DXA scan |
|Age	|Patient age, as it appears in the DXA scan |
|DOB	|Patient date of birth, as it appears in the DXA scan |
|Sex	|Patient sex, as it appears in the DXA scan |
|Ethnicity	|Patient Ethnicity, as it appears in the DXA scan |
|Height	|Patient Height, as it appears in the DXA scan |
|Weight	|Patient Weight, as it appears in the DXA scan |

###### <p dir='rtl' align='right'>[Back to Top](#Content)</p>
#### iDXA: Total Body Bone
If the Total Body Bone option was selected, a “TotalBodyBone.csv” would be generated in “SingleType” subfolder ([Figure 7: Schematic for the “.csv” output files in the “SingleType” Subfolder for the DXA Data Xtraction Assistant](#Output-Details)). Table 5 introduced the meaning of each column.

*Table 5: Total Body Bone output*

|Variables	|Explanation|
|---|---|
|Patients_ID	|Patient ID, from the input file name|
|Patients_Visit	|Visit Number, from the input file name|
|Region	|Region of DXA measurement|
|BMD_g/cm2	|Areal Bone Mineral Density (g/cm2)|
|YA_T_score	|T-score|
|AM_Z_score	|Z-score|


###### <p dir='rtl' align='right'>[Back to Top](#Content)</p>
#### iDXA: Total Body Ext
If the Total Body Ext option was selected, a “TotalBodyExt.csv” would be generated in “SingleType” subfolder ([Figure 7: Schematic for the “.csv” output files in the “SingleType” Subfolder for the DXA Data Xtraction Assistant](#Output-Details)). Table 6 introduced the meaning of each column.

*Table 6: Total Body Ext output*

|Variables	|Explanation|
|---|---|
|Patients_ID	|Patient ID, from the input file name|
|Patients_Visit	|Visit Number, from the input file name|
|Region	|Region of DXA measurement|
|Tissue_Percent_Fat	|Tissue Fat (%)|
|Region_Percent_Fat	|Region Fat (%)|
|Tissue_lbs	|Tissue Mass (lbs)|
|Fat_lbs	|Fat Mass (lbs)|
|Lean_lbs	|Lean Mass (lbs)|
|BMC_lbs	|Bone Mineral Content (lbs)|
|Total_Mass_lbs	|Total Mass (lbs)|



###### <p dir='rtl' align='right'>[Back to Top](#Content)</p>
#### iDXA: Lumbar Spine
If the Lumbar Spine option was selected, a “LumbarSpine.csv” would be generated in “SingleType” subfolder ([Figure 7: Schematic for the “.csv” output files in the “SingleType” Subfolder for the DXA Data Xtraction Assistant](#Output-Details)). Table 4 introduced the meaning of each column.

*Table 4: Lumbar Spine output*

|Variables	|Explanation|
|---|---|
|Patients_ID	|Patient ID, from the input file name|
|Patients_Visit	|Visit Number, from the input file name|
|Region	|Region of DXA measurement|
|BMD_g/cm2	|Areal Bone Mineral Density (g/cm2)|
|YA_T_score	|T-score|
|AM_Z_score	|Z-score|


###### <p dir='rtl' align='right'>[Back to Top](#Content)</p>
#### iDXA: Total Hip
If the Total Hip option was selected, a “TotalHip.csv” would be generated in the “SingleType” subfolder of the output file path ([Figure 7: Schematic for the “.csv” output files in the “SingleType” Subfolder for the DXA Data Xtraction Assistant](#Output-Details)). Table 3 introduced the meaning of each column.

*Table 3: Total Hip output*

|Variables	|Explanation|
|---|---|
|Patients_ID	|Patient ID, from the input file name|
|Patients_Visit	|Visit Number, from the input file name|
|Region	|Region of DXA measurement|
|BMD_g/cm2	|Areal Bone Mineral Density (g/cm2)|
|YA_T_score	|T-score|
|AM_Z_score	|Z-score|


###### <p dir='rtl' align='right'>[Back to Top](#Content)</p>
#### iDXA: Radius Scan
If the Radius Scan option was selected, a “Rad.csv” would be generated in “SingleType” subfolder ([Figure 7: Schematic for the “.csv” output files in the “SingleType” Subfolder for the DXA Data Xtraction Assistant](#Output-Details)). Table 10 introduced the meaning of each column.

*Table 10: Radius Scan output*

|Variables	|Explanation|
|---|---|
|Patients_ID	|Patient ID, from the input file name|
|Patients_Visit	|Visit Number, from the input file name|
|Region	|Region of DXA measurement|
|BMD_g/cm2	|Areal Bone Mineral Density (g/cm2)|
|YA_T_score	|T-score|
|AM_Z_score	|Z-score|



###### <p dir='rtl' align='right'>[Back to Top](#Content)</p>
### iDXA: Merged Output
A “MergedOutput.csv” would be generated in the output path ([Figure 6: Merged Output](#Output-Details)). It would only contain the interested outcomes as selected ([Figure 5: Output Interface – Selecting the Interested Outcomes](#Scan-Type-Selection)). Table 11 introduced the meaning of each column when all options were picked up.

*Table 11: Merged Output*

|Options	|Variables	|Explanation|
|---|---|---|
|Demographic	|Patients_ID	|Patient ID, from the input file name|
|	|Visit	|Visit Number, from the input file name|
|	|Name	|Patient name appeared in the scan report|
|	|Age	|Patient age|
|	|DOB	|Patient date of birth|
|	|Sex	|Patient sex|
|	|Ethnicity	|Patient Ethnicity|
|	|Height	|Patient Height|
|	|Weight	|Patient Weight|
|Total Body Bone	|HeadBMD	|Head Areal Bone Mineral Density (g/cm2)|
|	|ArmsBMD	|Arms Areal Bone Mineral Density (g/cm2)|
|	|LegsBMD	|Legs Areal Bone Mineral Density (g/cm2)|
|	|TrunkBMD	|Trunk Areal Bone Mineral Density (g/cm2)|
|	|RibsBMD	|Ribs Areal Bone Mineral Density (g/cm2)|
|	|SpineBMD	|Spine Areal Bone Mineral Density (g/cm2)|
|	|PelvisBMD	|Pelvis Areal Bone Mineral Density (g/cm2)|
|	|TotalBMD	|Total Body Areal Bone Mineral Density (g/cm2)|
|	|TotalTScr	|Total Body T-score|
|	|TotalZScr	|Total Body Z-score|
|Total Body Ext	|ArmsTissuePerFat	|Arms Tissue Fat Percent(%)|
|	|ArmsRegPerFat	|Arms Region Fat Percent(%)|
|	|ArmsTissue	|Arms Tissue Mass (g)|
|	|ArmsFat	|Arms Fat Mass (g)|
|	|ArmsLean	|Arms Lean Mass (g)|
|	|ArmsBMC	|Arms Bone Mineral Content (g)|
|	|ArmsTotalMass	|Arms Total Mass (kg)|
|	|LegsTissuePerFat	|Legs Tissue Fat Percent(%)|
|	|LegsRegPerFat	|Legs Region Fat Percent(%)|
|	|LegsTissue	|Legs Tissue Mass (g)|
|	|LegsFat	|Legs Fat Mass (g)|
|	|LegsLean	|Legs Lean Mass (g)|
|	|LegsBMC	|Legs Bone Mineral Content (g)|
|	|LegsTotalMass	|Legs Total Mass (kg)|
|	|TrunkTissuePerFat	|Trunk Tissue Fat Percent(%)|
|	|TrunkRegPerFat	|Trunk Region Fat Percent(%)|
|	|TrunkTissue	|Trunk Tissue Mass (g)|
|	|TrunkFat	|Trunk Fat Mass (g)|
|	|TrunkLean	|Trunk Lean Mass (g)|
|	|TrunkBMC	|Trunk Bone Mineral Content (g)|
|	|TrunkTotalMass	|Trunk Total Mass (kg)|
|	|AndroidTissuePerFat	|Android Tissue Fat Percent(%)|
|	|AndroidRegPerFat	|Android Region Fat Percent(%)|
|	|AndroidTissue	|Android Tissue Mass (g)|
|	|AndroidFat	|Android Fat Mass (g)|
|	|AndroidLean	|Android Lean Mass (g)|
|	|AndroidBMC	|Android Bone Mineral Content (g)|
|	|AndroidTotalMass	|Android Total Mass (kg)|
|	|GynoidTissuePerFat	|Gynoid Tissue Fat Percent(%)|
|	|GynoidRegPerFat	|Gynoid Region Fat Percent(%)|
|	|GynoidTissue	|Gynoid Tissue Mass (g)|
|	|GynoidFat	|Gynoid Fat Mass (g)|
|	|GynoidLean	|Gynoid Lean Mass (g)|
|	|GynoidBMC	|Gynoid Bone Mineral Content (g)|
|	|GynoidTotalMass	|Gynoid Total Mass (kg)|
|	|TotalTissuePerFat	|Total Tissue Fat Percent(%)|
|	|TotalRegPerFat	|Total Region Fat Percent(%)|
|	|TotalTissue	|Total Tissue Mass (g)|
|	|TotalFat	|Total Fat Mass (g)|
|	|TotalLean	|Total Lean Mass (g)|
|	|TotalBMC	|Total Bone Mineral Content (g)|
|	|TotalMass	|Total Body Mass (kg)|
|Lumbar Spine	|L1L4BMD	|L1-L4 Areal Bone Mineral Density (g/cm2)|
|	|L1L4TScr	|L1-L4 T-score|
|	|L1L4ZScr	|L1-L4 Z-score|
|Total Hip  |LFNBMD	|Left Femoral Neck Areal Bone Mineral Density (g/cm2)|
|	|LFNTScr	|Left Femoral Neck T-score|
|	|LFNZScr	|Left Femoral Neck Z-score|
|	|RFNBMD	|Right Femoral Neck Areal Bone Mineral Density (g/cm2)|
|	|RFNTScr	|Right Femoral Neck T-score|
|	|RFNZScr	|Right Femoral Neck Z-score|
|	|LTHBMD	|Left Total Hip Neck Areal Bone Mineral Density (g/cm2)|
|	|LTHTScr	|Left Total Hip Neck T-score|
|	|LTHZScr	|Left Total Hip Neck Z-score|
|	|RTHBMD	|Right Total Hip Neck Areal Bone Mineral Density (g/cm2)|
|	|RTHTScr	|Right Total Hip Neck T-score|
|	|RTHZScr	|Right Total Hip Neck Z-score|
|	|MeanTHTScr	|Mean Total Hip Neck T-score|
|	|MeanTHBMD	|Mean Total Hip Neck Areal Bone Mineral Density (g/cm2)|
|Radius Scan |Rad1/3BMD |Third-distal Areal Bone Mineral Density (g/cm2)|
| |Ulna1/3BMD |Third-distal Ulna Areal Bone Mineral Density (g/cm2)|
| |Both1/3BMD |Third-distal Radius + Ulna Areal Bone Mineral Density (g/cm2)|
| |Rad1/3TScr |Third-distal T-score|
| |Rad1/3ZScr |Third-distal Z-score|

		

###### <p dir='rtl' align='right'>[Back to Top](#Content)</p>

## Norland
### Norland: Single Type
#### Norland: Demographic
The “Demographic.csv” file is a default file which is automatically generated when using the DXA Data Xtraction Assistant.  This file contains each patients’ demographic information, collected from each DXA output. This file includes 8 columns (Table 2). 

*Table 2: Demographic output*

|Variables|Description|
|---|---|
|Patients_ID|Patient ID, from the input file name|
|Patients_Visit|Visit Number, from the input file name|
|Name	|Patient name, as it appears in the DXA scan |
|Age	|Patient age, as it appears in the DXA scan |
|DOB	|Patient date of birth, as it appears in the DXA scan |
|Sex	|Patient sex, as it appears in the DXA scan |
|Ethnicity	|Patient Ethnicity, as it appears in the DXA scan |
|Height	|Patient Height, as it appears in the DXA scan |
|Weight	|Patient Weight, as it appears in the DXA scan |

###### <p dir='rtl' align='right'>[Back to Top](#Content)</p>
#### Norland: Total Body Bone
If the Total Body Bone option was selected, a “TotalBodyBone.csv” would be generated in “SingleType” subfolder ([Figure 7: Schematic for the “.csv” output files in the “SingleType” Subfolder for the DXA Data Xtraction Assistant](#Output-Details)). Table 5 introduced the meaning of each column.

*Table 5: Total Body Bone output*

|Variables	|Explanation|
|---|---|
|Patients_ID	|Patient ID, from the input file name|
|Patients_Visit	|Visit Number, from the input file name|
|Region	|Region of DXA measurement|
|BMD_g/cm2	|Areal Bone Mineral Density (g/cm2)|
|BMC_g	|Bone Mineral Content (g)|
|Area_cm2	|Area (cm2)|
|Lean_Mass_g	|Lean Mass (g)|
|Fat_Mass_g	|Fat Mass (g)|


###### <p dir='rtl' align='right'>[Back to Top](#Content)</p>
#### Norland: Total Body Composition
If the Total Body Composition option was selected, a “TotalBodyComp.csv” would be generated in “SingleType” subfolder ([Figure 7: Schematic for the “.csv” output files in the “SingleType” Subfolder for the DXA Data Xtraction Assistant](#Output-Details)). Table 6 introduced the meaning of each column.

*Table 6: Total Body Composition output*

|Variables	|Explanation|
|---|---|
|Patients_ID	|Patient ID, from the input file name|
|Patients_Visit	|Visit Number, from the input file name|
|Region	|Region of DXA measurement|
|Fat_Mass_kg	|Fat Mass (kg)|
|Lean_Mass_kg	|Lean Mass (kg)|
|BMC_kg	|Bone Mineral Content (kg)|
|Total_Mass_kg	|Total Mass (kg)|


###### <p dir='rtl' align='right'>[Back to Top](#Content)</p>
#### Norland: Lumbar Spine
If the Lumbar Spine option was selected, a “LumbarSpine.csv” would be generated in “SingleType” subfolder ([Figure 7: Schematic for the “.csv” output files in the “SingleType” Subfolder for the DXA Data Xtraction Assistant](#Output-Details)). Table 4 introduced the meaning of each column.

*Table 4: Lumbar Spine output*

|Variables	|Explanation|
|---|---|
|Patients_ID	|Patient ID, from the input file name|
|Patients_Visit	|Visit Number, from the input file name|
|Region	|Region of DXA measurement|
|BMD_g/cm2	|Areal Bone Mineral Density (g/cm2)|
|BMC_g	|Bone Mineral Content (g)|
|Area_cm2	|Area (cm2)|
|Length_cm	|Length (cm)|
|Width_cm	|Width (cm)|
|T_score	|T-score|
|Young_Ref_%	|The mean of a young adult reference|
|Z_score	|Z-score|
|Age_Match_%	|The mean of an age-matched reference|
|ST_Change_%	|ST Change (%)|
|ST_Change_%/year	|ST Change (%/year)|
|LT_Change_%	|LT Change (%)|
|LT_Change_%/year	|LT Change (%/year)|

###### <p dir='rtl' align='right'>[Back to Top](#Content)</p>
#### Norland: Total Hip
If the Total Hip option was selected, a “TotalHip.csv” would be generated in the “SingleType” subfolder of the output file path ([Figure 7: Schematic for the “.csv” output files in the “SingleType” Subfolder for the DXA Data Xtraction Assistant](#Output-Details)). Table 3 introduced the meaning of each column.

*Table 3: Total Hip output*

|Variables	|Explanation|
|---|---|
|Patients_ID	|Patient ID, from the input file name|
|Patients_Visit	|Visit Number, from the input file name|
|Region	|Region of DXA measurement|
|BMD_g/cm2	|Areal Bone Mineral Density (g/cm2)|
|BMC_g	|Bone Mineral Content (g)|
|Area_cm2	|Area (cm2)|
|T_score	|T-score|
|Young_Ref_%	|The mean of a young adult reference|
|Z_score	|Z-score|
|Age_Match_%	|The mean of an age-matched reference|
|ST_Change_%	|ST Change (%)|
|ST_Change_%/year	|ST Change (%/year)|
|LT_Change_%	|LT Change (%)|
|LT_Change_%/year	|LT Change (%/year)|

###### <p dir='rtl' align='right'>[Back to Top](#Content)</p>
#### Norland: Radius Scan
If the Radius Scan option was selected, a “Rad.csv” would be generated in “SingleType” subfolder ([Figure 7: Schematic for the “.csv” output files in the “SingleType” Subfolder for the DXA Data Xtraction Assistant](#Output-Details)). Table 10 introduced the meaning of each column.

*Table 10: Radius Scan output*

|Variables	|Explanation|
|---|---|
|Patients_ID	|Patient ID, from the input file name|
|Patients_Visit	|Visit Number, from the input file name|
|Region	|Region of DXA measurement|
|BMD_g/cm2	|Areal Bone Mineral Density (g/cm2)|
|BMC_g	|Bone Mineral Content (g)|
|Area_cm2	|Area (cm2)|
|Length_cm	|Length (cm)|
|Width_cm	|Width (cm)|
|T_score	|T-score|
|Young_Ref_%	|The mean of a young adult reference|
|Z_score	|Z-score|
|Age_Match_%	|The mean of an age-matched reference|
|ST_Change_%	|ST Change (%)|
|ST_Change_%/year	|ST Change (%/year)|
|LT_Change_%	|LT Change (%)|
|LT_Change_%/year	|LT Change (%/year)|


###### <p dir='rtl' align='right'>[Back to Top](#Content)</p>
### Norland: Merged Output
A “MergedOutput.csv” would be generated in the output path ([Figure 6: Merged Output](#Output-Details)). It would only contain the interested outcomes as selected ([Figure 5: Output Interface – Selecting the Interested Outcomes](#Scan-Type-Selection)). Table 11 introduced the meaning of each column when all options were picked up.

*Table 11: Merged Output*

|Options	|Variables	|Explanation|
|---|---|---|
|Demographic	|Patients_ID	|Patient ID, from the input file name|
|	|Visit	|Visit Number, from the input file name|
|	|Name	|Patient name appeared in the scan report|
|	|Age	|Patient age|
|	|DOB	|Patient date of birth|
|	|Sex	|Patient sex|
|	|Ethnicity	|Patient Ethnicity|
|	|Height	|Patient Height|
|	|Weight	|Patient Weight|
|Total Body Bone	|HeadBMD	|Head Areal Bone Mineral Density (g/cm2)|
|	|ArmsBMD	|Arms Areal Bone Mineral Density (g/cm2)|
|	|LegsBMD	|Legs Areal Bone Mineral Density (g/cm2)|
|	|TrunkBMD	|Trunk Areal Bone Mineral Density (g/cm2)|
|	|RibsBMD	|Ribs Areal Bone Mineral Density (g/cm2)|
|	|SpineBMD	|Spine Areal Bone Mineral Density (g/cm2)|
|	|PelvisBMD	|Pelvis Areal Bone Mineral Density (g/cm2)|
|	|TotalBMD	|Total Body Areal Bone Mineral Density (g/cm2)|
|	|TotalTScr	|Total Body T-score|
|	|TotalZScr	|Total Body Z-score|
|Total Body Ext	|ArmsTissuePerFat	|Arms Tissue Fat Percent(%)|
|	|ArmsRegPerFat	|Arms Region Fat Percent(%)|
|	|ArmsTissue	|Arms Tissue Mass (g)|
|	|ArmsFat	|Arms Fat Mass (g)|
|	|ArmsLean	|Arms Lean Mass (g)|
|	|ArmsBMC	|Arms Bone Mineral Content (g)|
|	|ArmsTotalMass	|Arms Total Mass (kg)|
|	|LegsTissuePerFat	|Legs Tissue Fat Percent(%)|
|	|LegsRegPerFat	|Legs Region Fat Percent(%)|
|	|LegsTissue	|Legs Tissue Mass (g)|
|	|LegsFat	|Legs Fat Mass (g)|
|	|LegsLean	|Legs Lean Mass (g)|
|	|LegsBMC	|Legs Bone Mineral Content (g)|
|	|LegsTotalMass	|Legs Total Mass (kg)|
|	|TrunkTissuePerFat	|Trunk Tissue Fat Percent(%)|
|	|TrunkRegPerFat	|Trunk Region Fat Percent(%)|
|	|TrunkTissue	|Trunk Tissue Mass (g)|
|	|TrunkFat	|Trunk Fat Mass (g)|
|	|TrunkLean	|Trunk Lean Mass (g)|
|	|TrunkBMC	|Trunk Bone Mineral Content (g)|
|	|TrunkTotalMass	|Trunk Total Mass (kg)|
|	|AndroidTissuePerFat	|Android Tissue Fat Percent(%)|
|	|AndroidRegPerFat	|Android Region Fat Percent(%)|
|	|AndroidTissue	|Android Tissue Mass (g)|
|	|AndroidFat	|Android Fat Mass (g)|
|	|AndroidLean	|Android Lean Mass (g)|
|	|AndroidBMC	|Android Bone Mineral Content (g)|
|	|AndroidTotalMass	|Android Total Mass (kg)|
|	|GynoidTissuePerFat	|Gynoid Tissue Fat Percent(%)|
|	|GynoidRegPerFat	|Gynoid Region Fat Percent(%)|
|	|GynoidTissue	|Gynoid Tissue Mass (g)|
|	|GynoidFat	|Gynoid Fat Mass (g)|
|	|GynoidLean	|Gynoid Lean Mass (g)|
|	|GynoidBMC	|Gynoid Bone Mineral Content (g)|
|	|GynoidTotalMass	|Gynoid Total Mass (kg)|
|	|TotalTissuePerFat	|Total Tissue Fat Percent(%)|
|	|TotalRegPerFat	|Total Region Fat Percent(%)|
|	|TotalTissue	|Total Tissue Mass (g)|
|	|TotalFat	|Total Fat Mass (g)|
|	|TotalLean	|Total Lean Mass (g)|
|	|TotalBMC	|Total Bone Mineral Content (g)|
|	|TotalMass	|Total Body Mass (kg)|
|Lumbar Spine	|L1L4BMD	|L1-L4 Areal Bone Mineral Density (g/cm2)|
|	|L1L4TScr	|L1-L4 T-score|
|	|L1L4ZScr	|L1-L4 Z-score|
|Total Hip  |LFNBMD	|Left Femoral Neck Areal Bone Mineral Density (g/cm2)|
|	|LFNTScr	|Left Femoral Neck T-score|
|	|LFNZScr	|Left Femoral Neck Z-score|
|	|RFNBMD	|Right Femoral Neck Areal Bone Mineral Density (g/cm2)|
|	|RFNTScr	|Right Femoral Neck T-score|
|	|RFNZScr	|Right Femoral Neck Z-score|
|	|LTHBMD	|Left Total Hip Neck Areal Bone Mineral Density (g/cm2)|
|	|LTHTScr	|Left Total Hip Neck T-score|
|	|LTHZScr	|Left Total Hip Neck Z-score|
|	|RTHBMD	|Right Total Hip Neck Areal Bone Mineral Density (g/cm2)|
|	|RTHTScr	|Right Total Hip Neck T-score|
|	|RTHZScr	|Right Total Hip Neck Z-score|
|	|MeanTHTScr	|Mean Total Hip Neck T-score|
|	|MeanTHBMD	|Mean Total Hip Neck Areal Bone Mineral Density (g/cm2)|
|Radius Scan |Rad1/3BMD |Third-distal Areal Bone Mineral Density (g/cm2)|
| |Ulna1/3BMD |Third-distal Ulna Areal Bone Mineral Density (g/cm2)|
| |Both1/3BMD |Third-distal Radius + Ulna Areal Bone Mineral Density (g/cm2)|
| |Rad1/3TScr |Third-distal T-score|
| |Rad1/3ZScr |Third-distal Z-score|

		


###### <p dir='rtl' align='right'>[Back to Top](#Content)</p>
