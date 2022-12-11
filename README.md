<h2>INFERENTIAL STATISTICS REPORT REGARDING GOODREADS USERS</h2>


<p>Elbion Redenica
</p>
<p>
Minerva University, San Francisco, CA, USA
</p>
<h3>INTRODUCTION</h3>


<p>
Reading is important and has countless benefits. If used effectively, reading allows us to improve our focus, memory, or communication skills while at the same time getting information about essentially anything we want. However, not everyone has the same reading preferences and experiences. Some like a specific form of writing, and others may prefer a specific genre. These preferences also lead to different reading experiences and influence readers' motivation. If one is unsure about their preferences, a great go-to for their next book inspiration is Goodreads. Goodreads is a popular website that allows users to review and rate books, and it has a large and active user base (Goodreads, 2019). After reading their recommended book from Goodreads, one can also go back and rate it on the platform. But what other factors influence one's rating toward a book on Goodreads? Is there a possibility that a bored or tired reader is frustrated by a book's length and rates the book low? Or do book lovers hate cliffhangers and enjoy reading the entire story to the last detail? This paper addresses the research question: "Do longer books have a lower average rating?"<strong> </strong>Longer books have a lower average rating because readers rate under the influence of emotions (i.e. frustration, tiredness) caused by a book’s length.
</p>
<p>
An analysis was conducted in CS50: Formal Analysis's "Assignment 2: Describing Data," and this statistics report is a continuation of it. While descriptive statistics and data visualization from the previous analysis suggest that long books have a higher average rating, this paper will expand the analysis on probability, distributions, confidence intervals, and significance. The population inferences are made about Goodreads’ book titles.
</p>
<h3>DATASET</h3>


<p>
Kaggle, a website that offers a range of tools and resources for data scientists and serves as a public data platform, offers a <a href="https://www.kaggle.com/datasets/jealousleopard/goodreadsbooks">dataset</a> of over 10,000 titles from Goodreads. This paper works with a sample of 200 titles from that dataset, the same used for the previous assignment, which can be found <a href="https://drive.google.com/drive/folders/1_gBg5oGivKhjNFgrbIoHogKeQHVtPdFs">here</a>. Since this paper focuses on whether long books are associated with low average ratings, two variables are most relevant for the analysis. Book length ("num_pages") is used as the independent variable and is a quantitative discrete variable whose input is whole, concrete numbers for the book pages (e.g., there cannot be 346.2 pages in a book). The dependent variable is the average rating in Goodreads (<code>"average_rating"</code>). This variable is measured by taking the values of all ratings and dividing them by the number of them to find the average rating for each book. We will treat "average_rating" as a quantitative discrete variable because it has a limited scope of valid values (0.00-5.00 with two decimals). If we were to count all these values, we would spend a finite amount of time doing so since we have specific values a user can type in as a set of rational numbers. A good analogy with book ratings is GPA, where the latter is also considered a discrete variable.<sup id="fnref1"><a href="#fn1" rel="footnote">1</a></sup> 
</p>
<h3>ANALYSIS</h3>


<h4>Hypotheses</h4>


<p>
A difference of means significance test is performed to address the research question of whether the average book rating is different for long books. Book length ("num_pages") as a variable is divided into two subgroups, "shortBooks" (number of pages < 350) and "longBooks" (number of pages ≥ 350). The significance level is set to default, α = 0.05. The hypotheses are defined as follows:
</p>
<ul>


$$H_{0}:\mu _{longBooks ratings}=\mu _{shortBooks ratings}$$

   

$$H_{A}:\mu _{longBooks ratings}<\mu _{shortBooks ratings}$$

</ul>
<p>
This is a one-tailed test because I am looking for a difference in the negative direction as I claim the average rating is lower for long books.
</p>
<h4>Summary Statistics</h4>


<p>
The dataset was read in Python using the pandas package for analysis. Before proceeding with hypothesis testing, descriptive statistics for the subgroups are examined. Appendix A provides summary statistics for the general dataset, and Appendix B shows the calculations for the subgroups regarding this report’s purposes. Table 1 shows summary statistics for each subgroup.<sup id="fnref2"><a href="#fn2" rel="footnote">2</a></sup> Figures 1 and 2 show the sample distribution for each group.<sup id="fnref3"><a href="#fn3" rel="footnote">3</a></sup>
</p>
<p>

