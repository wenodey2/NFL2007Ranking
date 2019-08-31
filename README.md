# NFL2007Ranking
Ranking of pro football teams based on the 2007 NFL regular season

The National Football League (NFL) is a professional American football league consisting of 32 teams, divided equally between the National Football Conference (NFC) and the American Football Conference (AFC). Both conferences consist of four four-team divisions. Each team plays 16 regular-season games; thus, teams do not play all other teams during a single regular season. The focus of this project is the 2007 NFL regular season. The scores for the 2007 season are obtained from https://www.pro-football-reference.com/years/2007/games.htm#games::none where is copied and saved as a CSV file.

The goal of this assignment is to rank the 32 teams after the regular season using an algorithm based on Markov chains. Each team is represented by a state in a Markov chain, and team ranks are based on values that are proportional to the stationary probabilities of the constructed Markov chain. The task is to convert the available game scores into a transition matrix, and provide a justification for such a conversion. Two different versions of the matrix will be proposed.

For the constructed matrices, the corresponding stationary distributions should be computed, and team ranks should be produced.

##INTRODUCTION
R is used for this study. Weekly data scores data was obtained in the form of a CSV file and the columns Winner, Loser, Points Scored by Winner and Points Scored by loser were imported into R.

##METHOD 1
Since the game scores serve as proxies for the relative strengths of the teams, the difference between the points scored by the winner of a game and points scored by the loser of a game can be taken as a measure of how much stronger the winner is. In this method, a 32 x 32 matrix is created, and each row and column represent one. Each row contains the score difference for each game the team wins against other teams. Losses are assigned a zero. 

To formulate the transition matrix, the sum of each element is divided by the sum of the elements in each row. By this formulation, the matrix is a stochastic matrix.

The stationary distribution of the transition matrix is computed, and the team ranks is given below. The New England Patriots are the strongest team, while the St. Louis Rams are the weakest team.

##METHOD 2
Since the game scores serve as proxies for the relative strengths of the teams, the quotient of the points scored by the winner of a game and points scored by the loser of a game can be taken as a measure of how much stronger the winner is. In this method, a 32 x 32 matrix is created, and each row and column represent one. Each row contains the score quotient of the points scored by the winner of a game and points scored by the loser of a game for each game the team wins against other teams. Losses are assigned a zero. For games where the losing team did not score, as score of 1 is assigned to the loser and 1 is also added to the winning score, before the quotient is obtained.

To formulate the transition matrix, the sum of each element is divided by the sum of the elements in each row. By this formulation, the matrix is a stochastic matrix.

The stationary distribution of the transition matrix is computed, and the team ranks is given below. The New England Patriots are the strongest team, while the San Francisco 49ers are the weakest team.

The table below shows the rankings based on the two methods.

![Rankings Table](https://github.com/wenodey2/NFL2007Ranking/blob/master/RankingTable.PNG)
![Image of Yaktocat](https://octodex.github.com/images/yaktocat.png)


