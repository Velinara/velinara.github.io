# An Analysis of Legal Recorded Gun Purchases and Violent Gun Crime Over Time by State
### by Casey Harris

## Table of Contents
1. Introduction
2. Description of Data and Data Sources
3. Pruning, Analysis, and Visualization of FBI NICS Data and Altered FBI NICS Data
4. Analysis and Visualization of CDC Data
5. Comparisons between Altered FBI NICS Data and CDC Data
6. Conclusions

## 1. Introduction
It's no secret that gun-related crime is a big problem in America. The number of mass shootings in 2019 alone is over 390 [[1]](https://www.gunviolencearchive.org/), more than the number of days in a year. (FINISH)

## 2. Description of Data and Data Sources
The first data set I will be examining is from the FBI's National Instant Criminal Background Check System (NICS) Firearm Checks [[2]](https://www.fbi.gov/file-repository/nics_firearm_checks_-_month_year_by_state_type.pdf/view) which has been parsed into a csv file by Buzzfeed [[3]](https://github.com/BuzzFeedNews/nics-firearm-background-checks) from the years 1998 - 2019. In Buzzfeed's Github, they note some very important caveats about the data, which can also be found in the NICS Firearm Checks PDF. These caveats are that:

1. A one-to-one correlation cannot be made between a firearm background check and a firearm sale.
2. The FBI’s numbers don’t include private gun sales, many of which do not require a background check.

Despite these caveats, the FBI’s NICS numbers are widely accepted as the best proxy for total gun sales in a given time period. However, I also plan on using a method to better estimate the number of gun sales. A professor at Georgia Regents University named Jurgen Brauer recommends a method in the Small Arms Survey [[4]](http://www.smallarmssurvey.org/fileadmin/docs/F-Working-papers/SAS-WP14-US-Firearms-Industry.pdf) where "each long gun and handgun check was counted as 1.1 sales. Each multiple-gun check was counted as two sales. Permit checks and other types of checks were omitted. The multiplier is an estimate based on Mr. Brauer's interviews with gun shop owners."

The second set of data I will be examining is from the Centers for Disease Control and Prevention's (CDC) fatal injury reports from 1999 - 2017 [[5]](https://www.cdc.gov/injury/wisqars/fatal.html). I submitted a request to their database and I specified that I only wanted information about violent crime involving guns for each state. (FINISH)

## 3. Pruning, Analysis, and Visualization of FBI NICS Data
This is a sample of what the table from the csv looks like unaltered:
(INSERT CELL 2)

It was indicated by The New York Times analyzed NICS data in Dec. 2015 that not all columns in the table represent sales. Handgun, Long Gun, and Multiple indicate sales, while others are excluded. In that case,  will keep only the pertinent information, which is the year/month, state, handgun, long gun, and multiple. I'm also going to remove the 4 US territories that are included so that we'll be left with the 50 states.
(INSERT CELL 3)

That looks a bit more reasonable. However, I'm not interested in having it in a month by month format. I also want to have the years line up between this data and the CDC data, so I will be condensing the Year_Month column into only Year, and I will drop all years before 1999 and after 2017.
(INSERT CELL 4)

Now I'm going to get a general idea of the trend of gun purchasing overall in the United States from 1999 to 2017. Keep in mind that this data has not been altered yet with Jurgen Brauer's suggested method to get a more accurate estimation of sales. 
(INSERT CELL 5)

Overall it appears there has been a positive trend in the number of background checks, which implies more guns being purchased. It is noteworthy that there is a slight dip around the year 2005. Next, I will adjust the numbers of the background checks to better represent the true number of gun sales.
(INSERT CELL 6)

Without the method suggested by Jurgen Brauer to better estimate the number of gun sales, we would ultimately have overlooked thousands of gun sales. The most obvious example of this in the graphs is that Multiple Gun background checks were doubled, resulting in the upper bound for Multiple Guns increasing by 200,000. I will be using the altered data exclusively from this point on.

I am now interested in seeing which state has sold the most guns total. I will be summing all gun sales for each state across all years.
(INSERT CELL 7)

It is clear from the choropleth map that Texas as a state has seen the most gun purchases between 1999 and 2017. How does that stack up against crime statistics? Is Texas also the state where the most gun crime occurs?

## 4. Analysis and Visualization of CDC Data
This is a sample of what the table from the csv looks like unaltered:
(INSERT CELL 8)

I'm not particularly interested in information outside of the year, state, population, deaths, crude rate, and age-adjusted rate, so I will remove all other rows. I will also remove the rows with NaN, as they are simply rows that contain the overall totals for each year.
(INSERT CELL 9)
