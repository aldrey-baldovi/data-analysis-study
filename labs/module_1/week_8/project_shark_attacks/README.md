# Project 02: Data Cleaning and Data Manipulation 

## Description
This is the result of the second project, using all the knowledge acquired up to week 8.

## Data source
The link to the dataset:  [Global Shark Attack File](http://www.sharkattackfile.net/incidentlog.htm)
This dataset provides a global shark attack information.

## Objective
The central objective of this project was to answer a problem statement practicing data cleaning and data manipulation.

## Resources

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
 
   - The dataset was filtered to use only the needed columns to answer the hypothesis presented: 

```df = ['date', 'year', 'type', 'country', 'sex', 'age','species','activity','fatal']```

 **Renaming columns**
 
   - Lower case and no spaces
    
 **Working with null values**
 
   - Dropping lines or replacing values
    
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
|SEX      | CENTURY  |FATAL CASES|
|--       |--        |--         |
| Male    |18        |74         |
|         |19        |256        |
|         |20        |714        |
|         |21        |143        |
| Female  |18        |5          |
|         |19        |9          |
|         |20        |72         |
|         |21        |22         |

### Are there more death cases with the activity surf in the last years?

**All years for male and female sex:**
| ACTIVITY |   CASES   |FATAL CASES|
|--        |--         |--         |
|Surfing   |**1033**      |67         |
|Swimming  |724        |**184**        |
|Fishing   |531        |70         |
|Diving    |325        |81         |

Activity group with more death cases: **Swimming**

**18th Century:**
|SEX      | ACTIVITY |FATAL CASES|
|--       |--        |--         |
| Male    |**Swimming**  |**3**          |
|         |Fishing   |1          |
|         |Other     |1          |
| Female  |-         |-          |

Activity group with more death cases: **Swimming**

**19th Century:**
|SEX      | ACTIVITY |FATAL CASES|
|--       |--        |--         |
| Male    |**Swimming**  |**17**         |
|         |Bathing   |11         |
|         |Other     |6          |
|         |Fishing   |2          |
|         |Boarding  |4          |
|         |Fishing   |2          |
|         |Floating  |1          |
|         |Surfing   |1          |
| Female  |-         |-          |


Activity group with more death cases: **Swimming**

**20th Century:**
|SEX      | ACTIVITY |FATAL CASES|
|--       |--        |--         |
| Male    |**Swimming**  |**134**        |
|         |Other     |69         |
|         |Diving    |53         |
|         |Fishing   |49         |
|         |Surfing   |34         |
|         |Bathing   |15         |
|         |Boarding  |6          |
|         |Floating  |5          |
|         |Boat      |3          |
|         |Snorkling |1          |
|         |Yatching  |1          |
| Female  |**Swimming**  |**20**         |
|         |Other     |10         |
|         |Diving    |9          |
|         |Bathing   |3          |
|         |Floating  |1          |
|         |Kayaking  |1          |
|         |Snorkling |1          |
|         |Surfing   |1          |

Activity group with more death cases: **Swimming**

**21th Century:**
|SEX      | ACTIVITY |FATAL CASES|
|--       |--        |--         |
| Male    |**Swimming**  |**30**         |
|         |**Surfing**   |**30**         |
|         |Diving    |17         |
|         |Fishing   |17         |
|         |Boarding  |16         |
|         |Other     |8          |
|         |Snorkling |8          |
|         |Bathing   |1          |
|         |Boat      |1          |
|         |Kayaking  |1          |
| Female  |**Swimming**  |**11**         |
|         |Snorkling |6          |
|         |Diving    |2          |
|         |Fishing   |1          |
|         |Bathing   |1          |
|         |Surfing   |1          |

Activity group with more death cases: **Swimming**


There were more fatal cases with the activity surf in the last years, but it wasn't the most fatal activity.

### Are there more unprovoked death cases?

Yes, there was 100 unprovoked death cases against 1 provoked death case. The other cases had invalid or questionable information.

Regarding cases with no deaths, there was 4704 unprovoked cases and 600 provoked cases

### Are there more death cases with young people in all centuries?



### Are there more death cases with young people in all centuries?

**Summing up:**
Age group with more cases in 18th century: **Teenager**
Age group with more cases in 19th, 20th and 21th centuries: **Young Adult**

Table X. Fatal cases by sex male by 18th century by age group
|AGE GROUP  |FATAL CASES|
|---------  |-----------|
|           |18th Century|
|**Male**   | --        |
| Kids      |0          |
|**Teenager**   |**3**         |
|Young Adult|1          |
|Adult      |1          |
|Elder      |0          |

Age group with more cases: **Teenager**

Table X. Fatal cases by sex male by 19th century by age group
|AGE GROUP  |FATAL CASES|
|---------  |-----------|
|           |19th Century|
|**Male**   | --        |
| Kids      |8          |
|Teenager   |7          |
|**Young Adult**|**22**         |
|Adult      |5          |
|Elder      |0          |

Age group with more cases: **Young Adult**

Table X. Fatal cases by sex male and female by 20th century by age group
|AGE GROUP  |FATAL CASES|
|---------  |-----------|
|           |20th Century|
|**Male**   | --        |
| Kids      |22         |
|Teenager   |82         |
|**Young Adult**|**184**        |
|Adult      |70         |
|Elder      |12         |
|**Female** | --        |
| Kids      |4          |
|Teenager   |9          |
|**Young Adult**|**19**         |
|Adult      |10         |
|Elder      |4          |

Age group with more cases: **Young Adult**

Table X. Fatal cases by sex male and female by 21th century by age group
|AGE GROUP  |FATAL CASES|
|---------  |-----------|
|           |21th Century|
|**Male**   | --        |
| Kids      |0          |
|Teenager   |13         |
|**Young Adult**|**56**         |
|Adult      |46         |
|Elder      |14         |
|**Female** | --        |
| Kids      |1          |
|Teenager   |3          |
|**Young Adult**|**7**          |
|Adult      |4          |
|**Elder**      |**7**          |

Age group with more cases: **Young Adult**

### Are there more death cases in locations with no legislation or safety measures?
### Are there more death cases in summer seasons?





---
## Conclusion






