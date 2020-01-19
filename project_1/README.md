# ![](https://ga-dash.s3.amazonaws.com/production/assets/logo-9f88ae6c9c3871690e33280fcf557f33.png) Project 1: Standardized Testing, Statistical Summaries and Inference

### Problem Statement
The new format for the SAT was released in March 2016.  This report explores the state performance of SAT and ACT in the year of 2017 and 2018 and find areas where SAT participation rate can be improved.

## Data Dictionary

|Feature|Type|Dataset|Description|
|---|---|---|---|
|state|string|act_2017/sat_2017|one of the 51 states|
|participation_act_2017|float|act_2017|Participation rate of the test (%)|
|english_act_2017|float|act_2017|The state average of English test result|
|math_act_2017|float|act_2017|The state average of Math test result|
|reading_act_2017|float|act_2017|The state average of Reading test result|
|science_act_2017|float|act_2017|The state average of Science test result|
|composite_act_2017|float|act_2017|The state average of the overall result, composite is calculated by averaging the 4 tests|
|participation_sat_2017|float|sat_2017|Participation rate of the test (%)|
|ebrw_sat_2017|float|sat_2017|The state average of Evidence-Based Reading and Writing(ebrw) test result|
|math_sat_2017|float|sat_2017|The state average of Math test result|
|total_sat_2017|float|sat_2017|The state average of the overall result, which is the sum of the ebrw and math|

### Investigation
The data contains the SAT and ACT scores of 51 states between 2017 and 2018.  

SAT has 2 test components: Evidence-Based Reading and Writing and Math.  Total scores is the sum of the two test.

ACT has 4 test components: English, Math, Reading and Science.  The final score Composite is the average of the four tests.

Participation rates of each state is also included in both SAT and ACT results.

By performing descriptive analysis, States with SAT participation rate change were analyzed.  It highlights the difference observed from year to year. States with the lowest SAT participation rates are also looked into.

### Conclusion and Recommendation
SAT and ACT are two widely accepted tests for college admission. the number of states that requires SAT/ACT has been climbing steadily, in another words, other tests like PARCC are continuously eroding. However, it's noticed from the analysis that states that have 100% ACT participation rate, in return have very low participation rate in SAT. Although students have the options to choose the tests, once a state mandates a test, naturally the take-up rate of other tests would be low.

From the data, we can see SAT tests are gaining recognition as more states are accepting it as the compulsory test for high school graduands.

In order to improve SAT participation rate, we can focus on states that have the lowest SAT participation rate (<20%), but excludes those that already requires ACT

Lowest SAT participating states like Iowa, Kansas, New Mexico and South Dakota are in the direction to shift to SAT or ACT.
Partnering with individual state department and promoting SAT as the test for their high school students would be the direction to go.
