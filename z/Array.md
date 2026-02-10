
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
 