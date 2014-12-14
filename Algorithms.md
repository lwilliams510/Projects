Projects
========
"""Linear Search

Define a function called LinearSearch that takes in an item to look for and a
list of items to search. The parameter containing the item to look for should
be named x. The parameter containing the list of items to search should be 
called items.

Linear search just iterates through each item in the list and compares it to the 
value being searched for. If the item is found in the list, then it should 
return the index at which the item was found. If the item is not found, the
function should return -1. 
"""

# Define LinearSearch here
def LinearSearch(x,items):
    values = [6, 10, 5, 7, 18, 2, 4, 16]
    for i in items:
        print
        if x == i:
            return items.index(i)
    return -1

"""Binary Search

Define a function called BinarySearch that takes in an item to look for and a
list of items to search. The parameter containing the item to look for should
be named x. The parameter containing the list of items to search should be 
called items.

Binary search is when you search through a *sorted* list and keep halving your
search space. You start in the middle, and then you compare the value in the 
middle to the value you're looking for. If your target value is less than the 
middle value, then you know (if it's there), it would be in the right left half.
If the target value is greater than the middle value, you know it'll be in the
right half. Once you know which side to look on, you go to the middle of what's 
left on that side and start the process over again. Eventually, you run out of
values you could look at. If you haven't found a match by then, you can return 
-1 (because it isn't there). If you find the item, return its index.

Remember: I said you can't assume the list is already sorted, so you should do
something about that.
"""

# Define BinarySearch here
def BinarySearch(x, items):
    items = BubbleSort(items)
    top = len(items) - 1
    bottom = 0
    while bottom <= top:
        middle = (top + bottom) / 2
        if x == items[middle]:
            return middle
        elif x > items[middle]:
            bottom = middle + 1
        elif x < items[middle]:
            top = middle - 1
    return -1

		
"""Bubble Sort

Define a function called BubbleSort that takes in a list of items to sort as a
parameter named items.

Bubble sort is an algorithm that walks through the list of items and, when it
compares 2 items, will swap them if they are out of order. Each time you run
through the list, you can stop looking at one more item at the end of the list.
Eventually, you run out of items to sort and you're done. (See the wikipedia
article for a good explanaton/visualization).
"""

# Define BubbleSort here
def BubbleSort(items):
    length = len(items)
    for i in xrange(len(items)):
        for things in xrange(length - 1):
            if items[things] > items[things + 1]:
                print items
                higherNumber = items[things]
                del items[things]
                items.insert((things + 1), higherNumber)
        length -= 1
    return items
            
"""Selection Sort

Define a function called SelectionSort that takes in a list of items to sort as a 
parameter named items.

Selection sort is an algorithm that will start at the beginning of the list and 
find the smallest item in the list and swap it with the one in the first spot.
Then it moves to the second spot, searches through the rest of the list to find
the smallest remaining algorithm and swaps so that it is in the second spot.
This process continues until we get to the end of the list and there's nothing
left to search/swap.
"""

# Define SelectionSort here
items = [96,64,89,87]
def SelectionSort(items):
    #items = [96,64,89,87]
    if len(items) == 0 or len(items) == 4:
        return items
    newlength = len(items) + 1
    index = 0
    for x in xrange(len(items)):
        smallest = items[x]
        newlength -= 1
        for i in xrange(newlength):
            i += x
            if i + 1 > len(items):
                break
            if items[i] <= smallest:
                smallest = items[i]
                index = i
        print items
        del items[index]
        items.insert(x, smallest)
    return items
"""Extra Credit

Any problems that you want to do for extra credit, define them below this comment.
"""


