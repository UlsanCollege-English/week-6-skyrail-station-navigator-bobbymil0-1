[![Review Assignment Due Date](https://classroom.github.com/assets/deadline-readme-button-22041afd0340ce965d47ae6ef1cefeee28c7c493a6346c4f15d667ab976d596c.svg)](https://classroom.github.com/a/mHMwxQwH)
# Weekly Coding #5: Skyrail Station Navigator

## Summary
This project implements core binary-tree and BST operations for the Skyrail station navigator.
I built preorder, inorder, and postorder traversals that return values in the correct visit order.
I also implemented BST search (`bst_contains`) to efficiently locate a target value.
For insertion, `bst_insert` follows BST rules, creates a root for an empty tree, and ignores duplicates.
The implementation is written in Python 3.11+ using only the standard library.

---

## Approach
- Traversals use recursive helper functions with a shared result list.
- Each traversal has a clear base case (`None`) and only appends when visiting real nodes.
- `bst_contains` iteratively walks left or right using BST ordering until found or exhausted.
- `bst_insert` iteratively finds the insertion spot and links one new leaf node.
- Duplicate insert values are detected and ignored without modifying the tree.

---

## Complexity

### `preorder_values`
- **Time:** `O(n)`
- **Space:** `O(n)` total (`O(n)` output list + `O(h)` recursion stack)
- **Why:** Every node is visited exactly once and appended once. Recursion depth depends on tree height `h`.

### `inorder_values`
- **Time:** `O(n)`
- **Space:** `O(n)` total (`O(n)` output list + `O(h)` recursion stack)
- **Why:** The algorithm traverses left, node, right and still processes each node one time.

### `postorder_values`
- **Time:** `O(n)`
- **Space:** `O(n)` total (`O(n)` output list + `O(h)` recursion stack)
- **Why:** Left and right subtrees are visited before appending the node, but each node is still handled once.

### `bst_contains`
- **Time:** `O(h)` (average `O(log n)`, worst `O(n)`)
- **Space:** `O(1)`
- **Why:** It follows exactly one root-to-leaf path based on comparisons. Tree shape controls height `h`.

### `bst_insert`
- **Time:** `O(h)` (average `O(log n)`, worst `O(n)`)
- **Space:** `O(1)`
- **Why:** It walks one path to find the insertion point (or existing duplicate) and performs constant extra work.

---

## Edge-Case Checklist
- [x] Empty tree traversal returns `[]` (all three traversals immediately return an empty list)
- [x] Single-node traversal works correctly (single value is returned in all traversal orders)
- [x] `bst_contains` returns `False` for an empty tree (loop never starts, returns `False`)
- [x] `bst_contains` returns `False` when the target is missing (search path ends at `None`)
- [x] `bst_insert` creates a root when the tree is empty (returns `TreeNode(value)`)
- [x] `bst_insert` ignores duplicate values (returns original root without adding a new node)
- [x] I tested at least one deeper insert case (example: inserting `55` into the sample BST)

---

## Assistance & Sources
- **AI used? (Y/N):** Y
- **What AI helped with:** Planning, code drafting/refinement, complexity wording, and README structure.
- **Other sources used:** Assignment prompt and provided starter/test files only.

---

## Test Results
`python -m pytest -q`  
`15 passed in 0.01s`
