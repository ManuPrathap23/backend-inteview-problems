SAMPLE QUESTIONS FOR ONLINE TESTS

Question 1 :


An array has a special integer if that integer can be formed by calculating the sum of a number and its reverse .
Find how many interger are special in an array
Note: Trailing zeros from the reverse of a number formed need to be removed if they exist.

Input Specification:
input1: Array of strings where each string represents a number.
input2: Size of array.
Output Specification: 
Return number of special integers.

Example 1:
input1: {22,121}
input2: 2
Output: 2
Explanation: 
22 can be formed using 11+11, similarly, 121 can be formed using 29+92. Hence, the output is 2.
 
====================================================================================

Example 2: 
input1: {12,3}
input2: 2
Output: 1
Explanation: 
12 can be formed using 6+6, but no such number can be found for 3, hence, the output is 1.

Question 2 : 
Lost in the Forest
A boy is lost in an infinitely long 1 dimensional jungle. The jungle is such that if the boy is standing at location N, then, after the next step he would be moved to location (N/2) if N is even, and (3N + 1) if N is odd.
However, there is a magic door in the jungle that can take him to any location N he wants to go between location 1 and M (including both), but just once. 
Find the location that the boy should go to such that he reaches the maximum number of locations in the forest.
 
Input Specification:
input1: The value of M
Output Specification:
Return the location where the boy should go first. If there are multiple answers, then return the largest one.

Example 1:
 
input1: 5
Output: 3
Explanation: 
If he selects 3, then he can go to:
3->10->5->16->8->4->2->1.

Example 2: 
input1: 10
Output: 9
Explanation: 
If he selects 9, he can go to: 
9->28->14->7-> 22 ->11 ->34 ->17 ->52-> 26-> 13-> 40-> 20 ->10 ->5-> 16 ->8-> 4-> 2-> 1 

====================================================================================

Question 3
There are two players A and B who are interested in playing a game of numbers. In each move a player pick two distinct number, let’s say a1 and a2 and then replace all a2 by a1 or a1 by a2. They stop playing game if any one of them is unable to pick two number and the player who is unable to pick two distinct number in an array, looses the game. First player always move first and then second. Task is to find which player wins.

Examples:
Input :  arr[] = { 1, 3, 3, 2,, 2, 1 }
Output : Player 2 wins
Explanation:
First plays always looses irrespective
of the numbers chosen by him. For example,
say first player picks ( 1 & 3) 
replace all 3 by 1  
Now array Become { 1, 1, 1, 2, 2, 1 }
Then second player picks ( 1  2 )
either he replace 1 by 2 or 2 by 1 
Array Become { 1, 1, 1, 1, 1, 1 }
Now first player is not able to choose.
 
Input  : arr[] = { 1, 2, 1, 2 }
Output : Player 1 wins
From above examples, we can observe that if number of count of distinct element is even, first player always wins. Else second player wins.

Lets take an another example :
  int arr[] =  1, 2, 3, 4, 5, 6 
Here number of distinct element is even(n). If player 1 pick any two number lets say (4, 1), then we left with n-1 distinct element. So player second left with n-1 distinct element. This precess go on until distinct element become 1. Here n = 6
Player   :  P1    p2    P1   p2    P1     P2    
distinct : [n, n-1, n-2, n-3, n-4, n-5 ]  
 
"At this point no distinct element left, 
so p2 is unable to pick two Dis element."

Time Complexity to achieve: O(n)

====================================================================================

Question 4: Given arrival and departure times of all trains that reach a railway station, the task is to find the minimum number of platforms required for the railway station so that no train waits.
We are given two arrays which represent arrival and departure times of trains that stop
Examples:
Input: arr[] = {9:00, 9:40, 9:50, 11:00, 15:00, 18:00}
dep[] = {9:10, 12:00, 11:20, 11:30, 19:00, 20:00}
Output: 3
There are at-most three trains at a time (time between 11:00 to 11:20)
 
We need to find the maximum number of trains that are there on the given railway station at a time. A Simple Solution is to take every interval one by one and find the number of intervals that overlap with it. Keep track of maximum number of intervals that overlap with an interval. Finally return the maximum value. Time Complexity of this solution is O(n2).
We can solve the above problem in O(N Log N) time. The idea is to consider all events in sorted order. Once we have all events in sorted order, we can trace the number of trains at any time keeping track of trains that have arrived, but not departed.
For example consider the above example.
    arr[]  = {9:00,  9:40, 9:50,  11:00, 15:00, 18:00}
    dep[]  = {9:10, 12:00, 11:20, 11:30, 19:00, 20:00}
 
All events sorted by time.
Total platforms at any time can be obtained by subtracting total 
departures from total arrivals by that time.
 Time     Event Type     Total Platforms Needed at this Time    
 
 9:00       Arrival                  1
 
 9:10       Departure                0
 
 9:40       Arrival                  1
 
 9:50       Arrival                  2
 
 11:00      Arrival                  3 
 
 11:20      Departure                2
 
 11:30      Departure                1
 
 12:00      Departure                0
 
 15:00      Arrival                  1
 
 18:00      Arrival                  2 
 
 19:00      Departure                1
 
 20:00      Departure                0
 
Minimum Platforms needed on railway station = Maximum platforms 
                                              needed at any time 
                                           = 3  
Below is the implementation of the above approach. Note that the implementation doesn’t create a single sorted list of all events, rather it individually sorts arr[] and dep[] arrays, and then uses merge process of merge sort to process them together as a single sorted array.
Note : This approach assumes that trains are arriving and departing on same date.


====================================================================================


Question 5: Given a linked list, the task is to complete the function maxPalindrome which returns an integer denoting  the length of the longest palindrome list that exist in the given linked list.
Examples:
Input  : List = 2->3->7->3->2->12->24
Output : 5
The longest palindrome list is 2->3->7->3->2
 
Input  : List = 12->4->4->3->14
Output : 2
The longest palindrome list is 4->4
Input:
The first line of input contains an integer T denotingo the no of test cases. Then T test cases follow. The first line of each test case contains an integer N denoting the size of the linked list . Then in the next line are N space separated values of the given linked list.

Output:
For each test case output will be the required max length of the palindrome present in the given linked list.

Constraints:
1<=T<=100
1<=N<=100

Example(To be used only for expected output):
Input:
2
7
2 3 7 3 2 12 24
5
12 4 4 3 14
Output:
5
2

====================================================================================


Question 6:  Given an input stream of N characters consisting only of lower case alphabets. The task is to find the first non-repeating character, each time a character is inserted to the stream. If no non repeating element is found print -1.
Input:
The first line of input contains an integer T denoting the no of test cases. Then T test cases follow. Each test case contains an integer N denoting the size of the stream. Then in the next line are x characters which are inserted to the stream.
Output:
For each test case in a new line print the first non-repeating elements separated by spaces present in the stream at every instinct when a character is added to the stream, if no such element is present print -1.
Constraints:
1 <= T <= 200
1 <= N <= 500
Example:
Input:
2
4
a a b c
3
a a c 
Output:
a -1 b b
a -1 c


