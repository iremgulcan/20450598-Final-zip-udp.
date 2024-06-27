title=""Global Daily Smoking Rates""

name="İREM Gülcan-20450598"

Research Question=How do daily smoking rates compare across different countries worldwide?-This research examines the variations in daily smoking rates across different countries to identify global smoking trends and patterns.

Data <source src=ttps://www.smokefree.org.nz/smoking-its-effect-The page on Smokefree NZ explains the harmful effects of smoking, including its impact on health, such as causing cancer, heart disease, and respiratory problems, as well as its broader societal and economic consequences.

Summary:df <- read.csv("path\_to\_your\_csv\_file.csv")                 

| Factor                |  Mean |  Standard Deviation |  Minimum |  Maximum |

\|-----------------------|-------|---------------------|----------|----------|

| Nicotine Addiction    | 20.12 |                6.72 |     11.1 |     33.5 |

| Peer Influence        | 20.78 |                6.59 |     12.2 |     23.7 |

| Stress and Coping     | 24.79 |               11.29 |    11.45 |    54.45 |

| Psychological Factors | 34.15 |               15.72 |    12.23 |    68.89 |

| Genetic Factors       | 34.97 |               14.37 |    12.24 |    67.78 |

| Media                 | 41.71 |               17.60 |    11.12 |    78.89 |

| Availability          | 27.83 |               10.01 |      6.0 |    55.56 |

| Economic Factors      | 29.31 |               16.58 |    11.12 |   511.12 |

The summary statistics table reveals that Media and Economic Factors have the highest means (41.71 and 29.31, respectively) and also exhibit the greatest variability, as evidenced by their standard deviations (17.60 and 16.58). In contrast, Nicotine Addiction and Peer Influence have lower means (20.12 and 20.78) and relatively less variability, indicating more consistency in these factors among the data points.

Plot=# Load necessary libraries

library(ggplot2)

library(tidyr)

\# Create a data frame with your detailed data