</p>

<table>
  <tr>
   <td colspan="3" ><strong>Table 1: Summary statistics for the average rating for our two sample groups: short books (number of book pages < 350) and long books (number of book pages</strong> ≥ <strong>350). </strong>
   </td>
  </tr>
  <tr>
   <td>
   </td>
   <td>Short books (<code>shortBooks</code>)
   </td>
   <td>Long books (<code>longBooks</code>)
   </td>
  </tr>
  <tr>
   <td>Count
   </td>
   <td>
$$n_{1}=120$$
   </td>
   <td>
$$n_{1}=80$$
   </td>
  </tr>
  <tr>
   <td>Mean
   </td>
   <td>
$$\overline{x}_{1}=3.90$$
   </td>
   <td>
$$\overline{x}_{2}=4.03$$
   </td>
  </tr>
  <tr>
   <td>Median
   </td>
   <td>
$$3.95$$
   </td>
   <td>
$$4.025$$
   </td>
  </tr>
  <tr>
   <td>Mode
   </td>
   <td>
$$3.95$$
   </td>
   <td>
$$4.0$$
   </td>
  </tr>
  <tr>
   <td>Standard Deviation
   </td>
   <td>
$$s_{1}=0.32$$
   </td>
   <td>
$$s_{2}=0.22$$
   </td>
  </tr>
  <tr>
   <td>Range
   </td>
   <td>
$$2.02$$
   </td>
   <td>
$$1.02$$
   </td>
  </tr>
</table>


```

# using numpy's np.array() to create an array and plot it in a histogram
# # average ratings for books >= 350
# # dataAboveThreshold.average_rating, dataAboveThreshold.num_pages
averageRatingsAboveThreshold = np.array(dataAboveThreshold.average_rating)
plt.hist(averageRatingsAboveThreshold, bins, facecolor='r', alpha=0.7, edgecolor='k', linewidth=0)
plt.xlabel("Average Rating")
plt.ylabel("Frequency")
plt.xticks(bins[::1]) 
plt.xticks(rotation = 45)
plt.show()   
   
```

<center><img src="https://i.imgur.com/lPy3pE0.png" width="" alt="alt_text" title="image_tooltip"></center>

</p>
<p>
<strong>Figure 1.</strong> Histogram for long books (book length ≥ 350 pages)
</p>
<p>


<p id="gdcalert16" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: inline image link here (to images/image2.png). Store image on your image server and adjust path/filename/extension if necessary. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert17">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>


<img src="img/figure.png" width="" alt="alt_text" title="image_tooltip">

</p>
<p>
<strong>Figure 2.</strong> Histogram for short books (book length < 350 pages)
</p>
<h4>Conditions for Inference</h4>


<p>
Since I am estimating the standard error using the sample standard deviation, I choose to use the t-distribution. The t-distribution is more robust to the effects of small sample sizes (for n<30) and when the population standard deviation is unknown. 
</p>
<p>
The conditions to satisfy the usage of t-distribution for inference are:
</p>
<ul>

<li>The sample size is small (less than 30).

<li>The population standard deviation is unknown.

<li>The data are approximately normally distributed.
</li>
</ul>
<p>
While my sample size is greater than 30, the population standard deviation is unknown, and an approximately normal distribution is seen. Therefore, I use the t-distribution as my sampling distribution because it allows us to make more accurate inferences about the population mean.<sup id="fnref4"><a href="#fn4" rel="footnote">4</a></sup>
</p>
<h4>Difference of Means Test</h4>


<p>
To assess statistical significance, I compute the T-score to see if the difference in means between the two groups is statistically significant. To do so, I first compute the T-score using the usual formula for a difference of means test, where $$SE$$ is the standard error of the difference between the means. 
</p>
<p>

$$T=\dfrac{\mu _{longBooks ratings}-\mu _{shortBooks ratings}}{SE}$$


