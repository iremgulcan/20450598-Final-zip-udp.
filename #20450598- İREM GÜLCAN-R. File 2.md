#20450598- İREM GÜLCAN-R. File

\# Question 1a -Please write the name your term project.

\# Global smoking trends

\# Question 2a) Suppose we define x vector in R with x <- 10:20. What is the result if we run x[seq(1, 5, by = 3)]?----

\# <- 10:20

x = 10 11 12 13 14 15 16 17 18 19 20

seq(1, 5, by = 3)

1 4

x[seq(1, 5, by = 3)]

x[1] = 10

x[4] = 13

The R code `x <- 10:20` creates a vector from 10 to 20, and `x[seq(1, 5, by = 3)]` selects the elements at positions 1 and 4, resulting in `10 13

\# Question 2b Suppose we have two Tibbles, dt1 and dt2. Suppose that we want to return all rows from dt1 where there are matching values in dt2, and all columns from dt1 and dt2. If there are multiple matches between dt1 and dt2, all combination of the matches is returned. We want to store the results in dt3. What are the commands for this operation? -

\# To achieve this in R using Tibbles from the dplyr package, you can use the inner join function to return all rows from dt1 where there are matching values in dt2 and include all columns from both dt1 and dt2. If there are multiple matches, all combinations of the matches are returned.

\# Question 2c In Figure 1, there is a graph plotted by using the dt Tibble object. What are the required ggplot2 commands for this graph--

\# --library(ggplot2) ###

ggplot (data = dt, aes (x = x\_column, y = column)) +

`  `geom\_point () + # Example: scatter plot with points

`  `labs (title = "Figure 1", x = "X Axis Label", y = "Y Axis Label")

ggplot (data = dt, aes (x = time, y = value)) +

`  `geom\_line () +

`  `labs (title = "Figure 1", x = "Time", y = "Value")
This would create a line plot showing how value changes over time, with a title "Figure 1" and labeled axes. Adjust the geom function (geom\_line, geom\_point, etc.) according to the type of plot WE want to visualize

\# Question 2d If we run the commands below what will be the result of the myresult object? mylist <- list (1:3, c(3:5, NA)) myresult <- map(mylist, ~ mean(.x, na.rm = TRUE)) %>% unlist()-

#mylist <- list (1:3, c(3:5, NA)) 

myresult <- map (mylist, ~ mean(.x, na.rm = TRUE)) %>% unlist()

2 4

\# Question 2e: Suppose X1,··· ,X25 iid ∼ N(µ,σ) and let Z = 5( ¯ Xn − µ)/S. What is the R code to calculate P(Z ≤ 1)? -

\# # Assumptions

n <- 25 # Sample size

mu <- 0 # Mean

sigma <- 1 # Standard deviation

\# Calculation

z <- 5 \* (mean (norm (n, mu, sigma)) - mu) / sqrt(var(norm(n, mu, sigma)))

p\_value <- norm (1, 0, 1)

\# Result

cat ("P(Z ≤ 1) =", p\_value)-=24

\# Question 2f: Suppose we want to simulate die rolls in a backgammon game (in backgammon 2 dice are used) with a function. Using R commands and functions we covered in class, write a function that mimicks the dice roll and shows the results.

\## Function to simulate dice rolls in backgammon

simulate\_backgammon\_dice <- function() {

`  `# Roll the first die

`  `die1 <- sample(1:6, 1)

`  `# Roll the second die

`  `die2 <- sample(1:6, 1)

`  `# Print the results

`  `cat("Dice rolls:", die1, "and", die2, "\n")

`  `# Return the results as a vector

`  `return (c(die1, die2))

} Dice rolls: 3 and 5 

\# Question 2gSuppose that, using the titanic data in Question 2, we want to test if the survivors and non-survivors have the same mean for age. Which R command(s) do we need to use for this? (

\# # Load the Titanic dataset

data(Titanic)

\# Extract the age column and the survival status

age <- Titanic$Age

survived <- Titanic$Survived

\# Perform the two-sample t-test

t.test(age[survived == "Yes"], age[survived == "No"], 

var.equal = TRUE

To test if the survivors and non-survivors have the same mean for age in the Titanic dataset, assuming the two groups have the same variance, you can use the two-sample t-test in R.

\```r

\# Load the Titanic dataset

data(Titanic)

\# Extract the age column and the survival status

age <- Titanic Age

survived <- Titanic Survived

\# Perform the two-sample t-test

t.test(age[survived == "Yes"], age[survived == "No"], 

`       `var.equal = TRUE)

``

Explanation:

1\. We first load the Titanic dataset using the `data()` function.

2\. We extract the `Age` column and the `Survived` column from the Titanic dataset.

3\. We perform the two-sample t-test using the `t.test()` function. 

`   `- The first argument `age[survived == "Yes"]` provides the ages of the survivors.

`   `- The second argument `age[survived == "No"]` provides the ages of the non-survivors.

`   `- The `var.equal = TRUE` argument indicates that the two groups have the same variance.

The output of this code will provide the following information:

\- The mean age of the survivors and non-survivors

\- The t-statistic and the p-value of the test

\- The 95% confidence interval for the difference in mean ages

If the p-value is less than the chosen significance level (e.g., 0.05), you can conclude that the mean ages of the survivors and non-survivors are significantly different. Otherwise, you cannot reject the null hypothesis that the mean ages are the same.

\# Question 3a ----

#library(dplyr)

dat2 <- dat %>%

`  `filter(country %in% c("England", "Germany")) %>%

`  `mutate(gdp\_pc = gdp / population) 

\# A tibble: 6 x 5

`  `country  year   gdp population gdp\_pc

`  `<fct>   <int> <dbl>      <dbl>  <dbl>

1 England  2018 8000         80   100  

2 Germany 2018 10000        100   100  

3 England  2019 8100         90   110  

4 Germany 2019 11000        110   100  

5 England  2020 8500        100    85  

6 Germany 2020 10200        120    85
