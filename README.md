# Water Access Analysis
### Capstone Project - Data Science Diploma

Welcome! In here you will find details about my data science project. I will show you how I got started with the data analysis, and how I implemented machine learning.

### Introduction
In this project, I will analyze the impact of pollution affecting Canadian river basins. Data was obtained from the Government of Canada's Open Data site.

### Background
Over the last few decades, water has become a scarce resource in many communities across Canada. The aim of this analysis is to identify stressors affecting access to water and to predict water restrictions down the road. My ultimate goal is to help: 
* Corporations optimize their consumption
* Non-profits allocate resources to mitigate human impact
* Governments plan infrastructure projects more efficiently

  	![image](https://github.com/xavieruxchamp/Water-Access-Analysis/assets/44354258/4e1baca2-59b8-485e-bea8-0c5bd6e37c9c)

### Data cleaning
So far I have completed: Data collection, preliminary visualization, and initial Exploratory Data Analysis (EDA). In this process I have noticed certain limitations could hinder machine learning work. Namely, the datasets are focused on chemicals. I will also be looking into data quality issues stemming from the methods use (i.e. sample data collected at multiple sites by multiple parties and devices).

#### Data Dictionary
<html>

<head>

<!--
 /* Font Definitions */
 @font-face
	{font-family:"Cambria Math";
	panose-1:2 4 5 3 5 4 6 3 2 4;}
@font-face
	{font-family:Calibri;
	panose-1:2 15 5 2 2 2 4 3 2 4;}
 /* Style Definitions */
 p.MsoNormal, li.MsoNormal, div.MsoNormal
	{margin-top:0in;
	margin-right:0in;
	margin-bottom:8.0pt;
	margin-left:0in;
	line-height:107%;
	font-size:11.0pt;
	font-family:"Calibri",sans-serif;}
.MsoPapDefault
	{margin-bottom:8.0pt;
	line-height:107%;}
@page WordSection1
	{size:8.5in 11.0in;
	margin:1.0in 1.0in 1.0in 1.0in;}
div.WordSection1
	{page:WordSection1;}
-->


</head>

<body lang=EN-CA style='word-wrap:break-word'>

<div class=WordSection1>

<table class=MsoNormalTable border=1 cellspacing=0 cellpadding=0 width=630
 style='width:472.25pt;border-collapse:collapse;border:none'>
 <tr style='height:15.05pt'>
  <td width=148 style='width:110.8pt;border:solid windowtext 1.0pt;padding:
  0in 5.4pt 0in 5.4pt;height:15.05pt'>
  <p class=MsoNormal style='margin-bottom:0in;line-height:normal'><b><span
  style='color:black'>Variable</span></b></p>
  </td>
  <td width=175 style='width:131.15pt;border:solid windowtext 1.0pt;border-left:
  none;padding:0in 5.4pt 0in 5.4pt;height:15.05pt'>
  <p class=MsoNormal style='margin-bottom:0in;line-height:normal'><b><span
  style='color:black'>Column Name</span></b></p>
  </td>
  <td width=307 style='width:230.3pt;border:solid windowtext 1.0pt;border-left:
  none;padding:0in 5.4pt 0in 5.4pt;height:15.05pt'>
  <p class=MsoNormal style='margin-bottom:0in;line-height:normal'><b><span
  style='color:black'>Description</span></b></p>
  </td>
 </tr>
 <tr style='height:15.05pt'>
  <td width=148 style='width:110.8pt;border:solid windowtext 1.0pt;border-top:
  none;padding:0in 5.4pt 0in 5.4pt;height:15.05pt'>
  <p class=MsoNormal style='margin-bottom:0in;line-height:normal'><span
  style='color:black'>SAMPLE DATE AND TIME</span></p>
  </td>
  <td width=175 style='width:131.15pt;border-top:none;border-left:none;
  border-bottom:solid windowtext 1.0pt;border-right:solid windowtext 1.0pt;
  padding:0in 5.4pt 0in 5.4pt;height:15.05pt'>
  <p class=MsoNormal style='margin-bottom:0in;line-height:normal'><span
  style='color:black'>DATE_TIME_HEURE</span></p>
  </td>
  <td width=307 style='width:230.3pt;border-top:none;border-left:none;
  border-bottom:solid windowtext 1.0pt;border-right:solid windowtext 1.0pt;
  padding:0in 5.4pt 0in 5.4pt;height:15.05pt'>
  <p class=MsoNormal style='margin-bottom:0in;line-height:normal'><span
  style='color:black'>SAMPLE DATE AND TIME IN DD/MM/YYYY HH:MM FORMAT USING
  LOCAL TIME ZONE</span></p>
  </td>
 </tr>
 <tr style='height:15.05pt'>
  <td width=148 style='width:110.8pt;border:solid windowtext 1.0pt;border-top:
  none;padding:0in 5.4pt 0in 5.4pt;height:15.05pt'>
  <p class=MsoNormal style='margin-bottom:0in;line-height:normal'><span
  style='color:black'>DATUM</span></p>
  </td>
  <td width=175 style='width:131.15pt;border-top:none;border-left:none;
  border-bottom:solid windowtext 1.0pt;border-right:solid windowtext 1.0pt;
  padding:0in 5.4pt 0in 5.4pt;height:15.05pt'>
  <p class=MsoNormal style='margin-bottom:0in;line-height:normal'><span
  style='color:black'>DATUM</span></p>
  </td>
  <td width=307 style='width:230.3pt;border-top:none;border-left:none;
  border-bottom:solid windowtext 1.0pt;border-right:solid windowtext 1.0pt;
  padding:0in 5.4pt 0in 5.4pt;height:15.05pt'>
  <p class=MsoNormal style='margin-bottom:0in;line-height:normal'><span
  style='color:black'>DATUM USED FOR LATITUDE AND LONGITUDE</span></p>
  </td>
 </tr>
 <tr style='height:30.15pt'>
  <td width=148 style='width:110.8pt;border:solid windowtext 1.0pt;border-top:
  none;padding:0in 5.4pt 0in 5.4pt;height:30.15pt'>
  <p class=MsoNormal style='margin-bottom:0in;line-height:normal'><span
  style='color:black'>MEASUREMENT FLAG</span></p>
  </td>
  <td width=175 style='width:131.15pt;border-top:none;border-left:none;
  border-bottom:solid windowtext 1.0pt;border-right:solid windowtext 1.0pt;
  padding:0in 5.4pt 0in 5.4pt;height:30.15pt'>
  <p class=MsoNormal style='margin-bottom:0in;line-height:normal'><span
  style='color:black'>FLAG_MARQUEUR</span></p>
  </td>
  <td width=307 style='width:230.3pt;border-top:none;border-left:none;
  border-bottom:solid windowtext 1.0pt;border-right:solid windowtext 1.0pt;
  padding:0in 5.4pt 0in 5.4pt;height:30.15pt'>
  <p class=MsoNormal style='margin-bottom:0in;line-height:normal'><span
  style='color:black'>FLAG APPLICABLE TO MEASUREMENT VALUE (&lt;-LESS THAN,
  T-TRACE VALUE REPORTED BELOW DETECTION LIMIT BY LABORATORY)</span></p>
  </td>
 </tr>
 <tr style='height:15.05pt'>
  <td width=148 style='width:110.8pt;border:solid windowtext 1.0pt;border-top:
  none;padding:0in 5.4pt 0in 5.4pt;height:15.05pt'>
  <p class=MsoNormal style='margin-bottom:0in;line-height:normal'><span
  style='color:black'>LATITUDE</span></p>
  </td>
  <td width=175 style='width:131.15pt;border-top:none;border-left:none;
  border-bottom:solid windowtext 1.0pt;border-right:solid windowtext 1.0pt;
  padding:0in 5.4pt 0in 5.4pt;height:15.05pt'>
  <p class=MsoNormal style='margin-bottom:0in;line-height:normal'><span
  style='color:black'>LATITUDE</span></p>
  </td>
  <td width=307 style='width:230.3pt;border-top:none;border-left:none;
  border-bottom:solid windowtext 1.0pt;border-right:solid windowtext 1.0pt;
  padding:0in 5.4pt 0in 5.4pt;height:15.05pt'>
  <p class=MsoNormal style='margin-bottom:0in;line-height:normal'><span
  style='color:black'>LATITUDE IN DECIMAL DEGREES FOR THE NOTED DATUM</span></p>
  </td>
 </tr>
 <tr style='height:15.05pt'>
  <td width=148 style='width:110.8pt;border:solid windowtext 1.0pt;border-top:
  none;padding:0in 5.4pt 0in 5.4pt;height:15.05pt'>
  <p class=MsoNormal style='margin-bottom:0in;line-height:normal'><span
  style='color:black'>LONGITUDE</span></p>
  </td>
  <td width=175 style='width:131.15pt;border-top:none;border-left:none;
  border-bottom:solid windowtext 1.0pt;border-right:solid windowtext 1.0pt;
  padding:0in 5.4pt 0in 5.4pt;height:15.05pt'>
  <p class=MsoNormal style='margin-bottom:0in;line-height:normal'><span
  style='color:black'>LONGITUDE</span></p>
  </td>
  <td width=307 style='width:230.3pt;border-top:none;border-left:none;
  border-bottom:solid windowtext 1.0pt;border-right:solid windowtext 1.0pt;
  padding:0in 5.4pt 0in 5.4pt;height:15.05pt'>
  <p class=MsoNormal style='margin-bottom:0in;line-height:normal'><span
  style='color:black'>LONGITUDE IN DECIMAL DEGREES FOR THE NOTED DATUM</span></p>
  </td>
 </tr>
 <tr style='height:15.05pt'>
  <td width=148 style='width:110.8pt;border:solid windowtext 1.0pt;border-top:
  none;padding:0in 5.4pt 0in 5.4pt;height:15.05pt'>
  <p class=MsoNormal style='margin-bottom:0in;line-height:normal'><span
  style='color:black'>METHOD DETECTION LIMIT</span></p>
  </td>
  <td width=175 style='width:131.15pt;border-top:none;border-left:none;
  border-bottom:solid windowtext 1.0pt;border-right:solid windowtext 1.0pt;
  padding:0in 5.4pt 0in 5.4pt;height:15.05pt'>
  <p class=MsoNormal style='margin-bottom:0in;line-height:normal'><span
  style='color:black'>MDL_LDM</span></p>
  </td>
  <td width=307 style='width:230.3pt;border-top:none;border-left:none;
  border-bottom:solid windowtext 1.0pt;border-right:solid windowtext 1.0pt;
  padding:0in 5.4pt 0in 5.4pt;height:15.05pt'>
  <p class=MsoNormal style='margin-bottom:0in;line-height:normal'><span
  style='color:black'>METHOD DETECTION LIMIT REPORTED BY THE LABORATORY FOR THE
  NOTED METHOD</span></p>
  </td>
 </tr>
 <tr style='height:15.05pt'>
  <td width=148 style='width:110.8pt;border:solid windowtext 1.0pt;border-top:
  none;padding:0in 5.4pt 0in 5.4pt;height:15.05pt'>
  <p class=MsoNormal style='margin-bottom:0in;line-height:normal'><span
  style='color:black'>METHOD CODE</span></p>
  </td>
  <td width=175 style='width:131.15pt;border-top:none;border-left:none;
  border-bottom:solid windowtext 1.0pt;border-right:solid windowtext 1.0pt;
  padding:0in 5.4pt 0in 5.4pt;height:15.05pt'>
  <p class=MsoNormal style='margin-bottom:0in;line-height:normal'><span
  style='color:black'>METHOD_CODE</span></p>
  </td>
  <td width=307 style='width:230.3pt;border-top:none;border-left:none;
  border-bottom:solid windowtext 1.0pt;border-right:solid windowtext 1.0pt;
  padding:0in 5.4pt 0in 5.4pt;height:15.05pt'>
  <p class=MsoNormal style='margin-bottom:0in;line-height:normal'><span
  style='color:black'>NUMERIC ANALYTICAL METHOD CODE FROM THE NATIONAL VMV
  DICTIONARY</span></p>
  </td>
 </tr>
 <tr style='height:30.15pt'>
  <td width=148 style='width:110.8pt;border:solid windowtext 1.0pt;border-top:
  none;padding:0in 5.4pt 0in 5.4pt;height:30.15pt'>
  <p class=MsoNormal style='margin-bottom:0in;line-height:normal'><span
  style='color:black'>SHORT METHOD TITLE</span></p>
  </td>
  <td width=175 style='width:131.15pt;border-top:none;border-left:none;
  border-bottom:solid windowtext 1.0pt;border-right:solid windowtext 1.0pt;
  padding:0in 5.4pt 0in 5.4pt;height:30.15pt'>
  <p class=MsoNormal style='margin-bottom:0in;line-height:normal'><span
  style='color:black'>METHOD_TITLE</span></p>
  </td>
  <td width=307 style='width:230.3pt;border-top:none;border-left:none;
  border-bottom:solid windowtext 1.0pt;border-right:solid windowtext 1.0pt;
  padding:0in 5.4pt 0in 5.4pt;height:30.15pt'>
  <p class=MsoNormal style='margin-bottom:0in;line-height:normal'><span
  style='color:black'>SHORT METHOD TITLE FROM THE NATIONAL VMV DICTIONARY. 
  FULL METHOD DESCRIPTIONS AVAILABLE UPON REQUEST AT
  EC.MSQEINFORMATION-WQMSINFORMATION.EC@CANADA.CA</span></p>
  </td>
 </tr>
 <tr style='height:15.05pt'>
  <td width=148 style='width:110.8pt;border:solid windowtext 1.0pt;border-top:
  none;padding:0in 5.4pt 0in 5.4pt;height:15.05pt'>
  <p class=MsoNormal style='margin-bottom:0in;line-height:normal'><span
  style='color:black'>OCEAN DRAINAGE AREA</span></p>
  </td>
  <td width=175 style='width:131.15pt;border-top:none;border-left:none;
  border-bottom:solid windowtext 1.0pt;border-right:solid windowtext 1.0pt;
  padding:0in 5.4pt 0in 5.4pt;height:15.05pt'>
  <p class=MsoNormal style='margin-bottom:0in;line-height:normal'><span
  style='color:black'>OCEANDA</span></p>
  </td>
  <td width=307 style='width:230.3pt;border-top:none;border-left:none;
  border-bottom:solid windowtext 1.0pt;border-right:solid windowtext 1.0pt;
  padding:0in 5.4pt 0in 5.4pt;height:15.05pt'>
  <p class=MsoNormal style='margin-bottom:0in;line-height:normal'><span
  style='color:black'>OCEAN DRAINAGE AREA THAT MONITORING SITE IS LOCATED IN </span></p>
  </td>
 </tr>
 <tr style='height:15.05pt'>
  <td width=148 style='width:110.8pt;border:solid windowtext 1.0pt;border-top:
  none;padding:0in 5.4pt 0in 5.4pt;height:15.05pt'>
  <p class=MsoNormal style='margin-bottom:0in;line-height:normal'><span
  style='color:black'>PEARSE DRAINAGE AREA</span></p>
  </td>
  <td width=175 style='width:131.15pt;border-top:none;border-left:none;
  border-bottom:solid windowtext 1.0pt;border-right:solid windowtext 1.0pt;
  padding:0in 5.4pt 0in 5.4pt;height:15.05pt'>
  <p class=MsoNormal style='margin-bottom:0in;line-height:normal'><span
  style='color:black'>PEARSEDA</span></p>
  </td>
  <td width=307 style='width:230.3pt;border-top:none;border-left:none;
  border-bottom:solid windowtext 1.0pt;border-right:solid windowtext 1.0pt;
  padding:0in 5.4pt 0in 5.4pt;height:15.05pt'>
  <p class=MsoNormal style='margin-bottom:0in;line-height:normal'><span
  style='color:black'>PEARSE DRAINAGE AREA THAT MONITORING SITE IS LOCATED IN </span></p>
  </td>
 </tr>
 <tr style='height:15.05pt'>
  <td width=148 style='width:110.8pt;border:solid windowtext 1.0pt;border-top:
  none;padding:0in 5.4pt 0in 5.4pt;height:15.05pt'>
  <p class=MsoNormal style='margin-bottom:0in;line-height:normal'><span
  style='color:black'>PROVINCE/TERRITORY</span></p>
  </td>
  <td width=175 style='width:131.15pt;border-top:none;border-left:none;
  border-bottom:solid windowtext 1.0pt;border-right:solid windowtext 1.0pt;
  padding:0in 5.4pt 0in 5.4pt;height:15.05pt'>
  <p class=MsoNormal style='margin-bottom:0in;line-height:normal'><span
  style='color:black'>PROV_TERR</span></p>
  </td>
  <td width=307 style='width:230.3pt;border-top:none;border-left:none;
  border-bottom:solid windowtext 1.0pt;border-right:solid windowtext 1.0pt;
  padding:0in 5.4pt 0in 5.4pt;height:15.05pt'>
  <p class=MsoNormal style='margin-bottom:0in;line-height:normal'><span
  style='color:black'>PROVINCE OR TERRITORY THAT MONITORING SITE IS LOCATED IN</span></p>
  </td>
 </tr>
 <tr style='height:15.05pt'>
  <td width=148 style='width:110.8pt;border:solid windowtext 1.0pt;border-top:
  none;padding:0in 5.4pt 0in 5.4pt;height:15.05pt'>
  <p class=MsoNormal style='margin-bottom:0in;line-height:normal'><span
  style='color:black'>SAMPLE IDENTIFIER</span></p>
  </td>
  <td width=175 style='width:131.15pt;border-top:none;border-left:none;
  border-bottom:solid windowtext 1.0pt;border-right:solid windowtext 1.0pt;
  padding:0in 5.4pt 0in 5.4pt;height:15.05pt'>
  <p class=MsoNormal style='margin-bottom:0in;line-height:normal'><span
  style='color:black'>SAMPLE_ID_ÉCHANTILLON</span></p>
  </td>
  <td width=307 style='width:230.3pt;border-top:none;border-left:none;
  border-bottom:solid windowtext 1.0pt;border-right:solid windowtext 1.0pt;
  padding:0in 5.4pt 0in 5.4pt;height:15.05pt'>
  <p class=MsoNormal style='margin-bottom:0in;line-height:normal'><span
  style='color:black'>UNIQUE SAMPLE IDENTIFIER FROM MONITORING PROGRAM</span></p>
  </td>
 </tr>
 <tr style='height:45.25pt'>
  <td width=148 style='width:110.8pt;border:solid windowtext 1.0pt;border-top:
  none;padding:0in 5.4pt 0in 5.4pt;height:45.25pt'>
  <p class=MsoNormal style='margin-bottom:0in;line-height:normal'><span
  style='color:black'>SAMPLE DETECTION LIMIT</span></p>
  </td>
  <td width=175 style='width:131.15pt;border-top:none;border-left:none;
  border-bottom:solid windowtext 1.0pt;border-right:solid windowtext 1.0pt;
  padding:0in 5.4pt 0in 5.4pt;height:45.25pt'>
  <p class=MsoNormal style='margin-bottom:0in;line-height:normal'><span
  style='color:black'>SDL_LDE</span></p>
  </td>
  <td width=307 style='width:230.3pt;border-top:none;border-left:none;
  border-bottom:solid windowtext 1.0pt;border-right:solid windowtext 1.0pt;
  padding:0in 5.4pt 0in 5.4pt;height:45.25pt'>
  <p class=MsoNormal style='margin-bottom:0in;line-height:normal'><span
  style='color:black'>SAMPLE DETECTION LIMIT REPORTED BY THE LABORATORY FOR THE
  SPECIFIC ANALYIS OF THE REPORTED MEASUREMENT.  ELEVATED SAMPLE DETECTION
  LIMIT ABOVE METHOD DETECTION LIMITS MAY INDICATE DILUTION, MATRIX
  INTERFERENCE OR OTHER ISSUES WITH THE SPECIFIC ANALYSIS.</span></p>
  </td>
 </tr>
 <tr style='height:30.15pt'>
  <td width=148 style='width:110.8pt;border:solid windowtext 1.0pt;border-top:
  none;padding:0in 5.4pt 0in 5.4pt;height:30.15pt'>
  <p class=MsoNormal style='margin-bottom:0in;line-height:normal'><span
  style='color:black'>SITE DESCRIPTION</span></p>
  </td>
  <td width=175 style='width:131.15pt;border-top:none;border-left:none;
  border-bottom:solid windowtext 1.0pt;border-right:solid windowtext 1.0pt;
  padding:0in 5.4pt 0in 5.4pt;height:30.15pt'>
  <p class=MsoNormal style='margin-bottom:0in;line-height:normal'><span
  style='color:black'>SITE_DESC</span></p>
  </td>
  <td width=307 style='width:230.3pt;border-top:none;border-left:none;
  border-bottom:solid windowtext 1.0pt;border-right:solid windowtext 1.0pt;
  padding:0in 5.4pt 0in 5.4pt;height:30.15pt'>
  <p class=MsoNormal style='margin-bottom:0in;line-height:normal'><span
  style='color:black'>SITE DESCRIPTION THAT MAY INCLUDE SPECIFIC SAMPLING
  LOCATION, RATIONALE FOR MONITORING LOCATION (E.G. REFERENCE,
  UPSTREAM/DOWNSTREAM, ETC.), AND LOCAL LAND-USE INFORMATION. </span></p>
  </td>
 </tr>
 <tr style='height:15.05pt'>
  <td width=148 style='width:110.8pt;border:solid windowtext 1.0pt;border-top:
  none;padding:0in 5.4pt 0in 5.4pt;height:15.05pt'>
  <p class=MsoNormal style='margin-bottom:0in;line-height:normal'><span
  style='color:black'>SITE NAME</span></p>
  </td>
  <td width=175 style='width:131.15pt;border-top:none;border-left:none;
  border-bottom:solid windowtext 1.0pt;border-right:solid windowtext 1.0pt;
  padding:0in 5.4pt 0in 5.4pt;height:15.05pt'>
  <p class=MsoNormal style='margin-bottom:0in;line-height:normal'><span
  style='color:black'>SITE_NAME</span></p>
  </td>
  <td width=307 style='width:230.3pt;border-top:none;border-left:none;
  border-bottom:solid windowtext 1.0pt;border-right:solid windowtext 1.0pt;
  padding:0in 5.4pt 0in 5.4pt;height:15.05pt'>
  <p class=MsoNormal style='margin-bottom:0in;line-height:normal'><span
  style='color:black'>FULL SITE NAME FROM MONITORING PROGRAM</span></p>
  </td>
 </tr>
 <tr style='height:15.05pt'>
  <td width=148 style='width:110.8pt;border:solid windowtext 1.0pt;border-top:
  none;padding:0in 5.4pt 0in 5.4pt;height:15.05pt'>
  <p class=MsoNormal style='margin-bottom:0in;line-height:normal'><span
  style='color:black'>SITE NUMBER</span></p>
  </td>
  <td width=175 style='width:131.15pt;border-top:none;border-left:none;
  border-bottom:solid windowtext 1.0pt;border-right:solid windowtext 1.0pt;
  padding:0in 5.4pt 0in 5.4pt;height:15.05pt'>
  <p class=MsoNormal style='margin-bottom:0in;line-height:normal'><span
  style='color:black'>SITE_NO</span></p>
  </td>
  <td width=307 style='width:230.3pt;border-top:none;border-left:none;
  border-bottom:solid windowtext 1.0pt;border-right:solid windowtext 1.0pt;
  padding:0in 5.4pt 0in 5.4pt;height:15.05pt'>
  <p class=MsoNormal style='margin-bottom:0in;line-height:normal'><span
  style='color:black'>UNIQUE SITE NUMBER/IDENTIFICATION FROM MONITORING PROGRAM</span></p>
  </td>
 </tr>
 <tr style='height:15.05pt'>
  <td width=148 style='width:110.8pt;border:solid windowtext 1.0pt;border-top:
  none;padding:0in 5.4pt 0in 5.4pt;height:15.05pt'>
  <p class=MsoNormal style='margin-bottom:0in;line-height:normal'><span
  style='color:black'>SITE TYPE</span></p>
  </td>
  <td width=175 style='width:131.15pt;border-top:none;border-left:none;
  border-bottom:solid windowtext 1.0pt;border-right:solid windowtext 1.0pt;
  padding:0in 5.4pt 0in 5.4pt;height:15.05pt'>
  <p class=MsoNormal style='margin-bottom:0in;line-height:normal'><span
  style='color:black'>SITE_TYPE</span></p>
  </td>
  <td width=307 style='width:230.3pt;border-top:none;border-left:none;
  border-bottom:solid windowtext 1.0pt;border-right:solid windowtext 1.0pt;
  padding:0in 5.4pt 0in 5.4pt;height:15.05pt'>
  <p class=MsoNormal style='margin-bottom:0in;line-height:normal'><span
  style='color:black'>SAMPLE SITE TYPE (E.G. RIVER, LAKE, ETC.)</span></p>
  </td>
 </tr>
 <tr style='height:15.05pt'>
  <td width=148 style='width:110.8pt;border:solid windowtext 1.0pt;border-top:
  none;padding:0in 5.4pt 0in 5.4pt;height:15.05pt'>
  <p class=MsoNormal style='margin-bottom:0in;line-height:normal'><span
  style='color:black'>VALIDATION STATUS</span></p>
  </td>
  <td width=175 style='width:131.15pt;border-top:none;border-left:none;
  border-bottom:solid windowtext 1.0pt;border-right:solid windowtext 1.0pt;
  padding:0in 5.4pt 0in 5.4pt;height:15.05pt'>
  <p class=MsoNormal style='margin-bottom:0in;line-height:normal'><span
  style='color:black'>STATUS_STATUT</span></p>
  </td>
  <td width=307 style='width:230.3pt;border-top:none;border-left:none;
  border-bottom:solid windowtext 1.0pt;border-right:solid windowtext 1.0pt;
  padding:0in 5.4pt 0in 5.4pt;height:15.05pt'>
  <p class=MsoNormal style='margin-bottom:0in;line-height:normal'><span
  style='color:black'>LEVEL OF VALIDATION (P-PROVISIONAL, V-VALIDATED)</span></p>
  </td>
 </tr>
 <tr style='height:15.05pt'>
  <td width=148 style='width:110.8pt;border:solid windowtext 1.0pt;border-top:
  none;padding:0in 5.4pt 0in 5.4pt;height:15.05pt'>
  <p class=MsoNormal style='margin-bottom:0in;line-height:normal'><span
  style='color:black'>UNIT NAME</span></p>
  </td>
  <td width=175 style='width:131.15pt;border-top:none;border-left:none;
  border-bottom:solid windowtext 1.0pt;border-right:solid windowtext 1.0pt;
  padding:0in 5.4pt 0in 5.4pt;height:15.05pt'>
  <p class=MsoNormal style='margin-bottom:0in;line-height:normal'><span
  style='color:black'>UNIT_NAME</span></p>
  </td>
  <td width=307 style='width:230.3pt;border-top:none;border-left:none;
  border-bottom:solid windowtext 1.0pt;border-right:solid windowtext 1.0pt;
  padding:0in 5.4pt 0in 5.4pt;height:15.05pt'>
  <p class=MsoNormal style='margin-bottom:0in;line-height:normal'><span
  style='color:black'>FULL MEASUREMENT UNIT NAME FROM NATIONAL VMV DICTIONARY</span></p>
  </td>
 </tr>
 <tr style='height:15.05pt'>
  <td width=148 style='width:110.8pt;border:solid windowtext 1.0pt;border-top:
  none;padding:0in 5.4pt 0in 5.4pt;height:15.05pt'>
  <p class=MsoNormal style='margin-bottom:0in;line-height:normal'><span
  style='color:black'>UNIT</span></p>
  </td>
  <td width=175 style='width:131.15pt;border-top:none;border-left:none;
  border-bottom:solid windowtext 1.0pt;border-right:solid windowtext 1.0pt;
  padding:0in 5.4pt 0in 5.4pt;height:15.05pt'>
  <p class=MsoNormal style='margin-bottom:0in;line-height:normal'><span
  style='color:black'>UNIT_UNITÉ</span></p>
  </td>
  <td width=307 style='width:230.3pt;border-top:none;border-left:none;
  border-bottom:solid windowtext 1.0pt;border-right:solid windowtext 1.0pt;
  padding:0in 5.4pt 0in 5.4pt;height:15.05pt'>
  <p class=MsoNormal style='margin-bottom:0in;line-height:normal'><span
  style='color:black'>MEASUREMENT UNIT ABBREVIATION FROM NATIONAL VMV
  DICTIONARY</span></p>
  </td>
 </tr>
 <tr style='height:15.05pt'>
  <td width=148 style='width:110.8pt;border:solid windowtext 1.0pt;border-top:
  none;padding:0in 5.4pt 0in 5.4pt;height:15.05pt'>
  <p class=MsoNormal style='margin-bottom:0in;line-height:normal'><span
  style='color:black'>MEASUREMENT VALUE</span></p>
  </td>
  <td width=175 style='width:131.15pt;border-top:none;border-left:none;
  border-bottom:solid windowtext 1.0pt;border-right:solid windowtext 1.0pt;
  padding:0in 5.4pt 0in 5.4pt;height:15.05pt'>
  <p class=MsoNormal style='margin-bottom:0in;line-height:normal'><span
  style='color:black'>VALUE_VALEUR</span></p>
  </td>
  <td width=307 style='width:230.3pt;border-top:none;border-left:none;
  border-bottom:solid windowtext 1.0pt;border-right:solid windowtext 1.0pt;
  padding:0in 5.4pt 0in 5.4pt;height:15.05pt'>
  <p class=MsoNormal style='margin-bottom:0in;line-height:normal'><span
  style='color:black'>MEASUREMENT VALUE OR CONCENTRATION</span></p>
  </td>
 </tr>
 <tr style='height:15.05pt'>
  <td width=148 style='width:110.8pt;border:solid windowtext 1.0pt;border-top:
  none;padding:0in 5.4pt 0in 5.4pt;height:15.05pt'>
  <p class=MsoNormal style='margin-bottom:0in;line-height:normal'><span
  style='color:black'>VARIABLE NAME</span></p>
  </td>
  <td width=175 style='width:131.15pt;border-top:none;border-left:none;
  border-bottom:solid windowtext 1.0pt;border-right:solid windowtext 1.0pt;
  padding:0in 5.4pt 0in 5.4pt;height:15.05pt'>
  <p class=MsoNormal style='margin-bottom:0in;line-height:normal'><span
  style='color:black'>VARIABLE</span></p>
  </td>
  <td width=307 style='width:230.3pt;border-top:none;border-left:none;
  border-bottom:solid windowtext 1.0pt;border-right:solid windowtext 1.0pt;
  padding:0in 5.4pt 0in 5.4pt;height:15.05pt'>
  <p class=MsoNormal style='margin-bottom:0in;line-height:normal'><span
  style='color:black'>VARIABLE NAME FROM NATIONAL VMV DICTIONARY</span></p>
  </td>
 </tr>
 <tr style='height:15.05pt'>
  <td width=148 style='width:110.8pt;border:solid windowtext 1.0pt;border-top:
  none;padding:0in 5.4pt 0in 5.4pt;height:15.05pt'>
  <p class=MsoNormal style='margin-bottom:0in;line-height:normal'><span
  style='color:black'>VARIABLE CODE</span></p>
  </td>
  <td width=175 style='width:131.15pt;border-top:none;border-left:none;
  border-bottom:solid windowtext 1.0pt;border-right:solid windowtext 1.0pt;
  padding:0in 5.4pt 0in 5.4pt;height:15.05pt'>
  <p class=MsoNormal style='margin-bottom:0in;line-height:normal'><span
  style='color:black'>VARIABLE_CODE</span></p>
  </td>
  <td width=307 style='width:230.3pt;border-top:none;border-left:none;
  border-bottom:solid windowtext 1.0pt;border-right:solid windowtext 1.0pt;
  padding:0in 5.4pt 0in 5.4pt;height:15.05pt'>
  <p class=MsoNormal style='margin-bottom:0in;line-height:normal'><span
  style='color:black'>NUMERIC VARIABLE CODE FROM NATIONAL VMV DICTIONARY</span></p>
  </td>
 </tr>
 <tr style='height:15.05pt'>
  <td width=148 style='width:110.8pt;border:solid windowtext 1.0pt;border-top:
  none;padding:0in 5.4pt 0in 5.4pt;height:15.05pt'>
  <p class=MsoNormal style='margin-bottom:0in;line-height:normal'><span
  style='color:black'>VARIABLE TYPE</span></p>
  </td>
  <td width=175 style='width:131.15pt;border-top:none;border-left:none;
  border-bottom:solid windowtext 1.0pt;border-right:solid windowtext 1.0pt;
  padding:0in 5.4pt 0in 5.4pt;height:15.05pt'>
  <p class=MsoNormal style='margin-bottom:0in;line-height:normal'><span
  style='color:black'>VARIABLE_TYPE</span></p>
  </td>
  <td width=307 style='width:230.3pt;border-top:none;border-left:none;
  border-bottom:solid windowtext 1.0pt;border-right:solid windowtext 1.0pt;
  padding:0in 5.4pt 0in 5.4pt;height:15.05pt'>
  <p class=MsoNormal style='margin-bottom:0in;line-height:normal'><span
  style='color:black'>VARIABLE TYPE FROM NATIONAL VMV DICTIONARY</span></p>
  </td>
 </tr>
 <tr style='height:15.05pt'>
  <td width=148 style='width:110.8pt;border:solid windowtext 1.0pt;border-top:
  none;padding:0in 5.4pt 0in 5.4pt;height:15.05pt'>
  <p class=MsoNormal style='margin-bottom:0in;line-height:normal'><span
  style='color:black'>VMV CODE</span></p>
  </td>
  <td width=175 style='width:131.15pt;border-top:none;border-left:none;
  border-bottom:solid windowtext 1.0pt;border-right:solid windowtext 1.0pt;
  padding:0in 5.4pt 0in 5.4pt;height:15.05pt'>
  <p class=MsoNormal style='margin-bottom:0in;line-height:normal'><span
  style='color:black'>VMV_CODE</span></p>
  </td>
  <td width=307 style='width:230.3pt;border-top:none;border-left:none;
  border-bottom:solid windowtext 1.0pt;border-right:solid windowtext 1.0pt;
  padding:0in 5.4pt 0in 5.4pt;height:15.05pt'>
  <p class=MsoNormal style='margin-bottom:0in;line-height:normal'><span
  style='color:black'>NUMERIC VALID METHOD VARIABLE (VMV) CODE FROM NATIONAL
  VMV DICTIONARY</span></p>
  </td>
 </tr>
</table>

<p class=MsoNormal>&nbsp;</p>

</div>
</body>
</html>

### Exploratory Data Analysis

### Statistical Analysis

### Machine Learning

### Findings

### Next Steps

### Conclusion and Call to Action
