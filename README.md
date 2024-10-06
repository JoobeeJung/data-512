# HW 1 Professionalism & Reproducibility

### Goal
The goal of this project is to construct, analyze, and publish a dataset of monthly article traffic for a select set of pages from English Wikipedia, covering the period from July 1, 2015, through September 30, 2024. This analysis aims to provide insights into trends in article views, particularly related to rare diseases.

### License
This project utilizes data from the Wikimedia Foundation and adheres to their [Terms of Use](https://foundation.wikimedia.org/wiki/Policy:Terms_of_Use). The dataset created is made available under the [Creative Commons CC-BY license](https://creativecommons.org/licenses/by/4.0/), which permits sharing and adaptation of the material as long as appropriate credit is given. 

The ToU applies to the dataset by ensuring that all data usage respects user privacy and adheres to the ethical guidelines set forth by Wikimedia. This includes proper attribution to the original sources and compliance with any restrictions on data handling and sharing.

The dataset specifically comprises counts of pageviews from a selected subset of Wikipedia articles related to rare diseases. This subset was identified by using a database maintained by the National Organization for Rare Diseases [(NORD)](https://rarediseases.org/) and matching articles that are either about a rare disease or contain relevant sections discussing rare diseases.

This project is based on a code example developed by Dr. David W. McDonald for use in DATA 512, a course in the UW MS Data Science degree program. The original code is provided under the Creative Commons CC-BY license. Revision 1.3 - August 16, 2024.


### API Documentation

*   https://www.mediawiki.org/wiki/Wikimedia_REST_API
*   https://wikimedia.org/api/rest_v1/#/Pageviews%20data
*   https://doc.wikimedia.org/generated-data-platform/aqs/analytics-api/reference/page-views.html


###  Data Files:

1. **Monthly Mobile Access Data**
   - **Filename:** `rare-disease_monthly_mobile_201507-202409.json`
   - **Description:** This file contains monthly page view data for selected articles with mobile access, aggregated to sum both mobile web and mobile app.

2. **Monthly Desktop Access Data**
   - **Filename:** `rare-disease_monthly_desktop_201507-202409.json`
   - **Description:** This file contains monthly page view data for selected articles with desktop access.

3. **Monthly Cumulative Data**
   - **Filename:** `rare-disease_monthly_cumulative_201507-202409.json`
   - **Description:** This file combines the desktop and mobile data into a single cumulative file, summarizing total views per article.

### Data Schema and Description

The dataset consists of a DataFrame 7 columns. Below is a description of each column:

| Column       | Description                                                       |
|--------------|-------------------------------------------------------------------|
| `project`    | Domain and subdomain of a Wikimedia project. For all projects, use all-projects          |
| `article`    | Page title in URL-encoded format       |
| `granularity`| Time interval between data points    |
| `timestamp`  | The timestamp for the data point, indicating the month of traffic data. |
| `access`     |Method of access (e.g., "desktop", "mobile-web", "mobile-app").                  |
| `agent`      | Type of user agent|
| `views`      | The number of views recorded for the article during the specified month. |

This schema allows for straightforward analysis of article traffic over time, enabling researchers to track trends and make comparisons across different articles.


### Known Issues or Special Considerations
* API Rate Limits : Be aware of the API rate limits set by Wikimedia, which may affect data collection if the requests exceed the allowed limits.
