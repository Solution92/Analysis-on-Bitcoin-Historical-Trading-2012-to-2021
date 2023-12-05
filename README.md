# Analysis-on-Bitcoin-Historical-Trading-2012-to-2021

## Table of Content
- [Project Overview](#project-overview)
- [Data Source](#data-source)
- [Tools Used](#tools-used)
- [Data Cleaning and Preparation](#data-cleaning-and-preparation)
- [Exploratory Data Analysis (EDA)](#exploratory-data-analysis-eda)
- [Data Analysis](#data-analysis)
- [Dashboard](#dashboard)
- [Result and Findings](#result-and-findings)
- [Recommendation](#recommendation)
- [Limitations](#limitations)
- [Reference](#reference)


### Project Overview

Bitcoin is a decentralized digital currency, often referred to as a cryptocurrency, that was created in 2009 by an anonymous person or group of people using the pseudonym Satoshi Nakamoto. It operates on a technology called blockchain, which is a distributed ledger that records all transactions across a network of computers.

Bitcoin allows for peer-to-peer transactions without the need for intermediaries like banks. It has gained widespread attention for its potential to revolutionize the traditional financial system. Bitcoin can be bought, sold, and used for various transactions, and its value can be highly volatile, making it both a digital currency and a speculative investment.

### Data Source

The dataset was provided in a CSV file format by the client which I am not permitted to disclose.

### Tools Used

Power BI

### Data Cleaning and Preparation

![Screenshot_130](https://github.com/Solution92/Analysis-on-Bitcoin-Historical-Trading-2012-to-2021/assets/144762124/3bf8d743-3d3e-43c1-9fd0-3a0e0707ce02)
The Raw file

The dataset has only 8 columns with a lot of unwanted values. The ‘Timestamp’, ‘Open’, ‘High’, ‘Low’, ‘Close’, etc. I needed a Date column so that it would be easy to craft out the ‘Year’ and ‘Month’ columns.

The ‘Timestamp’ column happens to be the only one I can use to create my ‘Date’, ‘Year’, and ‘Month’ columns respectively.

Using a function in the power query editor, I create a custom column from the ‘Add Column’ pane. This is the process: Go to add column > Click on custom column > Give your custom column a name > In the formula space, type > #datetime(1970,1,1,0,0,0) + #duration(0,0,0,[Timestamp]).

This formula created a new column with the date and time.

![Screenshot_131](https://github.com/Solution92/Analysis-on-Bitcoin-Historical-Trading-2012-to-2021/assets/144762124/8c5b9027-9f19-402a-8313-e733f5d3f931)

### Exploratory Data Analysis (EDA)

I have generated the following key Performance Indicators (KPIs) and insights:

- Total Volume (BTC)
- Total Volume (Currency)
- Total Weighted Price
- Avg. Weighted Price By Yr
- Monthly Avg. Weighted Price
- Total Volume (Currency) By Yr
- Volume(Btc) Over Yr.

### Data Analysis
~~~
DAX/Measures:

Total Volume (BTC) = SUM(‘Bitcoin Historical Data’[Volume_(BTC)]) = 34M

Total Volume (Currency) = SUM(‘Bitcoin Historical Data’[Volume_(Currency)]) = 150.92bn

Total Weighted Price = SUM(‘Bitcoin Historical Data’[Weighted_Price]) = 21.71bn

Avg. Weighted Price By Yr = CALCULATE(AVERAGE(‘Bitcoin Historical Data’[Weighted_Price])) = 6.01k
~~~

### Dashboard

![Screenshot_132](https://github.com/Solution92/Analysis-on-Bitcoin-Historical-Trading-2012-to-2021/assets/144762124/26e6fd2c-d5ec-4871-918d-401cb26693fc)

### Result and Findings

- At 3,302,945,169.65, March had the highest Sum of Weighted_Price and was 250.68% higher than April, which had the lowest Sum of Weighted_Price at 941,879,492.93.  March accounted for 15.21% of Sum of Weighted_Price.  Across all 12 Month Name, Sum of Weighted_Price ranged from 941,879,492.93 to 3,302,945,169.65.  
- Meanwhile, at 35,119,515,058.06, 2021 had the highest Sum of Volume_(Currency) and was 8,257,191,470.10% higher than 2011, which had the lowest Sum of Volume_(Currency) at 425.32.  2021 accounted for 23.27% of Sum of Volume_(Currency).  Sum of Volume_(Currency) and Sum of Year diverged the most when the Year was 2021, when Sum of Volume_(Currency) were 34,860,776,533.06 higher than Sum of Year.  
- And, finally, at 5,525,311.39, 2015 had the highest Sum of Volume_(BTC) and was 5,796,620.93% higher than 2011, which had the lowest Sum of Volume_(BTC) at 95.32.  2015 accounted for 16.40% of Sum of Volume_(BTC).  Across all 11 Year, Sum of Volume_(BTC) ranged from 95.32 to 5,525,311.39. 

### Recommendation

- Based on the findings, it's recommended to closely monitor and analyze the factors contributing to the significant fluctuations in Sum of Weighted_Price, Sum of Volume_(Currency), and Sum of Volume_(BTC) across different months and years. 
- Identify the key drivers behind the peak in March for Sum of Weighted_Price, the spike in 2021 for Sum of Volume_(Currency), and the surge in 2015 for Sum of Volume_(BTC). 
- Additionally, consider investigating any anomalies or outliers that might have influenced these results. 
- This analysis can provide valuable insights for decision-making, risk management, and optimization of trading or investment strategies in the cryptocurrency market.

### Limitations

_ The dataset's limitations may include potential data anomalies or outliers that could distort the results, as evidenced by extreme percentage differences and values, such as the 8,257,191,470.10% increase in Sum of Volume_(Currency) from 2011 to 2021. 
- Additionally, the dataset's accuracy relies on the reliability of the sources providing cryptocurrency market data, and any inconsistencies or errors in data collection could impact the overall validity of the findings. 
- The absence of contextual information about external events, market dynamics, or regulatory changes during the analyzed period could limit a comprehensive understanding of the observed trends. 
- Lastly, the dataset's temporal scope may influence the generalizability of findings, and caution should be exercised in extrapolating trends, especially if market conditions have significantly evolved since the last recorded data point.

### Reference

[kaggle.com](https://www.kaggle.com/datasets/prasoonkottarathil/btcinusd), holds the power to access any of such datasets on bitcoine.

















