Count The Common Subsequence in two Strings
In this article, we will learn how to write a python program to count common subsequence in two strings. We will have two strings n and m.

Lets understand with the help of example.
m= “ABC”

n= “AB”

The subsequence of m = A,B,C, AB, BC, AC, ABC  and n=A,B,AB

The count of common subsequences is 3 that is (A,B AB)

Count Common Subsequence In Two Strings
Algorithm:
Initialize the variables.
Accept the inputs.
Iterate each character from  first string .
Iterate each character from second string.
Match these characters one by one.
If they matches store the count.
Print count.
Python program to count common sub sequence in two strings
Python Code
Run
#Count Common Subsequence in two Strings
n="ABC"
m="AB"
l1,l2=len(n),len(m)
cnt=[[0 for i in range(l2+1)] for i in range(l1+1)]
for i in range(1,l1+1):
    for j in range(1,l2+1):
         if(n[i-1] == m[j-1]):
             cnt[i][j] = 1 + cnt[i][j-1] + cnt[i-1][j]
         else:
             cnt[i][j] = cnt[i][j-1] + cnt[i-1][j] - cnt[i-1][j-1]
print(cnt[l1][l2])
Output:
3
