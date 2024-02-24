# A-Levels Research Project for the United Kingdom.

This data project provides information on A-level enrolment percentages per region and subject in schools in England for the year 2022-2023.

I started this project to support my son's choice of where to study for his A-levels. We had two options: use data to support our decision or ask friends. It turned out to be more complicated than initially thought but highly rewarding. 

Since he is a science student, I wanted to see which schools had the highest percentage of key stage 4 (KS4) students progressing to science-focused studies in A-Levels (KS5). Those schools provided more encouragement in the sciences and maths, hence the numbers. I also wanted to see which schools produce students ending up in Russel group schools or Oxbridge (Oxford or Cambridge). Could we marry this data to see schools that, on average, deliver on these and more? 


## Data Source: 
https://explore-education-statistics.service.gov.uk/ 
The information is based on data collected via awarding organizations, the school census, and the Individualized Learner Record.
Suppression is applied to protect the disclosure of personal information or characteristics.
This source data describes the data included in the A-level and other 16 to 18 performances from 2022/23.


## Tools Used:
* Azure Data Studio
* MSSQL
* PowerBI


## Methodology:
The OFSTED ratings for each school were converted to the numerical values as my OFSTED index.
"Outstanding" = 100
"Good" = 75
"Requires improvement" = 50
"Inadequate"= 30
Points were deducted for years since the last OFSTED visit was conducted. This means that a school with an OFSTED rating of outstanding but was last visited ten years ago will lose points for that. I wrote the following DAX to create values to divide the OFSTED index and create the OFSTED Score (converted to a percentage).
```	IF(yearssince >= 1 && yearssince <=2,1,
            IF(yearssince>=3 && yearssince<=5,3,
            IF(yearssince>5,5)))
```
Since my son thought that Russell Group Institution and Oxbridge (Oxford and Cambridge) were a big deal, I created a bias by increasing the weighting of Russel Group Institutions by a multiple of 1.2 and Oxbridge by 1.5. 


## PowerBI Dashboard
<iframe title="A_Levels_Project_2024" width="600" height="373.5" src="https://app.powerbi.com/view?r=eyJrIjoiY2I0ZTYyOTUtY2NmYi00ZDE2LThiMDktY2E5OTRhMjg1MDBkIiwidCI6IjliNGE1Yjc1LTE5N2ItNGNkMS1hNTQwLTg5YWRjMTQxYWYxMCJ9" frameborder="0" allowFullScreen="true"></iframe>

## Key Findings for the North East:
At the time of the project, I was in the Northeast and wanted to know the top schools in the region. 


### The top 5 schools in the North East based on percentage of students progressing to Oxford or Cambridge are: 
St Leonard's Catholic School, County Durham, 6%
Durham Johnston Comprehensive School, County Durham, 5% 
Teesdale School and Sixth Form, County Durham, 5%	 
St Mary's Catholic School, Newcastle upon Tyne, 4%	 
Emmanuel College, Gateshead, 4%	 

  
### The top 5 schools in the North East with the highest percentage of students progressing to Russell Group Schools are:
* Durham Johnston Comprehensive School, County Durham, 62%	 
* St Cuthbert's High School, Newcastle upon Tyne, 44%	 
* Sacred Heart Catholic High School, Newcastle upon Tyne, 43%	 
* St Mary's Catholic School, Newcastle upon Tyne, 42%	 
* Queen Elizabeth High School, Northumberland, 39%	 


### The top 5 schools in the North East progressing to study Maths or Science in their A-Levels are:
* North East Futures UTC, Newcastle upon Tyne, 35.70%	 
* Durham Johnston Comprehensive School, County Durham, 23.83%	 
* East Durham College, County Durham, 21.58% 
* St Leonard's Catholic School, County Durham, 21.08%	 
* Emmanuel College, Gateshead, 21.03%	

     
### Overall top ten Schools in North-East, based on all the indices:
* North East Futures UTC, Newcastle upon Tyne, 35.85%	 
* Durham Johnston Comprehensive School, County Durham, 33.41%	 
* St Mary's Catholic School, Newcastle upon Tyne, 3.26%	 
* St Bede's Catholic School and Byron Sixth Form College, County Durham,  30.02%	 
* St Leonard's Catholic School, County Durham, 30.01%	 
* Jesmond Park Academy, Newcastle upon Tyne, 29.64%	 
* Macmillan Academy, Middlesbrough, 28.66%	 
* St Aidan's Catholic Academy, Sunderland, 27.17%	 
* Emmanuel Colleg, Gateshead, 27.15%	 
* Dyke House Sports and Technology College, Hartlepool, 27.01%	 

  
## Other Findings

### The A-Level enrolment percentages per region per science subject are as follows: ​
* London: Maths (32.71%), Chemistry (19.19%), Biology (21.52%) ​
* South East: Maths (27.36%), Chemistry (15.14%), Biology (19.54%) ​
* East of England: Maths (26.66%), Chemistry (14.84%), Biology (19.56%) ​
* West Midlands: Maths (25.87%), Chemistry (19.76%), Biology (24.09%) ​
* South West: Maths (25.31%), Chemistry (15.21%), Biology (21.39%)​


### The top 5 regions with the highest A-Level enrolment percentages in Maths are:
* London (32.71%)
* South East (27.36%) ​
* East of England (26.66%) ​
* West Midlands (25.87%) ​
* South West (25.31%) ​


### The top 5 regions with the highest A-Level enrolment percentages in Chemistry are:
* West Midlands (19.76%) ​
* London (19.19%)
* South West (15.21%) ​
* South East (15.14%) ​
* East of England (14.84%) ​


### The top 5 regions with the highest A-Level enrolment percentages in Biology are:
* West Midlands (24.09%) ​
* London (21.52%)
* South West (21.39%) ​
* South East (19.54%) ​
* East of England (19.56%) ​
