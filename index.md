---
title       : An overview on tourism data in Spain
subtitle    : 
author      : Martin Pons
job         : 
framework   : io2012        # {io2012, html5slides, shower, dzslides, ...}
highlighter : highlight.js  # {highlight.js, prettify, highlight}
hitheme     : tomorrow      # 
widgets     : [bootstrap, quiz, shiny, interactive]            # {mathjax, quiz, bootstrap, shiny, interactive}
mode        : selfcontained # {standalone, draft}
knit        : slidify::knit2slides
ext_widgets: {rCharts: [libraries/morris]}
---

## The Motivation

- One Of the main sources for getting toursim related data in Spain is the Touristic Studies Institute (IET).
- The data is presented in the form of time series tables
- Students from tourism degrees in Spain could get a better global vision if this data were displayed in animated charts

<img src="assets/img/Captura.png" height="350", width="400"/>

--- .class #id 

## The Process

- Ann App was developed using slidify package in R software
- The original app gets the data direclty from the (IET). However, for the course project this data is first downloaded and then readed locally.
- Four time series From the IET were used for the app:
  1. Total number of visitors in Spain by tipology (Tourists and Excursionists)
  2. Total number of tourists in Spain by region
  3. Average days spent in Spain by tourists from the main tourists provider countries
  4. Mean daily expenditures by tourist form the main tourist provider contries
- A preprocessing, cleaning and formatting of the data was carried out in order to display the desired charts
- The charts were built using rCharts an GoogleVis packages from R

--- .class #id 

## The App

- Three charts are displayed in the app:
  1. Total number of visitors in Spain in differnent levels of aggregation
  2. Interannual growth rates in different regions in Spain
  3. An animated chart in time displaying the average number of days spent by international tourists from different countries in Spain vs. the main daily expenditures from tourist in these countries.
  
  
<img src="assets/img/Captura2.png" height="380", width="480"/>

--- .class #id 

## A Real Example

We display here one of the charts built using rCharts


```r
require(rCharts)
data<-read.csv("assets/inter.regions.csv")
m1<-mPlot(x=as.character("Date"), y="Catalonia", data=data, type="Line")
m1$print('chart1')
```


