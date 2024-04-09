**SENG 637- Dependability and Reliability of Software Systems***

**Lab. Report \#5 – Software Reliability Assessment**

| Group \#: 1    |     
| -------------- | 
| Student Names: |     
| Romil Dhagat   | 
| Yajur Vashisht |    
| Clark Harrison Dy |  
| Nick Nikolov |  
| Yene Irvine | 

# Introduction

In this report we will be testing one software system using two sets of reliability testing tools. Failure data of a software system has been provided, and will be analyzed using both C-SFRAT and RDC. 

The first tool used is C-SFRAT, which contains built-in tools to guide the model selection process. The other reliability testing tool used is ‘Reliability Demonstration Chart (RDC)’. RDC-11 is a graphical tool used to plot testing data over time, and is used to determine if the target failure rate is passed or failed. The RDC plot helps determine if the system under test has reached an acceptable level of failure intensity. 

# Assessment Using Reliability Growth Testing 

![alt text](<SS1.png>)

![alt text](<SS2.png>)

![alt text](<SS3.png>)

![alt text](<SS4.png>)

## C-SFRAT Results
Result of model comparison (selecting top two models)

The two top models after using C-SFRAT and the provided data/model in the excel sheet were:

- S Distribution
- Truncated Logistic

Both of these models held the lowest AIC and BIC scores, 127.323 and 133.059, respectively.

Result of range analysis (an explanation of which part of data is good for proceeding with the analysis)	

The useful range of data was determined by examining the cumulative plot and excluding the initial steep curve, which represents an 'infant mortality' phase with high failure rates. The latter flat region suggests a period of relative stability in the system's performance, which was used for model fitting. This begins after interval 4 for the provided data.

A discussion on decision making given a target failure rate
Target failure rate has advantages and disadvantages when being utilized as a metric for software testing. 

The advantages include it has helped identify the most stable operational periods. It also helps developers in understanding and predicting system behavior as fixes and updates are implemented.

The disadvantages include model selection sensitivity for a range of data. Early system failures are skewed by model fitting, which can lead to optimistic reliability results. Additionally, the presence of significant variance in the failure intensity plot suggests that some external factors affecting reliability may not have been captured by the models.


# Assessment Using Reliability Demonstration Chart 

Failure Data Headers:
T - Time Interval
FC - Failure Count
E - Execution Time (in hours)
F - Failure Identification Work (in person hours)
C - Computer Time Failure Identification (in hours)

​
MTTF = Number of Failures / Total Operating Time
 = 93 failures / 54.3 hours
MTTF = 1.71

### Select the MTTF_Min for where the SUT becomes acceptable. MTTF = 5

![alt text](<SS5.png>)

### Set MTTF to twice of MTTF_min and plot the failure data. MTTF = 10

![alt text](<SS6.png>)

### Set MTTF to twice of MTTF_min and plot the failure data. MTTF = 2.5

![alt text](<SS7.png>)

Initial MTTF_Min was chosen as the scenario for which the SUT becomes acceptable. As shown in the first figure. Through trial and error this was determined to be approx. 5.

The use of an RDC is advantageous when we want to find out what the reliability trend of a system is, given that our failure data is limited to a few failures, and the time of failures are known. The RDC provides a versatile, time and cost efficient way of analyzing the reliability of the system by giving us a clear visual representation of the reliability improvement progress over time, making it easier to track and understand, which provides a guided assessment of risk. However, the use of an RDC is complex, and can be time-consuming to update, especially if there are frequent changes in the reliability testing. Additionally, RDC can’t be used to calculate an exact quantitative value for reliability of the SUT, and we are only provided with a result of accepted/rejected/needs more testing. 

# Comparison of Results

Comparing the results from the reliability growth testing and reliability demonstration chart (RDC) parts of the lab reveals distinct approaches to assessing system reliability. In the reliability growth testing section, C-SFRAT identified the top two models, S Distribution and Truncated Logistic, with the lowest AIC and BIC scores. The analysis also determined the useful range of data for model fitting, excluding the initial steep curve representing an 'infant mortality' phase. This approach emphasizes iterative improvement over time and model selection based on data fitting. Conversely, in the RDC section, the determination of MTTFmin was guided by the scenario where the system becomes acceptable, approximated at 5. RDC provides a visual representation of reliability trends over time, offering a quick assessment of system performance but lacks precise quantitative reliability values. While reliability growth testing focuses on predictive modeling and iterative improvement, RDC offers a snapshot view of reliability status, suitable for scenarios with limited failure data. Both approaches have their advantages and drawbacks, with reliability growth testing providing detailed modeling but requiring continuous updates, while RDC offers simplicity and quick assessment but lacks granularity in reliability quantification. Ultimately, the choice between reliability growth testing and RDC depends on factors such as available data, project requirements, and desired level of detail in reliability analysis.

# Discussion on Similarity and Differences of the Two Techniques

Reliability growth testing and reliability demonstration chart share fundamental objectives in assessing system reliability. Both methodologies use failure data collected during testing to analyze the system's performance and identify areas for improvement. They provide insights into the system's failure behavior, whether it's through continuous testing cycles in reliability growth testing or snapshot analysis at specific time points in RDC. Additionally, regardless of the specific tools used for each technique, they all analyze failure data and aid in the overall reliability assessment process.

Reliability growth testing and RDC differ in their methodologies and applications. Reliability growth testing involves continuous testing and analysis aimed at improving the system's reliability over time through iterative cycles of testing and refinement. In contrast, RDC provides a static view of the system's reliability status at specific time points, typically at the conclusion of testing phases or intervals, and assesses whether the observed failure rates meet reliability goals. While reliability growth testing focuses on predicting future reliability performance based on historical data and iterative improvement, RDC emphasizes compliance testing and certification processes, evaluating whether the system meets predefined reliability requirements.

Both techniques' overall goal is the same, to keep reliability up, however how they go about it and the insights gained are different. Using both in conjunction will help increase the reliability for the product being tested.


# How the team work/effort was divided and managed

The team's work and efforts were divided based on the complexity and nature of various aspects of the assignments. We used a buddy system for the assignment while splitting up the two techniques. This approach allowed all of the group to learn aspects of testing while being able to help other group members.

# Difficulties encountered, challenges overcome, and lessons learned

The main difficulty was setting up, understanding and executing the lab, this was due to the fact that there was some misunderstanding on the platforms used. There was an error in the installation of the software however once we overcame that issue the lab was pretty straight forward.

# Comments/feedback on the lab itself

This lab taught us how to assess system reliability through two methodologies: reliability growth testing and RDC.  By using tools like CASRE, SRTAT, or RDC-11, we learned to analyze failure data, measure failure rates, and understand key reliability metrics like MTTF or AIC scores.. Through practical exercises, we compared these techniques, gaining insights into their respective strengths and applications in system development and testing. 