</p>
<p>
I take a conservative estimate for the degrees of freedom of the t-distribution, where 

<p id="gdcalert19" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: equation: use MathJax/LaTeX if your publishing platform supports it. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert20">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>

 and 

<p id="gdcalert20" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: equation: use MathJax/LaTeX if your publishing platform supports it. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert21">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>

 are the sizes of the two groups. 
</p>
<p>


<p id="gdcalert21" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: equation: use MathJax/LaTeX if your publishing platform supports it. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert22">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>


</p>
<p>
The T-score of 3.49 means that the difference in means is 3.49 standard errors away from zero, resulting in a one-tailed p-value of 0.0004 < 0.05. This p-value represents the probability that the difference in means between the two groups would be this large or larger if there were no actual differences between the groups.<sup id="fnref5"><a href="#fn5" rel="footnote">5</a></sup> Thus, I conclude that the data favors the alternative hypothesis that there is a significant difference in means between the two groups.
</p>
<p>
To assess practical significance, I need a measure of effect size. Here, I choose Hedge’s g because it is a standardized measure that can be compared across different studies. Computing Hedge’s g requires the pooled standard deviation,
</p>
<p>


<p id="gdcalert22" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: equation: use MathJax/LaTeX if your publishing platform supports it. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert23">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>


</p>
<p>
…where 

<p id="gdcalert23" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: equation: use MathJax/LaTeX if your publishing platform supports it. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert24">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>

 and 

<p id="gdcalert24" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: equation: use MathJax/LaTeX if your publishing platform supports it. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert25">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>

 are the standard deviations of the two groups. The calculation of g produces an effect size of 0.466. Thus, I can say that the effect size is moderate, indicating that the difference in means between the two groups is not just statistically significant but also practically significant. In the context of the average book ratings, the difference in means is of moderate practical importance.<sup id="fnref6"><a href="#fn6" rel="footnote">6</a></sup>
</p>
<h4>Confidence Intervals</h4>


<p>
I continue examining the hypotheses by constructing a confidence interval for each subgroup's mean book average rating, long books and short books. These intervals will provide plausible ranges of values for the mean of each group. The confidence interval is 95% because we set our significance level to 0.05. Since the conditions mentioned above for inference are checked, and the confidence interval calculations are validated, I use the t-distribution for inference. 
</p>
<p>
To compute the confidence interval for the mean book average rating of each group, I use the following:
</p>
<p>


<p id="gdcalert25" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: equation: use MathJax/LaTeX if your publishing platform supports it. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert26">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>



<p id="gdcalert26" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: equation: use MathJax/LaTeX if your publishing platform supports it. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert27">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>

]
</p>
<p>
…where 

<p id="gdcalert27" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: equation: use MathJax/LaTeX if your publishing platform supports it. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert28">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>

is the confidence interval, mean is the sample mean, 

<p id="gdcalert28" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: equation: use MathJax/LaTeX if your publishing platform supports it. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert29">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>

 is the z-score for the chosen confidence level, and 

<p id="gdcalert29" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: equation: use MathJax/LaTeX if your publishing platform supports it. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert30">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>

is the standard error of the mean. The z-score for a 95% confidence interval is 1.96. I compute the standard error using the following:
</p>
<p>


<p id="gdcalert30" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: equation: use MathJax/LaTeX if your publishing platform supports it. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert31">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>


</p>
<p>
…where 

<p id="gdcalert31" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: equation: use MathJax/LaTeX if your publishing platform supports it. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert32">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>

is the sample standard deviation and n is the sample size. The full calculation can be found in Appendix C.<sup id="fnref7"><a href="#fn7" rel="footnote">7</a></sup> The resulting 95% confidence intervals for each group, rounded to two decimal places, are:
</p>
<ul>

<li>Short books: [3.19, 4.60]

