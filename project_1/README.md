# Project 1: Standardized Test Analysis

# Problem Statement

The aim of this study is to determine whether ACT and SAT have good predictive validity. ACT and SAT scores will be compared with GPA scores by college. 


## Data Dictionary

|Feature|Type|Dataset|Description|
|---|---|---|---|
|state|object|sat_act_2017|US states|
|sat2017_part|float|sat_act_2017|participation rates of the entire high school population taking SAT in 2017 by state|
|sat2017_total|int|sat_act_2017|total SAT scores in 2017 by state|
|act2017_part|float|sat_act_2017|participation rates of the entire high school population taking ACT in 2017 by state|
|act2017_ave|float|sat_act_2017|average ACT scores in 2017 by state|
|state|object|sat_act_2018|US states|
|sat2018_part|float|sat_act_2018|participation rates of the entire high school population taking SAT in 2018 by state|
|sat2018_total|int|sat_act_2018|total SAT scores in 2018 by state|
|act2018_part|int|sat_act_2018|participation rates of the entire high school population taking ACT in 2018 by state|
|act2018_ave|float|sat_act_2018|average ACT scores in 2018 by state|
|college|object|college_merged|colleges in the US|
|admissions|float|college_merged|admissions rate by college|
|act_mid|float|college_merged|median ACT scores by college|
|sat_ave|float|college_merged|average SAT scores by college|
|ave_gpa|float|college_merged|average GPA scores by college|



## Summary of results
* There is a positive correlation between both standardised tests (SAT and ACT test scores) with the college GPA scores. Therefore, these tests can predict academic performance in college.
* The correlation between both tests (SAT and ACT test scores) with college GPA scores were similar. 
<br> * There is a myth that prestigious colleges, like those in the Ivy League prefer the SAT over the ACT. While many university admissions offices have publicly stated that this is not true, the results shown here demonstrates that both the SAT and ACT do have similar predictive validity, and both can be regarded as similar in predicting academic success in college.
* Colleges who are highly selective, such as the Ivy League admits students with higher SAT and ACT scores, which also leads to higher GPA scores.
<br> * This relationship has been addressed as the Swimmer’s Body Illusion (Dobelli, Rolf (2013). The art of thinking clearly. Sceptre: London). Graduates from the Ivy League are highly successful. This does not mean that these colleges are excellent schools. It is because these colleges admit only the best and the brightest individuals.



## Conclusion and Recommendations
Admittedly, standardized tests are far from perfect. They cannot capture students' attitudes, such as being punctual to class, handing in assignments, etc. However, getting rid of them altogether is not beneficial to colleges who aims to determine the academic potential of incoming students. Furthermore, there could be a wide variation in grading standards between high schools. 
<br> The results here showed that there is a correlation between SAT scores and college GPA scores. Similarly, there is a correlation between ACT scores and college GPA scores. In addition, both SAT and ACT scores are similar in predicting future academic success in students entering college. 
<br> Unless there is a better way to predict a college student's success, removing standardised tests such as the SAT and ACT tests will not enable colleges to make better decisions during student admissions. Moreover, highly selective colleges who admits the most intelligent students, also produce high-performing graduates. 








