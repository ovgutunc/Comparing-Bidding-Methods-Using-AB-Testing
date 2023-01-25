# **E-Commerce-Website-EDA-and-AB-Testing**

## **Introduction:**

## **Data Acquisition:**

The datasets named as Control_group and Test_group contains 30 rows and 10 attributes. Each row corresponds to A/B test results of the company for Control and Test groups on August 2019. The attributes are as follows:<br>

**• Campaign Name:** Target campaign type for ad landing page.<br>

**• Spend [USD]:** The amount of money spent on advertising in the campaign.<br>

**• # of Impressions:** The number of people who viewed the ad in the campaign (contains repeated viewing of the same person for the ad).<br>

**• Reach:** The number of unique people who saw the ad in the campaign.<br>

**• # of Website Clicks:** The number of users who clicked on the website link in the campaign's advertisement.<br>

**• # of Searches:** The number of users who performed a search on the website.<br>

**• # of View Content:** Number of users who have viewed product details.<br>

**• # of Add to Cart:** The number of users who have added the product to the cart.<br>

**• # of Purchase:** The number of users who have purchased the product.<br>

## **Data Cleaning:**
**1)	Missing Values Handling:**<br />

7 out of 10 columns excluding "campaign_name","date" and "spend_usd" have missing values in only one row. To handle this, missing values are replaced with mean values of their own column.<br />

**2)	Duplicated Values Handling:**<br />

A/B Test Results datasets which are control group and test group do not have any duplicated records.<br />

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

Hypothesis Testing is considered to determine whether the difference of CTR(%) and Conversion Rate(%)in performance between Control group and Test group is statistically significant or not. From the perspective of assumptions of statistical test such as normality, homogeneity of variances, random sampling, sample size and data type, tests are selected to make decisions about the campaigns as follows:

**1) Shapiro-Wilk Test**<br />
**2) Fligner-Killeen Test**<br />
**3) Mann-Whitney U test**<br />

## **Conclusion:**
