# Top Interview Questions

> this version is for 2019-12-13

**本文档记录的是题解或论坛讨论中比较好的答案**，我自己的写的屑代码在easy/medium/hard文件夹中


## 1	Two Sum    		 	 	

## 2	Add Two Numbers    		 	 	

## 3	Longest Substring Without Repeating Characters

大意：给定字符串，求没有相同字符的最长子字符串的长度。

求解方式：

1.暴力求解($n^3$)

2.利用Set特性，利用一个sliding window遍历进行查询。最多需要2n步

3.(2的优化版本，最多只需要n步)利用hashmap对其进行求解，对于每一个字符，都判断是否在目前的字符串中出现过。若出现过，则用现在位置减去上一次的位置，得到要保留当前字母的目前得到的最大的字符串的长度。另外，**如果能够确定字符串的范围，比如确认是在ASCII128中的字符，那么我们可以用int[128]数组来直接代替hashmap**，以下为代码示例
```JAVA
public class Solution {
    public int lengthOfLongestSubstring(String s) {
        int n = s.length(), ans = 0;
        Map<Character, Integer> map = new HashMap<>(); // current index of character
        // try to extend the range [i, j]
        for (int j = 0, i = 0; j < n; j++) {
            if (map.containsKey(s.charAt(j))) {
                i = Math.max(map.get(s.charAt(j)), i);
            }
            ans = Math.max(ans, j - i + 1);
            map.put(s.charAt(j), j + 1);
        }
        return ans;
    }
}
```

## 4	Median of Two Sorted Arrays    		 	 	

题目大意：给定两个vector数组，找到两个数组中的所有数的中位数，要求时间在$log(m+n)$内

## 5	Longest Palindromic Substring    		 	 	
7	Reverse Integer    		 	 	
8	String to Integer (atoi)    		 	 	
10	Regular Expression Matching    		 	 	
11	Container With Most Water    		 	 	
13	Roman to Integer    		 	 	
14	Longest Common Prefix    		 	 	
15	3Sum    		 	 	
17	Letter Combinations of a Phone Number    		 	 	
19	Remove Nth Node From End of List    		 	 	
20	Valid Parentheses    		 	 	
21	Merge Two Sorted Lists    		 	 	
22	Generate Parentheses    		 	 	
23	Merge k Sorted Lists    		 	 	
26	Remove Duplicates from Sorted Array    		 	 	
28	Implement strStr()    		 	 	
29	Divide Two Integers    		 	 	
33	Search in Rotated Sorted Array    		 	 	
34	Find First and Last Position of Element in Sorted Array    		 	 	
36	Valid Sudoku    		 	 	
38	Count and Say    		 	 	
41	First Missing Positive    		 	 	
42	Trapping Rain Water    		 	 	
44	Wildcard Matching    		 	 	
46	Permutations    		 	 	
48	Rotate Image    		 	 	
49	Group Anagrams    		 	 	
50	Pow(x, n)    		 	 	
53	Maximum Subarray    		 	 	
54	Spiral Matrix    		 	 	
55	Jump Game    		 	 	
56	Merge Intervals    		 	 	
62	Unique Paths    		 	 	
66	Plus One    		 	 	
69	Sqrt(x)    		 	 	
70	Climbing Stairs    		 	 	
73	Set Matrix Zeroes    		 	 	
75	Sort Colors    		 	 	
76	Minimum Window Substring    		 	 	
78	Subsets    		 	 	
79	Word Search    		 	 	
84	Largest Rectangle in Histogram    		 	 	
88	Merge Sorted Array    		 	 	
91	Decode Ways    		 	 	
94	Binary Tree Inorder Traversal    		 	 	
98	Validate Binary Search Tree    	
101	Symmetric Tree    		 	 	
102	Binary Tree Level Order Traversal    		 	 	
103	Binary Tree Zigzag Level Order Traversal    		 	 	
104	Maximum Depth of Binary Tree    		 	 	
105	Construct Binary Tree from Preorder and Inorder Traversal    		 	 	
108	Convert Sorted Array to Binary Search Tree    		 	 	
116	Populating Next Right Pointers in Each Node    		 	 	
118	Pascal's Triangle    		 	 	
121	Best Time to Buy and Sell Stock    		 	 	
122	Best Time to Buy and Sell Stock II    		 	 	
124	Binary Tree Maximum Path Sum    		 	 	
125	Valid Palindrome    		 	 	
127	Word Ladder    		 	 	
128	Longest Consecutive Sequence    		 	 	
130	Surrounded Regions    		 	 	
131	Palindrome Partitioning    		 	 	
134	Gas Station    		 	 	
136	Single Number    		 	 	
138	Copy List with Random Pointer    		 	 	
139	Word Break    		 	 	
140	Word Break II    		 	 	
141	Linked List Cycle    		 	 	
146	LRU Cache    		 	 	
148	Sort List    		 	 	
149	Max Points on a Line    		 	 	
150	Evaluate Reverse Polish Notation    		 	 	
152	Maximum Product Subarray    		 	 	
155	Min Stack    		 	 	
160	Intersection of Two Linked Lists    		 	 	
162	Find Peak Element    		 	 	
163	Missing Ranges    		 	 	
166	Fraction to Recurring Decimal    		 	 	
169	Majority Element    		 	 	
171	Excel Sheet Column Number    		 	 	
172	Factorial Trailing Zeroes    		 	 	
179	Largest Number    		 	 	
189	Rotate Array    		 	 	
190	Reverse Bits    		 	 	
191	Number of 1 Bits    		 	 	
198	House Robber    		 	 	
200	Number of Islands    		 	 	
202	Happy Number    		 	 	
204	Count Primes    		 	 	
206	
Reverse Linked List    		 	 	
207	
Course Schedule    		 	 	
208	
Implement Trie (Prefix Tree)    		 	 	
210	
Course Schedule II    		 	 	
212	
Word Search II    		 	 	
215	
Kth Largest Element in an Array    		 	 	
217	
Contains Duplicate    		 	 	
	218	
