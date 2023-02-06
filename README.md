 The aim of this report is to search Data Science jobs in the UK  and categorise them into either high paying or low paying, and identify key factors which have the most impact in the process.

 Data collection

 In order to collect the data we scraped (automated retrieval) the Indeed job search platform. We searched every city in the UK for a range of data related jobs and keywords (data scientist, data analyst, data engineer, machine learning, business intelligence, quantitive analyst, statistician). We retrieved the city, the job title, the salary and the job description.

 Data cleaning and feature engineering

 Once the data had been retrieved, it was cleaned by filling in any missing values where possible, or removing the data point if that was not possible, this left us with 1227 unique job listings.

 To determine what is considered high paying, we took the median of the salaries collected, anything above is considered high paying and anything below low paying.

 We also looked dissected the job, looking for key words in order to evaluate the level of the position, low (intern, trainee), low-mid (graduate or junior), mid (unspecified, for example ‘data scientist) or high level (senior, head or lead).

 In order to train our model and then test them on unseen data, the data set was split in two, 80% in the training section, 20% in the test section.

 Analysis

 We began by looking at the bearing location would have on the salary.  We used location as the sole predictor, and London was shown to be the greatest indicator of higher salary (55% of high salary jobs are in London, and only 39% of total jobs). The next cities likely to secure a higher salary are Gloucestershire, Basingstoke and Edinburgh, but they all lag significantly behind London. At the oppose end of the spectrum jobs in Newcastle were most likely to have a low salary, followed by Preston and Bath.

 The next step of the analysis was to examine the job level (determined from job title). As one would expect, high level jobs are indicative of a high salary. 76% of high level jobs are high salary. Logically, mid level jobs should follow but this isn’t the case. The data collected shows low level jobs are actually more likely to be high pay - I will address this more in the limitations section below. Following low level is mid level, then low to mid level.

 The next group of models carried out combined location and job level; they reinforced what the previous models told us; London is the biggest indicator of high pay, followed by a high job level, then Gloucestershire and Edinburgh. Having a job in Newcastle, Preston, or a low to mid level job would significantly increase the chance of low pay.

 Our most accurate model came from doing NLP (natural language processing) on the job description. This process breaks down the description into key words, counting each and assigning a weighting based on the value of each word at predicting the salary grade. Using this technique we can predict salary grade with 81% precision. Part of this process involved examining the most valuable words; we did this for all salary grades followed high and low individually. There are a lot of similarities; ‘data’, ‘business’ and ‘experience’ featuring heavily in both sets. Words which featured more predominantly in the high pay grade, but not as much in low pay grade, include ‘science’, ‘machine’, ‘python’, ‘models’ . These are technical words with particular skills attached. The low pay grade jobs have more weighting towards generic words, ‘work’, ‘support’, ‘reporting’, ‘analyst’.

 Limitations, risks and recommendations

 The main limitation to this report and these models is the high/low salary indicator is based on the median of all the jobs collected. In reality it would be best to compare jobs against similar ones, both in terms of seniority and location; comparing the salary of a  Lead data scientist in London against that of a data science intern in Newcastle has little merit. It would be more beneficial to know if a job has a high salary given it’s high level and in London. Another limitation is the scope of jobs added into this data set; the skills and salary of a Machine Learning engineer and a statistician might be vastly different, yet they are clumped into this dataset together.

 When determining job level we used fairly limited criteria, including assessing ‘assistant’ as a low level job - on examination, 3/22 low level jobs were contained ‘assistant’, all of which were in the high salary class.

 In order to improve, I recommend adjusting the consideration for high/low salary based on location and job level, and categorising job level more effectively.

 Conclusions

 Whilst the final model is effective at predicting a high/low salary, the limitations listed above are considerable and real world application is questionable.
