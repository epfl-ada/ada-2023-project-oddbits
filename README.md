# Analyzing User Progress in Wikispedia Gameplay
## Abstract
In our upcoming analysis, we seek to determine whether engaging in computer gaming enhances the overall learning experience for players. Leveraging the Wikispeedia dataset provides a solid foundation for our study. With key information such as a unique player identifier, game duration, and a comprehensive list of played games, we can extract correlations between these gaming activities and the players' knowledge levels. However, determining the players' level poses a challenge due to factors such as the varying difficulty of different games and their impact on learning. Additionally, we question the assumption that repeating the same game leads to genuine improvement, considering the possibility of mere memorization. We'll also investigate if improvement persists when revisiting the same game and how skill development unfolds with longer gaming experiences. These inquiries will guide our exploration into the unclear relationship between gaming and knowledge enhancement.

## Research Questions
1. Is there a corrolation between the time intervals between games and the improvment?
2. What factors influence user ratings, and can they be predicted based on gameplay data?
3. Does the reason for failure (timeout or reset) provide insights into topics where users struggle the most?
4. How can we determine the difficulty of a given level? Do we use the minimal length, the semantics, etc…?
5. How can we estimate the improvement of a players’ level after a given game but most importantly before the game? How can we know what He/She is good at?
6. How can we detect if someone’s level is actually improving? How can we detect the effect of memorization?
7. What is the possibility that different players used the same computer and thus have the same “unique” identifier? What can we do to solve this problem?

## Methods
As discussed in the [Abstract](#Abstract) section we aim to attack our problem from multiple angles as some of which would show blocked roads. To name a few examples with the respective steps:
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
	    - Use the same data from before and compute the Game length.
	Plot the variation of game length in respect to experience.
	- Findings:
	    - All the 4 games have the same optimal length (minimum number of clicks). This raises the question of what else do they have in common? Can we be able to predict the popularity of a game on Wikispeedia using the data we have?
	    - People are usually away from the optimal length.
	- Conclusions:
	    - Unfortunately, yet again visually we cannot see a correlation between the 2.

**_Note:_** we were working on a skwed data therefor where unable to draw any important conclusions about the players. However, we have come up with good performance metrics e.g. mean time per page. These can be used to creat a performance score that is more representative which in combination with the difficulty of the level that we can estimate using other metrics (e.g. frequency of failure) we may find the corrolations and relationships that we are looking for.

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
1. **Marc:** Data Preprocessing, Code Merging, Cleanups
2. **Antoine & Anthony:** Data Exploration
3. **Omar:** Efficency Computation, Visualization
4. **Fouad:** Semantic Text Analysis
### Week 12-14: Statistical Analysis and Hypothesis Testing
1. **Antoine & Anthony & Marc:** Further Statistical Analysis
2. **Fouad:** Hypothesis Testing, Further Semantic Analysis
3. **Omar:** Visualizations, work on website.

#### Timeline for P3

- W12: Work on data, finishing up semantic analysis, website setup.
- W13: Finalization of statistical work, work on website.
- W14: Finishing touches.
