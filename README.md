# Wikipedia Article Web Traffic Time Series Analysis
### Forecasting future views of Wikipedia pages by total traffic, types, and topics

Created Date: June 8, 2022
Authored By: Aaliyah Hänni

## Overview
This project outlines the exploration of web traffic for a sample of approximately 145,000 Wikipedia articles over a two year period. The attached report outlines several forecasts for the weekly number of page views over time, and explores potential relationships between page views, traffic types and article topics.
![weekly_topics](https://github.com/aaliyahfiala42/Wiki_Time_Series_Analysis/blob/main/images/weekly_topics.jpg)


## Project Goals
### Wikipedia Article Page Views Over Time 
Using daily web traffic information for a sample of Wikipedia articles, we will explore several key properties, such as identifying potential trends or seasonality in the total number of page views of varying articles over time. We will then generate forecast predictions of web traffic for the different articles, and compare predictions against the true number of page views.

![weekly_total](https://github.com/aaliyahfiala42/Wiki_Time_Series_Analysis/blob/main/images/weekly_total.jpg)

The best forecast found for this time series was an Arima(0,1,0) model, which shows the following forecast: 

![total_forcast](https://github.com/aaliyahfiala42/Wiki_Time_Series_Analysis/blob/main/images/total_forecast.jpg)

### Wikipedia Article Page Views Over Time by Traffic Type
For a given Wikipedia article site visit there are three types of traffic that Wikipedia measures: mobile, desktop, and spider. Mobile and desktop traffic are site visits from individual users through different interfaces, while spider traffic is access to a site from a web-crawler that was developed to collect data. For this analysis, we explore differences between the types of traffic in Wikipedia articles over time, and identify the types of relationships that exist between them.
![weekly_type](https://github.com/aaliyahfiala42/Wiki_Time_Series_Analysis/blob/main/images/weekly_type.jpg)

![type_scatterplot](https://github.com/aaliyahfiala42/Wiki_Time_Series_Analysis/blob/main/images/type_scatterplot.jpg)

![desktop_forecast](https://github.com/aaliyahfiala42/Wiki_Time_Series_Analysis/blob/main/images/desktop_forecast.jpg)

### Wikipedia Topics Page Views Over Time
There are natural groupings of Wikipedia articles by topic, such as articles about flowers, sports, or historical events. For this analysis, we will explore the page traffic over time for varying Wikipedia topics. To determine a Wikipedia article topic, we will develop a simple classification model to group articles based on tokenized article titles. Then we will explore relationships in the aggregated sum of page views over time for the varying topics. The topics were determined using Wikipedia’s defined ![WikiProject Lists of Topics](https://en.wikipedia.org/wiki/Wikipedia:WikiProject_Lists_of_topics).

![topic_scatterplot](https://github.com/aaliyahfiala42/Wiki_Time_Series_Analysis/blob/main/images/topic_scatterplot.jpg)

## Data
The data set used for this analysis will be the Web Traffic Time Series Forecasting provided by Google Inc, and hosted on Kaggle  (Google Inc., 2017). This dataset contains the daily count of unique user visits to 145,063 Wikipedia articles from July 1st, 2015 to September 10th, 2017. These articles are in multiple languages, have varying grades (i.e article content assessment score), and contain multiple topics. The dataset also groups the counts of the number of articles accessed by each traffic type: all, mobile, desktop, and spider. 

The data was aggregated to give weekly totals of traffic views, for all articles visited, as well by type. To obtain the article topics, a clustering algorithm was applied on the article titles to group them into 1 of 11 defined Wikipedia topics of Art and culture, Geography and places, Health and fitness, History and events, Mathematics and abstractions, Natural sciences and nature, People and self, Philosophy and thinking, Religion and spirituality, Social sciences and society, and Technology and applied sciences

## Conclusions
Analyzing the time series of total weekly Wikipedia Article traffic, the ARIMA model with a single difference value performed the best in comparison to other models applied. With this model, we were able to achieve reasonable predictions that all fell within the standard error. 

Surprisingly, of the different types of web traffic analyzed, the ARIMA model for the desktop had the best predictions, even though the desktop time series contained the most variation in the data. In contrast the spider traffic type had the worst predictions, and obtained predictions even outside of the prediction intervals. Although desktop and mobile views were significantly correlated, the model generated did not have great evaluation metrics when compared to the test set.

The topic time series was the most difficult to model, and due to the large number and variation of topics. The ARIMA models all appeared to provide fairly accurate forecasts, with the exception of the three topics: technology, religion, and nature. The multivariate analysis of mathematics and technology proved fruitful, as there was a strong correlation identified, while the relationship explored between art and philosophy appeared nonexistent. 

Overall, there does appear to be a pattern in Wikipedia web traffic with relation to time, although it is not always clear and highly sensitive to large peaks and valleys. The total number of views appears to be the easiest to model, but there were some interesting correlations found between page view types and topics.

## Cited Sources
Brigo, F., Lattanzi, S., Bragazzi, N., Nardone, R., Moccia, M., & Lavorgna, L. (2018, February 5). Why do people search Wikipedia for information on multiple sclerosis? Multiple Sclerosis and Related Disorders. Retrieved April 9, 2022, from https://www.sciencedirect.com/science/article/pii/S2211034818300476?casa_token=12JD_y_NnVIAAAAA%3AHs6WgvUlGzhk3kSQToSki32Pz5ksktGCqrNUKUZRe1bnbwqOT9TG_MaB_ZZaNGrd_T7SAgCHlw 

Google Inc. (2017, September 12). Web traffic time series forecasting. Kaggle. Retrieved April 9, 2022, from https://www.kaggle.com/competitions/web-traffic-time-series-forecasting/overview 

Scheepers, T. (2018, January 16). Wikipedia Summary Dataset. GitHub. Retrieved April 9, 2022, from https://github.com/tscheepers/Wikipedia-Summary-Dataset 

Wikimedia Foundation. (2022, April 5). Size of Wikipedia. Wikipedia. Retrieved April 9, 2022, from https://en.wikipedia.org/wiki/Wikipedia:Size_of_Wikipedia 


