## U.S. Mass Shootings Exploratory Analysis 

This notebook conducts exploratory analysis of U.S. Mass Shootings using a [dataset](https://www.kaggle.com/zusmani/us-mass-shootings-last-50-years) of events dated 1966 - 2017. The dataset contains 323 recorded events, with information for metadata categories:
- Title
- Location
- Date
- Summary
- Fatalities
- Injured
- Total victims
- Mental health issues
- Race
- Gender
- Employment status
- Latitude/longitude

I first approached this dataset by first examining and cleaning it to be suitable for analysis and manipulation. I then conducted exploratory data analysis by visualizing several aggregate information (datetime; yearly, quarterly, monthly, days of the week, weekday vs weekend), and cautiously examining other factors (shooters' gender, race, mental health, state of employment). 

For non-categorical variables (event summaries, descriptions), I conducted a textual analysis by using the WordCloud module to assess predominent words - that is, words that were most frequently used in event descriptions and summaries. Using the results of this analysis, it became possible to focus on specific kinds of shootings to begin to understand their trends. 
