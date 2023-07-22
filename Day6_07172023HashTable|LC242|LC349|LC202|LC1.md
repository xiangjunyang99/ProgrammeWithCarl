**To Do List** 
Hashtable, 242, 349. 202, 1.

## [HashTable](https://www.programmercarl.com/%E5%93%88%E5%B8%8C%E8%A1%A8%E7%90%86%E8%AE%BA%E5%9F%BA%E7%A1%80.html#%E5%93%88%E5%B8%8C%E5%87%BD%E6%95%B0)
- Array is Hashtable. We use hashtable to judge if an element is in an array or not.
- Hash Function. We use hash function to reflect a list of element onto a hash table.
- Hash collision. To solve this we use LinkedList or Linear probe.
- Hashtable structure: array, set, map.
- In summary, hashtable sacrifices space for lower time complexity.

## [LeetCode 242 - Valid Anagram](https://leetcode.com/problems/valid-anagram/)
[LC242Article](https://www.programmercarl.com/0242.%E6%9C%89%E6%95%88%E7%9A%84%E5%AD%97%E6%AF%8D%E5%BC%82%E4%BD%8D%E8%AF%8D.html#_242-%E6%9C%89%E6%95%88%E7%9A%84%E5%AD%97%E6%AF%8D%E5%BC%82%E4%BD%8D%E8%AF%8D)

class Solution:
    def isAnagram(self, s: str, t: str) -> bool:
        record = [0]*26
        for i in s:
            record[ord(i)-ord("a")] += 1

        for i in t:
            record[ord(i)-ord("a")] -= 1

        for i in range(26):
            if record[i] != 0:
                return False
        return True

Given two strings, we are asked to return whether the two strings are anagram.
First, we initiate an array of size 26 with all values equal to 0, it is used to traverse all elements in those strings.
Then, we use for loop to traverse the first string, and document the element appears in it.
The trick here is we use ord to return the Unicode of letters in the string. 
By substracting the first letter in the English alphabet, we have the relative index from 0 to 25 which indicates the corresponding letter.
Here we complete the first round traversal and add each appearance of the letter by 1.

Then, we traverse the second string ans substract the corresponding letter by 1.

Last, we judge if the hashtable array contains no numbers, which means the two strings are anagram, otherwise they are not.


## [LeetCode 349 - Intersection of Two Arrays](https://leetcode.com/problems/intersection-of-two-arrays/)
[LeetCode349](https://www.programmercarl.com/0349.%E4%B8%A4%E4%B8%AA%E6%95%B0%E7%BB%84%E7%9A%84%E4%BA%A4%E9%9B%86.html#_349-%E4%B8%A4%E4%B8%AA%E6%95%B0%E7%BB%84%E7%9A%84%E4%BA%A4%E9%9B%86)
Given two integer arrays nums1 and nums2, return an array of their intersection. 
Each element in the result must be unique and you may return the result in any order.

        table = [0] * 1005
        res = []
        for i in nums1:
            table[i] += 1

        for i in nums2:
            if table[i] != 0:
                res.append(i)
                table[i] = 0
        
        return res

We are given two arrays this time. First we initiate an array of size 1005 for traversal purpose and a res array to contain the result.
Then we traverse the first array and document the element to the corresponding position at table.

Then for the second time traversal, to judge if the position contains any element or not. If contains then append the element into res.
And after the appending delete the element by setting it's value to zero to avoid repeating.

Lastly, return res list, that's the intersection.


## [LeetCode 202 - Happy Number](https://leetcode.com/problems/happy-number/)
[LC202Article](https://programmercarl.com/0202.%E5%BF%AB%E4%B9%90%E6%95%B0.html)

class Solution:
    def isHappy(self, n: int) -> bool:
        record = []
        while n not in record:
            record.append(n)
            new_num = 0
            n_str = str(n)
            for i in n_str:
                new_num += int(i)**2
            if new_num == 1:
                return True
            else:
                n = new_num      
        return False


The main point of the question is similar to LC 349 but with a Happy Number shell.
If the new sum appears in the record which means the number can never be added up to 1 then return false, otherwise repeat the squares addition.

Here is the trick, we make the integer as string and partition each element to do the squares addition.
Then to judge if the new sum equals to 1, if it equals to 1 then return True, otherwise update the new  sum to repeat the process.
Once the new sum appears in the historical record return False; or there is 1 return True it's Happy Number.


## [LeetCode 1 - Two Sum](https://leetcode.com/problems/two-sum/)
[LC1Article](https://www.programmercarl.com/0001.%E4%B8%A4%E6%95%B0%E4%B9%8B%E5%92%8C.html#_1-%E4%B8%A4%E6%95%B0%E4%B9%8B%E5%92%8C)















