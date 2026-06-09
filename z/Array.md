
**Data structure**: A way to structure data

> Arrays are always contiguous.

>[!note]
>RAM stands for Random Access Memory, which means we can access any portion of the memory in constant time.

When we are storing data in RAM, we don't always get to choose where that data be stored. Every value in RAM will be stored at a particular address.

Arrays are stored in RAM the exact same way they look
![[attachments/array.png]]

## 03. Static Arrays

- fixed size
- languages like Python and JavaScript there are no static arrays. They offer dynamic arrays as default
- removing a value means overwriting it  with a new value
![[attachments/static-array.png]]

| **Operation**       | **Big-O Time**   |
| ------------------- | ---------------- |
| r / w i-th element  | O (1)            |
| Insert / Remove End | O (1)            |
| Insert Middle       | O (n) (Shifting) |
| Remove Middle       | O (n) (Shifting) |
here n is the no. of elements in the array;

 >[!note] length vs size of array
 >**Length** means the no. of elements in the array.
 >**Size** means max capacity of array.

## 04. Dynamic Arrays

- we don't specify its size but the language will set its size to some default value (in java its size will be 10)
 ![[dynamic-array.png]]
 >[!question] Why double the size of array instead of just increasing it by 1?
 >Amortized time complexity O(1). It can also be thought of average time complexity.

- Tradeoff between creating new array and copying elements into it VS empty spaces.

![[amortized-time-complexity.png]]

>[!question] Why constants are ignored in Big-O?
>In Big-O growth rate matters. Functions will intersect at some point and after that the higher growth rate function will grow much faster. This is what we care about (growth rate).

![[growth-rate.png]]


| Operation           | Big-O Time                  |
| ------------------- | --------------------------- |
| r/w i-th element    | O(1)                        |
| Insert / Remove End | O(1) (amortized complexity) |
| Insert Middle       | O(n) (Shifting)             |
| Remove Middle       | O(n) (Shifting)             |

