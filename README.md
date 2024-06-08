# Deciphering Long-Term CO2 Trends: A Time Series Analysis of Mauna Loa Data

## Introduction

In 1958, Charles David Keeling (1928-2005) from the Scripps Institution of Oceanography began recording carbon dioxide (CO2) concentrations in the atmosphere at an observatory located about 3,400 meters altitude on the Mauna Loa Volcano on Hawaii Island. The location was chosen because it is not influenced by changing CO2 levels due to the local vegetation and because prevailing wind patterns on this tropical island tend to bring well-mixed air to the site. While the recordings are made near a volcano (which tends to produce CO2), wind patterns tend to blow the volcanic CO2 away from the recording site. Air samples are taken several times a day, and concentrations have been observed using the same measuring method for over 60 years. In addition, samples are stored in flasks and periodically reanalyzed for calibration purposes. The observational study is now run by Ralph Keeling, Charles's son. The result is a data set with very few interruptions and very few inhomogeneities. It has been called the "most important data set in modern climate research."

## Data

The data set for this problem can be found in `co2.csv`. It provides the concentration of CO2 recorded at Mauna Loa for each month starting March 1958. More description is provided in the data set file. We will be considering only the CO2 concentration given in column 5. The goal of the problem is to fit the data and understand its variations. You will encounter missing data points; part of the exercise is to deal with them appropriately.

## Model Description

Let \( C_t \) be the average CO2 concentration in month \( t \) ( \( t = 1, 2, \ldots \), counting from March 1958). We will look for a description of the form:

\[ C_t = P(t) + S(t) + R_t \]

where:

- \( P(t) \) accounts for the long-term trend.
- \( t_i \) is time at the middle of the \( i \)-th month, measured in fractions of years after Jan 15, 1958. Specifically, we take:

\[ t_i = \frac{i + 0.5}{12} \quad i = 0, 1, 2, \ldots \]

where \( t_0 \) corresponds to Jan 1958, adding 0.5 is because the first measurement is halfway through the first month.

- \( S(t) \) is periodic in \( t \) with a fixed period, accounting for the seasonal pattern.
- \( R_t \) is the remaining residual that accounts for all other influences.

The decomposition is meaningful only if the range of \( P \) is much larger than the amplitude of \( S \) and this amplitude in turn is substantially larger than that of \( R_t \).

## Tasks

1. Split the data into training and test datasets - you can perform an 80-20 split. All model fitting should be done on the training set and all the remaining data should be used for evaluation (for the purpose of model selection), i.e., prediction errors should be reported with respect to the test set.
2. Handle incomplete data sets using at least one method.
3. Perform time series regression and find the deterministic and periodic trends in data.
4. Interpret residuals.

## Requirements

- Python 3.x
- Pandas
- Numpy
- Matplotlib
- Statsmodels

## Installation

Clone the repository and navigate to the project directory:

```bash
git clone https://github.com/yourusername/mauna-loa-co2-analysis.git
cd mauna-loa-co2-analysis
```
Install the required Python packages:
``` bash 
pip install -r requirements.txt
```
## Usage

Run the main analysis script:

```bash
python main.py
```
## Results

The results will include:

- Trend analysis plots
- Seasonal pattern identification
- Residual analysis

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Acknowledgements

- [Scripps Institution of Oceanography](https://scripps.ucsd.edu/)
- [Ralph Keeling](https://en.wikipedia.org/wiki/Ralph_Keeling)
- [MITx 6.419x Data Analysis: Statistical Modeling and Computation in Applications team](https://www.edx.org/learn/data-analysis/massachusetts-institute-of-technology-data-analysis-statistical-modeling-and-computation-in-applications)
- [CSAIL at MIT](https://www.csail.mit.edu/)


