Inferential Statistics Report Regarding Goodreads Users
Elbion Redenica
Minerva University, San Francisco, CA, USA


INTRODUCTION	1
DATASET	2
ANALYSIS	3
Hypotheses	3
Summary Statistics	3
Conditions for Inference	5
Difference of Means Test	5
Confidence intervals	6
RESULTS AND CONCLUSIONS	7
REFERENCES	8
REFLECTION	8
APPENDIX	8
Appendix A: Import, Analyze, and Visualize Data	9
Appendix B: Examining the Subgroups	12
Appendix C: Difference of Means Test	15
Appendix D: Confidence Interval	16



INTRODUCTION
Reading is important and has countless benefits. If used effectively, reading allows us to improve our focus, memory, or communication skills while at the same time getting information about essentially anything we want. However, not everyone has the same reading preferences and experiences. Some like a specific form of writing, and others may prefer a specific genre. These preferences also lead to different reading experiences and influence readers' motivation. If one is unsure about their preferences, a great go-to for their next book inspiration is Goodreads. Goodreads is a popular website that allows users to review and rate books, and it has a large and active user base (Goodreads, 2019). After reading their recommended book from Goodreads, one can also go back and rate it on the platform. But what other factors influence one's rating toward a book on Goodreads? Is there a possibility that a bored or tired reader is frustrated by a book's length and rates the book low? Or do book lovers hate cliffhangers and enjoy reading the entire story to the last detail? This paper addresses the research question: "Do longer books have a lower average rating?" Longer books have a lower average rating because readers rate under the influence of emotions (i.e. frustration, tiredness) caused by a book’s length.

An analysis was conducted in CS50: Formal Analysis's "Assignment 2: Describing Data," and this statistics report is a continuation of it. While descriptive statistics and data visualization from the previous analysis suggest that long books have a higher average rating, this paper will expand the analysis on probability, distributions, confidence intervals, and significance. The population inferences are made about Goodreads’ book titles.

DATASET
Kaggle, a website that offers a range of tools and resources for data scientists and serves as a public data platform, offers a dataset of over 10,000 titles from Goodreads. This paper works with a sample of 200 titles from that dataset, the same used for the previous assignment, which can be found here. Since this paper focuses on whether long books are associated with low average ratings, two variables are most relevant for the analysis. Book length ("num_pages") is used as the independent variable and is a quantitative discrete variable whose input is whole, concrete numbers for the book pages (e.g., there cannot be 346.2 pages in a book). The dependent variable is the average rating in Goodreads ("average_rating"). This variable is measured by taking the values of all ratings and dividing them by the number of them to find the average rating for each book. We will treat "average_rating" as a quantitative discrete variable because it has a limited scope of valid values (0.00-5.00 with two decimals). If we were to count all these values, we would spend a finite amount of time doing so since we have specific values a user can type in as a set of rational numbers. A good analogy with book ratings is GPA, where the latter is also considered a discrete variable. 

ANALYSIS
Hypotheses
A difference of means significance test is performed to address the research question of whether the average book rating is different for long books. Book length ("num_pages") as a variable is divided into two subgroups, "shortBooks" (number of pages < 350) and "longBooks" (number of pages ≥ 350). The significance level is set to default, α =0.05. The hypotheses are defined as follows:
H0: μlongBooks ratings= μshortBooks ratings 
HA: μlongBooks ratings< μshortBooks ratings 

This is a one-tailed test because I am looking for a difference in the negative direction as I claim the average rating is lower for long books.
Summary Statistics
The dataset was read in Python using the pandas package for analysis. Before proceeding with hypothesis testing, descriptive statistics for the subgroups are examined. Appendix A provides summary statistics for the general dataset, and Appendix B shows the calculations for the subgroups regarding this report’s purposes. Table 1 shows summary statistics for each subgroup. Figures 1 and 2 show the sample distribution for each group.

Table 1: Summary statistics for the average rating for our two sample groups: short books (number of book pages < 350) and long books (number of book pages ≥ 350). 



Short books (shortBooks)
Long books (longBooks)
Count
n1=120
n2=80
Mean
x1=3.90
x2=4.03
Median
3.95
4.025
Mode
3.95
4.0
Standard Deviation
s1=0.32
s2=0.22
Range
2.02
1.02



Figure 1. Histogram for long books (book length ≥ 350 pages)


Figure 2. Histogram for short books (book length < 350 pages)

Conditions for Inference
Since I am estimating the standard error using the sample standard deviation, I choose to use the t-distribution. The t-distribution is more robust to the effects of small sample sizes (for n<30) and when the population standard deviation is unknown. 

The conditions to satisfy the usage of t-distribution for inference are:
The sample size is small (less than 30).
The population standard deviation is unknown.
The data are approximately normally distributed.

While my sample size is greater than 30, the population standard deviation is unknown, and an approximately normal distribution is seen. Therefore, I use the t-distribution as my sampling distribution because it allows us to make more accurate inferences about the population mean.
Difference of Means Test
To assess statistical significance, I compute the T-score to see if the difference in means between the two groups is statistically significant. To do so, I first compute the T-score using the usual formula for a difference of means test, where SE is the standard error of the difference between the means. 

