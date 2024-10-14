# HW 2 Considering Bias in Data


## Data Schemas and Intermediary Files

**Input Data:**

*   **politicians_by_country.AUG.2024.csv:**
    *   Columns: country, name, url
    *   Description: Contains a list of politicians for each country, their names, and Wikipedia article URLs.

*   **population_by_country_AUG.2024.csv:**
    *   Columns: Geography, Population
    *   Description: Contains the population for each country or region.

**Output Data:**

*   **wp_politicians_by_country.csv:**
    *   Columns: country, region, population, article_title, revision_id, article_quality
    *   Description: The primary output file. Contains data on each politician's Wikipedia article, including the country, region, population, article title, revision ID, and article quality score.

**Intermediary Files:**

*   **wp_countries-no_match.txt:**
    *   Description: Contains a list of countries that did not have a matching entry in the `politicians_by_country.AUG.2024.csv` and `population_by_country_AUG.2024.csv`
