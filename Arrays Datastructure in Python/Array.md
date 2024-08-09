# Arrays in Python


## Way to find element in array



### Lookup by index
- Time complexity: O(1)

```python	
arr = [1, 2, 3, 4, 5]
print(arr[2]) 
```

### Lookup by value
- Time complexity: O(n)

```python
arr = [1, 2, 3, 4, 5]
for i in arr:
    if i == 3:
        return i
```

### Array Traversal
- Time complexity: O(n)

```python
arr = [1, 2, 3, 4, 5]
for i in arr:
    print(i)
```

### Insertion and Deletion
- Time complexity: O(n)

```python
# Insertion
arr = [1, 2, 3, 4, 5]
arr.insert(2, 7)

# Deletion
arr = [1, 2, 3, 4, 5]
arr.remove(1)
```

- In these operations the shifting of elements takes place which makes the time complexity O(n).

## Types of Arrays
- There are two types of arrays:
    1. Static Array
    2. Dynamic Array (List in Python)

## How they are different?
- Static array is a simple array in which the size of the array is fixed and cannot be changed.
- Dynamic array is a resizable array in which the size of the array can be changed dynamically. Like in Python, we have lists which are dynamic arrays.

## How a dynamic array works?
- When the size of the array is full, a new array is created with double the size of the original array and all the elements are copied to the new array. This process is called resizing. 

## Advantages of dynamic array over static array
- Dynamic array is more flexible than static array as the size of the array can be changed dynamically. 
- It is more memory efficient as the memory is allocated only when needed.
- It is more time efficient as the time complexity of insertion and deletion is O(n) in dynamic array as compared to O(1) in static array.

## What arrays can store?
- Arrays can store elements of any data type like integers, strings, characters, etc.
- Apart from this they can also store complex objects.

```python
arr = [1,2,4,5,6,2]

arr = ["hello", "world", "python"]

arr = [
    {"name": "John", "age": 25},
    {"name": "Doe", "age": 30},
    {"name": "Jane", "age": 35}
]
```

## 2D Arrays & 3D Arrays
- 2D arrays are arrays of arrays. They are used to represent matrices.
- 3D arrays are arrays of 2D arrays. They are used to represent 3D objects.

```python
arr = [
    [1, 2, 3], 
    [4, 5, 6], 
    [7, 8, 9]
]

arr = [
    [
        [1, 2, 3], 
        [4, 5, 6], 
        [7, 8, 9]
    ],
    [
        [10, 11, 12], 
        [13, 14, 15], 
        [16, 17, 18]
    ],
    [
        [19, 20, 21], 
        [22, 23, 24], 
        [25, 26, 27]
    ]
]
```


### Some Important Points
> **Time Complexity:** Time complexity is a way to represent the amount of time taken by the program to run as a function of the length of the input.

> **In simple way**, we can consider that if we iterate through an array one time or we use a single loop then the time complexity will be O(n) where n is the length of the array and when we iterate through the array with two loops one in another (i.e. nested loop) then the time complexity will be O(n^2).

> **Space Complexity:** Space complexity is a way to represent the amount of space taken by the program to run as a function of the length of the input.


## Problems based on Arrays


### [Problem - 1](https://github.com/codebasics/data-structures-algorithms-python/blob/master/data_structures/2_Arrays/2_arrays_exercise.md)

Let us say your expense for every month are listed below,
1. January - 2200
1. February - 2350
1. March - 2600
1. April - 2130
1. May - 2190

Create a list to store these monthly expenses and using that find out,
```
1. In Feb, how many dollars you spent extra compare to January?
2. Find out your total expense in first quarter (first three months) of the year.
3. Find out if you spent exactly 2000 dollars in any month
4. June month just finished and your expense is 1980 dollar. Add this item to our monthly expense list
5. You returned an item that you bought in a month of April and
got a refund of 200$. Make a correction to your monthly expense list
based on this
```

### Solution:

```python
expenses = [2200, 2350, 2600, 2130, 2190]

# 1. In Feb, how many dollars you spent extra compare to January?
ans1 = expenses[1] - expenses[0]

# 2. Find out your total expense in first quarter (first three months) of the year.
ans2 = expenses[0] + expenses[1] + expenses[2]

# 3. Find out if you spent exactly 2000 dollars in any month
for i in expenses:
    if i == 2000:
        ans3 = True
        break
    else:
        ans3 = False
    
# 4. June month just finished and your expense is 1980 dollar. Add this item to our monthly expense list
expenses.append(1980)

# 5. You returned an item that you bought in a month of April and got a refund of 200$. Make a correction to your monthly expense list based on this
expenses[3] = expenses[3] - 200
```
---
### [Problem - 2](https://github.com/codebasics/data-structures-algorithms-python/blob/master/data_structures/2_Arrays/2_arrays_exercise.md)

You have a list of your favourite marvel super heros.
```python
heros=['spider man','thor','hulk','iron man','captain america']
```
Using this find out,
```
1. Length of the list
2. Add 'black panther' at the end of this list
3. You realize that you need to add 'black panther' after 'hulk',
   so remove it from the list first and then add it after 'hulk'
4. Now you don't like thor and hulk because they get angry easily :)
    So you want to remove thor and hulk from list and replace them with doctor strange (because he is cool).
    Do that with one line of code.
5. Sort the heros list in alphabetical order (Hint. Use dir() functions to list down all functions available in list)
```

### Solution:

```python
heros=['spider man','thor','hulk','iron man','captain america']

# 1. Length of the list
ans1 = len(heros)

# 2. Add 'black panther' at the end of this list
heros.append('black panther')

# 3. You realize that you need to add 'black panther' after 'hulk', so remove it from the list first and then add it after 'hulk'
heros.remove('black panther')
heros.insert(3, 'black panther')

# 4. Now you don't like thor and hulk because they get angry easily :) So you want to remove thor and hulk from list and replace them with doctor strange (because he is cool). Do that with one line of code.
heros[1:3] = ['doctor strange']

# 5. Sort the heros list in alphabetical order (Hint. Use dir() functions to list down all functions available in list)
heros.sort()
```
---
### [Problem - 3](https://github.com/codebasics/data-structures-algorithms-python/blob/master/data_structures/2_Arrays/2_arrays_exercise.md)

Create a list of all odd numbers between 1 and a max number. Max number is something you need to take from a user using input() function

### Solution:

```python
maxnumber = int(input("Enter the maximum number: "))

list = []

for i in range(1, maxnumber+1):
    if i % 2 != 0:
        list.append(i)
```

---
<h3 style="text-align:right;margin-top:0">Don't forget to leave a ⭐ to this Repository</h3>