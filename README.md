# Analyzing-Trends-in-the-Frequency-of-Plane-Crashes-Over-Time
Repository for my project assessing trends and changes in frequency of plane crashes between 1918 and 2022.

This is the repo for my ITEC 4220 Advanced Analytics project in which I assess trends in air crashes and their associated fatalities over time. To start, I 
downloaded the historical plane crash data set as PlaneCrashes.csv from Kaggle at the url https://www.kaggle.com/datasets/abeperez/historical-plane-crash-data. 
With this project, I hope to evaluate the relative safety of air travel across different eras of aviation.

Here is some preliminary analysis in R:

```
pc <- read.csv("PlaneCrashes.csv")
Year <- pc$Year
annual_deaths <- aggregate(`Total.fatalities` ~ Year, data = pc, sum) #total plane crash fatalities per unique year
head(annual_deaths)
```
This barplot shows the annual frequency of plane crash fatalities. I chose a barplot for this because "Year" is discrete rather than continuous.
```
barplot(annual_deaths$Total.fatalities,
        names.arg = annual_deaths$Year, main = "Annual Plane Crash Fatalities", xlab = "Year", ylab = "Total Fatalities", las = 2)
#"las = 2" turns the x axis labels on their side so more numbers can fit
```

Mode of "Year" in the dataset. This will display the year with the most plane crashes
```
annual_crashes <- table(Year)
worst_year_crashes <- names(sort(annual_crashes, decreasing = TRUE))[1]
#This gets the mode by creating a frequency table, sorting it, and taking the largest number
worst_year_crashes
```

Linear regression was able to find a downward trend, evidenced by a years coefficient of -0.6691, but wasn't able to deem it statistically significant due to a p value of 0.1464
```
years <- 1918:2022
model <- lm(annual_crashes ~ years)
summary(model)
```

Histogram of annual plane crashes
```
hist(Year, ylim = c(0,1000), main = "Number of Plane Crashes Per Year", 
     ylab = "Number of Plane Crashes",breaks = 104)
```
I chose to perform a Wilcox test for this because it is non-parametric, making it a better test for a non normal distribution than a t test. I chose to split the data at 1977 because it was the year of the deadliest aviation accident in history, the Tenerife disaster, where two fully loaded 747s collided on the runway in the Canary Islands after one of them began to take off without clearance.

I chose to perform a Wilcox test for this because it is non-parametric, making it a better test for a non normal distribution than a t test. I chose to split the data at 1977 because it was the year of the deadliest aviation accident in history, the Tenerife disaster, where two fully loaded 747s collided on the runway in the Canary Islands after one of them began to take off without clearance.

Unfortunately, a p-value of 0.9871 is far too large to deem the difference in means between pre and post Tenerife air crash fatalities statistically significant.
```
pre_77 <- annual_deaths[annual_deaths$Year <= 1977, "Total.fatalities"]
post_77 <- annual_deaths[annual_deaths$Year > 1977, "Total.fatalities"]
wilcox.test(pre_77, post_77)
```

[html](https://github.com/PeteDavis2002/Analyzing-Trends-in-the-Frequency-of-Plane-Crashes-Over-Time/blob/main/PlaneCrashesMarkdown.html)

[PlaneCrashes dataset as JSON](https://github.com/PeteDavis2002/Analyzing-Trends-in-the-Frequency-of-Plane-Crashes-Over-Time/blob/main/PlaneCrashes.json)
