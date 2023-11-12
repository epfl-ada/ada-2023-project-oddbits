# P2: Project proposal and initial analyses
When you are done with Homework H1, you will continue to work on the next project milestone. In Milestone P2, together with your team members, you will agree on and refine your project proposal. Your first task is to select a project. Even though we provide the datasets for you to use, at this juncture, it is your responsibility to perform initial analyses and verify that what you propose is feasible given the data (including any additional data you might bring in yourself), which is crucial for the success of the project.

The goal of this milestone is to intimately acquaint yourself with the data, preprocess it, and complete all the necessary descriptive statistics tasks. We expect you to have a pipeline in place, fully documented in a notebook, and show us that you have clear project goals.

When describing the relevant aspects of the data, and any other datasets you may intend to use, you should in particular show (non-exhaustive list):

- That you can handle the data in its size.
- That you understand what’s in the data (formats, distributions, missing values, correlations, etc.).
- That you considered ways to enrich, filter, transform the data according to your needs.
- That you have a reasonable plan and ideas for methods you’re going to use, giving their essential mathematical details in the notebook.
- That your plan for analysis and communication is reasonable and sound, potentially discussing alternatives to your choices that you considered but dropped.

We will evaluate this milestone according to how well these steps have been done and documented, the quality of the code and its documentation, the feasibility and critical awareness of the project. We will also evaluate this milestone according to how clear, reasonable, and well thought-through the project idea is. Please use the second milestone to really check with us that everything is in order with your project (idea, feasibility, etc.) before you advance too much with the final Milestone P3! There will be project office hours dedicated to helping you.

You will work in a public GitHub repository dedicated to your project, which can be created by following this link. The repository will automatically be named ada-2023-project-<your_team_name>. By the Milestone P2 deadline, each team should have a single public GitHub repo under the epfl-ada GitHub organization, containing the project proposal and initial analysis code.

## P2 deliverable (done as a team): GitHub repository with the following:

- Readme.md file containing the detailed project proposal (up to 1000 words). Your README.md should contain:
  - Title
  - bstract: A 150 word description of the project idea and goals. What’s the motivation behind your project? What story would you like to tell, and why?
  - Research Questions: A list of research questions you would like to address during the project.
  - Proposed additional datasets (if any): List the additional dataset(s) you want to use (if any), and some ideas on how you expect to get, manage, process, and enrich it/them. Show us that you’ve read the docs and some examples, and that you have a clear idea on what to expect. Discuss data size and format if relevant. It is your responsibility to check that what you propose is feasible.
  - Methods
  - Proposed timeline
  - Organization within the team: A list of internal milestones up until project Milestone P3.
  - Questions for TAs (optional): Add here any questions you have for us related to the proposed project.
- Notebook containing initial analyses and data handling pipelines. We will grade the correctness, quality of code, and quality of textual descriptions.


### START OF THE FIRST README FILE 

# Analyzing User Progress in Wikispedia Gameplay

## Abstract

In order to identify the changes in users' actual skills and efficiency with time and with increased experience, this study analyses the behaviour of players inside the Wikispedia dataset. Important components in the collection include user-hashed IDs, chosen paths, timestamps, game length, and user ratings. The main motivation for this research is to identify trends in user behaviour that can provide light on the elements that either support or obstruct advancement in the gaming environment. We seek to verify the widely held belief in the gaming world that playing a game repeatedly improves one's skills, we want to check if this also stands in the context of the Wikispedia game. By carefully analysing the above elements, we hope to improve our knowledge of the complex dynamics influencing user abilities and participation, which will lead to our understanding of how users interact with the Wikispedia.

## Research Questions

1. Does the user's true level and efficiency increase with the number of games played or repeated?
2. Is there a correlation between time passed and user improvement in gameplay? (for users who play games with a wide spread in the timestamp of each game)
3. How does the experience gained in each game contribute to overall user progress?
4. What factors influence user ratings, and can they be predicted based on gameplay data? -> not sure we want to look into this
5. Does the reason for failure (timeout or reset) provide insights into topics where users struggle the most?


## Methods

To gain a thorough grasp of user behaviour and evolution in the Wikispedia dataset we will be using CCDfs so we can monitor the change in efficiency as the number of games played increases, giving us a dynamic representation of user growth. We will evaluate the importance of our results using statistical analysis, guaranteeing the validity of our judgements. Comparative analysis will be used to compare different data clusters, like players that play different numbers of games (less than 20, 20–150, and more than 200 games). A personalised efficiency measure will be developed that accounts for characteristics such as game time, path length, and user experience, and may even go so far as to consider the semantic intricacy of selected paths. The clear display of trends, correlations, and causation between variables will be made easier with the use of visualisation techniques with libraries such as Matplotlib and Seaborn. Finally, hypothesis testing will thoroughly examine the importance of the learned information, to confirm the validity of our conclusions.

## Proposed Timeline

1. **Week 3-5:** Brain storming
- Each member comes up with 3 different ideas to be assessed by the TAs 

2. **Week 7-9:** Exploratory Data Analysis
   - Perform initial data exploration to understand the structure of the dataset.
   - Preprocess the data, handle missing values, and extract relevant features.
   - Conduct EDA to identify patterns, trends, and outliers in user behavior.
   - Visualize key insights and relationships within the dataset.
- The creation of the Readme file

3. **Week 12-14:** Statistical and Final Analysis and Documentation
   - Apply statistical methods to further confirm relationships between variables.
   - Conduct hypothesis testing to validate findings.
   - Summarize key findings and insights.
   - Prepare the final documentation to be presented.

## Organization Within the Team

**Week 7-9: Data Exploration and Preprocessing**
1. **Marc Nassif:** Data Preprocessing
2. **Antoine Hinary & Anthony Dawoud:** Data Exploration
3. **Omar Shalby:** Efficency score computation
4. **Fouad Mahmoud:** Visualization support

**Week 12-14: Statistical Analysis and Hypothesis Testing**
1. **Antoine Hinary & Anthony Dawoud & Marc Nassif:** Further Statistical Analysis
2. **Fouad Mahmoud:** Hypothesis Testing
3. **Omar Shalby:** Responsible for the final Analysis and deliverable

## Questions for TAs

