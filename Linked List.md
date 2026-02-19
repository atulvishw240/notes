
Made up of **ListNode** (object), which encapsulates a **value** and a **next** pointer.

Iterating over a linked list is O(n), where n is the size of our linked list
```ruby
curr = ListNode1
while (curr != nil)
  curr = curr.next
```

It would be helpful if we track the **head** and **tail** of the linked list as our implementation.

Removing any node from linked list is O(1) operation, assuming we have the pointer to previous node that we are trying to remove.

Practically speaking if you have to search for the element you want to remove then its a O(n) operation. You'll first search the element and then remove it.

