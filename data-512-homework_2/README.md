# HW 2 Considering Bias in Data

## Data Schemas and Intermediary Files

**Input Data:**

*   `politicians_by_country.AUG.2024.csv`
    *   Columns: country, name, url
    *   Description: Contains a list of politicians for each country, their names, and Wikipedia article URLs.

*   `population_by_country_AUG.2024.csv`
    *   Columns: Geography, Population
    *   Description: Contains the population for each country or region.

**Output Data:**

*   `wp_politicians_by_country.csv`
    *   Columns: country, region, population, article_title, revision_id, article_quality
    *   Description: Contains data on each politician's Wikipedia article, including the country, region, population, article title, revision ID, and article quality score.

**Intermediary Files:**

*   `wp_countries-no_match.txt`
    *   Description: Contains a list of countries that did not have a matching entry in the `politicians_by_country.AUG.2024.csv` and `population_by_country_AUG.2024.csv`

## Research Implications
Before beginning this analysis, I anticipated potential biases in the data, particularly a skew toward English-speaking populations and countries with stronger representation in Western culture. Given that Wikipedia is a volunteer-driven platform, I expected that regions and topics attracting more attention from contributors would be better covered. This turned out to be accurate, as my analysis showed that countries in Europe, for example, have higher article coverage per capita and quality coverage per capita compared to other regions. This pattern suggests that Wikipedia’s coverage may indeed be influenced by the interests and accessibility of contributors, which aligns with my initial expectations.

One surprising finding was the contrast between Monaco’s rankings in coverage and quality. Monaco ranks in the top 10 for article coverage per capita, but it is in the bottom 10 for quality coverage per capita. This discrepancy could reflect the tendency of some regions or topics to receive a high quantity of attention without a corresponding level of detail or accuracy in the content. Additionally, the development of internet infrastructure in different countries likely plays a role in this disparity. Many of the countries with lower rankings for coverage and quality are places with less internet penetration or development, which could limit participation in platforms like Wikipedia.

Moreover, the dataset itself is biased due to the exclusion of certain key countries. For instance, the absence of the United States and Canada in the dataset limits the representation of Northern America. As a result, we cannot fully capture the diversity of global regions, leading to biased conclusions that may overrepresent or underrepresent entire areas based on the countries present or missing from the dataset.

To address these limitations, I would suggest transforming the dataset by introducing weights that account for disparities in internet access and global engagement. However, selecting these weights would require careful consideration to avoid introducing new biases while trying to correct existing ones. The aim would be to ensure that countries with lower internet development aren’t disproportionately underrepresented in the analysis.

In conclusion, while this dataset is valuable for understanding Wikipedia’s coverage of politicians per capita and article quality, it must be approached with caution due to its inherent gaps and biases. A researcher could still use it effectively for specific studies, but only with a clear understanding of its limitations and by supplementing it with additional data where possible.
