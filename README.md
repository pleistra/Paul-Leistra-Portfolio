# Paul Leistra, Data Analyst Portfolio

## About
Hi, I'm Paul! Thanks for checking out my portfolio!

I'm a detail-oriented mathematician who has taught high school math for the past 20+ years. And now it is time for a new challenge as I look to begin a second career as a data analyst.

Teaching and data analytics have a lot of the same core skills. I know how to explain technical ideas to a non-technical audience and how to keep my audience engaged. I can read an audience and adapt on the fly, as necessary. I communicate clearly and collobarate effectively.

In terms of some hard skills, I've taking courses in data analytics and data science (Google's Data Analytics certificate as well as a Data Science Certificate from the University of Waterloo). Through these courses and through some natural curiosity, I'm picking up skills in SQL, Python, R, Pandas, NumPy, Tableau, etc.

I'm looking to secure a data analyst position for summer or fall of 2025. I'm looking to join a team where I can be mentored, but also be expected to produce results.

Here's my [resume](Resume-PaulLeistra.pdf).

## New Course Study
The private high school I teach at is growing. So much so that we have the opportunity to add new courses to our program.
In addition to my role as math teacher, I am also a vice-principal at my school. The Board of Directors tasked me with spearheading the data-driven decision making process to determine which new course(s) we should consider offering.
I'm pleased to be able to have this real-life study as part of my portfolio.

### Problem Statement
Our school is growing and we need to add one to three new senior courses starting in September 2025. Create a proposal of which courses our school should consider adding.

### Data Collection
The Enrolment Study makes use of three datasets.
1. Enrolment data for all courses in publicly-funded Ontario Schools. The data came from Ontario's Open Source Data Catalogue.
2. Enrolment data for all grades in publicly-funded Ontario Schools. The data came from Ontario's Open Source Data Catalogue.
3. Enrolment data for courses at my school. I have not received permission from my school to share this data publicly, so I will only state some general conclusions that arose from this data.
4. Survey results from my school community. I have not received permission from my school to share this data publicly, so I will only state some general conclusions that arose from this data.

### Data Cleaning and Preprocessing
The data collected from the Ontario Open Source Data Catalogue was organized as separate files for each school year. The most recent data available is from the 2022-23 school year. 

BigQuery was used to clean the data:
1. Each Ontario course has a unique Course Code. INNER JOIN was used to get the data table that includes course codes and enrolment data for each year from 2015-16 to 2021-22.
2. Courses with an enrolment of fewer than 10 students were recorded as "<10". Each of these entries were assigned a value of 10.
3. Only data from senior classes was of interest for our school. A DISTINCT query on the “grade” column was used to determine if there were any unusual values in the grade column. There were not, so a WHERE query was used to retain only senior-level classes.
4. The table was a wide table; I changed it to a long table.
5. The first letter of each course code indicates the department of that course (eg: ADA1O is a course in the Arts department). A "department" column was engineered using CASE statements along with SUBSTR (course_code,1,1).

### Analysis/Modeling

#### Step 1
The enrolment of Ontario schools was graphed to check if any surprising trends have happened in the total enrolment in the province of Ontario. It turns out that enrolment in Ontario schools in Grades 11 and 12 has been relatively constant over the last eight years. Because of this, I chose to use actual enrolment numbers throughout the study rather than some value prorated on the number of students in the province in that year.

#### Step 2
I drilled down to the department level next. The relevance to the New Course Study is to determine if there are any departments that are seeing either:
1. Significantly more enrolment than at my school, proportionally, or
2. Significant growth that may indicate an important shift in education in Ontario.

The data told us that the Business department is under-represented at my school in terms of enrolment.

This aligned with results from our community survey, specifically about which departments our community was interested in seeing more offerings in. The dashboard is [here](https://public.tableau.com/app/profile/paul.leistra/viz/SurveyData-Departments/DeptDashboard3).

#### Step 3
I drilled down even further to the course level next. 

In this step, I considered which courses are popular in the province but are not offered at my school. The dashboard is [here](https://public.tableau.com/authoring/HistoricEnrolmentOntario/Dashboard1#1).

This helped to inform the community survey. Our community was asked to rate their interest in a list of particular courses the school is considering adding. The dashboard showing the most desired courses is [here](https://public.tableau.com/app/profile/paul.leistra/viz/SurveyData-Courses/LevelofInterestbyCourse).

### Recommendations
A recommendation for the addition of a Fitness course was approved by the Board of Directors. This course featured heavily in the school community survey, is currently under-represented at my school (compared to the provincial enrolment numbers), and is a course that we have the facilities and staffing to be able to implement quickly.

### Conclusions
The study was very much appreciated by our supporting community. Many respondants expressed appreciation for being involved in the decision making process. The Board also appreciated the process, so much so that a decision has been made to hold a bi-annual community survey.
