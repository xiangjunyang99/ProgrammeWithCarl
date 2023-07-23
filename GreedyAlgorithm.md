** To Do List **
- LeetCode 455 - Assign Cookies
- LeetCode 376 - Wiggle Subsequence


## LeetCode 455 - Assign Cookies
          class Solution:
              def findContentChildren(self, g: List[int], s: List[int]) -> int:
                  g.sort()
                  s.sort()
          
                  index = len(s) - 1
                  result = 0
          
                  for i in range(len(g)-1, -1, -1):
                      if index >= 0 and s[index]>=g[i]:
                          result += 1
                          index -= 1
          
                  return result

- Greedy Algorithm, there is no solid solution, for this question the main point is to attribute the most greedy child with the largest biscuit.
- Firstly, we have to sort the two groups. The default sorting order is increasing.
- Then, define the largest index of the biscuit group, and the final result number which initializing as 0.
- Use for loop to loop over the children group, to satisfy the most greedy child with the largest biscuit. If there is no such large biscuit to satisfy the child , then for loop to the another child with smaller content.
- Attention! As the order is increasing after the sort, so the range is to iterate the sequence in inverse order.
- Ex.
    list_1 = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
    for i in range(len(list_1)-1, -1, -1):
        print(i)
- the output from the above codes is: 9 to 0
range(start, stop, step)
start: The first value in the sequence.
stop: The loop will stop before reaching this value.
step: The difference between each pair of consecutive values in the sequence.

like in the example above, the list_1 has length 10, so len(list_1)-1 equals 9, the range is [9, -1) and in reverse order
so the result is 9, 8, 7, 6, 5, 4, 3, 2, 1, 0 exactly 9 to 0

- In our case, i is the child index, so the range is from the last index to 0.
- If there is no such a big cookie to make the child content, it will go to the next for loop for the next child.
- index >= 0, this code makes sure the index is valid
- If the cookie s could make child content then add one to the final result integer, and also move the index to the next cookie.


## LeetCode 376 - Wiggle Subsequence

            class Solution:
                def wiggleMaxLength(self, nums: List[int]) -> int:
                    if len(nums) <= 1:
                        return len(nums)
            
                    curdiff = 0
                    prediff = 0
                    result = 1
            
                    for i in range(len(nums) - 1):
                        curdiff = nums[i+1]-nums[i]
                        if (prediff<=0 and curdiff>0) or (prediff>=0 and curdiff<0):
                            result += 1
                            prediff = curdiff
                    
                    return result

- if there is less than two elements in the list then return the list length
- define the current difference and previous difference for later comparison; and the final result integer
- use a for loop to iterate the list, calculate the differences
- if the two differences have opposite direction then there is one redirecting point; add one to the final result
- inside the if statement, update the prediff to the curdiff only if the if statement is met, this exclude the monotone increasing with plain situation


