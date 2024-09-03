## **Overview**

Data Handling: The code processes historical CFB game data and returning production statistics from CSV files.
Graph Construction: It builds a graph where nodes represent teams, and edges represent the results of games between teams.
Ranking with PageRank: It applies the PageRank algorithm to determine the importance or ranking of teams based on their performance.
Prediction: It predicts the outcomes of future games based on current rankings.
Evaluation: It evaluates the accuracy of predictions and generates rankings for teams.


## **Data Initialization and Reading:**

returning_prod is a dictionary to store the percentage of returning production for each team, read from ret.csv.
teams is a list to store unique team names extracted from game data.
Build the Graph:

build_graph(week, year): Constructs an adjacency matrix g representing the graph. Each entry in the matrix captures the result of games between teams up to the specified week of the given year. The matrix is populated with log-transformed differences in team performance metrics (e.g., scores).
PageRank Centrality:

pr(A, alpha=0.85, num_teams=130, num_terms=10): Implements the PageRank algorithm to compute the importance of each team. The algorithm iteratively updates the importance score based on the graph's adjacency matrix A. The alpha parameter controls the damping factor, while num_terms controls the number of iterations.
Ranking Teams:

largest_elements(lst, k=25): Returns the indices of the top k elements in a list, used to rank teams based on their PageRank scores.

## **Predict Game Outcomes:**

predict_games(week, num_teams, year, x, filter_teams=False): Predicts game outcomes for a given week of a specified year based on team rankings x. It compares predicted results with actual game outcomes to compute prediction accuracy.
predict_games_top(week, num_teams, year, x, indices): Similar to predict_games, but focuses only on games involving the top indices teams.
Prediction Loops:

prediction_loop(years, num_terms, start_week=3): Iterates over all games in the given years and weeks, computes team rankings using PageRank, and evaluates prediction accuracy across all games.
prediction_loop_top25(years, num_terms, start_week=3, k=25, end_week=15): Focuses on predicting outcomes for the top 25 teams. It computes PageRank rankings and evaluates prediction accuracy specifically for these top teams.
Ranking Teams for a Given Year:

rankings(year): Builds the graph for the final week of the given year, computes team rankings using PageRank, and prints the top 60 teams.

### **Using Rankings to Predict Ranked Games:**

2019 Accuracy: 81%

2021 Accuracy: 79%

2022 Accuracy: 71%

[What is this](2019)

## **Rankings:**

### **2022 Rankings**
1:  Georgia (1)

2:  Michigan (2)

3:  Ohio State (4)

4:  TCU (3)

5:  USC (10)

6:  Alabama (5)

7:  Tennessee (6)

8:  Penn State (11)

9:  Texas (20)

10:  Tulane (16)

11:  Clemson (7)

12:  Coastal Carolina (UR)

13:  Illinois ((UR)

14:  Troy (24)

15:  Notre Dame (21)

16:  South Alabama (UR)

17:  UCF (UR)

18:  Boise State (UR)

19:  LSU (17)

20:  Florida State (13)

21:  Washington (12)

22:  Louisville (UR)

23:  Kansas State (9)

24:  North Carolina (UR)

25:  UT San Antonio (25)

### **2021 Rankings**
1:  Michigan

2:  Georgia

3:  Cincinnati

4:  Alabama

5:  Baylor

6:  Ohio State

7:  Pittsburgh

8:  Notre Dame

9:  UT San Antonio

10:  Louisiana

11:  NC State

12:  Oregon

13:  Appalachian State

14:  Utah

15:  Ole Miss

16:  Michigan State

17:  Oklahoma State

18:  Wake Forest

19:  Houston

20:  Boise State

21:  Army

22:  BYU

23:  Kentucky

24:  Wisconsin

25:  Minnesota


### **2019 Rankings**
1:  Ohio State

2:  LSU

3:  Clemson

4:  Wisconsin

5:  Memphis

6:  Oregon

7:  Appalachian State

8:  Boise State

9:  Georgia

10:  Utah

11:  Oklahoma

12:  Alabama

13:  UCF

14:  Louisiana

15:  Penn State

16:  Baylor

17:  Notre Dame

18:  SMU

19:  Florida

20:  Air Force

21:  Auburn

22:  Navy

23:  Michigan

24:  San Diego State

25:  Minnesota

## **Key Points**

While there are obvious shortcomings in the algorithm, the rankings are quite similar to that of the AP Poll and for certain teams, you might argue that the rankings are more accurate. Traditionally, the AP Poll can predict the outcome of games with ranked teams 70% of the time. We find that for ranked games, my graph based rankings predict the outcome of the games with 78% accuracy.

Graph Representation: Teams are nodes, and game outcomes are edges with weights based on performance differences.

PageRank: A centrality measure used to rank teams based on their performance in the graph.

Prediction Accuracy: The code evaluates how well the predicted outcomes match actual results.

Focus on Top Teams: Specific functions cater to predicting outcomes involving only the top-ranked teams.

## **Visualization**
Although the code imports matplotlib.pyplot, it doesn't use it for visualization. To add visualization, you could plot the PageRank scores or the adjacency matrix.
This approach leverages graph theory and PageRank to provide insights into team rankings and predict future game outcomes, blending statistical analysis with graph-based algorithms.