<li>Long books: [3.13, 4.92]
</li>
</ul>
<p>
For each interval, I can be 95% confident that the true population mean lies within the interval. This means that I am 95% confident that the mean book average rating for short books is between 3.19 and 4.60, and for long books is between 3.13 and 4.92. The fact that the two intervals overlap means that they are not statistically significant.
</p>
<h3>RESULTS AND CONCLUSIONS</h3>


<p>
The average book rating among long and short books is examined in this report concerning the research question. Based on the result of the test of statistical and practical significance between the subgroups (p=0.0004, g=0.466), there is evidence to suggest that the null hypothesis is false; hence, it should be rejected. However, this was not supported by the confidence intervals for the two subgroups as they would overlap: [3.19, 4.60] and [3.13, 4.92]. According to Greenland et al. (2016), saying that if two confidence intervals overlap, the difference between the two hypotheses is not significant is incorrect. Therefore, for this report's purposes, I am concluding that, indeed, the null hypothesis is rejected.<sup id="fnref8"><a href="#fn8" rel="footnote">8</a></sup> 
</p>
<p>
These conclusions are inductive because they are based on a population sample and are used to make inferences about the population as a whole. Yet they are strong because the p-value and effect size indicate that the observed difference between the groups is statistically and practically significant (moderately, according to Cohen). However, the reliability of the conclusions can be questioned because of the limitations mentioned above, such as the mismatch between the confidence intervals and the p-value test.<sup id="fnref9"><a href="#fn9" rel="footnote">9</a></sup>
</p>
<p>
In summary, I have shown that there is a significant difference in average book ratings between long books and short books on Goodreads. To further investigate this matter, one should follow up by conducting a more comprehensive and rigorous study, conducting more tests to mitigate the limitations, which would allow one to more confidently and accurately conclude whether there is a significant difference in average book ratings between long books and short books in Goodreads.
</p>
<h3></h3>


<h3>REFERENCES</h3>


<p>

    Goodreads. (2019). <em>About Goodreads</em>. Goodreads.com. <a href="https://www.goodreads.com/about/us">https://www.goodreads.com/about/us</a>
</p>
<p>

    Greenland, S., Senn, S. J., Rothman, K. J., Carlin, J. B., Poole, C., Goodman, S. N., & Altman, D. G. (2016). Statistical tests, P values, confidence intervals, and power: a guide to misinterpretations. <em>European Journal of Epidemiology</em>, <em>31</em>(4), 337–350. <a href="https://doi.org/10.1007/s10654-016-0149-3">https://doi.org/10.1007/s10654-016-0149-3</a>
</p>
<h3>REFLECTION</h3>


<p>
To determine the soundness of the statistical analysis, the assumptions of the statistical tests and methods are checked. For instance, in the case of a t-test, I assumed the normality of data, which were checked to be approximately true by #dataviz. Inductively, if the assumption of normality is satisfied, then the t-scores for the confidence intervals or significance test are likely to be accurate.
</p>
<p>
I appreciate Prof. Stan's class instructions and the feedback from Class Assessments in Forum, which helped me better understand the overall Unit on Probability and Statistics. I also thank Dilnaz, CS peer tutor, for her help with my hypothesis and other classmates (Godson, George, and Salome), whom I had discussions with regarding the issue of the confidence interval and p-value mismatch. 
</p>
<h3>APPENDIX</h3>


<p>
The full Jupyter notebook file and the data can be accessed in the zipped folder submitted as a secondary file. This project can also be found at my <a href="https://github.com/elbionredenica/statisticalinference_goodreads">GitHub repository</a>.<sup id="fnref10"><a href="#fn10" rel="footnote">10</a></sup>
</p>
<h4>Appendix A: Import, Analyze, and Visualize Data</h4>


<p>


<p id="gdcalert32" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: inline image link here (to images/image3.png). Store image on your image server and adjust path/filename/extension if necessary. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert33">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>


<img src="images/image3.png" width="" alt="alt_text" title="image_tooltip">

</p>
<p>


<p id="gdcalert33" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: inline image link here (to images/image4.png). Store image on your image server and adjust path/filename/extension if necessary. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert34">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>


<img src="images/image4.png" width="" alt="alt_text" title="image_tooltip">

</p>
<p>


