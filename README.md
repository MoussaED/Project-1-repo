# Project-1-repo
Module7Project
group members:
1) Starla Halliday
2) Yemi Gebremikael
3) Amberlie Ann Clutterbuck
4) Moussa Diop
   _______________________________
**Project Overview:** Perform exploratory data analysis of drug & biologic contract funding for minority-owned pharmaceutical & manufacturing organizations to uncover patterns in government spending during FY2020-2022

**Hypothesis:** There **_is a change_ **in U.S. Government Drugs & Biologicals spending in minority-owned pharmaceutical & medicine manufacturing businesses between FY20-FY22

**Null Hypothesis:** There **_is no change_ **in U.S. Government Drugs & Biologicals spending in minority-owned pharmaceutical & medicine manufacturing businesses between FY20-FY22

Input Parameters were used to address the large dataset. The dataset was filtered down to establish a sample size for the project. 

**Filters Used**

Focus: Minority-Owned Businesses

Contract Type: BPA, Purchase Order, Delivery Contract, & Definitive Contract

Fiscal Years: FY2020 – FY2022 (October 1st, 2019 – September 30th, 2022)

Performance Location: United States of America

Product Service Code: Drugs & Biologics

North American Industry Classification System (NAICS): Pharmaceutical & Medicine Manufacturing

**Output Parameters**

Federal Award Amount: Obligated dollar amount from federal agencies with congressionally appropriated money

Awarding Federal Agencies: Department of Defense, Department of Health & Human Services, Department of Veteran's Affairs

Performance States: CA | CO | DE | FL | GA | HI | IL | KY | MA | MD | MI | MO | NJ | NY | OH | SC | TN | TX | VA | WA

**Data Collection & Curation**

The API used was derived from USASpending.Gov. An official open data source of federal spending information, including information about federal awards such as contracts, grants, & loans. 

There were several APIs available for use; however, based on the project focus area the team selected a Post API capturing spending by award which identified the needed data points. The API used was Paginated (results were divided into small datasets or pages due to size). The API limit parameter was set to 100 rows per page. As such, data rows for the merged dataframe were derived from the first paginated dataset of each quarter in the designated fiscal year to capture a sample spread of the overall dataset. 

The dataset also required cleaning to convert calendar year to fiscal year via adding columns to capture fiscal year and fiscal year quarter to allow for a more accurate analysis. The dataset was also scrubbed to remove outliers, which were significantly different from the dataset, using the lower and upper quartiles which greatly skewed the dataset. Removing of the outlier data assisted in addressing the distortion of the results as well as statistical analysis. This allows for a more accurate conclusion on the dataset analyzed. 

**Project Questions**

Four questions were identified to analyze the data. Graphs were generated to provide visuals. 

1. How many contracts & how much funding was awarded to minority-owned pharmaceutical & manufacturing organizations during FY2020 – FY2022?
   ![image](https://github.com/MoussaED/Project-1-repo/assets/133922704/180de008-194c-4773-96d1-30cb7c8fd722)

3. Is there a spike in federal funding of minority-owned pharmaceutical & manufacturing organizations depending on the fiscal quarter/year?
![image](https://github.com/MoussaED/Project-1-repo/assets/133922704/a470735d-d5b3-4623-8a81-1fc871dada0c)

4. Which federal agencies awarded the most federal dollars to minority-owned pharmaceutical & manufacturing organizations?
![image](https://github.com/MoussaED/Project-1-repo/assets/133922704/b5071e28-a848-4146-8337-8798b240be49)

5. Which U.S. states received the most # of contracts & funding?
![image](https://github.com/MoussaED/Project-1-repo/assets/133922704/b4e1f878-cfe7-4546-a241-29666194dae9)

**Challenges**

1. The raw dataset was extensive. There were over 1.4 million contract data points available for review. To address the depth and breadth, the dataset was reduced based on identified filters to assist in making the data more manageable in the time allotted for research and analysis. Additional research would be needed to further investigate the hypothesis.

2. The API used was a POST API. Experience on the team was limited. The team was required to research and troubleshoot how to use a POST API request versus a GET API request. The team had to troubleshoot the coding to identify and clear issues. This challenge allowed fo the team to further develop their understanding of API coding and associated challenges.

3. There were several APIs available for use which posed a challenge in selection while avoiding scope creep via changing focus or priority sets. The sheer volume of data offered created a challenge in maintaining the project focus. The team selected an API that offered the datapoints needed to conduct initial research.

4. The team attempted to create a location map via Geoapify Location plot; however, there was not enough information available (the dataset had null values for state in many cases). The team attempted to troubleshoot the issue by manually identifying longitude and latitude; however, the dataset did not align and the attempt to create this graph was unsuccessful.

**Conclusion**

Based on the data analyzed, there is a change in U.S. Government Drugs & Biologicals spending in minority-owned pharmaceutical & medicine manufacturing businesses between FY20-FY22. This conclusion was drawn based on use of the paired T-Test. The vaiables used were the contract amount awarded and fiscal year. The T-Test returned a P Value well below the 0.05 threshold (4.236811439575075e-15) allowing for the conclusion that the null hypothesis may be reuected and the results are not by chance. 

Further research and analysis are required to support the hypothesis conclusion. This research may include additional filtering of the USASpending dataset to focus on minority-owned organizations by category (Asian-Pacific-American Owned, Black-American Owned, Hispanic American Owned, Native-American Owned, Women-Owned). An analysis on small business data in comparison to large or non-small businesses may also provide additional insight into government spending. With that research on for-profit versus non-profit business may also provide additional insight.
________________________________________________

**References:**

Format numbers in pandas as currency in thousands or millions. (n.d.). Stack Overflow. https://stackoverflow.com/questions/41271673/format-numbers-in-pandas-as-currency-in-thousands-or-millions

Pandas Fiscal Year – Get Financial Year with Pandas. (2021, January 21). https://datagy.io/pandas-fiscal-year/.https://www.statology.org/pandas-group-by-quarter/

Usaspending-api/usaspending_api/api_contracts/search_filters.md at master · fedspendingtransparency/usaspending-api. (n.d.). GitHub. https://github.com/fedspendingtransparency/usaspending-api/blob/master/usaspending_api/api_contracts/search_filters.md#time-period












