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

**• Date:**<br> 

## **Data Cleaning:**
**•	Missing Values Handling:**<br />
7 out of 10 columns excluding "campaign_name","date" and "spend_usd" have missing values in only one row. To handle this, missing values are replaced with mean values of their own column.<br />

**•	Duplicated Values Handling:**<br />
A/B Test Results datasets which are control group and test group do not have any duplicated records.<br />

**•	Changing Data Types:**<br />
The data type of "Date" column format is corrected from "object" to "datetime64[ns]".Additionally, the columns whose data types are "float64" are changed to "int64" to get the same format in both datasets.

**•	Adding Performance Metrics:**<br />
To gauge which campaign are most appealing to the users, new performance metrics are identified :
- CTR(%)=

## **Exploratory Data Analysis:**
**1) Descriptive Statistics**<br />

**2) What is the total number of records for each attributes per campaign ?**<br />

**3) What is the relationship between attributes ?**<br />

**4) What is the comparison of CTR(%) and Conversion Rate(%) per campaign ?**<br />

## **Hypothesis Testing:**
**1) Shapiro-Wilk Test**<br />
**2) Fligner-Killeen Test**<br />
**3) Mann-Whitney U test**<br />

## **Conclusion:**
