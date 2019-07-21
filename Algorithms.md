## Notes

* The term 'Big O Notation' is a simple term for:
  * how fast an algorithm takes to run when thinking about operation count.
* Big O represents the worst case scenario for each algorithm.
* Factorial time can be represented as O(n!)
  * This is often times associated with the problem called: 'A Traveling Salesperson' (compsci)
* Every recursive function has two parts:
  1. _Base_ case: what breaks the recursive calls
  1. _Recursive_ case: the part of the function that calls itself.

## Binary Search

* Search for anything in logarithmic time.
  * This equates to O(log n) for n amount of items
* Speed of completion increases as the number of items in the list increases.
* _Only_ works on a sorted list of items.

## Sorting

* We often times perform O(n^2) when sorting through a list.
  * This equates to searching once, moving the item, and repeating for all items in the list.

### Data Structures Refresher

## Array

* Set list of items in a chunk of memory.
  * If a new one is needed and no extra slots were allocated, 
      copying and adding the new item is required.
* Random and sequential access allowed.

## Lists (Linked)

* Items are added to the list by linking their next item in memory.
* Adding doesn't reqire coping the whole list, 
    just associating the last item with the new item being added.
* Getting to the 'last item' is expensive because you have to traverse the whole list.
* Inserting (in the middle) is cheap though and performant
  * Insert + update references is easier than in an Array
  * True with deletes as well.
* _Only_ sequential access allowed
