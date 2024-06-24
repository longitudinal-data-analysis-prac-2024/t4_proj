```{=html}
<!---
title: "our_front_cover"
author: "chrysie"
date: "2024-05-16"
output:
  html_document:
    theme: cerulean  # Choose a Bootstrap theme
    highlight: tango  # Choose a syntax highlighting style
    toc: true        # Table of contents
    toc_float: true  # Floating table of contents
    keep_md: false   # Hide the YAML header in the rendered HTML output
--->
```
Chrysie, Tat and Zoe's LDAP Project

<img src="https://media1.tenor.com/m/rtY9m7EokSYAAAAC/cat-loading.gif"/>

# Background

Our longitudinal project was based on Rice et al., 2017 <https://doi.org/10.5255/UKDA-SN-852714>

This was titled: A longitudinal multi-informant study of psychological adjustment and academic attainment over the transition from primary school to secondary school

# Our research question

To investigate the role of our IVs on psychological adjustment in children from primary to secondary school

IVs: personal characteristics, attitudes to school, relationships & academic attainment

We looked at this over 3 waves - end of year 6, start of year 7 and end of year 7

# Cleaning and processing our data

First, we had to clean and process our data. For example, here is our code where we separating the SDQ (Strengths & Difficulties Questionnaire) into the 3 waves and summing up the rows of data:

cols_C1B \<- new_data[, c("C1_B1", "C1_B2", "C1_B5", "C1_B10", "C1_B11", "C1_B12", "C1_B13", "C1_B14", "C1_B15", "C1_B16", "C1_B17", "C1_B18", "C1_B19", "C1_B20", "C1_B21", "C1_B22", "C1_B23", "C1_B24", "C1_B25")]

cols_C2B \<- new_data[, c("C2_B1", "C2_B2", "C2_B5", "C2_B10", "C2_B11", "C2_B12", "C2_B13", "C2_B14", "C2_B15", "C2_B16", "C2_B17", "C2_B18", "C2_B19", "C2_B20", "C2_B21", "C2_B22", "C2_B23", "C2_B24", "C2_B25")]

cols_C3B \<- new_data[, c("C3_B1", "C3_B2", "C3_B5", "C3_B10", "C3_B11", "C3_B12", "C3_B13", "C3_B14", "C3_B15", "C3_B16", "C3_B17", "C3_B18", "C3_B19", "C3_B20", "C3_B21", "C3_B22", "C3_B23", "C3_B24", "C3_B25")]

C1_Btotal \<- rowSums(cols_C1B) C2_Btotal \<- rowSums(cols_C2B) C3_Btotal \<- rowSums(cols_C3B)

Once we had organised all our data like this, we created a tibble & converted into long format.

long_data \<- sum_data %\>%

pivot_longer(

cols = matches("C[123]"),

names_to = c("timepoint", "measure"),

names_pattern = "C(\\d+)(.\*)" ) %\>%

pivot_wider(names_from = measure, values_from = value ) %\>%

rename(Time = timepoint) %\>%

mutate(Time = factor(Time, levels = c("1", "2", "3"))) %\>%

arrange(ID, Time) %\>%

relocate(Time, .after = ID) %\>%

mutate(Time = as.numeric(Time)) %\>%

mutate_at(vars(ends_with("total")), \~replace_na(., 0)) %\>%

mutate_at(vars(FSM, Eng, Mat), \~replace_na(.,0))

source(analysis.Rmd)

# Our results

Here is a figure showing the change in SDQ score over time![](output/base_mod_fig.jpg)

Here is a figure showing effect of free school meals on SDQ score over time![](output/fsm_mod_fig.jpg)

# Descriptive data

We also had a look at some demographic data out of interest. Here are the children's grades[ ](scripts/descriptives/gradegraph.png)

Here is the ethnicity of the children[ ](scripts/descriptives/ethnicitygraph.png)

The gender:[ ](scripts/descriptives/gendergraph.png)

And the languages most commonly spoken as the first language:[ ](scripts/descriptives/languages_wordcloud.png)