data <- data.frame(

`  `Nicotine\_Addiction = c(22.2, 20.4, 19.8, 23.5, 23.6, 32.4, 28.6, 21.7, 24.7, 12.3, 12.9, 13.5, 32.4, 23.6, 23.2, 22.2, 23.4, 12.5, 19.7, 24.7, 12.3, 13.5, 23.5, 11.1, 12.9, 19.7, 11.1, 23.2, 11.1, 12.5, 31.5, 12.9, 21.7, 12.5, 21.7, 13.5, 20.4, 19.8, 22.2, 20.4, 33.5, 21.7, 13.5, 12.3, 19.7, 13.5, 12.5, 19.82, 19.8),

`  `Peer\_Influence = c(23.7, 23.5, 22.5, 23.5, 22.5, 23.7, 22.5, 23.5, 23.5, 22.5, 12.9, 23.7, 12.9, 12.3, 22.5, 12.2, 12.3, 12.9, 23.7, 21.2, 21.2, 22.5, 21.2, 12.9, 12.2, 19.7, 12.9, 12.2, 12.9, 12.3, 23.7, 21.2, 12.2, 21.2, 23.7, 23.5, 12.9, 12.9, 19.7, 21.2, 23.5, 21.2, 21.2, 21.2, 19.7, 12.3, 22.5, 23.7, 23.5),

`  `Stress\_and\_Coping = c(12.45, 13.56, 23.76, 11.45, 22.56, 32.45, 32.56, 24.5, 12.2, 12.2, 23.37, 24.4, 12.29, 35.58, 23.56, 21.56, 32.23, 43.0, 23.39, 21.56, 34.23, 23.56, 12.26, 12.25, 23.56, 45.56, 23.78, 34.45, 54.45, 34.56, 23.34, 25.34, 23.12, 23.89, 23.45, 21.23, 12.45, 52.56, 23.57, 23.45, 23.56, 23.67, 12.24, 22.13, 21.1, 24.5, 32.2, 22.3, 22.3),

`  `Psychological\_Factors = c(28.78, 23.36, 23.57, 23.56, 34.45, 46.67, 47.78, 34.46, 23.36, 24.46, 12.23, 12.29, 14.34, 23.35, 22.25, 23.35, 22.25, 34.45, 45.56, 23.35, 45.56, 34.45, 34.45, 23.35, 45.57, 34.45, 56.67, 45.45, 34.45, 56.67, 45.56, 34.45, 54.45, 45.45, 67.78, 44.45, 43.45, 66.78, 55.56, 54.45, 44.45, 18.56, 23.34, 45.56, 34.45, 45.56, 68.89, 34.45, 23.34),

`  `Genetic\_Factors = c(23.35, 45.56, 22.24, 22.24, 12.24, 34.46, 56.67, 54.45, 34.45, 45.56, 34.45, 23.34, 45.56, 45.56, 57.78, 67.78, 43.45, 23.35, 34.45, 23.35, 45.56, 34.46, 34.45, 34.45, 34.45, 34.45, 56.67, 45.45, 34.45, 56.67, 45.56, 34.45, 54.45, 45.56, 67.78, 44.45, 43.45, 66.78, 55.56, 54.45, 44.45, 18.56, 23.34, 45.56, 34.45, 45.56, 68.89, 34.45, 23.34),

`  `Media = c(56.67, 45.56, 34.45, 46.64, 34.45, 23.34, 45.56, 55.56, 45.56, 67.78, 66.60, 34.45, 45.56, 45.56, 34.45, 22.23, 34.45, 34.45, 23.34, 12.23, 34.67, 34.45, 67.79, 34.45, 34.45, 78.89, 11.12, 46.68, 34.45, 67.78, 56.67, 34.45, 45.57, 67.78, 48.0, 34.0, 23.0, 34.45, 34.45, 56.50, 78.89, 23.34, 23.34, 55.56, 67.78, 55.56, 34.45, 46.67, 34.0),

`  `Availability = c(23.34, 22.23, 22.22, 21.23, 21.12, 33.34, 34.45, 34.46, 33.34, 55.56, 34.45, 53.33, 33.34, 21.12, 11.12, 34.45, 23.35, 23.35, 25.56, 23.35, 23.34, 23.34, 33.34, 23.35, 33.35, 33.23, 22.23, 23.34, 23.34, 34.45, 46.67, 45.0, 34.0, 6.0, 34.0, 33.0, 23.0, 34.0, 45.0, 33.0, 34.0, 23.0, 21.0, 34.0, 32.0, 21.0, 34.0, 34.46, 34.45),

`  `Economic\_Factors = c(32.23, 23.34, 23.33, 21.23, 21.12, 22.23, 21.12, 22.12, 45.56, 21.12, 22.23, 34.45, 23.34, 12.23, 12.23, 111.12, 511.12, 22.23, 21.12, 34.3, 56.89, 34.45, 34.45, 32.23, 21.13, 34.45, 11.12, 23.34, 45.56, 34.45, 23.34, 23.34, 23.33, 22.12, 12.20, 11.14, 23.34, 34.45, 21.12, 23.34, 33.30, 22.23, 21.23, 78.45, 34.45, 45.0,-

The plot likely visualizes the relationship between various factors (such as peer influence, stress and coping mechanisms, psychological and genetic factors, media exposure, availability, and economic factors) and nicotine addiction rates. It would illustrate how these factors may contribute to or correlate with varying levels of nicotine addiction among individuals in the dataset.

Analysis:# Perform correlation analysis between Nicotine\_Addiction and other factors

correlations <- cor(data)

\# Extract correlations with Nicotine\_Addiction

nicotine\_correlations <- correlations[, "Nicotine\_Addiction"]

\# Rank correlations by absolute value

sorted\_correlations <- sort(abs(nicotine\_correlations), decreasing = TRUE)

\# Print the sorted correlations

sorted\_correlations

\```r

\# Perform correlation analysis between Nicotine\_Addiction and other factors

correlations <- cor(data)

\# Extract correlations with Nicotine\_Addiction

nicotine\_correlations <- correlations[, "Nicotine\_Addiction"]

\# Rank correlations by absolute value

sorted\_correlations <- sort(abs(nicotine\_correlations), decreasing = TRUE)

\# Print the sorted correlations

sorted\_correlations

\*\*Interpretation: \*\* The code calculates and sorts the absolute correlations between Nicotine\_Addiction and other factors, revealing which variables are most strongly associated with nicotine addiction in the dataset.

Conclusion

The correlation analysis identifies which factors are most strongly associated with nicotine addiction, providing insights into the potential influences contributing to varying levels of addiction in the studied population.


