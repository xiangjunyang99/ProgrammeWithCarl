** To Do List **
- LeetCode 509 - Fibonacci Number
- LeetCode 70 - Climbing Stairs
- LeetCode 746 -
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







## LeetCode 







## LeetCode 









