# Airline Customer Satisfaction Analysis

A Python-based customer analytics project exploring airline passenger satisfaction, service experience, and customer segments using survey data.

## Project overview

This project analyses **103,924 airline passenger survey responses** across **25 original variables**. The objective is to understand which parts of the passenger experience are associated with satisfaction and whether meaningful customer groups can be identified for more targeted operational and retention decisions.

The project combines data preparation, exploratory analysis, regression-based missing-value treatment, correlation analysis, and customer clustering.

## Business questions

### Customer satisfaction

* Which passenger and service-experience factors are associated with satisfaction or dissatisfaction?
* How could an airline use these findings to improve the customer experience and retention?

### Customer segmentation

* Which groups of similar passengers can be identified in the data?
* How do these groups differ by travel behaviour, class, loyalty, service ratings, and satisfaction?
* How could the airline adapt its operations or customer communication for each group?

## Repository contents

* **`Python Data Analysis code.ipynb`**: complete data preparation and analysis workflow
* **`Analysis of Results.pdf`**: summary of the analysis and business interpretation

## Dataset

The dataset contains passenger-level information including:

* age and gender
* loyal or disloyal customer status
* business or personal travel
* travel class and flight distance
* departure and arrival delays
* ratings for online booking, boarding, Wi-Fi, seat comfort, food, entertainment, baggage handling, check-in, cleanliness, and other services
* overall satisfaction outcome

The raw dataset is not currently included in this repository. To reproduce the notebook, add the source file as `data/passenger_data.csv` and update the import path in the notebook.

## Tools and libraries

* Python
* pandas
* NumPy
* scikit-learn
* Matplotlib
* Jupyter Notebook / Google Colab

## Analysis workflow

1. Inspected the structure, data types, and completeness of the raw survey data.
2. Standardised column names and prepared categorical fields with one-hot encoding.
3. Investigated **310 missing values** in the arrival-delay variable.
4. Used linear regression to estimate the missing arrival-delay values.
5. Treated survey responses recorded as zero where zero represented “not applicable”.
6. Used correlation analysis and a heat map to explore relationships between service variables and passenger satisfaction.
7. Applied K-means clustering to identify three passenger groups.
8. Compared K-means with DBSCAN using the Davies-Bouldin score.
9. Translated the analytical results into customer and operational implications.

## Customer segments identified

The K-means analysis produced three broad passenger groups.

### Cluster 0: shorter-distance, economy-heavy passengers

* **64,731 passengers**
* average flight distance: approximately **539**
* approximately **59% Economy Class**
* approximately **76% loyal customers**
* approximately **33% satisfied**

This is the largest and least satisfied segment. It suggests an important opportunity for service improvement and retention activity, especially across the economy and shorter-distance experience.

### Cluster 1: long-distance, loyal business travellers

* **15,992 passengers**
* average flight distance: approximately **3,091**
* approximately **91% Business Class**
* approximately **98% loyal customers**
* approximately **72% satisfied**

This is the most satisfied and highest-value-looking segment in the analysis. Maintaining service quality and loyalty among these passengers should be a priority.

### Cluster 2: mid-distance, mixed business segment

* **23,179 passengers**
* average flight distance: approximately **1,694**
* approximately **64% Business Class**
* approximately **88% loyal customers**
* approximately **53% satisfied**

This segment sits between the other two groups and may offer the strongest opportunity for targeted improvements that move moderately satisfied passengers toward higher loyalty and satisfaction.

## Model comparison

The Davies-Bouldin score was used to compare the clustering approaches. Lower values indicate more compact and better-separated clusters.

* **K-means:** 0.514
* **DBSCAN:** 1.503

Within the tested setup, K-means produced the clearer segmentation.

## Business implications

The analysis suggests three practical directions:

1. **Improve the core economy experience.** The largest passenger group has the lowest satisfaction level, making it the clearest area for service-recovery and retention initiatives.
2. **Protect the loyal business segment.** Long-distance business travellers show high satisfaction and loyalty, so consistency and service quality are essential.
3. **Use segment-specific actions.** Rather than treating all passengers alike, service improvements, offers, and communication can be adapted to travel class, distance, loyalty, and satisfaction patterns.

## How to run the project

1. Clone or download this repository.
2. Create a folder named `data`.
3. Add the survey dataset as `data/passenger_data.csv`.
4. Update the data-import cell in the notebook to:

```python
path = "data/passenger_data.csv"
df = pd.read_csv(path)
```

5. Install the required packages:

```bash
pip install pandas numpy scikit-learn matplotlib jupyter
```

6. Open the notebook and run the cells in order:

```bash
jupyter notebook
```

## Limitations and next steps

This was an early applied Python analytics project. A stronger next version would:

* add the original dataset source and a data dictionary
* use a fully relative and reproducible file path
* separate explanatory analysis from predictive modelling more clearly
* standardise clustering features before model fitting
* exclude identifiers and outcome variables from customer-segmentation features
* validate the number of clusters with additional metrics and visualisations
* add a concise executive summary with prioritised recommendations

## Author
Muhammad Ahmed
**Muhammad Ahmed**
[LinkedIn](https://www.linkedin.com/in/muhammad-ahmed-iba/) | [GitHub](https://github.com/AhmedHMCEU)