<p id="gdcalert34" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: inline image link here (to images/image5.png). Store image on your image server and adjust path/filename/extension if necessary. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert35">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>


<img src="images/image5.png" width="" alt="alt_text" title="image_tooltip">

</p>
<p>


<p id="gdcalert35" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: inline image link here (to images/image6.png). Store image on your image server and adjust path/filename/extension if necessary. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert36">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>


<img src="images/image6.png" width="" alt="alt_text" title="image_tooltip">

</p>
<p>


<p id="gdcalert36" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: inline image link here (to images/image7.png). Store image on your image server and adjust path/filename/extension if necessary. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert37">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>


<img src="images/image7.png" width="" alt="alt_text" title="image_tooltip">

</p>
<p>


<p id="gdcalert37" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: inline image link here (to images/image8.png). Store image on your image server and adjust path/filename/extension if necessary. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert38">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>


<img src="images/image8.png" width="" alt="alt_text" title="image_tooltip">

</p>
<p>


<p id="gdcalert38" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: inline image link here (to images/image9.png). Store image on your image server and adjust path/filename/extension if necessary. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert39">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>


<img src="images/image9.png" width="" alt="alt_text" title="image_tooltip">

</p>
<p>


<p id="gdcalert39" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: inline image link here (to images/image10.png). Store image on your image server and adjust path/filename/extension if necessary. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert40">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>


<img src="images/image10.png" width="" alt="alt_text" title="image_tooltip">

</p>
<p>


<p id="gdcalert40" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: inline image link here (to images/image11.png). Store image on your image server and adjust path/filename/extension if necessary. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert41">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>


<img src="images/image11.png" width="" alt="alt_text" title="image_tooltip">

</p>
<h4>Appendix B: Examining the Subgroups</h4>


<p>


<p id="gdcalert41" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: inline image link here (to images/image12.png). Store image on your image server and adjust path/filename/extension if necessary. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert42">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>


<img src="images/image12.png" width="" alt="alt_text" title="image_tooltip">

</p>
<p>


<p id="gdcalert42" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: inline image link here (to images/image13.png). Store image on your image server and adjust path/filename/extension if necessary. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert43">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>


<img src="images/image13.png" width="" alt="alt_text" title="image_tooltip">

</p>
<p>


<p id="gdcalert43" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: inline image link here (to images/image14.png). Store image on your image server and adjust path/filename/extension if necessary. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert44">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>


<img src="images/image14.png" width="" alt="alt_text" title="image_tooltip">

</p>
<p>


<p id="gdcalert44" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: inline image link here (to images/image15.png). Store image on your image server and adjust path/filename/extension if necessary. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert45">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>


<img src="images/image15.png" width="" alt="alt_text" title="image_tooltip">


<p id="gdcalert45" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: inline image link here (to images/image16.png). Store image on your image server and adjust path/filename/extension if necessary. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert46">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>


<img src="images/image16.png" width="" alt="alt_text" title="image_tooltip">

</p>
<h4>Appendix C: Difference of Means Test</h4>


<p>


<p id="gdcalert46" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: inline image link here (to images/image17.png). Store image on your image server and adjust path/filename/extension if necessary. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert47">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>


<img src="images/image17.png" width="" alt="alt_text" title="image_tooltip">

</p>
<p>


<p id="gdcalert47" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: inline image link here (to images/image18.png). Store image on your image server and adjust path/filename/extension if necessary. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert48">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>


<img src="images/image18.png" width="" alt="alt_text" title="image_tooltip">

</p>
<h4>Appendix D: Confidence Interval</h4>


<p>


<p id="gdcalert48" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: inline image link here (to images/image19.png). Store image on your image server and adjust path/filename/extension if necessary. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert49">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>


<img src="images/image19.png" width="" alt="alt_text" title="image_tooltip">

</p>
<p>


<p id="gdcalert49" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: inline image link here (to images/image20.png). Store image on your image server and adjust path/filename/extension if necessary. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert50">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>


<img src="images/image20.png" width="" alt="alt_text" title="image_tooltip">

