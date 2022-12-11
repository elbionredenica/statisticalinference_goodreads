<!-- Output copied to clipboard! -->

<!-----
NEW: Check the "Suppress top comment" option to remove this info from the output.

Conversion time: 3.079 seconds.


Using this HTML file:

1. Paste this output into your source file.
2. See the notes and action items below regarding this conversion run.
3. Check the rendered output (headings, lists, code blocks, tables) for proper
   formatting and use a linkchecker before you publish this page.

Conversion notes:

* HTML and Markdown from Docs version 1.0
* Sun Dec 11 2022 22:03:22 GMT-0000 (UTC)
* Source doc: cs50_statisticalinference_assignment

WARNING:
You have some equations: look for ">>>>>  gd2md-html alert:  equation..." in output.

* Tables are currently converted to HTML tables.
* This document has images: check for >>>>>  gd2md-html alert:  inline image link in generated source and store images to your server. NOTE: Images in exported zip file from Google Docs may not appear in  the same order as they do in your doc. Please check the images!

* Footnote support in HTML is alpha: please check your footnotes.
----->


<p style="color: red; font-weight: bold">>>>>>  gd2md-html alert:  ERRORs: 0; WARNINGs: 1; ALERTS: 49.</p>
<ul style="color: red; font-weight: bold"><li>See top comment block for details on ERRORs and WARNINGs. <li>In the converted Markdown or HTML, search for inline alerts that start with >>>>>  gd2md-html alert:  for specific instances that need correction.</ul>

<p style="color: red; font-weight: bold">Links to alert messages:</p><a href="#gdcalert1">alert1</a>
<a href="#gdcalert2">alert2</a>
<a href="#gdcalert3">alert3</a>
<a href="#gdcalert4">alert4</a>
<a href="#gdcalert5">alert5</a>
<a href="#gdcalert6">alert6</a>
<a href="#gdcalert7">alert7</a>
<a href="#gdcalert8">alert8</a>
<a href="#gdcalert9">alert9</a>
<a href="#gdcalert10">alert10</a>
<a href="#gdcalert11">alert11</a>
<a href="#gdcalert12">alert12</a>
<a href="#gdcalert13">alert13</a>
<a href="#gdcalert14">alert14</a>
<a href="#gdcalert15">alert15</a>
<a href="#gdcalert16">alert16</a>
<a href="#gdcalert17">alert17</a>
<a href="#gdcalert18">alert18</a>
<a href="#gdcalert19">alert19</a>
<a href="#gdcalert20">alert20</a>
<a href="#gdcalert21">alert21</a>
<a href="#gdcalert22">alert22</a>
<a href="#gdcalert23">alert23</a>
<a href="#gdcalert24">alert24</a>
<a href="#gdcalert25">alert25</a>
<a href="#gdcalert26">alert26</a>
<a href="#gdcalert27">alert27</a>
<a href="#gdcalert28">alert28</a>
<a href="#gdcalert29">alert29</a>
<a href="#gdcalert30">alert30</a>
<a href="#gdcalert31">alert31</a>
<a href="#gdcalert32">alert32</a>
<a href="#gdcalert33">alert33</a>
<a href="#gdcalert34">alert34</a>
<a href="#gdcalert35">alert35</a>
<a href="#gdcalert36">alert36</a>
<a href="#gdcalert37">alert37</a>
<a href="#gdcalert38">alert38</a>
<a href="#gdcalert39">alert39</a>
<a href="#gdcalert40">alert40</a>
<a href="#gdcalert41">alert41</a>
<a href="#gdcalert42">alert42</a>
<a href="#gdcalert43">alert43</a>
<a href="#gdcalert44">alert44</a>
<a href="#gdcalert45">alert45</a>
<a href="#gdcalert46">alert46</a>
<a href="#gdcalert47">alert47</a>
<a href="#gdcalert48">alert48</a>
<a href="#gdcalert49">alert49</a>

<p style="color: red; font-weight: bold">>>>>> PLEASE check and correct alert issues and delete this message and the inline alerts.<hr></p>


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

<li>

<p id="gdcalert1" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: equation: use MathJax/LaTeX if your publishing platform supports it. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert2">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>



<li>

<p id="gdcalert2" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: equation: use MathJax/LaTeX if your publishing platform supports it. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert3">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>

 
</li>
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

<p id="gdcalert3" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: equation: use MathJax/LaTeX if your publishing platform supports it. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert4">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>


   </td>
   <td>

<p id="gdcalert4" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: equation: use MathJax/LaTeX if your publishing platform supports it. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert5">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>


   </td>
  </tr>
  <tr>
   <td>Mean
   </td>
   <td>

<p id="gdcalert5" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: equation: use MathJax/LaTeX if your publishing platform supports it. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert6">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>


   </td>
   <td>

<p id="gdcalert6" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: equation: use MathJax/LaTeX if your publishing platform supports it. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert7">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>


   </td>
  </tr>
  <tr>
   <td>Median
   </td>
   <td>

<p id="gdcalert7" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: equation: use MathJax/LaTeX if your publishing platform supports it. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert8">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>


   </td>
   <td>

<p id="gdcalert8" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: equation: use MathJax/LaTeX if your publishing platform supports it. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert9">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>


   </td>
  </tr>
  <tr>
   <td>Mode
   </td>
   <td>

<p id="gdcalert9" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: equation: use MathJax/LaTeX if your publishing platform supports it. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert10">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>


   </td>
   <td>

<p id="gdcalert10" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: equation: use MathJax/LaTeX if your publishing platform supports it. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert11">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>


   </td>
  </tr>
  <tr>
   <td>Standard Deviation
   </td>
   <td>

<p id="gdcalert11" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: equation: use MathJax/LaTeX if your publishing platform supports it. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert12">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>


   </td>
   <td>

<p id="gdcalert12" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: equation: use MathJax/LaTeX if your publishing platform supports it. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert13">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>


   </td>
  </tr>
  <tr>
   <td>Range
   </td>
   <td>

<p id="gdcalert13" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: equation: use MathJax/LaTeX if your publishing platform supports it. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert14">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>


   </td>
   <td>

<p id="gdcalert14" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: equation: use MathJax/LaTeX if your publishing platform supports it. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert15">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>


   </td>
  </tr>
</table>


<p>


<p id="gdcalert15" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: inline image link here (to images/image1.png). Store image on your image server and adjust path/filename/extension if necessary. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert16">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>


<img src="data:image/png;base64,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" width="" alt="alt_text" title="image_tooltip">

</p>
<p>
<strong>Figure 1.</strong> Histogram for long books (book length ≥ 350 pages)
</p>
<p>


<p id="gdcalert16" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: inline image link here (to images/image2.png). Store image on your image server and adjust path/filename/extension if necessary. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert17">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>


<img src="images/image2.png" width="" alt="alt_text" title="image_tooltip">

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
To assess statistical significance, I compute the T-score to see if the difference in means between the two groups is statistically significant. To do so, I first compute the T-score using the usual formula for a difference of means test, where 

<p id="gdcalert17" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: equation: use MathJax/LaTeX if your publishing platform supports it. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert18">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>

 is the standard error of the difference between the means. 
</p>
<p>


<p id="gdcalert18" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: equation: use MathJax/LaTeX if your publishing platform supports it. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert19">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>


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
