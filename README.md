# Paul Leistra, Data Analyst Portfolio

## About
Hi, I'm Paul! Thanks for checking out my portfolio!

I'm a detail-oriented mathematician who has taught high school math for the past 20+ years. And now it is time for a new challenge as I look to begin a second career as a data analyst.

Teaching and data analytics have a lot of the same core skills. I know how to explain technical ideas to a non-technical audience and how to keep my audience engaged. I can read an audience and adapt on the fly, as necessary. I communicate clearly and collobarate effectively.

In terms of some hard skills, I'm taking courses in data analytics and data science (Google's Data Analytics certificate as well as a Data Science Certificate from the University of Waterloo). Through these courses and through some natural curiosity, I'm picking up skills in SQL, Python, R, Pandas, NumPy, Tableau, etc. I have a strong mathematical mind (I ranked in the top 200 of all math students in North America in the Putnam math contest in my undergraduate career).

I'm looking to secure an entry-level data analyst position for summer or fall of 2025. I know I have a lot to learn, and am looking to join a team where I can be mentored but also be expected to produce results.

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
2. Courses with an enrolment of fewer than 10 students were recorded as "<10". Each of these entries were
3. Only data from senior classes was of interest for our school. A DISTINCT query on the “grade” column was used to determine if there were any unusual values in the grade column. There were not, so a WHERE query was used to retain only senior-level classes.
4. The table was a wide table; I changed it to a long table.
5. The first letter of each course code indicates the department of that course (eg: ADA1O is a course in the Arts department). A "department" column was engineered using CASE statements along with SUBSTR (course_code,1,1).

### Analysis/Modeling

#### Step 1
The enrolment of Ontario schools was graphed to check if any surprising trends have happened in the total enrolment in the province of Ontario.

The visualization is available [here](https://public.tableau.com/views/OntarioSecondarySchoolEnrolment/Dashboard2?:language=en-US&:sid=&:redirect=auth&:display_count=n&:origin=viz_share_link).

The graph shows that enrolment in Ontario schools in Grades 11 and 12 has been relatively constant over the last eight years. Because of this, I chose to use actual enrolment numbers throughout the study rather than some value prorated on the number of students in the province in that year (ie: I did not use per capita data).

#### Step 2
I drilled down to the department level next. The relevance to the New Course Study is to determine if there are any departments that are seeing either:
1. Significantly more enrolment than at my school, proportionally, or
2. Significant growth that may indicate an important shift in education in Ontario.

The visualization is available [here](https://public.tableau.com/views/OntarioSecondarySchoolEnrolment-Departments/Sheet1?:language=en-US&:sid=&:redirect=auth&:display_count=n&:origin=viz_share_link).

There data tells us several interesting things with respect to my school.
1. There was a department that is under-represented at my school in terms of enrolment (this became evident through this visualization when compared to data collected from my school)
2. There are two departments that have been experiencing growth in the last several years - Computers and First Nations, Metis and Inuit Studies.

As an aside, there are two additional patterns that could be very much of interest to another study, but is beyond the scope of this study.
1. Several departments saw a dramatic drop in enrolment in the 2020-21 school year. Among these are Arts, Physical Education, and Technology. This coincides with the Covid pandemic, and it is noticeable that these are all more "hands-on" courses. The effect of this blip, if any, could be the topic of another study.
2. The department of First Nations, Metis and Inuit Studies has seen very dramatic growth over the timeframe of this study. A valuable study would be to determine why this has happened, and to leverage that in other areas departments lag behind what policy makers and educators would like to see.

#### Step 3
I drilled down even further to the course level next. This data was used in conjunction with data from the survey of my school community. In the survey, there was a list of courses that our stakeholders (students, recent graduates, parents, teachers) would be interested in possibly adding to our program. Provincial enrolments in these courses helped inform the recommendations of the New Course Study.

Most of the analysis of this section makes use of the survey data from my school, which I've not been given permission to share, so I will simply show the visualization of enrolment by course. Admittedly, the visualization is a little clunky since there are so many courses in Ontario, but it was used to hone in on a few key courses that arose from the community survey.

The visualization is [here](https://public.tableau.com/views/EnrolmentbyCourse/Sheet1?:language=en-US&:sid=&:redirect=auth&:display_count=n&:origin=viz_share_link).

#### Step 4
Finally, I considered a list of the Ontario courses with the greatest enrolment that are not offered at my school. For example, HSP3U has had over 260,000 students registered in that course over the timeframe of the New Course Study. Any courses with more than that level of enrolment are already offered at my school.

The visualization is [here](https://public.tableau.com/views/HistoricEnrolmentOntario/Dashboard1?:language=en-US&:sid=&:redirect=auth&:display_count=n&:origin=viz_share_link).

### Recommendations
Recommendations for the addition of two new courses was made to the Board of Directors. Both courses featured heavily in the school community survey, and are either currently under-represented at my school or have seen rapid growth in the province over the last several years.

Recommendations included things like: how the course supports our school's mission and vision; budget implications; staffing implications; and physical space implications.

### Conclusions
If all goes as planned, the final decision will be received from our Board of Directors in December 2024 for implementation in September 2025.
