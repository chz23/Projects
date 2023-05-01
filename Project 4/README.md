# Project 4: Predicting Dengue Cases

### Background
Dengue is a common viral infection caused by mosquitoes that infects up to 400 million and kills 20,000 to 25,000 people in a year, making it a serious public health concern

Dengue has important economic consequences because of the burden to hospitals, work absenteeism and risk of death of symptomatic cases. 

Hence the importance of reducing dengue cases from a public health perspective as well as economic. 

### Problem Statement
- This project focuses on predicting dengue cases using simple, weather-based dengue forecasting model to predict potential dengue outbreak giving enough time to implement preventive measures, enhance dengue surveillance and control.

---

### Brief Summary 
From the research and analysis, 4 key factors appear to impact the rise of dengue cases:

1. The uniqueness of Singapore’s warm climate lends to higher dengue cases providing an optimal breeding ground for mosquitoes to thrive. Climate scientist Winston Chow from the College of Integrative Studies at Singapore Management University says “We will not be able to eradicate dengue (because) the constant weather extremes create the perfect breeding conditions for mosquitoes,”

2. Urbanization in a globalized world accounts for the rise in dengue cases. Singapore is a densely populated nation with 7810 persons per sqm as compared to Indonesia (which is one of the most populous nation) but has only 4383 persons per sqm. 

3. Social distance policy due to Covid-19 accounted for a significant rise of dengue cases in 2020, an all time high of 35,000 cases that year. With residential places in naturally ventilated spaces compared to air-conditioned office spaces invites more mosquitoes who are day-biters to bite people, leading to an increased rise of dengue cases. 

4. Singapore’s low herd immunity to denv3 is one of the leading causes of the sudden increase of dengue cases in 2020. Serological research studies show that Singapore’s exposure to denv3 compared to Indonesia is low. Singaporean kids exposure to denv3 is below 10% which is much lower to Indonesian kids who are 90% exposed to it which accounts for the low herd immunity to this new strain of dengue. Dengue cases in 2013 and 2014 were driven by denv1 while 2015 - 2017 dengue cases were driven by denv2. Thereafter from 2019 onwards denv3 were the predominant serotypes which could explain why there was a spike of dengue cases in 2019 from 2018.

5. East/North East suffer worse dengue outbreaks than the West

![Total Cases over Years](image/total_cases_over_year.gif "Total Cases over Years")

6. Outbreaks typically takes place in the middle of the year when it is hotter

![Total Cases over Months](image/total_cases_over_month.gif "Total Cases over Months")
---

### Models Used
The following Models were used:
1. Linear Regression 
2. Gradient Boosting

---

### Conclusions and Recommendations
Conclusions:
- Temperature and rainfall correlates strongly to dengue cases
- Low herd immunity to new dengue strain
- Singapore is densely populated
- EA Campaigns, Project Wolbachia are effective

Recommendations:
- NEA to spend more resources in vector control in East and North East
- Consider climate change predictors into future model
- Consider amount of Wolbachia Mosquito to be released, in the model
- Model dengue outbreak by zone