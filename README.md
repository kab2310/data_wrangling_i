# Data Wrangling I 

```{r}
### This repo has code from the first data wrangling topic in P8105.
```

---
title: "Data Import"
output: github_document 
---
##Set up data set 
```{r setup, echo=FALSE, message=FALSE}
library(tidyverse)
```


## Import the FAS Litters CSV
```{r}
litters_df = read_csv("FAS_litters.csv")
litters_df = janitor::clean_names(litters_df)
```

## Look at the dataset 
```{r eval = FALSE}
view(litters_df)
```

## Look at read_csv options 
```{r}
litters_df = 
  read_csv(
    file = "FAS_litters.csv",
    skip = 1
  )
```

What about missing data 
```{r}
litters_df
```

