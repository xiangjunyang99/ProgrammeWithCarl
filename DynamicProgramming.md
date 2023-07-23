** To Do List **
- LeetCode 509 - Fibonacci Number
- LeetCode 70 - Climbing Stairs
- LeetCode 746 - Min Cost Climbing Stairs
- LeetCode 62 -
- LeetCode 63 -
- LeetCode 343 - 

## LeetCode 509 - Fibonacci Number

                class Solution:
                    def fib(self, n: int) -> int:
                        if n == 0:
                            return 0 #corner case
                
                        dp = [0]*(n+1)
                
                        dp[0] = 0
                        dp[1] = 1
                
                        for i in range(2, n+1):
                            dp[i] = dp[i-1] + dp[i-2]
                
                        return dp[n]

Apply the 5 steps for dp problem.

## LeetCode 70 - Climbing Stairs

              class Solution:
                  def climbStairs(self, n: int) -> int:
                      if n <= 1:
                          return n
                      
                      dp = [0] * (n+1)
              
                      dp[1] = 1
                      dp[2] = 2
              
                      for i in range(3, n+1):
                          dp[i] = dp[i-1] + dp[i-2]
              
                      return dp[n]



## LeetCode 746 - Min Cost Climbing Stairs

                class Solution:
                    def minCostClimbingStairs(self, cost: List[int]) -> int:
                        dp = [0] *(len(cost)+1)
                
                        dp[0] = 0
                        dp[1] = 0
                
                        for i in range(2, len(cost) + 1):
                            dp[i] = min(dp[i-1]+cost[i-1], dp[i-2]+cost[i-2])
                
                        return dp[len(cost)]



## LeetCode 62 - Unique Paths

              class Solution:
                  def uniquePaths(self, m: int, n: int) -> int:
                      dp = [[0]*n for _ in range(m)]
              
                      for i in range(m):
                          dp[i][0] = 1
              
                      for j in range(n):
                          dp[0][j] = 1
              
                      for i in range(1, m):
                          for j in range(1, n):
                              dp[i][j] = dp[i-1][j] + dp[i][j-1]
              
                      
                      return dp[m-1][n-1]


## LeetCode 63 - Unique Paths II