</p>

<!-- Footnotes themselves at the bottom. -->

<h2>Notes</h2>
<div class="footnotes">
<hr>
<ol><li id="fn1">
<p>
     <strong>#variables:</strong> In the first steps of the report, I identify and classify different relevant variables and suggest a relationship between them. The variable roles and types suggest an analysis and direction for the report, and I discuss the importance and justification of using these variables throughout the paper.&nbsp;<a href="#fnref1" rev="footnote">&#8617;</a><li id="fn2">
<p>
     <strong>#descriptivestats:</strong> I calculated in Python and displayed the summary statistics (consisting of count, mean, median, mode, standard deviation, and range) for the given subgroups regarding the research question and the analysis of this report.&nbsp;<a href="#fnref2" rev="footnote">&#8617;</a><li id="fn3">
<p>
     <strong>#dataviz:</strong> Multiple graphs are generated to shape better the understanding of data distribution among the given sample. Figures 1 and 2 show the histogram coded in Python of average book ratings for each subgroup (divided by book-length). More histograms are shown in the Appendix. Good practices of data visualization and interpretation are followed for all of them.&nbsp;<a href="#fnref3" rev="footnote">&#8617;</a><li id="fn4">
<p>
     <strong>#distributions: </strong>The usage of t-distribution as a sampling distribution is justified considering the fulfillment of all the conditions. Note that the Central Limit Theorem was not mentioned as it was not relevant to justify the usage of the t-distribution because I was working with a relatively bigger sample. The normal distribution can be used to approximate the sampling distribution of the sample mean when the sample size is large, and this allowed me to calculate the confidence interval for the population mean as well.&nbsp;<a href="#fnref4" rev="footnote">&#8617;</a><li id="fn5">
<p>
     <strong>#probability: </strong> This statement expresses the idea that the p-value is a measure of the likelihood or probability that the observed difference in means between the two groups would be this large or larger if there were no actual differences between the groups. It also emphasizes that the probability is calculated under the assumption that the null hypothesis is true, meaning there is no actual difference between the two groups. In this case and in general hypothesis testing for statistical inference, the frequentist approach is more evident.&nbsp;<a href="#fnref5" rev="footnote">&#8617;</a><li id="fn6">
<p>
     <strong>#significance: </strong>I used a measure of significance, such as Hedge's g effect size, to interpret the observed statistical difference considering the sample size and to distinguish between statistical significance and practical significance of the results. This allowed me to evaluate the practical importance of the observed differences, in addition to their statistical significance.&nbsp;<a href="#fnref6" rev="footnote">&#8617;</a><li id="fn7">
<p>
    <strong> #confidenceintervals: </strong>The population parameter, average book rating, is estimated using confidence intervals based on a sample plus/minus the margin of error. The intervals for two subgroups of long vs. short books are interpreted correctly and are used to inform the analysis, noting the implications for statistical significance. An interesting case comes out in this analysis, and an external source is consulted to conclude results about it.&nbsp;<a href="#fnref7" rev="footnote">&#8617;</a><li id="fn8">
<p>
     Nevertheless, the confidence result is not to be dismissed; there is a 95% probability that the point estimate (the mean in each subgroup) is within the interval. Hypothetically, the interlap could be within the 5% which I am not confident on.&nbsp;<a href="#fnref8" rev="footnote">&#8617;</a><li id="fn9">
<p>
     <strong>#induction: </strong>This explanation describes how induction was used to draw conclusions about the population based on a sample of data, and it discusses the strengths and limitations of this approach. It is explained how the induction type is a generalization, and its strength and reliability are discussed.&nbsp;<a href="#fnref9" rev="footnote">&#8617;</a><li id="fn10">
<p>
     <strong>#organization: </strong>Several aspects of clear organization were employed to structure a written piece that is easy to read and replicate (especially with the code in the Appendix). This report follows a discovery organizational structure, starting with an introduction, following with multiple points which include analyses, and concluding with a result deriving from the very analyses.&nbsp;<a href="#fnref10" rev="footnote">&#8617;</a>

</ol></div>
