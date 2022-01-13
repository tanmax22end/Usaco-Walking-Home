# Usaco_Walking_Home
## Explanation and source code of the problem
### This problem was asked in USACO 2021 December Contest, Bronze

1. Lets first define the state of bessie in a cell (i,j) where(0<=i<n, 0<=j<n) and it doesn't contain any haybales.

2. There are only two possilble state of bessie either he/she maybe facing right or down.

3. Lets say we denote right as 0 and down as 1 in our dp state.

### Transition 
1. The only way we can come cell i,j where(i>0 && j>0) is from (i-1,j) or (i,j-1).

2. Hence we consider these two possiblities in our transition.

3. Now dp[i][j][1][k] signifies the number of possible ways to reach (i,j) with bessie facing downwards using k turn 
similarly dp[i][j][0][k] for bessie facing towards right.

4. Now bessie can only face downwads if it comes from cell (i-1,j). Similarly to face towards right it has to come from (i,j-1).
dp[i][j][1][k] = dp[i-1][j][0][k-1] -> if it has to take a turn from (i-1,j).
dp[i][j][1][k] = dp[i-1][j][1][k] -> for no change of direction.

Similarly we can do for dp[i][j][0][k].

### Time Complexity comes out to be O(n^2.k)

I hope it helps.
