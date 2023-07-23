**To Do 💙List ** 👺Someone has ever experienced same interview questions in the questions below.
● 20. 有效的括号
● 1047. 删除字符串中的所有相邻重复项
● 150. 逆波兰表达式求值

## LeetCode 20 - Valid Parentheses

      class Solution:
          def isValid(self, s: str) -> bool:
              stack = []
      
              for item in s:
                  if item == '(':
                      stack.append(')')
                  elif item == '[':
                      stack.append(']')
                  elif item == '{':
                      stack.append('}')
                  elif not stack or stack[-1] != item:
                      return False
                  else:
                      stack.pop()
              
              return True if not stack else False

- We use a stack structure to complete this question.
- Use for loop to iterate the string and put the corresponding right parenthesis into the stack structure.
- If there appears another right parenthesis then cancel with the left one, we pop the right out of the stack structure.
- After all the iterations we have make sure there is no element left then there is no redundant elements.


## LeetCode 1047 - Remove All Adjacent Duplicates In String










## LeetCode 150 - Evaluate Reverse Polish Notation






