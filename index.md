# An Analysis of Legal Recorded Gun Purchases vs Violent Gun Crime by State
### by Casey Harris

### Table of Contents
1. Introduction
2. Description of Data and Data Sources
3. Pruning, Analysis, and Visualization of FBI NICS Data
4. Analysis and Visualization of CDC Data (With Comparisons to FBI NICS Data)
5. Analysis and Visualization of Altered FBI NICS Data (With Comparisons to CDC Data)
6. Conclusions

## 1. Introduction
It's no secret that gun-related crime is a big problem in America. The number of mass shootings in 2019 alone is over 390 [[1]](https://www.gunviolencearchive.org/), more than the number of days in a year. (NOT FINISHED)

## 2. Description of Data and Data Sources
I have grabbed data from several different sources to explore this topic. The first data set I will be examining is from the FBI's National Instant Criminal Background Check System (NICS) Firearm Checks [[2]](https://www.fbi.gov/file-repository/nics_firearm_checks_-_month_year_by_state_type.pdf/view) which has been parsed into a csv file by Buzzfeed [[3]](https://github.com/BuzzFeedNews/nics-firearm-background-checks). In Buzzfeed's Github, they note some very important caveats about the data, which can also be found in the NICS Firearm Checks PDF. These caveats are that:

1. A one-to-one correlation cannot be made between a firearm background check and a firearm sale.
2. The FBI’s numbers don’t include private gun sales, many of which do not require a background check.

Despite these caveats, the FBI’s NICS numbers are widely accepted as the best proxy for total gun sales in a given time period.

However, I also plan on using a method to better estimate the number of gun sales. A professor at Georgia Regents University named Jurgen Brauer recommends a method in the Small Arms Survey [[4]](http://www.smallarmssurvey.org/fileadmin/docs/F-Working-papers/SAS-WP14-US-Firearms-Industry.pdf)
