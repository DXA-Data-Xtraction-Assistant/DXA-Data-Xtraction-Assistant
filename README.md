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
      - [Lunar Prodigy: Total Body Bone](#Lunar-Prodigy-Total-Body-Bone)
      - [Lunar Prodigy: Total Body Bone Ext](#Lunar-Prodigy-Total-Body-Bone-Ext)
      - [Lunar Prodigy: Total Body Ext](#Lunar-Prodigy-Total-Body-Ext)
      - [Lunar Prodigy: Lumbar Spine Ext](#Lunar-Prodigy-Lumbar-Spine-Ext)
      - [Lunar Prodigy: Total Hip Ext](#Lunar-Prodigy-Total-Hip-Ext)
      - [Lunar Prodigy: Radius Scan](#Lunar-Prodigy-Radius-Scan)
    - [Lunar Prodigy: Merged Output](#Lunar-Prodigy-Merged-Output)
  - [MG](#MG)
    - [MG: Single Type](#MG-Single-Type)
      - [MG: Demographic](#MG-Demographic)
      - [MG: Total Body Bone](#MG-Total-Body-Bone)
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
  - [Norland](#Norland)
    - [Norland: Single Type](#Norland-Single-Type)
      - [Norland: Demographic](#Norland-Demographic)
      - [Norland: Total Body Bone](#Norland-Total-Body-Bone)
      - [Norland: Total Body Composition](#Norland-Total-Body-Composition)
      - [Norland: Lumbar Spine](#Norland-Lumbar-Spine)
      - [Norland: Total Hip](#Norland-Total-Hip)
      - [Norland: Radius Scan](#Norland-Radius-Scan)
    - [Norland: Merged Output](#Norland-Merged-Output)


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
* must be .xps or .pdf files

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
|Rad|Radius Scan|

For example, a patient indexed as SSSH0001 went for a DXA scan at the 2nd time, then the Body Composition scan output should be saved as SSSH0001\_2\_BC.xps (do not include any other characters). 

![Figure 1: DXA outputs example](/FIG/FIG1.png)

*Figure 1: DXA outputs example*


###### <p dir='rtl' align='right'>[Back to Top](#Content)</p>
# Usage
The DXA Data Xtraction Assistant allows users to choose the input and output file paths. It also allows users to customize the output DXA data, to streamline “.csv” file outputs. In this section, we will introduce the User Interface of the Converter.

###### <p dir='rtl' align='right'>[Back to Top](#Content)</p>
## Select Type of DXA Scanner
A user interface will appear when you double click and run this application ([Figure 2: User Interface – Selecting Type of DXA Scanners](#Select-Type-of-DXA-Scanner)). Three DXA manufactures, Hologic, GE, and Norland are supported. 

![Figure 2: User Interface – Selecting Type of DXA Scanners](/FIG/FIG2.png)

*Figure 2: User Interface – Selecting Type of DXA Scanners*

* The Hologic button works for Horizon model with Apex software v5.5
* The Norland button works for both ELITE and XR-800 models, both of which use the same Illuminatus v 4.7.5 software.
* The GE button navigates to a new page ([Figure 3: User Interface – GE scanners](#Select-Type-of-DXA-Scanner)). 
	* The MG button supports GE Lunar Prodigy enCORE software v12, 
	* The Lunar Prodigy button supports enCORE v.16
	* The iDXA button works for enCORE v17 and 18. 

![Figure 3: User Interface – GE scanners](/FIG/FIG3.png)

*Figure 3: User Interface – GE scanners*

## Select Input and Output Paths
After selecting the type of DXA scanner, users can select the input and output folders ([Figure 4: Input Interface – Selecting Input and Output Paths](#Select-Input-and-Output-Paths)). 
The input folder should be the folder that contains all DXA outputs (see [DXA Outputs](#DXA-Outputs)). The output folder is the folder where the output “.csv” files will be saved. Both input and output folders can be located anywhere on your computer or in an accessible cloud storage location. 

* Click the Input Folder and Output Folder buttons to select the file path for these locations. 
* Once both of these have been assigned, click the Transform button.  This will start the DXA Data Xtraction Assistant conversion process. 
* Click Step 3 to enter the next process.

![Figure 4: Input Interface – Selecting Input and Output Paths](/FIG/FIG4.png)

*Figure 4: Input Interface – Selecting Input and Output Paths*

###### <p dir='rtl' align='right'>[Back to Top](#Content)</p>
## Scan Type Selection
DXA Data Xtraction Assistant provides several options for the users to customize their output files ([Figure 5: Output Interface – Selecting the Interested Outcomes](#Scan-Type-Selection)). 
* Check all data that should be included in the DXA Data Xtraction Assistant output “.csv” file.  
* Then, click the Merge button. 
The “.csv” files with the chosen data will then be saved in the assigned output file path.

![Figure 5: Output Interface – Selecting the Interested Outcomes](/FIG/FIG5.png)

*Figure 5: Output Interface – Selecting the Interested Outcomes*

###### <p dir='rtl' align='right'>[Back to Top](#Content)</p>
# Output Details
The created “.csv” output files will be saved in the provided file path. Output files are automatically provided using two types of output formats: (1) the first separates out information into one “.csv” file for participant information and a separate “.csv” file for each DXA scan type; (2) the second output format results in a large, merged table containing all information (participant information and scan type). Details of this process are introduced in the following sections.
The output “.csv” files include two merged file, named “Full_Merged.csv” and "Abbreviated_Merged.csv", as well as a data dictionary, in the selected output file path. A subfolder named as “SingleType” ([Figure 6: Merged Output](#Output-Details)) would be created, which contains the participant information in one file, “Demographic.csv” and the information for each requested DXA scan type as separate “.csv” file ([Figure 7: Schematic for the “.csv” output files in the “SingleType” Subfolder for the DXA Data Xtraction Assistant](#Output-Details)).

![Figure 6: Merged Output](/FIG/FIG6.png)

*Figure 6: Merged Output*

![Figure 7: Schematic for the “.csv” output files in the “SingleType” Subfolder for the DXA Data Xtraction Assistant](/FIG/FIG7.png)

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
|Weight	|Patient Weight, as it appears in the DXA scan |

###### <p dir='rtl' align='right'>[Back to Top](#Content)</p>
#### Hologic: Total Body Bone
If the Total Body Bone option was selected, a “TotalBodyBone.csv” would be generated in “SingleType” subfolder ([Figure 7: Schematic for the “.csv” output files in the “SingleType” Subfolder for the DXA Data Xtraction Assistant](#Output-Details)). Table 3 introduced the meaning of each column.

*Table 3: Total Body Bone output*

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
Table 4 introduced the meaning of each column for “TotalBodyComp_Adipose.csv”

*Table 4: Total Body Composition - Adipose output*

|Patients_ID	|Patient ID, from the input file name|
|---|---|
|Patients_Visit	|Visit Number, from the input file name|
|Measure	|Measurement names|
|Result	|Measurement values|
|Tscore	|T-scores|
|Zscore	|Z-scores|

Table 5 introduced the meaning of each column for “TotalBodyComp_Composition.csv”

*Table 5: Total Body Composition - Composition output*

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

Table 6 introduced the meaning of each column for “TotalBodyComp_Lean.csv”

*Table 6: Total Body Composition - Lean output*

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
If the Total Body Ext option was selected, a “TotalBodyExt.csv” would be generated in “SingleType” subfolder ([Figure 7: Schematic for the “.csv” output files in the “SingleType” Subfolder for the DXA Data Xtraction Assistant](#Output-Details)). Table 7 introduced the meaning of each column.

*Table 7: Total Body Ext output*

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
If the Lumbar Spine option was selected, a “LumbarSpine.csv” would be generated in “SingleType” subfolder ([Figure 7: Schematic for the “.csv” output files in the “SingleType” Subfolder for the DXA Data Xtraction Assistant](#Output-Details)). Table 8 introduced the meaning of each column.

*Table 8: Lumbar Spine output*

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
If the Total Hip Ext option was selected, a “TotalHipExt.csv” would be generated in the “SingleType” subfolder of the output file path ([Figure 7: Schematic for the “.csv” output files in the “SingleType” Subfolder for the DXA Data Xtraction Assistant](#Output-Details)). Table 9 introduced the meaning of each column.

*Table 9: Total Hip Ext output*

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
The output “.csv” files include two merged file, named “Full_Merged.csv” and "Abbreviated_Merged.csv", in the selected output file path ([Figure 6: Merged Output](#Output-Details)). It would only contain the interested outcomes as selected ([Figure 5: Output Interface – Selecting the Interested Outcomes](#Scan-Type-Selection)). The variable names are described in the data dictionary.

###### <p dir='rtl' align='right'>[Back to Top](#Content)</p>

## Lunar Prodigy
### Lunar Prodigy: Single Type
#### Lunar Prodigy: Demographic
The “Demographic.csv” file is a default file which is automatically generated when using the DXA Data Xtraction Assistant.  This file contains each patients’ demographic information, collected from each DXA output. This file includes 8 columns (Table 11). 

*Table 11: Demographic output*

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
#### Lunar Prodigy: Total Body Bone
If the Total Body Bone option was selected, a “TotalBodyBone.csv” would be generated in “SingleType” subfolder ([Figure 7: Schematic for the “.csv” output files in the “SingleType” Subfolder for the DXA Data Xtraction Assistant](#Output-Details)). Table 12 introduced the meaning of each column.

*Table 13: Total Body Bone output*

|Variables	|Explanation|
|---|---|
|Patients_ID	|Patient ID, from the input file name|
|Patients_Visit	|Visit Number, from the input file name|
|Region	|Region of DXA measurement|
|BMD_g/cm2	|Areal Bone Mineral Density (g/cm2)|
|YA_Percent	|The mean of a young adult reference (%)|
|YA_T_score	|T-score|
|AM_Percent	|The mean of an age-matched reference (%)|
|AM_Z_score	|Z-score|


###### <p dir='rtl' align='right'>[Back to Top](#Content)</p>
#### Lunar Prodigy: Total Body Bone Ext
If the Total Body Bone Ext option was selected, a “TotalBodyBoneExt.csv” would be generated in “SingleType” subfolder ([Figure 7: Schematic for the “.csv” output files in the “SingleType” Subfolder for the DXA Data Xtraction Assistant](#Output-Details)). Table 13 introduced the meaning of each column.

*Table 13: Total Body Bone Ext output*

|Variables	|Explanation|
|---|---|
|Patients_ID	|Patient ID, from the input file name|
|Patients_Visit	|Visit Number, from the input file name|
|Region	|Region of DXA measurement|
|BMD_g/cm2	|Areal Bone Mineral Density (g/cm2)|
|YA_Percent	|The mean of a young adult reference (%)|
|YA_T_score	|T-score|
|AM_Percent	|The mean of an age-matched reference (%)|
|AM_Z_score	|Z-score|
|BMC_g	|Bone Mineral Content (g)|
|Area_cm2	|Area (cm2)|


###### <p dir='rtl' align='right'>[Back to Top](#Content)</p>
#### Lunar Prodigy: Total Body Ext
If the Total Body Ext option was selected, a “TotalBodyExt.csv” would be generated in “SingleType” subfolder ([Figure 7: Schematic for the “.csv” output files in the “SingleType” Subfolder for the DXA Data Xtraction Assistant](#Output-Details)). Table 14 introduced the meaning of each column.

*Table 14: Total Body Ext output*

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
If the Lumbar Spine Ext option was selected, a “LumbarSpineExt.csv” would be generated in “SingleType” subfolder ([Figure 7: Schematic for the “.csv” output files in the “SingleType” Subfolder for the DXA Data Xtraction Assistant](#Output-Details)). Table 15 introduced the meaning of each column.

*Table 15: Lumbar Spine Ext output*

|Variables	|Explanation|
|---|---|
|Patients_ID	|Patient ID, from the input file name|
|Patients_Visit	|Visit Number, from the input file name|
|Region	|Region of DXA measurement|
|BMD_g/cm2	|Areal Bone Mineral Density (g/cm2)|
|YA_Percent	|The mean of a young adult reference (%)|
|YA_T_score	|T-score|
|AM_Percent	|The mean of an age-matched reference (%)|
|AM_Z_score	|Z-score|
|BMC_g	|Bone Mineral Content (g)|
|Area_cm2	|Area (cm2)|
|Width_cm	|Width (cm)|
|Height_cm	|Height (cm)|

###### <p dir='rtl' align='right'>[Back to Top](#Content)</p>
#### Lunar Prodigy: Total Hip Ext
If the Total Hip Ext option was selected, a “TotalHipExt.csv” would be generated in the “SingleType” subfolder of the output file path ([Figure 7: Schematic for the “.csv” output files in the “SingleType” Subfolder for the DXA Data Xtraction Assistant](#Output-Details)). Table 16 introduced the meaning of each column.

*Table 16: Total Hip Ext output*

|Variables	|Explanation|
|---|---|
|Patients_ID	|Patient ID, from the input file name|
|Patients_Visit	|Visit Number, from the input file name|
|Region	|Region of DXA measurement|
|BMD_g/cm2	|Areal Bone Mineral Density (g/cm2)|
|YA_Percent	|The mean of a young adult reference (%)|
|YA_T_score	|T-score|
|AM_Percent	|The mean of an age-matched reference (%)|
|AM_Z_score	|Z-score|
|BMC_g	|Bone Mineral Content (g)|
|Area_cm2	|Area (cm2)|

###### <p dir='rtl' align='right'>[Back to Top](#Content)</p>
#### Lunar Prodigy: Radius Scan
If the Radius Scan option was selected, a “Rad.csv” would be generated in “SingleType” subfolder ([Figure 7: Schematic for the “.csv” output files in the “SingleType” Subfolder for the DXA Data Xtraction Assistant](#Output-Details)). Table 17 introduced the meaning of each column.

*Table 17: Radius Scan output*

|Variables	|Explanation|
|---|---|
|Patients_ID	|Patient ID, from the input file name|
|Patients_Visit	|Visit Number, from the input file name|
|Region	|Region of DXA measurement|
|BMD_g/cm2	|Areal Bone Mineral Density (g/cm2)|
|YA_Percent	|The mean of a young adult reference (%)|
|YA_T_score	|T-score|
|AM_Percent	|The mean of an age-matched reference|
|AM_Z_score	|Z-score|


###### <p dir='rtl' align='right'>[Back to Top](#Content)</p>
### Lunar Prodigy: Merged Output
The output “.csv” files include two merged file, named “Full_Merged.csv” and "Abbreviated_Merged.csv", in the selected output file path ([Figure 6: Merged Output](#Output-Details)). It would only contain the interested outcomes as selected ([Figure 5: Output Interface – Selecting the Interested Outcomes](#Scan-Type-Selection)). The variable names are described in the data dictionary.
									

###### <p dir='rtl' align='right'>[Back to Top](#Content)</p>

## MG
### MG: Single Type
#### MG: Demographic
The “Demographic.csv” file is a default file which is automatically generated when using the DXA Data Xtraction Assistant.  This file contains each patients’ demographic information, collected from each DXA output. This file includes 8 columns (Table 18). 

*Table 18: Demographic output*

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
If the Total Body Bone Ext option was selected, a “TotalBodyBoneExt.csv” would be generated in “SingleType” subfolder ([Figure 7: Schematic for the “.csv” output files in the “SingleType” Subfolder for the DXA Data Xtraction Assistant](#Output-Details)). Table 19 introduced the meaning of each column.

*Table 20: Total Body Bone Ext output*

|Variables	|Explanation|
|---|---|
|Patients_ID	|Patient ID, from the input file name|
|Patients_Visit	|Visit Number, from the input file name|
|Region	|Region of DXA measurement|
|BMD_g/cm2	|Areal Bone Mineral Density (g/cm2)|
|YA_T_score	|T-score|
|AM_Z_score	|Z-score|


###### <p dir='rtl' align='right'>[Back to Top](#Content)</p>
#### MG: Total Body Bone Ext
If the Total Body Bone Ext option was selected, a “TotalBodyBoneExt.csv” would be generated in “SingleType” subfolder ([Figure 7: Schematic for the “.csv” output files in the “SingleType” Subfolder for the DXA Data Xtraction Assistant](#Output-Details)). Table 20 introduced the meaning of each column.

*Table 20: Total Body Bone Ext output*

|Variables	|Explanation|
|---|---|
|Patients_ID	|Patient ID, from the input file name|
|Patients_Visit	|Visit Number, from the input file name|
|Region	|Region of DXA measurement|
|BMD_g/cm2	|Areal Bone Mineral Density (g/cm2)|
|YA_Percent	|The mean of a young adult reference (%)|
|YA_T_score	|T-score|
|AM_Percent	|The mean of an age-matched reference (%)|
|AM_Z_score	|Z-score|
|BMC_g	|Bone Mineral Content (g)|
|Area_cm2	|Area (cm2)|


###### <p dir='rtl' align='right'>[Back to Top](#Content)</p>
#### MG: Total Body Ext
If the Total Body Ext option was selected, a “TotalBodyExt.csv” would be generated in “SingleType” subfolder ([Figure 7: Schematic for the “.csv” output files in the “SingleType” Subfolder for the DXA Data Xtraction Assistant](#Output-Details)). Table 21 introduced the meaning of each column.

*Table 21: Total Body Ext output*

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
If the Lumbar Spine Ext option was selected, a “LumbarSpineExt.csv” would be generated in “SingleType” subfolder ([Figure 7: Schematic for the “.csv” output files in the “SingleType” Subfolder for the DXA Data Xtraction Assistant](#Output-Details)). Table 22 introduced the meaning of each column.

*Table 22: Lumbar Spine Ext output*

|Variables	|Explanation|
|---|---|
|Patients_ID	|Patient ID, from the input file name|
|Patients_Visit	|Visit Number, from the input file name|
|Region	|Region of DXA measurement|
|BMD_g/cm2	|Areal Bone Mineral Density (g/cm2)|
|YA_Percent	|The mean of a young adult reference (%)|
|YA_T_score	|T-score|
|AM_Percent	|The mean of an age-matched reference (%)|
|AM_Z_score	|Z-score|
|BMC_g	|Bone Mineral Content (g)|
|Area_cm2	|Area (cm2)|
|Width_cm	|Width (cm)|
|Height_cm	|Height (cm)|

###### <p dir='rtl' align='right'>[Back to Top](#Content)</p>
#### MG: Total Hip Ext
If the Total Hip Ext option was selected, a “TotalHipExt.csv” would be generated in the “SingleType” subfolder of the output file path ([Figure 7: Schematic for the “.csv” output files in the “SingleType” Subfolder for the DXA Data Xtraction Assistant](#Output-Details)). Table 23 introduced the meaning of each column.

*Table 23: Total Hip Ext output*

|Variables	|Explanation|
|---|---|
|Patients_ID	|Patient ID, from the input file name|
|Patients_Visit	|Visit Number, from the input file name|
|Region	|Region of DXA measurement|
|BMD_g/cm2	|Areal Bone Mineral Density (g/cm2)|
|YA_Percent	|The mean of a young adult reference (%)|
|YA_T_score	|T-score|
|AM_Percent	|The mean of an age-matched reference (%)|
|AM_Z_score	|Z-score|
|BMC_g	|Bone Mineral Content (g)|
|Area_cm2	|Area (cm2)|

###### <p dir='rtl' align='right'>[Back to Top](#Content)</p>
#### MG: Radius Scan
If the Radius Scan option was selected, a “Rad.csv” would be generated in “SingleType” subfolder ([Figure 7: Schematic for the “.csv” output files in the “SingleType” Subfolder for the DXA Data Xtraction Assistant](#Output-Details)). Table 24 introduced the meaning of each column.

*Table 24: Radius Scan output*

|Variables	|Explanation|
|---|---|
|Patients_ID	|Patient ID, from the input file name|
|Patients_Visit	|Visit Number, from the input file name|
|Region	|Region of DXA measurement|
|BMD_g/cm2	|Areal Bone Mineral Density (g/cm2)|
|YA_Percent	|The mean of a young adult reference (%)|
|YA_T_score	|T-score|
|AM_Percent	|The mean of an age-matched reference (%)|
|AM_Z_score	|Z-score|
|BMC_g	|Bone Mineral Content (g)|
|Area_cm2	|Area (cm2)|


###### <p dir='rtl' align='right'>[Back to Top](#Content)</p>
### MG: Merged Output
The output “.csv” files include two merged file, named “Full_Merged.csv” and "Abbreviated_Merged.csv", in the selected output file path ([Figure 6: Merged Output](#Output-Details)). It would only contain the interested outcomes as selected ([Figure 5: Output Interface – Selecting the Interested Outcomes](#Scan-Type-Selection)). The variable names are described in the data dictionary.
		

###### <p dir='rtl' align='right'>[Back to Top](#Content)</p>

## iDXA
### iDXA: Single Type
#### iDXA: Demographic
The “Demographic.csv” file is a default file which is automatically generated when using the DXA Data Xtraction Assistant.  This file contains each patients’ demographic information, collected from each DXA output. This file includes 8 columns (Table 25). 

*Table 25: Demographic output*

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
If the Total Body Bone option was selected, a “TotalBodyBone.csv” would be generated in “SingleType” subfolder ([Figure 7: Schematic for the “.csv” output files in the “SingleType” Subfolder for the DXA Data Xtraction Assistant](#Output-Details)). Table 26 introduced the meaning of each column.

*Table 26: Total Body Bone output*

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
If the Total Body Ext option was selected, a “TotalBodyExt.csv” would be generated in “SingleType” subfolder ([Figure 7: Schematic for the “.csv” output files in the “SingleType” Subfolder for the DXA Data Xtraction Assistant](#Output-Details)). Table 27 introduced the meaning of each column.

*Table 27: Total Body Ext output*

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
If the Lumbar Spine option was selected, a “LumbarSpine.csv” would be generated in “SingleType” subfolder ([Figure 7: Schematic for the “.csv” output files in the “SingleType” Subfolder for the DXA Data Xtraction Assistant](#Output-Details)). Table 28 introduced the meaning of each column.

*Table 28: Lumbar Spine output*

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
If the Total Hip option was selected, a “TotalHip.csv” would be generated in the “SingleType” subfolder of the output file path ([Figure 7: Schematic for the “.csv” output files in the “SingleType” Subfolder for the DXA Data Xtraction Assistant](#Output-Details)). Table 29 introduced the meaning of each column.

*Table 29: Total Hip output*

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
If the Radius Scan option was selected, a “Rad.csv” would be generated in “SingleType” subfolder ([Figure 7: Schematic for the “.csv” output files in the “SingleType” Subfolder for the DXA Data Xtraction Assistant](#Output-Details)). Table 30 introduced the meaning of each column.

*Table 30: Radius Scan output*

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
The output “.csv” files include two merged file, named “Full_Merged.csv” and "Abbreviated_Merged.csv", in the selected output file path ([Figure 6: Merged Output](#Output-Details)). It would only contain the interested outcomes as selected ([Figure 5: Output Interface – Selecting the Interested Outcomes](#Scan-Type-Selection)). The variable names are described in the data dictionary.

		

###### <p dir='rtl' align='right'>[Back to Top](#Content)</p>

## Norland
### Norland: Single Type
#### Norland: Demographic
The “Demographic.csv” file is a default file which is automatically generated when using the DXA Data Xtraction Assistant.  This file contains each patients’ demographic information, collected from each DXA output. This file includes 8 columns (Table 31). 

*Table 31: Demographic output*

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
If the Total Body Bone option was selected, a “TotalBodyBone.csv” would be generated in “SingleType” subfolder ([Figure 7: Schematic for the “.csv” output files in the “SingleType” Subfolder for the DXA Data Xtraction Assistant](#Output-Details)). Table 32 introduced the meaning of each column.

*Table 32: Total Body Bone output*

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
If the Total Body Composition option was selected, a “TotalBodyComp.csv” would be generated in “SingleType” subfolder ([Figure 7: Schematic for the “.csv” output files in the “SingleType” Subfolder for the DXA Data Xtraction Assistant](#Output-Details)). Table 33 introduced the meaning of each column.

*Table 33: Total Body Composition output*

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
If the Lumbar Spine option was selected, a “LumbarSpine.csv” would be generated in “SingleType” subfolder ([Figure 7: Schematic for the “.csv” output files in the “SingleType” Subfolder for the DXA Data Xtraction Assistant](#Output-Details)). Table 34 introduced the meaning of each column.

*Table 34: Lumbar Spine output*

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
|Young_Ref_%	|The mean of a young adult reference (%)|
|Z_score	|Z-score|
|Age_Match_%	|The mean of an age-matched reference (%)|
|ST_Change_%	|ST Change (%)|
|ST_Change_%/year	|ST Change (%/year)|
|LT_Change_%	|LT Change (%)|
|LT_Change_%/year	|LT Change (%/year)|

###### <p dir='rtl' align='right'>[Back to Top](#Content)</p>
#### Norland: Total Hip
If the Total Hip option was selected, a “TotalHip.csv” would be generated in the “SingleType” subfolder of the output file path ([Figure 7: Schematic for the “.csv” output files in the “SingleType” Subfolder for the DXA Data Xtraction Assistant](#Output-Details)). Table 35 introduced the meaning of each column.

*Table 35: Total Hip output*

|Variables	|Explanation|
|---|---|
|Patients_ID	|Patient ID, from the input file name|
|Patients_Visit	|Visit Number, from the input file name|
|Region	|Region of DXA measurement|
|BMD_g/cm2	|Areal Bone Mineral Density (g/cm2)|
|BMC_g	|Bone Mineral Content (g)|
|Area_cm2	|Area (cm2)|
|T_score	|T-score|
|Young_Ref_%	|The mean of a young adult reference (%)|
|Z_score	|Z-score|
|Age_Match_%	|The mean of an age-matched reference (%)|
|ST_Change_%	|ST Change (%)|
|ST_Change_%/year	|ST Change (%/year)|
|LT_Change_%	|LT Change (%)|
|LT_Change_%/year	|LT Change (%/year)|

###### <p dir='rtl' align='right'>[Back to Top](#Content)</p>
#### Norland: Radius Scan
If the Radius Scan option was selected, a “Rad.csv” would be generated in “SingleType” subfolder ([Figure 7: Schematic for the “.csv” output files in the “SingleType” Subfolder for the DXA Data Xtraction Assistant](#Output-Details)). Table 36 introduced the meaning of each column.

*Table 36: Radius Scan output*

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
|Young_Ref_%	|The mean of a young adult reference (%)|
|Z_score	|Z-score|
|Age_Match_%	|The mean of an age-matched reference (%)|
|ST_Change_%	|ST Change (%)|
|ST_Change_%/year	|ST Change (%/year)|
|LT_Change_%	|LT Change (%)|
|LT_Change_%/year	|LT Change (%/year)|


###### <p dir='rtl' align='right'>[Back to Top](#Content)</p>
### Norland: Merged Output
The output “.csv” files include two merged file, named “Full_Merged.csv” and "Abbreviated_Merged.csv", in the selected output file path ([Figure 6: Merged Output](#Output-Details)). It would only contain the interested outcomes as selected ([Figure 5: Output Interface – Selecting the Interested Outcomes](#Scan-Type-Selection)). The variable names are described in the data dictionary.


###### <p dir='rtl' align='right'>[Back to Top](#Content)</p>
