# Weekly Coding #5: Skyrail Station Navigator

## Summary
This project implements core binary tree traversals and binary search tree (BST) operations for the Skyrail station navigator.

Included functions:
- `preorder_values`
- `inorder_values`
- `postorder_values`
- `bst_contains`
- `bst_insert`

## Approach
- Traversals use recursion with a base case of `None`.
- Traversal orders:
  - preorder -> node, left, right
  - inorder -> left, node, right
  - postorder -> left, right, node
- `bst_contains` uses iterative search and follows BST ordering.
- `bst_insert` iteratively finds the insertion point and ignores duplicates.

## Complexity
- Traversals (`preorder_values`, `inorder_values`, `postorder_values`)
  - Time: `O(n)`
  - Space: `O(n)` for output list plus recursion stack up to tree height
- `bst_contains`
  - Time: `O(h)` (average `O(log n)`, worst `O(n)`)
  - Space: `O(1)`
- `bst_insert`
  - Time: `O(h)` (average `O(log n)`, worst `O(n)`)
  - Space: `O(1)`

## Edge Cases Covered
- Empty tree traversal returns `[]`
- Single-node traversal works correctly
- BST search on empty tree returns `False`
- Missing BST values return `False`
- Insert into empty tree creates the root
- Duplicate insertions are ignored

## Assistance and Sources
- AI used: Yes
- How it was used: Helped with structure checks and README cleanup
- Other sources: Assignment brief and starter tests

## Test Results
```bash
python -m pytest -q
15 passed in 0.02s
```
