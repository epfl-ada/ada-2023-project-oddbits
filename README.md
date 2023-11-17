# Analyzing User Progress in Wikispedia Gameplay
## Abstract
In our upcoming analysis, we seek to determine whether playing the game Wikispeedia teaches the players skills, be it path traversal using optimal paths, or using category matching, or even semantics. Using the provided dataset including game durations, paths taken, and a comprehensive list of played games, we can extract correlations between these gaming activities and the players' knowledge levels. However, determining the players' level poses a challenge due to factors such as the varying difficulty of different games and their impact on learning. Additionally, we question the assumption that repeating the same game leads to genuine improvement, considering the possibility of mere memorization. We'll also investigate if improvement persists when revisiting the same game and how skill development unfolds with longer gaming experiences. These inquiries will guide our exploration into the unclear relationship between gaming and knowledge enhancement.

## Research Questions
1. Is there a correlation between the time intervals between games and the improvment?
2. Where do players struggle the most? Why?
3. How can we determine the difficulty of a given level? Do we use the optimal length, the category differences, etc...
4. How can we estimate the improvement of a players’ level after a given game? How can we know what they are good at?
5. How can we detect if someone’s level is actually improving? How can we detect the effect of memorization?

## Methods
As discussed in the [Abstract](#Abstract) section we aim to attack our problem from multiple angles as we are bound to run into dead-ends. To name a few examples with the respective steps:
- We can study the improvement in speed when a player plays the same game repeatedly.
  - Steps:
       - Find the most played games as it’s more probable to find a user that played the same game twice if the game was played 1000+ times.
       - Extract the users that played the same game a few times. Compare them to the ones that only played once or twice.
       - Check for improvement in speed.
	- Findings:
	    - 4 games have been played 1000+ times.
	    - The Dataset was too constrained thus became too small (~ only a few people) to be considered representative. 
	    - The players that did play a few times did so in a very short time implying that they might have been memorizing the path and that maybe a group of people were competing on the same computer.
	- Conclusions:
	    - This idea does not lead to robust conclusions. This part has thus been removed from the notebook.
- We can expand our search by studying if the speed improves when the player has previously played a lot in general.
	- Steps:
	    - Find the people that only played the game once to exclude the possibility of memorization.
	    - Compute their experience from the original data (previous games played).
	    - Check for improvement.
	- Findings:
	    - The number of players with less experience is way larger than the ones with higher experience (5-10+ games). In other words, we have skewed data.
	- Conclusions:
	    - We have used a scatter plot to visualize the data of the 4 games. However, visually we cannot tell that there is a direct improvement in the time of the game.
- We now consider that maybe time is not a valid measurement of the player's knowledge. So, we try and see how close they get to the optimal path with experience.
	- Steps:
	    - Compute the Game length of the players.
	    - Plot the variation of game length in respect to experience.
	- Findings:
	    - All the 4 games have the same optimal length. This raises questions like what else do they have in common? Can we predict the popularity of a game on Wikispeedia using the data we have?
	    - People are usually away from the optimal length.
	- Conclusions:
	    - Unfortunately, yet again visually we cannot see a correlation between the two.

**_Note:_** we were working on skewed data therefore were unable to draw any conclusive results about the players. However, we have come up with good performance metrics e.g. mean time per page. These can be used to create a performance score that is more representative (taking into account the individual factors that at first glance might leed to beleiving that there is no improvement at all), which, in combination with the difficulty of the level that we are able to estimate, may lead us to the correlations and relationships we are looking for.

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
- Before W12: Fixing up, applying our current work in a more conclusive way.
- W12: Work on data, finishing up analysis, website setup.
- W13: Finalization of statistical work, work on website.
- W14: Finishing touches.
