Find whether arrays are disjoint or not
In this program we will  find whether arrays are disjoint or not using Python.Two arrays are disjoint if they don’t have no element in common.The intersection of two disjoint sets is an empty set.

Find whether arrays are disjoint or not
What is intersection and disjoint ?
Intersection is denoted by a symbol “∩” which when applied between two sets gives the common elements in the both sets/arrays. In python we can use either intersection( ) function or “&” symbol between two sets to find intersection.

set1= {1,2,3,4}  and  set2={5,6,7,8}
intersection of set1 and set2 is = { } . So this is disjoint.

set1 ={1,2,3,4}  and  set2={4,5,6,7}

intersection of set1 and set2 = {4} . So this is not disjoint

what is intersection
Find whether arrays are disjoint or not in python
Related Pages
Find all Symmetric pairs in an array

Find maximum product sub-array in a given array

Determine Array is a subset of another array or not

Determine can all numbers of an array be made equal

Finding Minimum sum of absolute difference of given array

Method Discussed :
Method 1 : Using Nested loop
Method 2 : Using Sorting and Merging
Method 3 : Using Set.
Method 4 : Using Intersection function.
Let’s discuss above methods in brief,

Method 1:
Input two arrays and pass them as arguments to a function
In the body of function initialize a nested for loop
Traverse the array 1 using the outer loop.Find whether arrays are disjoint or not using Python
Use the inner loop to check if the elements in array 2 are found in array 1.
If at least one element of array 2 is found in array 1, return False otherwise return True.
If function returns True display “Disjoint”,otherwise “Not disjoint”
 
Method 1 : Python Code:
def fun(l1,l2):
    for i in range(0,len(l1)):
        for j in range(0,len(l2)):
            if(l1[i]==l2[j]):
                return False
    return True

l1=list(map(int,input("Enter array1").split()))
l2=list(map(int,input("Enter array2").split()))
if(fun(l1,l2)):
    print("Disjoint")

else:
    print("Not disjoint")
Output:
Enter array1 1 2 3 4 5
Enter array2 4 5 6 7 8
Not disjoint
Method 2 :
In this method we first sort both the arrays, then use the concept of merging to compare the elements.

Method 2 : Python Code
def areDisjoint(set1, set2, m, n):
    # Sort the given two sets
    set1.sort()
    set2.sort()
 
    # Check for same elements 
    # using merge like process
    i = 0; j = 0
    while (i < m and j < n):
         
        if (set1[i] < set2[j]):
            i += 1
        elif (set2[j] < set1[i]):
            j += 1
        else: # if set1[i] == set2[j]
            return False
    return True
 
 
# Driver Code
arr1 = [12, 34, 11, 9, 3]
arr2 = [7, 2, 1, 5]
m = len(arr1)
n = len(arr2)
 
print("Yes") if areDisjoint(arr1, arr2, m, n) else print("No")
Output
Yes
Method 3
In this method we will use set. First insert the elements of first array in set, then start iterating over the second array and check if the elements present in the set or not.

Method 3 : Python Code
def areDisjoint(set1, set2, n1, n2):
   
  # Creates an empty hashset
  myset = set([])
   
  # Traverse the first set
  # and store its elements in hash
  for i in range (n1):
    myset.add(set1[i])
     
  for i in range (n2):
    if (set2[i] in myset):
      return False
  return True
 
# Driver method to test above method

arr1 = [10, 5, 3, 4, 6]
arr2 = [8, 7, 9, 3]
 
n1 = len(arr1)
n2 = len(arr2)
   
if (areDisjoint(arr1, arr2, n1, n2)):
    print ("Yes")
else:
    print("No")
Output
No
Method 4
Read 1st array as set using set() function 
Read 2nd array as set using set() function
By using intersection function in sets we can find whether there is any common element present in both sets or not
If intersection is empty then it is disjoint , else if it has at least one element it is not a disjoint
Method 4 : Python code
l1=set(map(int,input("Enter array1 ").split()))
l2=set(map(int,input("Enter array2 ").split()))
if(l1.intersection(l2)):
    print("Not a disjoint ")
else:
    print("disjoint")
Output:
Enter array1 1 2 3 4 5
Enter array2 6 7 9
disjoint
