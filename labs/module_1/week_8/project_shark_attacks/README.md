# Project 02: Data Cleaning and Data Manipulation 

## Description
This is the result of the second project, using all the knowledge acquired up to week 8.

## Data source
The link to the dataset:  [Global Shark Attack File](http://www.sharkattackfile.net/incidentlog.htm)
This dataset provides a global shark attack information.

## Objective
The central objective of this project was to answer a problem statement practicing data cleaning and data manipulation.

## Resources:

 - Python
 - Jupyter Notebook
 - Pandas
 - Numpy
 - Regular Expression

```python
import pandas as pd
import numpy as np
import re
```
## Process

 1. Obtaining dataset
 2. Establishing hypothesis

There are more death cases:
 - [x] with **man than woman**
 - [x] with **man than woman** in all centuries
 - [x] with the activity **`surf` in the last years** 
 - [x] **unprovoked** 
 - [x] with **young people** in all centuries
 - [x] in locations with no legislation or safety measures 
 - [ ] in **summer** seasons
	
 3. Cleaning and Manipulating dataset
 **Filtering dataset**
The dataset was filtered to use only the needed columns to answer the hypothesis presented: 
```df = ['date', 'year', 'type', 'country', 'sex', 'age','species','activity','fatal']```

    **Renaming columns**
    Lower case and no spaces
    
    **Working with null values**
    Dropping lines or replacing values
    
    **Correcting and manipulating data**
    - **fix_sex function:** to correct data from `df['sex']`
    - `.fillna()` and `.loc` to correct data from `df['fatal']`
    - **fix_age function:** to correct data from `df['age']`
    - **fix_activity function:** to correct data from `df['activity']`
	- `.groupby()` to group columns
	- `.query()` to consult dataset
 
	 **Establishing intervals**
    It was established intervals to `df['age']` and `df['year']`:

Table 1. Intervals to `df['age']`
|CATEGORY| AGE |
|--|--|
|Child|<13|
|Teenager|13 - 17|
|Young Adult|18 - 32|
|Adult|33 - 55|
|Elder| >55 |
    
 Table 2. Intervals to `df['year']`
|CATEGORY| YEAR |
|--|--|
|Century 18|<1800|
|Century 19|1801 to 1900|
|Century 20|1901 to 2000|
|Century 21|2001 to 2100|


## Results

### Are there more death cases with man than woman?
Yes! Table 3 shows the results.

Table 3. Fatal cases by sex 
|SEX| FATAL CASES |
|--|--|
| Male |1195|
| Female |108|

### Are there more death cases with man than woman in all centuries?
Yes! Table 4 shows the results.

Table 4. Fatal cases by sex by century
|SEX| CENTURY |FATAL CASES|
|--|--|--|
| Male |18|74|
||19|256|
||20|714|
||21|143|
| Female |18|5|
||19|9|
||20|72|
||21|22|

### Are there more death cases with the activity surf in the last years?
Yes! 





### Are there more unprovoked death cases?

### Are there more death cases with young people in all centuries?



### Are there more death cases with young people in all centuries?
### Are there more death cases in locations with no legislation or safety measures?
### Are there more death cases in summer seasons?



Table 4. Fatal cases by sex male by century 18 by age group
|AGE GROUP|FATAL CASES|
|---------|-----------|
|         | Century 18|
|**Male** | --        |
| Kids    | 74     |
|Teenager|256|
|Young Adult|714|
|Adult|143|
|Elder|5|

---
## Conclusion






