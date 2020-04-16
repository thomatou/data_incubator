# Evaluation of gender parity as a function of party affiliation

The goal of my project is to depict the evolution of gender representation in federal electoral politics. Being a traditionally male-dominated field that is nonetheless susceptible to (and demonstrative of) shifts in cultural, political, and economic attitudes and events, I was curious to see whether the feminist movements and iterations of “culture wars” of the 20th century had resulted in an increase in female representation in the U.S. House of Representatives and the U.S. Senate.

I started this project by using the [Propublica API](https://projects.propublica.org/api-docs/congress-api/members/), which holds a wealth of information relating to current and past members of congress. Unfortunately, its records start in the early 1990s, and I was forced to look elsewhere to have a more complete picture of the 20th century. I thus developed a [Python script](https://github.com/thomatou/data_incubator/blob/master/biography_congress_scraping_cleaning.ipynb) to scrape the [Biographical Directory of the United States Congress](http://bioguide.congress.gov/biosearch/biosearch1.asp), which maintains records going back to 1917—the date when the first woman was sworn into Congress. 

Though complete, the Biographical Directory does not explicitly list the gender of House and Senate members. A first-pass approach to determining gender was through the publicly-accessible R package `gender`, which makes its prediction based on an individual’s first name, date of birth, and matching Social Security Administration records.

![](/visuals/process_visual.png)

This approach was cross-validated on a gender-annotated dataset for the current members of Congress, where the gender-prediction methodology estimated a male/female ratio in Congress that was within ~2% of the actual value.

Visualizing this data has yielded some promising insights. For instance, female representation has historically been higher in the House of Representatives than in the Senate, but more recent data shows that this difference has largely levelled off, as evidenced in the plot below. While still underrepresented in both chambers of Congress, women occupy a roughly equal proportion of the seats in Senate as they do in the House of Representatives.

![](/visuals/Stacked_bar_chart.png)

A streamgraph representation of the gender split in Congress, using R’s dedicated `streamgraph` [package](https://github.com/hrbrmstr/streamgraph), provides an insightful look at the 20,000 members of Congress that have been in office over the past century. While the number of women in Congress has been steadily increasing over the past 30 years, the number of female democrats is growing noticeably faster than the number of female republicans.

![](/visuals/women_by_party_streamgraph.png)

Despite this steady increase in female representation, it remains that gender parity is still a while away.

![](/visuals/Streamgraph.png)

<span style="font-size:4em;">Female Democrats are represented in dark blue, female Republicans in dark red; male Democrats in light blue, and male Republicans in light red. The yellow line corresponds to independent members.</span>

While the issue of female underrepresentation in Congress has been reported on extensively, this public discussion has yet to be supplemented with clear and impactful visualizations that approach this issue from the point of view of party affiliation. Such observations should be part of the decision-making process for individuals or organizations that support political parties (notably through donations), and provide a 'quick and dirty' way of establishing whether a party's policy on gender representation aligns with one's convictions.
