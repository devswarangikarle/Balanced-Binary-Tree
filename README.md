# Balanced-Binary-Tree

Given a binary tree, determine if it is height-balanced.

Constraints:
The number of nodes in the tree is in the range [0, 5000].
-10^4 <= Node.val <= 10^4.

class Solution:
    def isBalanced(self, root: Optional[TreeNode]) -> bool:
        return (self.height(root) >= 0)
    
    def height(self, root: Optional[TreeNode]) -> int:
        if root is None:
            return 0  
        
        lh, rh = self.height(root.left), self.height(root.right)
        
        if lh < 0 or rh < 0 or abs(lh - rh) > 1:
            return -1
        
        return max(lh, rh) + 1
        
