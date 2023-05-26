A software used to convert DXA output from xps or pdf format into csv files.

**Need to update this later**

[![DOI](https://zenodo.org/badge/292389811.svg)](https://zenodo.org/badge/latestdoi/292389811)

***

**Thanks for your interest in using the DXA<sup>2</sup>. Using the DXA<sup>2</sup> for the first time requires three simple steps and we encourage you to read these instructions and watch the corresponding tutorial videos before trying to use the DXA<sup>2</sup> for the first time. Links to the three videos can be found [NEWVIDEO](NEWLINK).**

# Content
* [Step 1: Formatting and exporting your DXA scan reports](#Step-1-Formatting-and-exporting-your-DXA-scan-reports)

* [Step 2: Downloading and saving the DXA<sup>2</sup> application](#Step-2-Downloading-and-saving-the-DXA2-application)

* [Step 3: Using the DXA<sup>2</sup> application](#Step-3-Using-the-DXA2-application)

* [Troubleshooting/FAQ’s](#TroubleshootingFAQs)
    * [Formatting and Exporting your DXA scan reports](#Formatting-and-Exporting-your-DXA-scan-reports)
    * [Downloading and Saving DXA<sup>2</sup>](#Downloading-and-Saving-DXA2)
    * [Using the DXA<sup>2</sup> application](#Using-the-DXA2-application)
    
* [Links Tutorial Videos](NEWLINK)



# Step 1: Formatting and exporting your DXA scan reports

Different software versions display and organize DXA data differently. At your DXA computer ensure that the DXA reports to be extracted are formatted correctly. This can be accomplished by changing the report configurations, if needed, as shown in the [first tutorial video](https://www.youtube.com/watch?v=IuckTLeyZ0k).

Please scroll to find the software version that matches or is closest to what you are using and ensure your reports are configured to match these examples. Each DXA scan report for use in the DXA<sup>2</sup> should be saved to an external hard drive as either an *.xps* or *.pdf* file. Then, you can either transfer the scans from the external hard drive to a location on the computer where the DXA<sup>2</sup> application is located (or will be downloaded) or use the DXA<sup>2</sup> on the computer and save all outputs to the external hard drive.

* GE
  * [GE Prodigy – enCORE v.16](https://github.com/DXA-Data-Xtraction-Assistant/DXA-Data-Xtraction-Assistant/blob/master/DXA%20scan%20report%20examples/GE%20enCORE%20v%2016%20outputs.pdf) 
  * [GE iDXA – enCORE v.17 & 18](https://github.com/DXA-Data-Xtraction-Assistant/DXA-Data-Xtraction-Assistant/blob/master/DXA%20scan%20report%20examples/GE%20iDXA%20enCORE%20v%2017%20%26%2018%20outputs.pdf)
* [Hologic Horizon – Apex v 5.5](https://github.com/DXA-Data-Xtraction-Assistant/DXA-Data-Xtraction-Assistant/blob/master/DXA%20scan%20report%20examples/Hologic%20Horizon%20Apex%20v%205.5%20outputs.pdf)
* [Norland ELITE or XR-800 – Illuminatus v. 4.7.5](https://github.com/DXA-Data-Xtraction-Assistant/DXA-Data-Xtraction-Assistant/blob/master/DXA%20scan%20report%20examples/Norland%20Elite%20and%20XR-800%20Illuminatus%20v%204.7.5%20%20outputs.pdf)

After your reports have been configured, the DXA reports should be saved using the following file naming convention: 

<div align="center">

## PatientID\_Visit#\_ScanType 
</div>

**PatientID**: The Patient ID is the number used to identify or index patients. This identifier must be unique to each patient and composed of only letters and numbers (no spaces). There is no character limit for the Patient ID. The Patient ID must be followed by an underscore, "\_".

**Visit#**: The Visit Number denotes the number of times, or visits, that a patient is scanned using the DXA machine. 
The visit number must be a number but there is no limit to the length. For example, for a pre and post study design, the visit number would be denoted using "1" and "2". The Visit# must be followed by an underscore, "\_". 

**ScanType**: Lastly, the Scan Type is the suffix that denotes the type of DXA scan report. See the suffix name for each type of DXA report in Table 1 below. 

*Table 1: Guide for how to rename DXA reports for use with DXA<sup>2</sup>.*

| Scan Type	| Main Report	| Needed file name format	| Enhanced Report	| Needed file name format|
|---|---|---|---|---|
|Total Body	| Total Body Densitometry	| PatientID\_visit#\_Bone	| Total Body Densitometry Enhanced Analysis	| PatientID\_visit#\_BoneExt |
| |Total Body Composition	| PatientID\_visit#\_BC	| Total Body Composition Enhanced Analysis	| PatientID\_visit#\_BCExt |
| Lumbar Spine	| Lumbar Spine Densitometry	| PatientID\_visit#\_LS	| Lumbar Spine Densitometry Enhanced Analysis	| PatientID\_visit#\_LSExt |
| Proximal Femur	| Dual Total Hip Densitometry |	PatientID\_visit#\_DH	| Dual Total Hip Densitometry Enhanced Analysis	| PatientID\_visit#\_DHExt |
| Radius	| L or R Radial Densitometry	| PatientID\_visit#\_Rad	| only the left OR the right radial scans can be processed at a time in the application.| |


###### <p dir='rtl' align='right'>[Back to Top](#Content)</p>

# Step 2: Downloading and saving the DXA<sup>2</sup> application

DXA<sup>2</sup> is a standalone application constructed using Python 3.7.  No other software is required to use the DXA<sup>2</sup>.  The process to download and initialize the DXA<sup>2</sup> can also be viewed using the [NEW second tutorial video](NEWLINK).

On the [main webpage](NEWLINK) click on the *DXA<sup>2</sup>\_DOWNLOAD\_ME\_V1_1.exe* file in the first box and then click the "Download" button near the middle of the screen in the gray box. Once the DXA<sup>2</sup> has finished downloading, you will find the application in your "Downloads" folder. The DXA<sup>2</sup> can be moved to another location on your computer or hard drive by dragging and dropping (or by using the cut and paste functions). If you have issues, please review the [Troubleshooting/FAQ’s](#TroubleshootingFAQs) at the end of these instructions.  


###### <p dir='rtl' align='right'>[Back to Top](#Content)</p>

# Step 3: Using the DXA<sup>2</sup> application

Once you have successfully downloaded the DXA<sup>2</sup>, it is time to use it! Double click the DXA<sup>2</sup> .exe file (femur icon) or right click and select "Run as Administrator". The first time you open DXA<sup>2</sup>, it may take a minute or two to load. After the initial use, the DXA<sup>2</sup> will load faster. You will be greeted by an introduction page that provides a link to the GitHub site. We encourage you to read all of these written instructions and [view all three tutorial videos](NEWLINK) prior to using the DXA<sup>2</sup>. 

Although the DXA<sup>2</sup> is free, the developers request that users cite the DXA<sup>2</sup> in their publications using the following citation:( **Include citation here** ). After selecting "I agree", you will be prompted to select the manufacturer and the software version for your DXA machine. As noted in the DXA<sup>2</sup>, 

You will first need to select the input, or file path to your properly saved DXA reports, and the output folder, or file path for where the extracted data should be saved. Once you have selected the input folder, output folder, you need to select the software version of your DXA machine and click "transform". After this has been completed, the final screen will thank you for using the DXA<sup>2</sup> and will remind users to cite our work. If you have any issues with using the DXA<sup>2</sup>, please review the [Troubleshooting/FAQ’s](#TroubleshootingFAQs) below or the [third tutorial video](NEWLINK).

if you do not see the specific software version for your DXA machine, please try the option "Customized" and upload your own template file by clicking the button "Template File". See [here](TEMPLATE) for more details.


Tips for success: 
1. Ensure that your input folder **ONLY** includes the properly configured and formatted DXA reports (*.pdf* or *.xps* files). If any of these files are improperly named for use in the DXA<sup>2</sup> or if there are other files in the input folder, the DXA<sup>2</sup> will not work. 
2. It is helpful for the first few times using the DXA<sup>2</sup> to have your output file folder empty, prior to transformation and merging, so you can recognize all the output and its organization. 

###### <p dir='rtl' align='right'>[Back to Top](#Content)</p>

# Troubleshooting/FAQ’s

## Formatting and Exporting your DXA scan reports

### Can I name my scans whatever I want? 

No. The patient or participant ID's can be any alphanumeric sequence but cannot contain spaces. The naming format for each DXA report is **PatientID\_Visit#\_ScanType**. This format is how the DXA<sup>2</sup> will correctly identify, transform, and merge your DXA report data. As noted in our publication, the time required to reconfigure and/or resave DXA reports using this format is minimal but is a necessary step to successfully use the DXA<sup>2</sup>.

### I did a scan not listed in Table 1 and don’t know how to save it. 

The DXA machine has a variety of capabilities (e.g. aortic calcification) not listed in Table 1 in the instructions. If this is the case, please try the option "Customized" and upload your own template file by clicking the button "Template File". If you need further assistance, please email the administrator at DXA2@health.missouri.edu and they will work with you directly. 

### Why can’t I just do Steps 1 to 3 on my DXA computer? 

Most DXA manufactures discourage users from connecting their DXA computer to the internet. However, if your DXA computer is internet-enabled, you can follow steps 2 and 3 on your DXA computer. If your DXA computer is not connected to the internet, be sure to move all reconfigured and/or renamed DXA reports (*.xps* or *.pdf* files) to an external hard drive for transport to your Windows computer of choice.

### Can I share this resource and do I need to pay for something? 

The DXA<sup>2</sup> is free to use and share. The DXA<sup>2</sup> was created to save time, eliminate errors, and expand the amount of DXA data available for use without associated increased costs. We encourage you to share the DXA<sup>2</sup> with your colleagues. All that we require is that the DXA<sup>2</sup> is properly cited when utilizing data extracted using the DXA<sup>2</sup> ( **include our citation** ). 


###### <p dir='rtl' align='right'>[Back to Top](#Content)</p>

## Downloading and Saving DXA<sup>2</sup>

### Why is this not working on my Mac? 

Currently the DXA<sup>2</sup> does not work on Apple products.

### When I try to open DXA<sup>2</sup>, Microsoft Defender stops me from running the application. 

The first time you download and use the DXA<sup>2</sup>, click “More info” and then click "Run anyway". 

### My computer tells me: This app can’t run on your PC. 

If this is the case, try reopening the DXA<sup>2</sup> by right clicking and selecting "Run as an administrator".  Then select "yes" to run and open the application.

### I can’t find the download file (*.exe* file). 

Navigate to your downloads folder and search there. If the DXA<sup>2</sup> is not located there, return to the GitHub site and retry downloading. Ensure you don’t have any pop-up blockers inhibiting the download.


###### <p dir='rtl' align='right'>[Back to Top](#Content)</p>

## Using the DXA<sup>2</sup> application

### When I click "transform" or "merge", I don’t get a confirmation box/nothing happens. 

This can mean one of two things. 
First, double check that you **ONLY** have *.pdf* or *.xps* files in the input folder and check that all DXA scans are named using the correct format for the DXA<sup>2</sup> (see Table 1). Even one mistake in the file name will prevent the DXA<sup>2</sup> from working. 
Second, if your reports are not configured properly or you selected the wrong manufacture/software version for your reports, the DXA<sup>2</sup> won't be able to read your DXA scans. As noted in the instructions and the tutorial videos, if your DXA software version is not listed, please email the DXA<sup>2</sup> administrator at DXA2@health.missouri.edu and we will work with you directly. 

### In my data files (either merged or abbreviated), I am missing data. 

Be sure to double check that the report containing that data was correctly named using the DXA<sup>2</sup> format. For instance, if you saved the radial scans as "\_Radius" instead of “_Rad”, the DXA<sup>2</sup> will not retrieve those data. 

### How do I know what these abbreviated variable names mean? 

In your output folder, you will find a data dictionary that lists all variables and their abbreviations.

### I need data from a report not listed. 
If you have data that is not extracted by the DXA<sup>2</sup>, please email the DXA<sup>2</sup> administrator at DXA2@health.missouri.edu and we will work with you directly. 


###### <p dir='rtl' align='right'>[Back to Top](#Content)</p>