T = longBooks rating - shortBooks ratingSE

I take a conservative estimate for the degrees of freedom of the t-distribution, where n1 and n2 are the sizes of the two groups. 

df = min(n1, n2) - 1

The T-score of 3.49 means that the difference in means is 3.49 standard errors away from zero, resulting in a one-tailed p-value of 0.0004 < 0.05. This p-value represents the probability that the difference in means between the two groups would be this large or larger if there were no actual differences between the groups. Thus, I conclude that the data favors the alternative hypothesis that there is a significant difference in means between the two groups.

To assess practical significance, I need a measure of effect size. Here, I choose Hedge’s g because it is a standardized measure that can be compared across different studies. Computing Hedge’s g requires the pooled standard deviation,

spooled=(n1-1)s12+ (n2-1)s22n1+ n2 - 2

…where s1 and s2 are the standard deviations of the two groups. The calculation of g produces an effect size of 0.466. Thus, I can say that the effect size is moderate, indicating that the difference in means between the two groups is not just statistically significant but also practically significant. In the context of the average book ratings, the difference in means is of moderate practical importance.
Confidence intervals
I continue examining the hypotheses by constructing a confidence interval for each subgroup's mean book average rating, long books and short books. These intervals will provide plausible ranges of values for the mean of each group. The confidence interval is 95% because we set our significance level to 0.05. Since the conditions mentioned above for inference are checked, and the confidence interval calculations are validated, I use the t-distribution for inference. 

To compute the confidence interval for the mean book average rating of each group, I use the following:

CI=[-zSE, -zSE]

…where CI is the confidence interval, mean is the sample mean, z is the z-score for the chosen confidence level, and SE is the standard error of the mean. The z-score for a 95% confidence interval is 1.96. I compute the standard error using the following:

SE=sn

…where s is the sample standard deviation and n is the sample size. The full calculation can be found in Appendix C. The resulting 95% confidence intervals for each group, rounded to two decimal places, are:
Short books: [3.19, 4.60]
Long books: [3.13, 4.92]
For each interval, I can be 95% confident that the true population mean lies within the interval. This means that I am 95% confident that the mean book average rating for short books is between 3.19 and 4.60, and for long books is between 3.13 and 4.92. The fact that the two intervals overlap means that they are not statistically significant.

RESULTS AND CONCLUSIONS
The average book rating among long and short books is examined in this report concerning the research question. Based on the result of the test of statistical and practical significance between the subgroups (p=0.0004, g=0.466), there is evidence to suggest that the null hypothesis is false; hence, it should be rejected. However, this was not supported by the confidence intervals for the two subgroups as they would overlap: [3.19, 4.60] and [3.13, 4.92]. According to Greenland et al. (2016), saying that if two confidence intervals overlap, the difference between the two hypotheses is not significant is incorrect. Therefore, for this report's purposes, I am concluding that, indeed, the null hypothesis is rejected. 

These conclusions are inductive because they are based on a population sample and are used to make inferences about the population as a whole. Yet they are strong because the p-value and effect size indicate that the observed difference between the groups is statistically and practically significant (moderately, according to Cohen). However, the reliability of the conclusions can be questioned because of the limitations mentioned above, such as the mismatch between the confidence intervals and the p-value test.

In summary, I have shown that there is a significant difference in average book ratings between long books and short books on Goodreads. To further investigate this matter, one should follow up by conducting a more comprehensive and rigorous study, conducting more tests to mitigate the limitations, which would allow one to more confidently and accurately conclude whether there is a significant difference in average book ratings between long books and short books in Goodreads.
REFERENCES
Goodreads. (2019). About Goodreads. Goodreads.com. https://www.goodreads.com/about/us
Greenland, S., Senn, S. J., Rothman, K. J., Carlin, J. B., Poole, C., Goodman, S. N., & Altman, D. G. (2016). Statistical tests, P values, confidence intervals, and power: a guide to misinterpretations. European Journal of Epidemiology, 31(4), 337–350. https://doi.org/10.1007/s10654-016-0149-3

REFLECTION
To determine the soundness of the statistical analysis, the assumptions of the statistical tests and methods are checked. For instance, in the case of a t-test, I assumed the normality of data, which were checked to be approximately true by #dataviz. Inductively, if the assumption of normality is satisfied, then the t-scores for the confidence intervals or significance test are likely to be accurate.

I appreciate Prof. Stan's class instructions and the feedback from Class Assessments in Forum, which helped me better understand the overall Unit on Probability and Statistics. I also thank Dilnaz, CS peer tutor, for her help with my hypothesis and other classmates (Godson, George, and Salome), whom I had discussions with regarding the issue of the confidence interval and p-value mismatch. 

APPENDIX
The full Jupyter notebook file and the data can be accessed in the zipped folder submitted as a secondary file. This project can also be found at my GitHub repository.
Appendix A: Import, Analyze, and Visualize Data










Appendix B: Examining the Subgroups




Appendix C: Difference of Means Test



Appendix D: Confidence Interval