<div id = 'chart1' class = 'rChart morris'></div>
<script type='text/javascript'>
    var chartParams = {
 "element": "chart1",
"width":            800,
"height":            400,
"xkey": "Date",
"ykeys": [
 "Catalonia" 
],
"data": [
 {
 "Date": "2001-01-01",
"Andalusia":          0.056,
"Balearic.Islands":          0.024,
"Canary.Islands":          0.057,
"Catalonia":          0.349,
"Valencia":          0.173,
"Madrid":          0.161,
"Rest.of.regions":          0.103,
"Spain":          0.034 
},
{
 "Date": "2001-02-01",
"Andalusia":         -0.014,
"Balearic.Islands":          0.114,
"Canary.Islands":          0.042,
"Catalonia":          0.093,
"Valencia":          0.117,
"Madrid":           0.18,
"Rest.of.regions":          0.062,
"Spain":         -0.004 
},
{
 "Date": "2001-03-01",
"Andalusia":         -0.033,
"Balearic.Islands":          0.019,
"Canary.Islands":          0.057,
"Catalonia":          0.027,
"Valencia":          0.111,
"Madrid":          0.019,
"Rest.of.regions":          0.002,
"Spain":         -0.011 
},
{
 "Date": "2001-04-01",
"Andalusia":         -0.079,
"Balearic.Islands":         -0.076,
"Canary.Islands":         -0.026,
"Catalonia":          0.176,
"Valencia":          0.046,
"Madrid":         -0.033,
"Rest.of.regions":           0.03,
"Spain":          0.001 
},
{
 "Date": "2001-05-01",
"Andalusia":          0.063,
"Balearic.Islands":          0.021,
"Canary.Islands":          0.022,
"Catalonia":          0.174,
"Valencia":           0.13,
"Madrid":          0.099,
"Rest.of.regions":          0.032,
"Spain":         -0.027 
},
{
 "Date": "2001-06-01",
"Andalusia":          0.082,
"Balearic.Islands":          0.025,
"Canary.Islands":           0.05,
"Catalonia":          0.079,
"Valencia":          0.064,
"Madrid":           0.26,
"Rest.of.regions":          0.105,
"Spain":         -0.037 
},
{
 "Date": "2001-07-01",
"Andalusia":          0.153,
"Balearic.Islands":          -0.02,
"Canary.Islands":          0.014,
"Catalonia":          0.012,
"Valencia":         -0.025,
"Madrid":          0.377,
"Rest.of.regions":          0.148,
"Spain":         -0.072 
},
{
 "Date": "2001-08-01",
"Andalusia":          0.344,
"Balearic.Islands":          0.036,
"Canary.Islands":          0.032,
"Catalonia":          0.209,
"Valencia":         -0.056,
"Madrid":          0.189,
"Rest.of.regions":          0.137,
"Spain":         -0.061 
},
{
 "Date": "2001-09-01",
"Andalusia":          0.073,
"Balearic.Islands":          0.003,
"Canary.Islands":          0.006,
"Catalonia":         -0.002,
"Valencia":         -0.008,
"Madrid":           0.07,
"Rest.of.regions":          0.092,
"Spain":         -0.112 
},
{
 "Date": "2001-10-01",
"Andalusia":          0.065,
"Balearic.Islands":         -0.103,
"Canary.Islands":         -0.004,
"Catalonia":         -0.041,
"Valencia":          0.065,
"Madrid":         -0.203,
"Rest.of.regions":          0.048,
"Spain":          -0.06 
},
{
 "Date": "2001-11-01",
"Andalusia":          0.025,
"Balearic.Islands":         -0.075,
"Canary.Islands":         -0.029,
"Catalonia":          0.029,
"Valencia":          -0.02,
"Madrid":         -0.152,
"Rest.of.regions":          0.153,
"Spain":         -0.054 
},
{
 "Date": "2001-12-01",
"Andalusia":          0.127,
"Balearic.Islands":          0.015,
"Canary.Islands":          0.012,
"Catalonia":          0.109,
"Valencia":          0.057,
"Madrid":         -0.142,
"Rest.of.regions":          0.147,
"Spain":          -0.02 
},
{
 "Date": "2002-01-01",
"Andalusia":          0.128,
"Balearic.Islands":         -0.125,
"Canary.Islands":         -0.061,
"Catalonia":          0.108,
"Valencia":         -0.058,
"Madrid":         -0.083,
"Rest.of.regions":          0.017,
"Spain":          0.012 
},
{
 "Date": "2002-02-01",
"Andalusia":          0.173,
"Balearic.Islands":          -0.12,
"Canary.Islands":          0.012,
"Catalonia":          0.288,
"Valencia":           0.05,
"Madrid":          0.016,
"Rest.of.regions":          0.213,
"Spain":          0.084 
},
{
 "Date": "2002-03-01",
"Andalusia":          0.224,
"Balearic.Islands":          0.125,
"Canary.Islands":          0.032,
"Catalonia":          0.548,
"Valencia":          0.202,
"Madrid":         -0.043,
"Rest.of.regions":          0.351,
"Spain":           0.16 
},
{
 "Date": "2002-04-01",
"Andalusia":         -0.121,
"Balearic.Islands":         -0.282,
"Canary.Islands":         -0.124,
"Catalonia":         -0.115,
"Valencia":         -0.151,
"Madrid":         -0.135,
"Rest.of.regions":          0.073,
"Spain":         -0.008 
},
{
 "Date": "2002-05-01",
"Andalusia":          0.072,
"Balearic.Islands":         -0.057,
"Canary.Islands":         -0.039,
"Catalonia":          0.209,
"Valencia":          0.015,
"Madrid":         -0.165,
"Rest.of.regions":          0.101,
"Spain":          0.094 
},
{
 "Date": "2002-06-01",
"Andalusia":          0.006,
"Balearic.Islands":         -0.055,
"Canary.Islands":         -0.048,
"Catalonia":          0.128,
"Valencia":         -0.002,
"Madrid":              0,
"Rest.of.regions":          0.187,
"Spain":          0.049 
},
{
 "Date": "2002-07-01",
"Andalusia":         -0.076,
"Balearic.Islands":         -0.098,
"Canary.Islands":         -0.035,
"Catalonia":          0.143,
"Valencia":          0.013,
"Madrid":         -0.088,
"Rest.of.regions":           0.18,
"Spain":          0.039 
},
{
 "Date": "2002-08-01",
"Andalusia":         -0.062,
"Balearic.Islands":           0.02,
"Canary.Islands":          0.022,
"Catalonia":          0.344,
"Valencia":          0.363,
"Madrid":          0.024,
"Rest.of.regions":          0.259,
"Spain":          0.089 
},
{
 "Date": "2002-09-01",
"Andalusia":          0.005,
"Balearic.Islands":         -0.115,
"Canary.Islands":         -0.018,
"Catalonia":          0.009,
"Valencia":          0.025,
"Madrid":          0.058,
"Rest.of.regions":          0.192,
"Spain":           0.06 
},
{
 "Date": "2002-10-01",
"Andalusia":          0.076,
"Balearic.Islands":          -0.06,
"Canary.Islands":         -0.005,
"Catalonia":           0.16,
"Valencia":          0.135,
"Madrid":          0.228,
"Rest.of.regions":          0.334,
"Spain":          0.103 
},
{
 "Date": "2002-11-01",
"Andalusia":          0.018,
"Balearic.Islands":          0.028,
"Canary.Islands":          0.041,
"Catalonia":           0.25,
"Valencia":          0.184,
"Madrid":          0.098,
"Rest.of.regions":          0.008,
"Spain":          0.164 
},
{
 "Date": "2002-12-01",
"Andalusia":          0.017,
"Balearic.Islands":         -0.005,
"Canary.Islands":          0.015,
"Catalonia":         -0.035,
"Valencia":          0.081,
"Madrid":         -0.081,
"Rest.of.regions":          0.355,
"Spain":          0.068 
},
{
 "Date": "2003-01-01",
"Andalusia":          0.123,
"Balearic.Islands":          0.034,
"Canary.Islands":          0.076,
"Catalonia":          0.089,
"Valencia":          0.222,
"Madrid":         -0.135,
"Rest.of.regions":          0.324,
"Spain":          0.102 
},
{
 "Date": "2003-02-01",
"Andalusia":          0.031,
"Balearic.Islands":         -0.028,
"Canary.Islands":         -0.002,
"Catalonia":          0.148,
"Valencia":          0.034,
"Madrid":         -0.058,
"Rest.of.regions":          0.078,
"Spain":         -0.045 
},
{
 "Date": "2003-03-01",
"Andalusia":         -0.071,
"Balearic.Islands":         -0.235,
"Canary.Islands":         -0.041,
"Catalonia":         -0.086,
"Valencia":         -0.131,
"Madrid":         -0.214,
"Rest.of.regions":         -0.078,
"Spain":          0.057 
},
{
 "Date": "2003-04-01",
"Andalusia":          0.086,
"Balearic.Islands":          0.238,
"Canary.Islands":          0.151,
"Catalonia":          0.195,
"Valencia":          0.205,
"Madrid":         -0.008,
"Rest.of.regions":          0.087,
"Spain":           0.08 
},
{
 "Date": "2003-05-01",
"Andalusia":          0.129,
"Balearic.Islands":          0.015,
"Canary.Islands":          0.019,
"Catalonia":          0.003,
"Valencia":          0.146,
"Madrid":          0.012,
"Rest.of.regions":          0.169,
"Spain":          0.172 
},
{
 "Date": "2003-06-01",
"Andalusia":          0.055,
"Balearic.Islands":         -0.015,
"Canary.Islands":         -0.025,
"Catalonia":          0.043,
"Valencia":         -0.066,
"Madrid":         -0.035,
"Rest.of.regions":          0.065,
"Spain":          0.167 
},
{
 "Date": "2003-07-01",
"Andalusia":          0.043,
"Balearic.Islands":          0.008,
"Canary.Islands":         -0.021,
"Catalonia":          0.054,
"Valencia":          0.035,
"Madrid":          0.152,
"Rest.of.regions":         -0.063,
"Spain":          0.056 
},
{
 "Date": "2003-08-01",
"Andalusia":          0.039,
"Balearic.Islands":          0.032,
"Canary.Islands":         -0.036,
"Catalonia":         -0.165,
"Valencia":         -0.079,
"Madrid":         -0.001,
"Rest.of.regions":         -0.122,
"Spain":          0.059 
},
{
 "Date": "2003-09-01",
"Andalusia":              0,
"Balearic.Islands":         -0.059,
"Canary.Islands":         -0.059,
"Catalonia":          0.014,
"Valencia":           0.07,
"Madrid":         -0.025,
"Rest.of.regions":          0.045,
"Spain":          0.084 
},
{
 "Date": "2003-10-01",
"Andalusia":         -0.001,
"Balearic.Islands":          0.043,
"Canary.Islands":         -0.018,
"Catalonia":          -0.01,
"Valencia":          0.051,
"Madrid":          0.053,
"Rest.of.regions":          -0.06,
"Spain":          0.117 
},
{
 "Date": "2003-11-01",
"Andalusia":         -0.054,
"Balearic.Islands":          0.038,
"Canary.Islands":         -0.061,
"Catalonia":          0.034,
"Valencia":          0.037,
"Madrid":            0.1,
"Rest.of.regions":          0.047,
"Spain":           0.09 
},
{
 "Date": "2003-12-01",
"Andalusia":         -0.056,
"Balearic.Islands":          0.158,
"Canary.Islands":         -0.041,
"Catalonia":          0.249,
"Valencia":         -0.039,
"Madrid":          0.323,
"Rest.of.regions":         -0.067,
"Spain":          0.118 
},
{
 "Date": "2004-01-01",
"Andalusia":         -0.009,
"Balearic.Islands":          0.098,
"Canary.Islands":         -0.012,
"Catalonia":          0.207,
"Valencia":          0.041,
"Madrid":          0.385,
"Rest.of.regions":          0.069,
"Spain":          0.133 
},
{
 "Date": "2004-02-01",
"Andalusia":          0.063,
"Balearic.Islands":          0.067,
"Canary.Islands":           0.02,
"Catalonia":          0.282,
"Valencia":          0.086,
"Madrid":          0.144,
"Rest.of.regions":          0.094,
"Spain":          0.263 
},
{
 "Date": "2004-03-01",
"Andalusia":         -0.076,
"Balearic.Islands":         -0.034,
"Canary.Islands":         -0.081,
"Catalonia":          0.106,
"Valencia":         -0.017,
"Madrid":          0.226,
"Rest.of.regions":          0.013,
"Spain":          0.017 
},
{
 "Date": "2004-04-01",
"Andalusia":          0.011,
"Balearic.Islands":         -0.071,
"Canary.Islands":          -0.09,
"Catalonia":          0.031,
"Valencia":         -0.006,
"Madrid":           0.15,
"Rest.of.regions":          0.069,
"Spain":          0.123 
},
{
 "Date": "2004-05-01",
"Andalusia":          -0.04,
"Balearic.Islands":              0,
"Canary.Islands":         -0.097,
"Catalonia":          0.192,
"Valencia":          0.011,
"Madrid":           0.25,
"Rest.of.regions":           0.08,
"Spain":          0.016 
},
{
 "Date": "2004-06-01",
"Andalusia":         -0.041,
"Balearic.Islands":         -0.045,
"Canary.Islands":          -0.11,
"Catalonia":         -0.041,
"Valencia":          0.038,
"Madrid":          0.052,
"Rest.of.regions":         -0.039,
"Spain":          0.024 
},
{
 "Date": "2004-07-01",
"Andalusia":          0.023,
"Balearic.Islands":          0.086,
"Canary.Islands":         -0.063,
"Catalonia":          0.035,
"Valencia":         -0.093,
"Madrid":         -0.018,
"Rest.of.regions":         -0.039,
"Spain":          0.096 
},
{
 "Date": "2004-08-01",
"Andalusia":         -0.014,
"Balearic.Islands":         -0.027,
"Canary.Islands":          -0.06,
"Catalonia":          0.041,
"Valencia":         -0.055,
"Madrid":          0.053,
"Rest.of.regions":         -0.018,
"Spain":          0.001 
},
{
 "Date": "2004-09-01",
"Andalusia":           0.07,
"Balearic.Islands":          0.079,
"Canary.Islands":         -0.016,
"Catalonia":          0.113,
"Valencia":          0.027,
"Madrid":          0.039,
"Rest.of.regions":          0.055,
"Spain":          0.012 
},
{
 "Date": "2004-10-01",
"Andalusia":          0.022,
"Balearic.Islands":          0.105,
"Canary.Islands":          0.016,
"Catalonia":            0.2,
"Valencia":          0.066,
"Madrid":         -0.051,
"Rest.of.regions":          0.166,
"Spain":          0.136 
},
{
 "Date": "2004-11-01",
"Andalusia":          0.056,
"Balearic.Islands":          0.157,
"Canary.Islands":         -0.009,
"Catalonia":          0.207,
"Valencia":           0.08,
"Madrid":          0.076,
"Rest.of.regions":          0.118,
"Spain":           0.05 
},
{
 "Date": "2004-12-01",
"Andalusia":          0.059,
"Balearic.Islands":          0.074,
"Canary.Islands":          0.024,
"Catalonia":          0.203,
"Valencia":          0.207,
"Madrid":          0.165,
"Rest.of.regions":          0.241,
"Spain":          0.054 
},
{
 "Date": "2005-01-01",
"Andalusia":           0.09,
"Balearic.Islands":          0.231,
"Canary.Islands":          0.008,
"Catalonia":          0.129,
"Valencia":          0.125,
"Madrid":         -0.002,
"Rest.of.regions":         -0.014,
"Spain":          0.042 
},
{
 "Date": "2005-02-01",
"Andalusia":         -0.018,
"Balearic.Islands":          0.061,
"Canary.Islands":         -0.048,
"Catalonia":           0.07,
"Valencia":          0.006,
"Madrid":         -0.053,
"Rest.of.regions":          0.045,
"Spain":          0.029 
},
{
 "Date": "2005-03-01",
"Andalusia":           0.14,
"Balearic.Islands":          0.219,
"Canary.Islands":              0,
"Catalonia":          0.288,
"Valencia":          0.302,
"Madrid":            0.1,
"Rest.of.regions":          0.342,
"Spain":          0.189 
},
{
 "Date": "2005-04-01",
"Andalusia":         -0.061,
"Balearic.Islands":         -0.072,
"Canary.Islands":         -0.068,
"Catalonia":          0.074,
"Valencia":          0.009,
"Madrid":          0.009,
"Rest.of.regions":          0.063,
"Spain":          0.002 
},
{
 "Date": "2005-05-01",
"Andalusia":          0.039,
"Balearic.Islands":         -0.023,
"Canary.Islands":         -0.042,
"Catalonia":          0.093,
"Valencia":          0.193,
"Madrid":          0.049,
"Rest.of.regions":          0.207,
"Spain":          0.114 
},
{
 "Date": "2005-06-01",
"Andalusia":          0.076,
"Balearic.Islands":           0.02,
"Canary.Islands":          0.004,
"Catalonia":          0.146,
"Valencia":          0.165,
"Madrid":          0.038,
"Rest.of.regions":          0.202,
"Spain":          0.165 
},
{
 "Date": "2005-07-01",
"Andalusia":          0.086,
"Balearic.Islands":          0.023,
"Canary.Islands":          0.002,
"Catalonia":          0.114,
"Valencia":           0.14,
"Madrid":          0.095,
"Rest.of.regions":          0.171,
"Spain":          0.155 
},
{
 "Date": "2005-08-01",
"Andalusia":          0.046,
"Balearic.Islands":         -0.001,
"Canary.Islands":         -0.032,
"Catalonia":           0.13,
"Valencia":           0.03,
"Madrid":          0.025,
"Rest.of.regions":          0.274,
"Spain":           0.06 
},
{
 "Date": "2005-09-01",
"Andalusia":          0.037,
"Balearic.Islands":          0.035,
"Canary.Islands":         -0.018,
"Catalonia":          0.135,
"Valencia":          0.163,
"Madrid":          0.169,
"Rest.of.regions":           0.31,
"Spain":          0.174 
},
{
 "Date": "2005-10-01",
"Andalusia":         -0.009,
"Balearic.Islands":         -0.035,
"Canary.Islands":           0.01,
"Catalonia":          0.119,
"Valencia":          0.065,
"Madrid":          0.097,
"Rest.of.regions":          0.148,
"Spain":          0.063 
},
{
 "Date": "2005-11-01",
"Andalusia":          0.112,
"Balearic.Islands":         -0.039,
"Canary.Islands":           0.01,
"Catalonia":           0.12,
"Valencia":          0.049,
"Madrid":           0.14,
"Rest.of.regions":          0.313,
"Spain":          0.037 
},
{
 "Date": "2005-12-01",
"Andalusia":          0.101,
"Balearic.Islands":          -0.03,
"Canary.Islands":         -0.022,
"Catalonia":          0.077,
"Valencia":          0.005,
"Madrid":         -0.041,
"Rest.of.regions":          0.153,
"Spain":           0.08 
},
{
 "Date": "2006-01-01",
"Andalusia":         -0.071,
"Balearic.Islands":         -0.146,
"Canary.Islands":         -0.058,
"Catalonia":          0.128,
"Valencia":         -0.005,
"Madrid":          0.149,
"Rest.of.regions":          0.107,
"Spain":            0.1 
},
{
 "Date": "2006-02-01",
"Andalusia":         -0.054,
"Balearic.Islands":         -0.189,
"Canary.Islands":         -0.025,
"Catalonia":          0.159,
"Valencia":          0.047,
"Madrid":          0.103,
"Rest.of.regions":          0.096,
"Spain":          0.133 
},
{
 "Date": "2006-03-01",
"Andalusia":         -0.064,
"Balearic.Islands":         -0.179,
"Canary.Islands":          0.037,
"Catalonia":          0.037,
"Valencia":         -0.068,
"Madrid":           0.25,
"Rest.of.regions":         -0.018,
"Spain":          0.032 
},
{
 "Date": "2006-04-01",
"Andalusia":          0.108,
"Balearic.Islands":          0.182,
"Canary.Islands":          0.152,
"Catalonia":          0.206,
"Valencia":          0.163,
"Madrid":          0.336,
"Rest.of.regions":          0.176,
"Spain":          0.143 
},
{
 "Date": "2006-05-01",
"Andalusia":         -0.009,
"Balearic.Islands":          0.042,
"Canary.Islands":           0.04,
"Catalonia":          0.119,
"Valencia":         -0.012,
"Madrid":          0.234,
"Rest.of.regions":          0.149,
"Spain":          0.088 
},
{
 "Date": "2006-06-01",
"Andalusia":         -0.042,
"Balearic.Islands":          0.096,
"Canary.Islands":          0.085,
"Catalonia":          0.069,
"Valencia":          0.021,
"Madrid":          0.108,
"Rest.of.regions":          -0.03,
"Spain":         -0.061 
},
{
 "Date": "2006-07-01",
"Andalusia":         -0.045,
"Balearic.Islands":          0.029,
"Canary.Islands":          0.046,
"Catalonia":          -0.03,
"Valencia":          0.033,
"Madrid":          0.201,
"Rest.of.regions":         -0.001,
"Spain":         -0.047 
},
{
 "Date": "2006-08-01",
"Andalusia":         -0.186,
"Balearic.Islands":          0.019,
"Canary.Islands":          0.029,
"Catalonia":          0.087,
"Valencia":          0.089,
"Madrid":          0.173,
"Rest.of.regions":         -0.006,
"Spain":          0.023 
},
{
 "Date": "2006-09-01",
"Andalusia":         -0.052,
"Balearic.Islands":          0.041,
"Canary.Islands":          0.015,
"Catalonia":          0.113,
"Valencia":         -0.009,
"Madrid":          0.187,
"Rest.of.regions":          -0.01,
"Spain":          0.013 
},
{
 "Date": "2006-10-01",
"Andalusia":          0.006,
"Balearic.Islands":         -0.009,
"Canary.Islands":         -0.035,
"Catalonia":          0.067,
"Valencia":          0.032,
"Madrid":          0.174,
"Rest.of.regions":          0.085,
"Spain":          0.024 
},
{
 "Date": "2006-11-01",
"Andalusia":         -0.012,
"Balearic.Islands":         -0.027,
"Canary.Islands":         -0.028,
"Catalonia":          0.038,
"Valencia":          0.072,
"Madrid":          0.124,
"Rest.of.regions":         -0.013,
"Spain":          0.066 
},
{
 "Date": "2006-12-01",
"Andalusia":         -0.014,
"Balearic.Islands":          0.073,
"Canary.Islands":          0.005,
"Catalonia":           0.05,
"Valencia":          0.029,
"Madrid":           0.05,
"Rest.of.regions":         -0.053,
"Spain":          0.073 
},
{
 "Date": "2007-01-01",
"Andalusia":          0.064,
"Balearic.Islands":          0.012,
"Canary.Islands":         -0.024,
"Catalonia":          0.068,
"Valencia":          0.044,
"Madrid":          0.093,
"Rest.of.regions":          0.041,
"Spain":          0.051 
},
{
 "Date": "2007-02-01",
"Andalusia":          0.062,
"Balearic.Islands":          0.089,
"Canary.Islands":         -0.002,
"Catalonia":         -0.007,
"Valencia":          0.108,
"Madrid":          0.264,
"Rest.of.regions":         -0.015,
"Spain":         -0.031 
},
{
 "Date": "2007-03-01",
"Andalusia":          0.131,
"Balearic.Islands":          0.177,
"Canary.Islands":          0.019,
"Catalonia":          0.047,
"Valencia":          0.086,
"Madrid":          0.095,
"Rest.of.regions":         -0.042,
"Spain":          0.064 
},
{
 "Date": "2007-04-01",
"Andalusia":           0.01,
"Balearic.Islands":          -0.07,
"Canary.Islands":         -0.114,
"Catalonia":         -0.061,
"Valencia":         -0.042,
"Madrid":          0.085,
"Rest.of.regions":         -0.011,
"Spain":          0.036 
},
{
 "Date": "2007-05-01",
"Andalusia":          0.052,
"Balearic.Islands":         -0.033,
"Canary.Islands":          -0.07,
"Catalonia":         -0.014,
"Valencia":         -0.014,
"Madrid":          0.054,
"Rest.of.regions":         -0.157,
"Spain":         -0.054 
},
{
 "Date": "2007-06-01",
"Andalusia":          0.049,
"Balearic.Islands":          0.027,
"Canary.Islands":         -0.039,
"Catalonia":          0.055,
"Valencia":          0.043,
"Madrid":           0.16,
"Rest.of.regions":          0.042,
"Spain":          0.136 
},
{
 "Date": "2007-07-01",
"Andalusia":          0.083,
"Balearic.Islands":          0.013,
"Canary.Islands":         -0.037,
"Catalonia":         -0.027,
"Valencia":          0.035,
"Madrid":          0.039,
"Rest.of.regions":          0.012,
"Spain":           0.12 
},
{
 "Date": "2007-08-01",
"Andalusia":           0.11,
"Balearic.Islands":           0.01,
"Canary.Islands":         -0.021,
"Catalonia":           0.03,
"Valencia":          0.073,
"Madrid":          0.022,
"Rest.of.regions":         -0.101,
"Spain":          0.091 
},
{
 "Date": "2007-09-01",
"Andalusia":          0.061,
"Balearic.Islands":         -0.006,
"Canary.Islands":         -0.018,
"Catalonia":          0.009,
"Valencia":          0.035,
"Madrid":          0.055,
"Rest.of.regions":         -0.098,
"Spain":          0.101 
},
{
 "Date": "2007-10-01",
"Andalusia":          0.057,
"Balearic.Islands":         -0.043,
"Canary.Islands":         -0.014,
"Catalonia":         -0.036,
"Valencia":         -0.054,
"Madrid":           0.17,
"Rest.of.regions":         -0.054,
"Spain":          0.048 
},
{
 "Date": "2007-11-01",
"Andalusia":         -0.016,
"Balearic.Islands":          0.077,
"Canary.Islands":          0.043,
"Catalonia":          0.095,
"Valencia":         -0.008,
"Madrid":          0.211,
"Rest.of.regions":         -0.111,
"Spain":          0.057 
},
{
 "Date": "2007-12-01",
"Andalusia":         -0.057,
"Balearic.Islands":         -0.029,
"Canary.Islands":          0.061,
"Catalonia":          0.029,
"Valencia":          0.006,
"Madrid":          0.021,
"Rest.of.regions":         -0.141,
"Spain":         -0.011 
},
{
 "Date": "2008-01-01",
"Andalusia":         -0.071,
"Balearic.Islands":          -0.02,
"Canary.Islands":          0.043,
"Catalonia":          0.031,
"Valencia":          0.023,
"Madrid":          0.213,
"Rest.of.regions":         -0.096,
"Spain":         -0.006 
},
{
 "Date": "2008-02-01",
"Andalusia":         -0.055,
"Balearic.Islands":          0.114,
"Canary.Islands":           0.09,
"Catalonia":          0.064,
"Valencia":          0.062,
"Madrid":          0.127,
"Rest.of.regions":          0.062,
"Spain":          0.053 
},
{
 "Date": "2008-03-01",
"Andalusia":          0.014,
"Balearic.Islands":          0.027,
"Canary.Islands":          0.049,
"Catalonia":          0.039,
"Valencia":          0.184,
"Madrid":          0.084,
"Rest.of.regions":          0.165,
"Spain":          0.067 
},
{
 "Date": "2008-04-01",
"Andalusia":         -0.058,
"Balearic.Islands":         -0.026,
"Canary.Islands":         -0.019,
"Catalonia":         -0.029,
"Valencia":          0.038,
"Madrid":           0.05,
"Rest.of.regions":         -0.068,
"Spain":         -0.035 
},
{
 "Date": "2008-05-01",
"Andalusia":         -0.027,
"Balearic.Islands":          0.085,
"Canary.Islands":          0.073,
"Catalonia":          0.009,
"Valencia":          0.081,
"Madrid":          0.071,
"Rest.of.regions":          0.109,
"Spain":          0.185 
},
{
 "Date": "2008-06-01",
"Andalusia":          0.007,
"Balearic.Islands":         -0.032,
"Canary.Islands":           0.01,
"Catalonia":          0.034,
"Valencia":          0.037,
"Madrid":          0.065,
"Rest.of.regions":         -0.049,
"Spain":          0.031 
},
{
 "Date": "2008-07-01",
"Andalusia":         -0.081,
"Balearic.Islands":         -0.031,
"Canary.Islands":         -0.043,
"Catalonia":         -0.115,
"Valencia":         -0.067,
"Madrid":         -0.009,
"Rest.of.regions":         -0.129,
"Spain":          0.008 
},
{
 "Date": "2008-08-01",
"Andalusia":          0.041,
"Balearic.Islands":          0.049,
"Canary.Islands":         -0.002,
"Catalonia":         -0.141,
"Valencia":         -0.009,
"Madrid":          0.101,
"Rest.of.regions":         -0.082,
"Spain":          0.029 
},
{
 "Date": "2008-09-01",
"Andalusia":           -0.1,
"Balearic.Islands":         -0.025,
"Canary.Islands":         -0.091,
"Catalonia":         -0.101,
"Valencia":         -0.015,
"Madrid":          0.045,
"Rest.of.regions":         -0.043,
"Spain":         -0.072 
},
{
 "Date": "2008-10-01",
"Andalusia":          -0.07,
"Balearic.Islands":          0.027,
"Canary.Islands":         -0.073,
"Catalonia":         -0.101,
"Valencia":          0.024,
"Madrid":         -0.037,
"Rest.of.regions":         -0.059,
"Spain":         -0.074 
},
{
 "Date": "2008-11-01",
"Andalusia":         -0.179,
"Balearic.Islands":         -0.112,
"Canary.Islands":         -0.035,
"Catalonia":         -0.104,
"Valencia":         -0.194,
"Madrid":         -0.163,
"Rest.of.regions":         -0.139,
"Spain":         -0.036 
},
{
 "Date": "2008-12-01",
"Andalusia":         -0.212,
"Balearic.Islands":          0.023,
"Canary.Islands":         -0.108,
"Catalonia":         -0.141,
"Valencia":         -0.212,
"Madrid":          0.066,
"Rest.of.regions":         -0.199,
"Spain":         -0.078 
},
{
 "Date": "2009-01-01",
"Andalusia":          -0.18,
"Balearic.Islands":          0.048,
"Canary.Islands":         -0.073,
"Catalonia":         -0.113,
"Valencia":         -0.229,
"Madrid":          -0.19,
"Rest.of.regions":         -0.151,
"Spain":          0.019 
},
{
 "Date": "2009-02-01",
"Andalusia":         -0.152,
"Balearic.Islands":         -0.169,
"Canary.Islands":         -0.175,
"Catalonia":         -0.126,
"Valencia":          -0.25,
"Madrid":         -0.101,
"Rest.of.regions":          -0.15,
"Spain":         -0.062 
},
{
 "Date": "2009-03-01",
"Andalusia":         -0.235,
"Balearic.Islands":         -0.188,
"Canary.Islands":         -0.204,
"Catalonia":         -0.216,
"Valencia":         -0.344,
"Madrid":          -0.05,
"Rest.of.regions":         -0.158,
"Spain":         -0.126 
},
{
 "Date": "2009-04-01",
"Andalusia":         -0.004,
"Balearic.Islands":           0.05,
"Canary.Islands":         -0.076,
"Catalonia":         -0.026,
"Valencia":         -0.051,
"Madrid":          0.124,
"Rest.of.regions":         -0.076,
"Spain":         -0.045 
},
{
 "Date": "2009-05-01",
"Andalusia":         -0.067,
"Balearic.Islands":         -0.116,
"Canary.Islands":         -0.188,
"Catalonia":         -0.137,
"Valencia":         -0.114,
"Madrid":          0.012,
"Rest.of.regions":         -0.169,
"Spain":         -0.098 
},
{
 "Date": "2009-06-01",
"Andalusia":         -0.078,
"Balearic.Islands":         -0.073,
"Canary.Islands":         -0.212,
"Catalonia":         -0.156,
"Valencia":         -0.142,
"Madrid":          0.076,
"Rest.of.regions":          0.027,
"Spain":         -0.079 
},
{
 "Date": "2009-07-01",
"Andalusia":         -0.077,
"Balearic.Islands":         -0.053,
"Canary.Islands":         -0.093,
"Catalonia":         -0.101,
"Valencia":         -0.003,
"Madrid":          0.063,
"Rest.of.regions":         -0.001,
"Spain":          0.013 
},
{
 "Date": "2009-08-01",
"Andalusia":              0,
"Balearic.Islands":         -0.123,
"Canary.Islands":         -0.134,
"Catalonia":         -0.113,
"Valencia":         -0.048,
"Madrid":         -0.034,
"Rest.of.regions":         -0.051,
"Spain":          0.005 
},
{
 "Date": "2009-09-01",
"Andalusia":          -0.14,
"Balearic.Islands":         -0.126,
"Canary.Islands":         -0.135,
"Catalonia":          -0.11,
"Valencia":         -0.124,
"Madrid":           0.07,
"Rest.of.regions":          0.034,
"Spain":          -0.04 
},
{
 "Date": "2009-10-01",
"Andalusia":         -0.041,
"Balearic.Islands":          -0.13,
"Canary.Islands":         -0.076,
"Catalonia":         -0.044,
"Valencia":         -0.027,
"Madrid":          0.276,
"Rest.of.regions":         -0.054,
"Spain":          0.105 
},
{
 "Date": "2009-11-01",
"Andalusia":          0.077,
"Balearic.Islands":         -0.186,
"Canary.Islands":         -0.067,
"Catalonia":         -0.086,
"Valencia":         -0.006,
"Madrid":          0.156,
"Rest.of.regions":         -0.052,
"Spain":          0.033 
},
{
 "Date": "2009-12-01",
"Andalusia":          0.246,
"Balearic.Islands":           -0.3,
"Canary.Islands":          -0.05,
"Catalonia":         -0.157,
"Valencia":         -0.039,
"Madrid":          0.087,
"Rest.of.regions":         -0.002,
"Spain":          0.055 
},
{
 "Date": "2010-01-01",
"Andalusia":           0.11,
"Balearic.Islands":         -0.314,
"Canary.Islands":          0.016,
"Catalonia":              0,
"Valencia":         -0.025,
"Madrid":          0.062,
"Rest.of.regions":          0.068,
"Spain":          0.041 
},
{
 "Date": "2010-02-01",
"Andalusia":          0.045,
"Balearic.Islands":         -0.188,
"Canary.Islands":          0.024,
"Catalonia":         -0.079,
"Valencia":          0.031,
"Madrid":         -0.117,
"Rest.of.regions":          -0.08,
"Spain":          0.039 
},
{
 "Date": "2010-03-01",
"Andalusia":          0.098,
"Balearic.Islands":           0.02,
"Canary.Islands":          0.049,
"Catalonia":           0.04,
"Valencia":           0.06,
"Madrid":         -0.098,
"Rest.of.regions":          0.003,
"Spain":          0.143 
},
{
 "Date": "2010-04-01",
"Andalusia":         -0.129,
"Balearic.Islands":         -0.204,
"Canary.Islands":         -0.129,
"Catalonia":         -0.073,
"Valencia":         -0.191,
"Madrid":         -0.191,
"Rest.of.regions":         -0.097,
"Spain":          0.062 
},
{
 "Date": "2010-05-01",
"Andalusia":          0.065,
"Balearic.Islands":         -0.054,
"Canary.Islands":          0.108,
"Catalonia":          0.024,
"Valencia":         -0.052,
"Madrid":          0.021,
"Rest.of.regions":          0.007,
"Spain":         -0.049 
},
{
 "Date": "2010-06-01",
"Andalusia":         -0.002,
"Balearic.Islands":         -0.004,
"Canary.Islands":          0.159,
"Catalonia":          0.025,
"Valencia":          0.081,
"Madrid":         -0.055,
"Rest.of.regions":         -0.077,
"Spain":          0.094 
},
{
 "Date": "2010-07-01",
"Andalusia":          0.027,
"Balearic.Islands":          0.094,
"Canary.Islands":          0.058,
"Catalonia":          0.122,
"Valencia":          0.004,
"Madrid":         -0.063,
"Rest.of.regions":         -0.114,
"Spain":          0.007 
},
{
 "Date": "2010-08-01",
"Andalusia":         -0.052,
"Balearic.Islands":          0.111,
"Canary.Islands":          0.079,
"Catalonia":          0.066,
"Valencia":         -0.013,
"Madrid":          0.002,
"Rest.of.regions":         -0.006,
"Spain":          0.013 
},
{
 "Date": "2010-09-01",
"Andalusia":          0.053,
"Balearic.Islands":          0.096,
"Canary.Islands":          0.129,
"Catalonia":          0.087,
"Valencia":          0.013,
"Madrid":         -0.081,
"Rest.of.regions":         -0.158,
"Spain":          0.141 
},
{
 "Date": "2010-10-01",
"Andalusia":          0.002,
"Balearic.Islands":          0.077,
"Canary.Islands":          0.097,
"Catalonia":          0.053,
"Valencia":         -0.014,
"Madrid":          0.019,
"Rest.of.regions":          0.025,
"Spain":          0.026 
},
{
 "Date": "2010-11-01",
"Andalusia":          0.018,
"Balearic.Islands":         -0.194,
"Canary.Islands":          0.047,
"Catalonia":          0.084,
"Valencia":          0.006,
"Madrid":              0,
"Rest.of.regions":          0.006,
"Spain":          -0.02 
},
{
 "Date": "2010-12-01",
"Andalusia":         -0.231,
"Balearic.Islands":         -0.183,
"Canary.Islands":          0.024,
"Catalonia":         -0.038,
"Valencia":         -0.072,
"Madrid":          0.087,
"Rest.of.regions":         -0.063,
"Spain":         -0.052 
},
{
 "Date": "2011-01-01",
"Andalusia":         -0.044,
"Balearic.Islands":          0.069,
"Canary.Islands":          0.088,
"Catalonia":           0.01,
"Valencia":          0.196,
"Madrid":          0.064,
"Rest.of.regions":         -0.066,
"Spain":          0.071 
},
{
 "Date": "2011-02-01",
"Andalusia":         -0.015,
"Balearic.Islands":         -0.087,
"Canary.Islands":          0.185,
"Catalonia":         -0.057,
"Valencia":         -0.051,
"Madrid":         -0.029,
"Rest.of.regions":         -0.004,
"Spain":          0.079 
},
{
 "Date": "2011-03-01",
"Andalusia":          0.006,
"Balearic.Islands":         -0.198,
"Canary.Islands":          0.182,
"Catalonia":          -0.11,
"Valencia":         -0.048,
"Madrid":         -0.066,
"Rest.of.regions":          0.014,
"Spain":         -0.002 
},
{
 "Date": "2011-04-01",
"Andalusia":           0.26,
"Balearic.Islands":           0.32,
"Canary.Islands":          0.527,
"Catalonia":         -0.059,
"Valencia":          0.239,
"Madrid":         -0.015,
"Rest.of.regions":          0.177,
"Spain":          0.083 
},
{
 "Date": "2011-05-01",
"Andalusia":         -0.036,
"Balearic.Islands":          0.101,
"Canary.Islands":           0.13,
"Catalonia":         -0.026,
"Valencia":          0.025,
"Madrid":         -0.123,
"Rest.of.regions":          0.033,
"Spain":          0.096 
},
{
 "Date": "2011-06-01",
"Andalusia":          0.148,
"Balearic.Islands":          0.126,
"Canary.Islands":          0.139,
"Catalonia":           0.06,
"Valencia":         -0.004,
"Madrid":         -0.119,
"Rest.of.regions":          0.147,
"Spain":          0.138 
},
{
 "Date": "2011-07-01",
"Andalusia":          0.022,
"Balearic.Islands":          0.131,
"Canary.Islands":          0.196,
"Catalonia":          0.005,
"Valencia":          0.057,
"Madrid":         -0.244,
"Rest.of.regions":          0.144,
"Spain":          0.065 
},
{
 "Date": "2011-08-01",
"Andalusia":         -0.046,
"Balearic.Islands":          0.089,
"Canary.Islands":          0.161,
"Catalonia":         -0.031,
"Valencia":          0.105,
"Madrid":          0.407,
"Rest.of.regions":          0.166,
"Spain":          0.012 
},
{
 "Date": "2011-09-01",
"Andalusia":          0.125,
"Balearic.Islands":          0.105,
"Canary.Islands":          0.209,
"Catalonia":          0.094,
"Valencia":          0.065,
"Madrid":         -0.044,
"Rest.of.regions":          0.191,
"Spain":          0.036 
},
{
 "Date": "2011-10-01",
"Andalusia":          0.113,
"Balearic.Islands":           0.06,
"Canary.Islands":          0.169,
"Catalonia":          0.075,
"Valencia":          0.096,
"Madrid":         -0.075,
"Rest.of.regions":          0.249,
"Spain":          0.021 
},
{
 "Date": "2011-11-01",
"Andalusia":         -0.099,
"Balearic.Islands":          0.086,
"Canary.Islands":          0.133,
"Catalonia":         -0.004,
"Valencia":          0.054,
"Madrid":         -0.014,
"Rest.of.regions":          0.021,
"Spain":         -0.009 
},
{
 "Date": "2011-12-01",
"Andalusia":          0.013,
"Balearic.Islands":         -0.243,
"Canary.Islands":          0.172,
"Catalonia":         -0.023,
"Valencia":          0.002,
"Madrid":         -0.038,
"Rest.of.regions":         -0.019,
"Spain":         -0.002 
},
{
 "Date": "2012-01-01",
"Andalusia":         -0.127,
"Balearic.Islands":         -0.238,
"Canary.Islands":          0.085,
"Catalonia":          0.119,
"Valencia":         -0.142,
"Madrid":          0.122,
"Rest.of.regions":          0.384,
"Spain":         -0.077 
},
{
 "Date": "2012-02-01",
"Andalusia":         -0.108,
"Balearic.Islands":         -0.117,
"Canary.Islands":          0.024,
"Catalonia":          0.052,
"Valencia":         -0.103,
"Madrid":          0.092,
"Rest.of.regions":          0.067,
"Spain":         -0.066 
},
{
 "Date": "2012-03-01",
"Andalusia":           -0.1,
"Balearic.Islands":           0.11,
"Canary.Islands":         -0.007,
"Catalonia":          0.125,
"Valencia":          0.014,
"Madrid":          0.051,
"Rest.of.regions":         -0.006,
"Spain":         -0.048 
},
{
 "Date": "2012-04-01",
"Andalusia":         -0.035,
"Balearic.Islands":         -0.053,
"Canary.Islands":         -0.137,
"Catalonia":           0.15,
"Valencia":         -0.169,
"Madrid":          0.072,
"Rest.of.regions":         -0.095,
"Spain":         -0.102 
},
{
 "Date": "2012-05-01",
"Andalusia":          -0.03,
"Balearic.Islands":          0.016,
"Canary.Islands":          0.009,
"Catalonia":          0.112,
"Valencia":          0.036,
"Madrid":          0.217,
"Rest.of.regions":          0.012,
"Spain":         -0.078 
},
{
 "Date": "2012-06-01",
"Andalusia":         -0.049,
"Balearic.Islands":          0.043,
"Canary.Islands":          0.047,
"Catalonia":          0.112,
"Valencia":           0.08,
"Madrid":          0.177,
"Rest.of.regions":         -0.111,
"Spain":         -0.134 
},
{
 "Date": "2012-07-01",
"Andalusia":         -0.033,
"Balearic.Islands":          0.021,
"Canary.Islands":         -0.014,
"Catalonia":          0.097,
"Valencia":          0.061,
"Madrid":           0.07,
"Rest.of.regions":          0.031,
"Spain":         -0.051 
},
{
 "Date": "2012-08-01",
"Andalusia":          0.043,
"Balearic.Islands":          0.021,
"Canary.Islands":              0,
"Catalonia":          0.152,
"Valencia":          0.019,
"Madrid":         -0.313,
"Rest.of.regions":          0.086,
"Spain":         -0.014 
},
{
 "Date": "2012-09-01",
"Andalusia":          0.043,
"Balearic.Islands":          0.088,
"Canary.Islands":         -0.004,
"Catalonia":          0.078,
"Valencia":          0.074,
"Madrid":         -0.057,
"Rest.of.regions":         -0.046,
"Spain":          0.001 
},
{
 "Date": "2012-10-01",
"Andalusia":         -0.064,
"Balearic.Islands":          0.008,
"Canary.Islands":         -0.024,
"Catalonia":          0.025,
"Valencia":         -0.046,
"Madrid":         -0.081,
"Rest.of.regions":         -0.069,
"Spain":         -0.069 
},
{
 "Date": "2012-11-01",
"Andalusia":          0.064,
"Balearic.Islands":         -0.029,
"Canary.Islands":         -0.037,
"Catalonia":          0.028,
"Valencia":          0.042,
"Madrid":          0.041,
"Rest.of.regions":         -0.054,
"Spain":         -0.029 
},
{
 "Date": "2012-12-01",
"Andalusia":         -0.101,
"Balearic.Islands":          0.098,
"Canary.Islands":         -0.001,
"Catalonia":          0.074,
"Valencia":          0.037,
"Madrid":         -0.217,
"Rest.of.regions":          0.046,
"Spain":         -0.011 
},
{
 "Date": "2013-01-01",
"Andalusia":         -0.079,
"Balearic.Islands":          0.157,
"Canary.Islands":         -0.062,
"Catalonia":          0.013,
"Valencia":           0.09,
"Madrid":         -0.074,
"Rest.of.regions":         -0.075,
"Spain":         -0.057 
},
{
 "Date": "2013-02-01",
"Andalusia":          0.027,
"Balearic.Islands":         -0.061,
"Canary.Islands":         -0.029,
"Catalonia":          0.076,
"Valencia":           0.08,
"Madrid":         -0.101,
"Rest.of.regions":         -0.028,
"Spain":         -0.038 
},
{
 "Date": "2013-03-01",
"Andalusia":          0.098,
"Balearic.Islands":          0.179,
"Canary.Islands":          0.042,
"Catalonia":          0.112,
"Valencia":          0.049,
"Madrid":          0.074,
"Rest.of.regions":           0.02,
"Spain":          0.094 
},
{
 "Date": "2013-04-01",
"Andalusia":         -0.014,
"Balearic.Islands":          0.087,
"Canary.Islands":         -0.007,
"Catalonia":          0.007,
"Valencia":          0.289,
"Madrid":          0.028,
"Rest.of.regions":         -0.038,
"Spain":          0.044 
},
{
 "Date": "2013-05-01",
"Andalusia":          0.052,
"Balearic.Islands":          0.127,
"Canary.Islands":          0.081,
"Catalonia":          0.063,
"Valencia":          0.169,
"Madrid":         -0.085,
"Rest.of.regions":          0.014,
"Spain":          0.141 
},
{
 "Date": "2013-06-01",
"Andalusia":          0.017,
"Balearic.Islands":          0.083,
"Canary.Islands":           0.03,
"Catalonia":          0.069,
"Valencia":          0.096,
"Madrid":         -0.119,
"Rest.of.regions":          0.067,
"Spain":          0.051 
},
{
 "Date": "2013-07-01",
"Andalusia":          0.066,
"Balearic.Islands":          0.011,
"Canary.Islands":          0.027,
"Catalonia":          0.028,
"Valencia":          0.048,
"Madrid":         -0.112,
"Rest.of.regions":          0.032,
"Spain":          0.022 
},
{
 "Date": "2013-08-01",
"Andalusia":          0.061,
"Balearic.Islands":          0.106,
"Canary.Islands":          0.061,
"Catalonia":          0.123,
"Valencia":          0.115,
"Madrid":         -0.222,
"Rest.of.regions":         -0.009,
"Spain":         -0.034 
},
{
 "Date": "2013-09-01",
"Andalusia":          0.027,
"Balearic.Islands":          0.028,
"Canary.Islands":          0.051,
"Catalonia":          0.075,
"Valencia":          0.059,
"Madrid":          0.014,
"Rest.of.regions":          0.069,
"Spain":         -0.027 
},
{
 "Date": "2013-10-01",
"Andalusia":           0.05,
"Balearic.Islands":          0.079,
"Canary.Islands":          0.075,
"Catalonia":           0.11,
"Valencia":          0.144,
"Madrid":         -0.053,
"Rest.of.regions":         -0.001,
"Spain":         -0.044 
},
{
 "Date": "2013-11-01",
"Andalusia":          0.051,
"Balearic.Islands":         -0.087,
"Canary.Islands":          0.179,
"Catalonia":          0.146,
"Valencia":           0.09,
"Madrid":         -0.106,
"Rest.of.regions":           0.08,
"Spain":         -0.043 
},
{
 "Date": "2013-12-01",
"Andalusia":          0.203,
"Balearic.Islands":          0.092,
"Canary.Islands":          0.132,
"Catalonia":          0.202,
"Valencia":          0.167,
"Madrid":          0.198,
"Rest.of.regions":          0.118,
"Spain":         -0.022 
},
{
 "Date": "2014-01-01",
"Andalusia":          0.236,
"Balearic.Islands":         -0.113,
"Canary.Islands":          0.137,
"Catalonia":          0.136,
"Valencia":          0.049,
"Madrid":          0.123,
"Rest.of.regions":          0.089,
"Spain":         -0.008 
},
{
 "Date": "2014-02-01",
"Andalusia":          0.104,
"Balearic.Islands":         -0.153,
"Canary.Islands":          0.111,
"Catalonia":           0.13,
"Valencia":          0.241,
"Madrid":          0.053,
"Rest.of.regions":          0.155,
"Spain":          0.044 
},
{
 "Date": "2014-03-01",
"Andalusia":         -0.105,
"Balearic.Islands":         -0.316,
"Canary.Islands":          0.077,
"Catalonia":          0.049,
"Valencia":          0.092,
"Madrid":          0.032,
"Rest.of.regions":          0.047,
"Spain":         -0.055 
},
{
 "Date": "2014-04-01",
"Andalusia":          0.196,
"Balearic.Islands":          0.084,
"Canary.Islands":          0.221,
"Catalonia":          0.116,
"Valencia":          0.038,
"Madrid":          0.009,
"Rest.of.regions":          0.218,
"Spain":          0.085 
},
{
 "Date": "2014-05-01",
"Andalusia":          0.104,
"Balearic.Islands":          0.012,
"Canary.Islands":          0.129,
"Catalonia":          0.023,
"Valencia":          0.028,
"Madrid":          0.117,
"Rest.of.regions":          0.091,
"Spain":         -0.022 
},
{
 "Date": "2014-06-01",
"Andalusia":          0.055,
"Balearic.Islands":          0.021,
"Canary.Islands":          0.081,
"Catalonia":          0.024,
"Valencia":          0.009,
"Madrid":          0.145,
"Rest.of.regions":          0.104,
"Spain":          0.025 
},
{
 "Date": "2014-07-01",
"Andalusia":          0.074,
"Balearic.Islands":          0.039,
"Canary.Islands":          0.084,
"Catalonia":          0.026,
"Valencia":          0.007,
"Madrid":          0.047,
"Rest.of.regions":          0.216,
"Spain":         -0.007 
} 
],
"id": "chart1",
"labels": "Catalonia" 
},
      chartType = "Line"
    new Morris[chartType](chartParams)
</script>
