# **Comparing Bidding Methods Using AB Testing**

## **Introduction:**

This project aims to compare the performance of current (Max-bidding) and new campaign (Average-bidding) for an e-commerce website to make a decision about which campaign to use in the future based on A/B test results by EDA and hypothesis testing.<br>

To get further information about exploratory data analysis and hypothesis testing, please check out **[Jupyter Notebook](https://github.com/ovgutunc/E-Commerce-Website-EDA-and-AB-Testing/blob/main/AB_test.ipynb).**  

## **Data Acquisition:**

The datasets named as Control_campaign(Max-bidding) and Test_campaign(Average-bidding) contains 30 rows and 10 attributes. Each row corresponds to A/B test results of the company for Control and Test campaigns on August 2019. The attributes are as follows:<br>

**• Campaign Name:** Target campaign type for ad landing page.<br>

**• Spend [USD]:** The amount of money spent on advertising in the campaign.<br>

**• # of Impressions:** The number of people who viewed the ad in the campaign (contains repeated viewing of the same person for the ad).<br>

**• Reach:** The number of unique people who saw the ad in the campaign.<br>

**• # of Website Clicks:** The number of users who clicked on the website link in the campaign's advertisement.<br>

**• # of Searches:** The number of users who performed a search on the website.<br>

**• # of View Content:** Number of users who have viewed product details.<br>

**• # of Add to Cart:** The number of users who have added the product to the cart.<br>

**• # of Purchase:** The number of users who have purchased the product.<br>

The link to the datasets is **[here](https://www.kaggle.com/datasets/ilkeryildiz/example-dataset-for-ab-test).**

## **Data Cleaning:**
**1)	Missing Values Handling:**<br />

7 out of 10 columns excluding "campaign_name","date" and "spend_usd" have missing values in only one row. To handle this, missing values are replaced with mean values of their own column.<br />

**2)	Duplicated Values Handling:**<br />

A/B Test Results datasets which are control campaign and test campaign do not have any duplicated records.<br />

**3)	Changing Data Types:**<br />

The data type of "Date" column format is corrected from "object" to "datetime64[ns]".Additionally, the columns whose data types are "float64" are changed to "int64" to get the same format in both datasets.

**4)	Adding Performance Metrics:**<br />

To gauge which campaign are most appealing to the users, new performance metrics are identified :

  - CTR(%) = Website clicks/ Impressions * 100
  - Conversion Rate(%) = Purchase / Website clicks * 100

## **Exploratory Data Analysis:**
**1) Descriptive Statistics**<br />

Before running hypothesis testing, to provide a concise summary of the data, the measures of central tendency(mean, median), variability(standard deviation, variance, IQR, and percentiles), skewness, and distribution as well as outliers are analyzed by using box plots.<br />

**2) What is the total number of records for each attribute per campaign ?**<br />

To gain a general overview about campaigns,  pie charts are used to compare the total values of each attribute.

**3) What is the relationship between attributes ?**<br />

Scatter plots are taken into consideration to get an idea about the strength and direction of the relationship between attributes.

**4) What is the comparison of CTR(%) and Conversion Rate(%) per campaign ?**<br />

Time-series plots are included to see the performances of both campaigns over time and determine any trends or pattern in the performance of CTR(%) and Conversion Rate(%).<br />

## **Hypothesis Testing:**

Hypothesis Testing is considered to determine whether the difference of CTR(%) and Conversion Rate(%)in performance between Control campaign and Test campaign is statistically significant or not.
From the perspective of assumptions of statistical test such as normality, homogeneity of variances, random sampling, sample size and data type, tests are selected to make decisions about the campaigns as follows:

**1) Shapiro-Wilk Test**<br />

It is performed to check the normality of campaigns in CTR(%) and Conversion Rate(%).

**2) Fligner-Killeen Test**<br />

It is performed to check the homogeneity of variances of campaigns in CTR(%) and Conversion Rate(%).

**3) Mann-Whitney U test**<br />

Based on the results of Shapiro-Wilk Test and Fligner-Killeen Test, Mann-Whitney U test is selected as a non-parametric test to find whether the medians of campaigns in CTR(%) and Conversion Rate(%) are equal or not.

## **Conclusion:**

• Test campaign, which is Average-bidding strategy, has a higher CTR(%) of %10.24 than Control campaign (%5.08), which is Max-bidding, which in turn found that the result is statistically significant.<br>

• Control campaign has a higher Conversion Rate(%) of %11.4 than Test campaign (%9.2). However, there is no sufficient evidence that the result is statistically significant.<br>

• Both campaigns have almost the same amount of purchases, Although Test campaign has a higher amount of money spent than Control campaign.<br>

• Control campaign, which is Max-bidding, has higher impressions and reach values with regard to the aim of Max-bidding strategy.<br>

• Overall, even if Test campaign has a higher CTR(%), it has a lower Conversion Rate (%) in terms of the mean value of performance metrics. It can be explained by marketing strategies and statistical requirements:<br>

>-The ad in campaign is targeting the wrong consumers.<br>

>-Working with a small size of data and having outliers affects the distribution, variability, and skewness with the selection of statistical methods resulting in a non-parametric test.<br>

• It is recommended to conduct A/B test with a larger amount of data focused on targeted people for a longer period of time to observe trends, patterns, and variations. This will allow us to use of the right statistical methods to determine which campaign is more effective in a statistical manner.<br>

_Thank you for your precious time.I hope you enjoy my data world as much as ı do._<br>
_Keep grinding !_<br>
