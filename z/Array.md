
**Data structure**: A way to structure data

> Arrays are always contiguous.

>[!note]
>RAM stands for Random Access Memory, which means we can access any portion of the memory in constant time.

## Static Arrays

- fixed size
- removing a value means overwriting with a new value

| **Operation**       | **Big-O Time** |
| ------------------- | -------------- |
| r / w i-th element  | O (1)          |
| Insert / Remove End | O (1)          |
| Insert Middle       | O (n)          |
| Remove Middle       | O (n)          |
here n is the no. of elements in the array;

 >[!note] length vs size of array
 >**Length** means the no. of elements in the array.
 >**Size** means max capacity of array.

## Dynamic Arrays

 ![[dynamic-array.png]]
 >[!question] Why double the size of array instead of just increasing it by 1?
 >Amortized time complexity.

- Tradeoff between creating new array and copying elements into it VS empty spaces.

![[amortized-time-complexity.png]]

>[!question] Why constants are ignored in Big-O?
>In Big-O growth rate matters. Functions will intersect at some point and after that the higher growth rate function will grow much faster. This is what we care about (growth rate).

![[growth-rate.png]]


| Operation           | Big-O Time                  |
| ------------------- | --------------------------- |
| r/w i-th element    | O(1)                        |
| Insert / Remove End | O(1) (amortized complexity) |
| Insert Middle       | O(n)                        |
| Remove Middle       | O(n)                        |

