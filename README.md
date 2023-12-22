**Our datastory** https://oddbits.eu

# Analyzing User's Choice of Countries in Pathfinding in Wikispeedia
## Abstract
Wikispeedia is a game about fast and efficient pathfinding from two articles. Oftentimes, users pass through articles more familiar to them, instead of jumping between unfamiliar articles. A readily available and often familiar recourse is country articles. But which countries do they pass through? Why do they choose *those* countries? Is it because they will lead to better success rates within the game, or due to external biases. Metrics are defined using measures of centrality and connectivity to gauge in-game performance, and external data is used to assess a country's economic and cultural footprint.

## Research Questions
1. What country articles do players cross through?
2. Do they choose these countries to get better success in-game?
3. Is their choice of countries motivated by external biases?

## Methods
After starting over from our P2 deliverable, we had to first look at success rates when related to the choice of countries:
- No concrete link was found!
So we were interested instead in looking at whether there were any in-game reasons involved:
- We measured centrality, as well as a direct number of neighbors, in order to measure whether the choice of articles was motivated by in-game reasons
   - While we found some links by regression, as players tended to use more central aricles more, as well as using articles with more neighbors more too.
   - We cannot discount the fact that this was caused *by* each article's centrality, and keeping in mind the unchanging success rate, it seems this was an accidental find, and rather a byproduct of each article's centrality
   - We found some interesting outliers, such as Lebanon, Georgia, Argentina and Armenia
- We started by looking for biases related to continental placement, which were quite straightforward. The choice of continents is detailed in the Notebook!
- We then went ahead with GDP, Population and Olympic Medal counts, regression, to see if those had an effect.
   - Promising initial graphs yielded a definite correlation with GDP, and a more muted relationship with Olympic medal counts.
      - We then checked whether or not the relation with Medals was due to GDP and Population (as confounders). It did not seem to be the case.
   - Checking back with Medals, we saw that there is *some* correlation, but we were unable to totally discount pure chance.
- Afterwards, we audited the share of articles visited by language, and found that articles about English speaking countries, were heavily overrepresented.

It seems human to expect a English-speaker-written game, played by English speakers, to favor English-speaking countries after all!

We can therefore answer our Research Questions as such:
1. Players tended to cross through country articles that were *more central*, but also stronger economically, European or North American and about English speaking countries.
2. The choice of the countries might have been either motivated by centrality, or *driven* by the article's centrality. Since players are not aware of an article's centrality when playing, the latter seems more likely than the former. The unchanging success rates for oft-chosen articles, as well as the disregarded overperformers also support this!
3. There certainly seems to be a cultural and economic consideration taken by the player, probably more unconscious than conscious. It is also visible that European countries and the USA, as well as English speaking nations, are overreprestend with regards to their actual share of the world's population!

## Timeline
1. **Week 3-5:** Brainstorming: Each member comes up with 3 different ideas to be assessed by the TAs
2. **Week 7-9:** Exploratory Data Analysis
   - Perform initial data exploration to understand the structure of the dataset.
   - Preprocess the data, handle missing values, and extract relevant features.
   - Identify patterns and trends within user behavior.
   - Visualize key insights and relationships within the dataset.
3. **Week 12-14:** Statistical and Final Analysis and Documentation
   - Apply statistical methods to further confirm relationships between variables.
   - Conduct hypothesis testing to validate findings.
   - Summarize key findings and insights.
   - Prepare the final documentation to be presented.

## Organization Within the Team
### Week 7-9: Data Exploration and Preprocessing
1. **Marc:** Data Preprocessing, Code Merging, Cleanups
2. **Antoine & Anthony:** Data Exploration
3. **Omar:** Efficency Computation, Visualization
4. **Fouad:** Article Semantic Scores Analysis, Code Quality Checks

### Week 12-14: Statistical Analysis, Hypothesis Testing - Project Redefinition
1. **Antoine:** Exploratory Data Analysis, Data Gathering.
2. **Anthony:** Exploratory Data Analysis, Data Viz, Hypothesis Testing.
3. **Marc:** Exploratory Data Analysis, Code Rewrites and Cleanup, Markdowns.
4. **Fouad:** Exploratory Data Analysis, Categorical Article Analysis, Code Quality Checks
5. **Omar:** Website, Graphic Design, Research

### Timeline during P3
- W12: Work on data.
- W13: Research and identification of alternate research question, work on website.
- W14: Final work.
