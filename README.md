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

<div style="position: relative; padding-bottom: 74.68879668049793%; height: 0;"><iframe src="https://www.loom.com/embed/d62eb79370654ff8a21893108458934c?sid=9fb44396-5fab-4a34-a58d-a51999a29c15" frameborder="0" webkitallowfullscreen mozallowfullscreen allowfullscreen style="position: absolute; top: 0; left: 0; width: 100%; height: 100%;"></iframe></div>
  	![image](https://github.com/xavieruxchamp/Water-Access-Analysis/assets/44354258/4e1baca2-59b8-485e-bea8-0c5bd6e37c9c)

### Data cleaning
So far I have completed: Data collection, preliminary visualization, and initial Exploratory Data Analysis (EDA). In this process I have noticed certain limitations could hinder machine learning work. Namely, the datasets are focused on chemicals. I will also be looking into data quality issues stemming from the methods use (i.e. sample data collected at multiple sites by multiple parties and devices).

#### Data Dictionary
<table>
<thead>
  <tr>
    <th>Variable</th>
    <th>Column Name</th>
    <th>Description</th>
  </tr>
</thead>
<tbody>
  <tr>
    <td>SAMPLE DATE AND TIME</td>
    <td>DATE_TIME_HEURE</td>
    <td>SAMPLE DATE AND TIME IN DD/MM/YYYY HH:MM FORMAT USING LOCAL TIME ZONE</td>
  </tr>
  <tr>
    <td>DATUM</td>
    <td>DATUM</td>
    <td>DATUM USED FOR LATITUDE AND LONGITUDE</td>
  </tr>
  <tr>
    <td>MEASUREMENT FLAG</td>
    <td>FLAG_MARQUEUR</td>
    <td>FLAG APPLICABLE TO MEASUREMENT VALUE (&lt;-LESS THAN, T-TRACE VALUE REPORTED BELOW DETECTION LIMIT BY LABORATORY)</td>
  </tr>
  <tr>
    <td>LATITUDE</td>
    <td>LATITUDE</td>
    <td>LATITUDE IN DECIMAL DEGREES FOR THE NOTED DATUM</td>
  </tr>
  <tr>
    <td>LONGITUDE</td>
    <td>LONGITUDE</td>
    <td>LONGITUDE IN DECIMAL DEGREES FOR THE NOTED DATUM</td>
  </tr>
  <tr>
    <td>METHOD DETECTION LIMIT</td>
    <td>MDL_LDM</td>
    <td>METHOD DETECTION LIMIT REPORTED BY THE LABORATORY FOR THE NOTED METHOD</td>
  </tr>
  <tr>
    <td>METHOD CODE</td>
    <td>METHOD_CODE</td>
    <td>NUMERIC ANALYTICAL METHOD CODE FROM THE NATIONAL VMV DICTIONARY</td>
  </tr>
  <tr>
    <td>SHORT METHOD TITLE</td>
    <td>METHOD_TITLE</td>
    <td>SHORT METHOD TITLE FROM THE NATIONAL VMV DICTIONARY.  FULL METHOD DESCRIPTIONS AVAILABLE UPON REQUEST AT EC.MSQEINFORMATION-WQMSINFORMATION.EC@CANADA.CA</td>
  </tr>
  <tr>
    <td>OCEAN DRAINAGE AREA</td>
    <td>OCEANDA</td>
    <td>OCEAN DRAINAGE AREA THAT MONITORING SITE IS LOCATED IN</td>
  </tr>
  <tr>
    <td>PEARSE DRAINAGE AREA</td>
    <td>PEARSEDA</td>
    <td>PEARSE DRAINAGE AREA THAT MONITORING SITE IS LOCATED IN</td>
  </tr>
  <tr>
    <td>PROVINCE/TERRITORY</td>
    <td>PROV_TERR</td>
    <td>PROVINCE OR TERRITORY THAT MONITORING SITE IS LOCATED IN</td>
  </tr>
  <tr>
    <td>SAMPLE IDENTIFIER</td>
    <td>SAMPLE_ID_ÉCHANTILLON</td>
    <td>UNIQUE SAMPLE IDENTIFIER FROM MONITORING PROGRAM</td>
  </tr>
  <tr>
    <td>SAMPLE DETECTION LIMIT</td>
    <td>SDL_LDE</td>
    <td>SAMPLE DETECTION LIMIT REPORTED BY THE LABORATORY FOR THE SPECIFIC ANALYIS OF THE REPORTED MEASUREMENT.  ELEVATED SAMPLE DETECTION LIMIT ABOVE METHOD DETECTION LIMITS MAY INDICATE DILUTION, MATRIX INTERFERENCE OR OTHER ISSUES WITH THE SPECIFIC ANALYSIS.</td>
  </tr>
  <tr>
    <td>SITE DESCRIPTION</td>
    <td>SITE_DESC</td>
    <td>SITE DESCRIPTION THAT MAY INCLUDE SPECIFIC SAMPLING LOCATION, RATIONALE FOR MONITORING LOCATION (E.G. REFERENCE, UPSTREAM/DOWNSTREAM, ETC.), AND LOCAL LAND-USE INFORMATION.</td>
  </tr>
  <tr>
    <td>SITE NAME</td>
    <td>SITE_NAME</td>
    <td>FULL SITE NAME FROM MONITORING PROGRAM</td>
  </tr>
  <tr>
    <td>SITE NUMBER</td>
    <td>SITE_NO</td>
    <td>UNIQUE SITE NUMBER/IDENTIFICATION FROM MONITORING PROGRAM</td>
  </tr>
  <tr>
    <td>SITE TYPE</td>
    <td>SITE_TYPE</td>
    <td>SAMPLE SITE TYPE (E.G. RIVER, LAKE, ETC.)</td>
  </tr>
  <tr>
    <td>VALIDATION STATUS</td>
    <td>STATUS_STATUT</td>
    <td>LEVEL OF VALIDATION (P-PROVISIONAL, V-VALIDATED)</td>
  </tr>
  <tr>
    <td>UNIT NAME</td>
    <td>UNIT_NAME</td>
    <td>FULL MEASUREMENT UNIT NAME FROM NATIONAL VMV DICTIONARY</td>
  </tr>
  <tr>
    <td>UNIT</td>
    <td>UNIT_UNITÉ</td>
    <td>MEASUREMENT UNIT ABBREVIATION FROM NATIONAL VMV DICTIONARY</td>
  </tr>
  <tr>
    <td>MEASUREMENT VALUE</td>
    <td>VALUE_VALEUR</td>
    <td>MEASUREMENT VALUE OR CONCENTRATION</td>
  </tr>
  <tr>
    <td>VARIABLE NAME</td>
    <td>VARIABLE</td>
    <td>VARIABLE NAME FROM NATIONAL VMV DICTIONARY</td>
  </tr>
  <tr>
    <td>VARIABLE CODE</td>
    <td>VARIABLE_CODE</td>
    <td>NUMERIC VARIABLE CODE FROM NATIONAL VMV DICTIONARY</td>
  </tr>
  <tr>
    <td>VARIABLE TYPE</td>
    <td>VARIABLE_TYPE</td>
    <td>VARIABLE TYPE FROM NATIONAL VMV DICTIONARY</td>
  </tr>
  <tr>
    <td>VMV CODE</td>
    <td>VMV_CODE</td>
    <td>NUMERIC VALID METHOD VARIABLE (VMV) CODE FROM NATIONAL VMV DICTIONARY</td>
  </tr>
</tbody>
</table>

### Exploratory Data Analysis
I spent quite a bit of time on this task, becoming familiar with the dataset. This is a large dataset, spanning 2 decades, with data fron locations all over Canada.

### Statistical Analysis
I identified the Target variable and performed some basic statistical analysis. As a result, I selected Linear Regression as my baseline model.

### Machine Learning
Over the next few days, I will work on modelling and so far I have selected: Linear Regression, Randon Forest, and Adaboost.

### Findings
There are issues with my dataset and I need to resolve them before moving to the modelling phase.

### Next Steps
Feature enginnering, ML Pipeline, and Dashboard.

### Conclusion and Call to Action
TBD/In Progress
