[![Review Assignment Due Date](https://classroom.github.com/assets/deadline-readme-button-22041afd0340ce965d47ae6ef1cefeee28c7c493a6346c4f15d667ab976d596c.svg)](https://classroom.github.com/a/TeyGQAqr)
# Week 3: The Royal Rail Ledger

## Summary
This assignment focuses on linked-list operations in a railway story setting. I implemented functions for building and reading a singly linked list, finding the first repeated value, removing banned cargo from a doubly linked list, and checking whether a train is a palindrome. The assignment uses both singly linked lists and doubly linked lists. The hardest part was correctly re-linking the previous and next pointers when removing nodes from the doubly linked list without breaking the chain.

---

## Approach

### `build_sll_from_list(values)`
- I started with an empty SinglyLinkedList and handled the empty input case first.
- I built the list by setting the head to the first value, then iterating through the rest and linking each new node to the previous one.
- I made sure the values stayed in the correct order by always appending to the tail using a `current` pointer.

### `sll_to_list(sll)`
- I started at the head node of the singly linked list.
- I traversed the list by following each node's `next` pointer until reaching `None`.
- I collected values in a Python list by appending each node's value during the traversal.

### `find_first_repeat_sll(sll)`
- I tracked values I had already seen by storing them in a Python `set` as I traversed the list.
- When I found a repeated value already in the set, I returned it immediately.
- If I reached the end with no repeat, I returned `None`.

### `remove_all_from_dll(dll, target)`
- I traversed the list using a `current` pointer starting from the head, saving `next` before any removal.
- When I found the target value, I updated the `prev` and `next` pointers of the surrounding nodes to skip over the removed node.
- I checked special cases such as removing the head node (updating `dll.head`), removing the tail node (updating `dll.tail`), and nodes in the middle.

### `is_train_palindrome(dll)`
- I compared values from both ends using a `left` pointer starting at the head and a `right` pointer starting at the tail.
- I stopped when the two pointers met or crossed, meaning all pairs had been checked.
- I returned `True` if all compared pairs matched, otherwise `False`.

---

## Complexity

### `build_sll_from_list(values)`
- **Time complexity:** O(n)
- **Space complexity:** O(n)
- **Why:** We visit each value once to create a node, and n nodes are stored in memory.

### `sll_to_list(sll)`
- **Time complexity:** O(n)
- **Space complexity:** O(n)
- **Why:** We traverse every node once, and the output list holds n values.

### `find_first_repeat_sll(sll)`
- **Time complexity:** O(n)
- **Space complexity:** O(n)
- **Why:** We scan the list once; the set can hold up to n values in the worst case.

### `remove_all_from_dll(dll, target)`
- **Time complexity:** O(n)
- **Space complexity:** O(1)
- **Why:** We traverse the entire list once and only use a fixed number of pointers.

### `is_train_palindrome(dll)`
- **Time complexity:** O(n)
- **Space complexity:** O(1)
- **Why:** We use two pointers moving inward from both ends with no extra data structures.

---

## Edge-case checklist

- [x] empty list
- [x] one-item list
- [x] target missing
- [x] repeated values
- [x] slice goes past end
- [x] size is zero
- [x] size is negative
- [x] original list unchanged in `priority_load`

---

## Assistance / Sources

- Python Documentation (docs.python.org):
  - Help received: Referenced how `set` lookups work and pointer reassignment for linked list node removal.

- Class lecture notes:
  - Help received: Reviewed singly and doubly linked list traversal patterns and edge case handling.