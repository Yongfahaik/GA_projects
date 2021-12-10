# ![](https://ga-dash.s3.amazonaws.com/production/assets/logo-9f88ae6c9c3871690e33280fcf557f33.png) Project 1: Improving SAT Participation Rates
By Yong Fah Aik

### Overview


The SAT has two sections of the test: Evidence-Based Reading and Writing and Math ([*source*](https://www.princetonreview.com/college/sat-sections)). The ACT has 4 sections: English, Mathematics, Reading, and Science, with an additional optional writing section ([*source*](https://www.act.org/content/act/en/products-and-services/the-act/scores/understanding-your-scores.html)). They have different score ranges, which you can read more about on their websites or additional outside sources (a quick Google search will help you understand the scores for each test):
* [SAT](https://collegereadiness.collegeboard.org/sat)
* [ACT](https://www.act.org/content/act/en.html)

Standardized tests have long been a controversial topic for students, administrators, and legislators. Since the 1940's, an increasing number of colleges have been using scores from sudents' performances on tests like the SAT and the ACT as a measure for college readiness and aptitude ([*source*](https://www.minotdailynews.com/news/local-news/2017/04/a-brief-history-of-the-sat-and-act/)). Supporters of these tests argue that these scores can be used as an objective measure to determine college admittance. Opponents of these tests claim that these tests are not accurate measures of students potential or ability and serve as an inequitable barrier to entry.

In 2016, the College Board made format, content and scoring changes to the SAT. 

With this in mind, the scoring sections are changed from the old format of three sections of Critical Reading, Writing and Math to the updated two sections of Evidence-Based Writing and Reading, and Math. The Essay portion of the SAT which was once part of the Writing section is now completely optional. With these two sections, the structure of the test is also adjusted to fit with the criteria.

The total scoring is then adjusted from the 600-2400 range to the new 400-1600 range. Another change is with regards to the guessing penalty, which was removed instead of the original $ \frac{1}{4} $.

### Problem Statement

The new format for the SAT was released in March 2016. As an employee of the College Board - the organization that manages and administers the SAT - I am a part of a team that tracks statewide participation and recommends where money is best spent to improve SAT participation rates. Since the introduction of the new format, levels of participation in the various states have changed with regards to the various legislative decisions.

This project is tasked with the exploration of the trends in SAT and ACT participation rates for the years 2017 to 2019, and seek to identify any trends that will help in the recommendations to the College Board on how to improve the participation rates in states with low or decreasing SAT participation rates.

---

### Datasets

#### Provided Data

There are 6 datasets utilized that are included in the [`data`](./data/) folder for this project. 

* [`act_2017.csv`](./data/act_2017.csv): 2017 ACT Scores by State ([source](https://blog.prepscholar.com/act-scores-by-state-averages-highs-and-lows))
* [`act_2018.csv`](./data/act_2018.csv): 2018 ACT Scores by State ([source](https://blog.prepscholar.com/act-scores-by-state-averages-highs-and-lows))
* [`act_2019.csv`](./data/act_2019.csv): 2019 ACT Scores by State ([source](https://blog.prepscholar.com/act-scores-by-state-averages-highs-and-lows))
* [`sat_2017.csv`](./data/sat_2017.csv): 2017 SAT Scores by State ([source](https://blog.collegevine.com/here-are-the-average-sat-scores-by-state/))
* [`sat_2018.csv`](./data/sat_2018.csv): 2018 SAT Scores by State ([source](https://blog.collegevine.com/here-are-the-average-sat-scores-by-state/))
* [`sat_2019.csv`](./data/sat_2019.csv): 2019 SAT Scores by State ([source](https://blog.prepscholar.com/average-sat-scores-by-state-most-recent))

---

### Data Dictionary
|Feature|Type|Dataset|Description|
|---|---|---|---|
|**state**|*object*|SAT 2017|The States of the country participating in SAT and ACT|
|**sat_part_17**|*float*|SAT 2017|The Participation Rate of students for the State for SAT 2017 (units percent to two decimal places, 0.02 means 2%)| 
|**sat_total_17**|*integer*|SAT 2017|The total mean score for the State for SAT 2017 (out of the possible score from 400 to 1,600)| 
|**sat_part_18**|*float*|SAT 2018|The Participation Rate of students for the State for SAT 2018 (units percent to two decimal places, 0.02 means 2%)|
|**sat_total_18**|*integer*|SAT 2018|The total mean score for the State for SAT 2018 (out of the possible score from 400 to 1,600)| 
|**sat_part_19**|*float*|SAT 2019|The Participation Rate of students for the State for SAT 2019 (units percent to two decimal places, 0.02 means 2%)| 
|**sat_total_19**|*integer*|SAT 2019|The total mean score for the State for SAT 2019 (out of the possible score from 400 to 1,600)| 
|**act_part_17**|*float*|ACT 2017|The Participation Rate of students for the State for ACT 2017 (units percent to two decimal places, 0.02 means 2%)| 
|**act_comp_17**|*float*|ACT 2017|The total composite score for the State for ACT 2017 (out of the possible score from 1 to 36)| 
|**act_part_18**|*float*|ACT 2017|The Participation Rate of students for the State for ACT 2018 (units percent to two decimal places, 0.02 means 2%)| 
|**act_comp_18**|*float*|ACT 2017|The total composite score for the State for ACT 2018 (out of the possible score from 1 to 36)| 
|**act_part_19**|*float*|ACT 2017|The Participation Rate of students for the State for ACT 2019 (units percent to two decimal places, 0.02 means 2%)| 
|**act_comp_19**|*float*|ACT 2017|The total composite score for the State for ACT 2019 (out of the possible score from 1 to 36)| 

---

### Conclusions and Recommendations

**Key takeaways:** 

1. *The Participation Rates for the SAT and ACT are inversely correlated, as such, when looking at the states with low SAT Participation Rates, these states will be likely to have high ACT Participation Rates.*
2. *There appears to be no relation between the current year's ACT Participation Rate to the Change in SAT Participation Rate from the current year to the next. Nor does there appear to be any relation between the current year's ACT Composite Score to the Change in the SAT Participation Rate from the current year to the next. As such we cannot use this to identify trends relating to how the Participation Rate will change from year to year.*
3. *Regarding the states with high ACT Participation Rates, as those states with near 100% ACT Participation Rates have made it compulsory to take ACT, our target states would have to shy away from these as it will be less cost-effective to do so. Taking this into account, our target states chosen for aid by the College Board would be Iowa, Kansas, New Mexico and Arizona as these states have low SAT Participation Rates while not having very high ACT Participation Rates.*

**Recommendations:** 

*By taking a look at the states with the drastic increases in SAT Participation Rates, we discover that these states either just made it compulsory to take the SAT or made it more accessible to the students through various policies. Judging from these successes in increasing the SAT Participation Rates, our recommendations will be as follows:*
- *Our targeted states for aid would be Iowa, Kansas and New Mexico* 
  1. *Working with the states to make SAT the compulsory test to take*
  2. *Working with the schools in the states in order to make SAT the more accessible test compared to ACT*
  3. *Covering all or part of the costs for taking the SAT test* 
