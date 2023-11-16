# Analyzing User Progress in Wikispedia Gameplay

## Abstract

In order to identify the changes in users' actual skills and efficiency with time and with increased experience, this study analyses the behaviour of players inside the Wikispedia dataset. Important components in the collection include user-hashed IDs, chosen paths, timestamps, game length, and user ratings. The main motivation for this research is to identify trends in user behaviour that can shed some light on the elements that either support or obstruct advancement in the gaming environment. We seek to verify the widely held belief in the gaming world that playing a game repeatedly improves one's skills, we want to check if this also stands in the context of the Wikispedia game. By carefully analysing the above elements, we hope to improve our knowledge of the complex dynamics influencing user abilities and participation, which will lead to our understanding of how users interact with the Wikispedia.


### Modified Abstract

In our upcoming analysis, we seek to determine whether engaging in computer gaming enhances the overall learning experience for players. Leveraging the Wikispeedia dataset provides a solid foundation for our study. With key information such as a unique player identifier, game duration, and a comprehensive list of played games, we can extract correlations between these gaming activities and the players' knowledge levels. However, determining the players' level poses a challenge due to factors such as the varying difficulty of different games and their impact on learning. Additionally, we question the assumption that repeating the same game leads to genuine improvement, considering the possibility of mere memorization. We'll also investigate if improvement persists when revisiting the same game and how skill development unfolds with longer gaming experiences. These inquiries will guide our exploration into the unclear relationship between gaming and knowledge enhancement.

## Research Questions

1. Does the user's true level and efficiency increase with the number of games played or repeated?
2. Is there a correlation between time passed and user improvement in gameplay? (for users who play games with a wide spread in the timestamp of each game)
3. How does the experience gained in each game contribute to overall user progress?
4. What factors influence user ratings, and can they be predicted based on gameplay data? -> not sure we want to look into this  ** CORRECT THIS BEFORE SUBMISSION **
5. Does the reason for failure (timeout or reset) provide insights into topics where users struggle the most?

### Extra Questions

6. How can we determine the difficulty of a given level? Do we use the minimal length, the semantics, etc…?
7. How can we estimate the improvement of a players’ level after a given game but most importantly before the game? How can we know what He/She is good at?
8. How can we detect if someone’s level is actually improving? How can we detect the effect of memorization?
9. What is the possibility that different players used the same computer and thus have the same “unique” identifier? What can we do to solve this problem?

## Proposed additional datasets :
**_Note:_** We do not need any addition dataset, we use this part to describe the datasets included with wikispeedia. Use this link to go to the next section [-> Methods](#Methods).
- articles

| Article |
|:-------:|

- categories

| Article | category |
|:-------:|:--------:|

- links

| linkSource | linkTarget |
|:----------:|:----------:|

- paths_finished

| hashedIpAddress | timestamp | durationInSec | path | rating |
|:---------------:|:---------:|:-------------:|:----:|:------:|

- paths_unfinished

| hashedIpAddress | timestamp | durationInSec | path | target | type |
|:---------------:|:---------:|:-------------:|:----:|:------:|:----:|

- shortest-path-distance-matrix

Here, no table is required. Each row represents an article in the same order as articles from above and they the row contains the optimal distance to all articles if it exists.


## Methods

To gain a thorough grasp of user behaviour and evolution in the Wikispedia dataset we will be using CCDfs so we can monitor the change in efficiency as the number of games played increases, giving us a dynamic representation of user growth. We will evaluate the importance of our results using statistical analysis, guaranteeing the validity of our judgements. Comparative analysis will be used to compare different data clusters, like players that play different numbers of games (less than 20, 20–150, and more than 200 games). A personalised efficiency measure will be developed that accounts for characteristics such as game time, path length, and user experience, and may even go so far as to consider the semantic intricacy of selected paths. The clear display of trends, correlations, and causation between variables will be made easier with the use of visualisation techniques with libraries such as Matplotlib and Seaborn. Finally, hypothesis testing will thoroughly examine the importance of the learned information, to confirm the validity of our conclusions.

## Modified Methods

As discussed in the Abstract section we aim to attack our problem from multiple angles as some of which would show blocked roads. To name a few examples with the respective steps:
- We can study the improvement in speed when a player plays the same game repeatedly.
  - Steps:
       - Find and filter the dataset to extract the most played games. The idea behind this is that it’s more probable to find a user that played the same game twice if the game was played 1000 times than if it was played 1-5 times.
       - Extract the users that played more than x times the same game. Where x is a choice that we set at 5 and compare them with the users that played y<x times. Where y was a choice, we set at 2.
       - Detect improvement in time.
	- Findings:
	    - We find out that 4 games have been played more than 1000 times.
	    - The Dataset was too constraint thus became too small (~ only a few people) to be considered representative. 
	    - The players that did play more than x times did so in a very short time implying that they might have been memorizing the path and that maybe a group of people were competing on the same computer.
	- Conclusions:
	    - This idea does not lead to robust conclusions. This part has thus been removed from the notebook.
- We can expand our search by studying if the speed improves when the player has previously played a lot in general.
	- Steps:
	    - Use the datasets of the 4 games from above to filter and find the people that only played the game once. This way we can exclude the possibility of memorization and friend competitions.
	    - From the original dataset, compute how many times the player played Wikispeedia before playing the game.
	    - Study the improvement in time.
	- Findings:
	    - Indeed, the dataset is way larger than the previous attempt. Moreover, the data describes our players better as mentioned above.
	    - The number of players with less experience, in other words played less games before is way larger than the ones with higher experience (5-10+ games). In other words, we have skewed data.
	- Conclusions:
	    - We have used a scatter plot to visualize the data of the 4 games. However, visually we cannot tell that there is a direct improvement in the time of the game.
- We now consider that maybe time is not a valid measurement of the player's knowledge. So, we try and see how close they get to the optimal path with experience.
	- Steps:
	    - The logic here is very close to the previous method, we filter the data and extract the players that played the 4 games of concern.
	    - Again, we then get their experience from the original data set.
	    - Now, we compute the Game length.
	Plot the variation of game length in respect to experience.
	- Findings:
	    - All the 4 games have the same optimal length (minimum number of clicks). This raises the question of what else do they have in common? Can we be able to predict the popularity of a game on Wikispeedia using the data we have?
	    - People are usually away from the optimal length.
	- Conclusions:
	    - Unfortunately, yet again visually we cannot see a correlation between the 2.



## Proposed Timeline

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

1. **Marc Nassif:** Data Preprocessing, Code Merging, Cleanups
2. **Antoine Hinary & Anthony Dawoud:** Data Exploration
3. **Omar Shalby:** Efficency Computation, Visualization
4. **Fouad Mahmoud:** Semantic Text Analysis

### Week 12-14: Statistical Analysis and Hypothesis Testing

1. **Antoine Hinary & Anthony Dawoud & Marc Nassif:** Further Statistical Analysis
2. **Fouad Mahmoud:** Hypothesis Testing, Further Semantic Analysis
3. **Omar Shalby:** Visualizations, work on website.

#### Timeline for P3

- W12: Work on data, finishing up semantic analysis, website setup.
- W13: Finalization of statistical work, work on website.
- W14: Finishing touches.

## Questions for TAs

