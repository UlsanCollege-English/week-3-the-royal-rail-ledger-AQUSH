# Week 3 Assignment: The Royal Rail Ledger

## Summary
In this assignment, I implemented several functions to work with singly linked lists (SLL) and doubly linked lists (DLL). The tasks included building a linked list from a Python list, converting a linked list back to a Python list, detecting the first repeated value, removing specific values from a doubly linked list, and checking whether a doubly linked list forms a palindrome.

These problems helped reinforce understanding of linked list traversal, pointer manipulation, and edge case handling.

---

## Approach

### Task 1: build_sll_from_list
- Created a new `SinglyLinkedList`
- Handled the empty list case
- Iterated through the input list and linked nodes sequentially

### Task 2: sll_to_list
- Traversed the linked list starting from the head
- Collected values into a Python list
- Returned the result

### Task 3: find_first_repeat_sll
- Used a `set` to track seen values
- Traversed the list from head to tail
- Returned the first value that appears twice

### Task 4: remove_all_from_dll
- Traversed the doubly linked list
- Carefully updated:
  - `prev.next`
  - `next.prev`
  - `dll.head`
  - `dll.tail`
- Stored `next_node` before modifying links to avoid losing traversal

### Stretch: is_train_palindrome
- Used two pointers:
  - one from the head
  - one from the tail
- Compared values while moving inward
- Stopped when pointers met or crossed

---

## Complexity

| Function                      | Time Complexity | Space Complexity |
|------------------------------|----------------|------------------|
| build_sll_from_list          | O(n)           | O(n)             |
| sll_to_list                  | O(n)           | O(n)             |
| find_first_repeat_sll        | O(n)           | O(n)             |
| remove_all_from_dll          | O(n)           | O(1)             |
| is_train_palindrome          | O(n)           | O(1)             |

---

## Edge Case Checklist

- [x] Empty singly linked list
- [x] Empty doubly linked list
- [x] Single-node lists
- [x] Repeated values
- [x] Removing from the head
- [x] Removing from the tail
- [x] Removing consecutive matching values
- [x] Removing all nodes from a list
- [x] Palindrome with even length
- [x] Palindrome with odd length

---

## Assistance & Sources

- Course lecture notes (Week 3: Linked Lists)
- Python documentation for sets
- Personal debugging and testing with `pytest`

No external code was copied. All implementations were written independently.