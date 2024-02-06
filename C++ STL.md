# List
### Advantages :
- once a position has been found, insertion and deletion are quick (constant time `O(1)`).
### Disadvantages : 
- Slow search `O(N)`.
- No random access with `[ ]` or `.at()`.
- The one node (element) uses a lot of memory when compared to  a vector.
### Notes : 
- `assign()` function is used to insert multiple elements in a list in a single operation and works in following ways :
- To assign multiple elements at once in a list :  <br>
`list.assign(NUMBER_OF_TIMES, ELEMENT);`

- To copy elements of 1 list into another : <br>
`list.assign(list2.begin(), list2.end());`

- To copy array of elements into list : <br>
`list.assign(arr, arr + SIZE);`
---
- To insert elements at any position of list : <br>
`insert(POS_ITER, NUMBER_OF_TIMES, ELEMENT)`
<br>

- How to use Iterator: 

```c++
	list<int> list1; 

	// using assign() to insert multiple numbers 
	// creates 3 occurrences of "2" 
	list1.assign(3,2); 

	// initializing list iterator to beginning 
	auto it = list1.begin(); 
	
	// iterator to point to 3rd position 
	advance(it,2); 
	
	// using insert to insert 1 element at the 3rd position 
	// inserts 5 at 3rd position 
	list1.insert(it,5); 
	
	// Printing the new list 
	for (auto l : list1) cout << l << ' ';
	cout << endl; 
	
	// using insert to insert 2 element at the 4th position 
	// inserts 2 occurrences of 7 at 4th position 
	list1.insert(it,2,7); 
	
	// Printing the new list 
	for (auto l : list1) cout << l << ' ';
	cout << endl; 
```
---
- list doesn't use the functions from `#include <algorithm>` library. it has its own functions. so if you want to sort or reverse use : 
<br>

`list1.sort();` `list1.reverse();` `list1.sort(greater<int>());`

---

- `list1.remove(ELEMENT);` : Delete all occurrences of this element.

- `list1.remove_if()` : deletes the occurrences of the values that returns **'true'** to the function passed

- using `list1.erase(it);` to erase single element.

- using `list1.erase(it,it1);` to erase multiple elements.

---

- using `list1.unique()` to remove duplicates from the list. <br>
**Note :** the list should be sorted before using this function.

- using `list1.splice(list1.begin(), list2);` transfer all the elements of list2.

- using `list2.merge(list1, comparator);` If no comparator is passed in parameter, then it merges two sorted lists into a single sorted list.
