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
library(readxl)
library(haven)
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

##What about missing data 
```{r}
litters_df = 
  read_csv(
    file = "FAS_litters.csv",
    na = c("NA", "", ".")
  )

litters_df = janitor:: clean_names(litters_df)

pull(litters_df, gd0_weight)
```

What if we code 'group' as a factor variable?

```{r}
litters_df = 
  read_csv(
    file = "FAS_litters.csv",
    na = c("NA", "", "."),
    col_types= cols(
      Group = col_factor()
    )
  )
```

##Import an excel file 

Import MLB 2011 summary data.
```{r}
mlb_df = read_excel("mlb11.xlsx" , sheet = "mlb11" )
```

##Import SAS data
```{r}
pulse_df = read_sas("public_pulse_data.sas7bdat")
print(pulse_df)
```

##Never use read.csv()

```{r}
litters_df = read.csv("FAS_litters.csv")
```

Never do this either:
```{r}
litters_df$L
```