The Skyline Problem    		 	 	
227	
Basic Calculator II    		 	 	
230	
Kth Smallest Element in a BST    		 	 	
234	
Palindrome Linked List    		 	 	
236	
Lowest Common Ancestor of a Binary Tree    		 	 	
237	
Delete Node in a Linked List    		 	 	
238	
Product of Array Except Self    		 	 	
239	
Sliding Window Maximum    		 	 	
240	
Search a 2D Matrix II    		 	 	
242	
Valid Anagram    		 	 	
251	
Flatten 2D Vector    		 	 	
253	
Meeting Rooms II    		 	 	
268	
Missing Number    		 	 	
269	
Alien Dictionary    		 	 	
277	
Find the Celebrity    		 	 	
279	
Perfect Squares    		 	 	
283	
Move Zeroes    		 	 	
285	
Inorder Successor in BST    		 	 	
287	
Find the Duplicate Number    		 	 	
289	
Game of Life    		 	 	
295	
Find Median from Data Stream    		 	 	
297	
Serialize and Deserialize Binary Tree    		 	 	
300	
Longest Increasing Subsequence    		 	 	
308	
Range Sum Query 2D - Mutable    		 	 	
315	
Count of Smaller Numbers After Self    		 	 	
322	
Coin Change    		 	 	
324	
Wiggle Sort II    		 	 	
326	
Power of Three    		 	 	
328	
Odd Even Linked List    		 	 	
329	
Longest Increasing Path in a Matrix    		 	 	
334	
Increasing Triplet Subsequence    		 	 	
340	
Longest Substring with At Most K Distinct Characters    		 	 	
341	
Flatten Nested List Iterator    		 	 	
344	
Reverse String    		 	 	
347	
Top K Frequent Elements    		 	 	
348	
Design Tic-Tac-Toe    		 	 	
350	
Intersection of Two Arrays II    		 	 	
371	
Sum of Two Integers    		 	 	
378	
Kth Smallest Element in a Sorted Matrix    		 	 	
380	
Insert Delete GetRandom O(1)    		 	 	
384	
Shuffle an Array    		 	 	
387	
First Unique Character in a String    		 	 	
395	
Longest Substring with At Least K Repeating Characters    		 	 	
412	
Fizz Buzz    		 	 	
454	
4Sum II    		 	 	 	 	