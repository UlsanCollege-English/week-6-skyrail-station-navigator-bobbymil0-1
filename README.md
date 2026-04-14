# Weekly Coding #5: Skyrail Station Navigator

## Summary
This project implements core binary tree and binary search tree (BST) operations for the Skyrail station navigator. It includes preorder, inorder, and postorder traversals, as well as BST search and insertion. The goal is to correctly apply tree traversal patterns and BST properties using Python’s standard library.

---

## Approach
- Traversals are implemented using recursion with a clear base case (`None`).
- Each traversal follows its correct visiting order:
  - preorder → node, left, right
  - inorder → left, node, right
  - postorder → left, right, node
- `bst_contains` uses an iterative approach to efficiently search by comparing values and moving left or right.
- `bst_insert` iteratively finds the correct position and inserts a new node while maintaining BST rules.
- Duplicate values are safely ignored to preserve tree integrity.

---

## Complexity

### `preorder_values`, `inorder_values`, `postorder_values`
- **Time:** `O(n)`
- **Space:** `O(n)`
- **Reason:** Each node is visited exactly once. The result list stores all node values, and recursion uses up to `O(h)` stack space.

### `bst_contains`
- **Time:** `O(h)` (average `O(log n)`, worst `O(n)`)
- **Space:** `O(1)`
- **Reason:** The algorithm follows a single path from root to leaf based on comparisons.

### `bst_insert`
- **Time:** `O(h)` (average `O(log n)`, worst `O(n)`)
- **Space:** `O(1)`
- **Reason:** Only one path is traversed to find the insertion point, and insertion itself is constant time.

---

## Edge Cases
- Empty tree traversal returns an empty list (`[]`)
- Single-node tree returns correct traversal output
- `bst_contains` returns `False` for empty trees
- `bst_contains` returns `False` if the value is not found
- `bst_insert` creates a root node when the tree is empty
- `bst_insert` ignores duplicate values
- Deep insertions maintain correct BST structure

---

## Assistance & Sources
- **AI used?** Yes , to improve and tackle my previous mistake
- **How it was used:** Helped refine code structure, improve readability, and format explanations in this README  
- **Other sources:** Assignment instructions and provided test files  

---

## Test Results
```bash
python -m pytest -q

