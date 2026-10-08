# Second-Minimum-Node-in-a-Binary-Tree
# Definition for a binary tree node.
# class TreeNode:
#     def __init__(self, val=0, left=None, right=None):
#         self.val = val
#         self.left = left
#         self.right = right
class Solution:
    def findSecondMinimumValue(self, root: TreeNode | None) -> int:
        if root is None:
            return -1
        r=[]
        def add(root,r):
            if root is None:
                return 
            r.append(root.val)
            add(root.left,r)
            add(root.right,r)
        add(root,r)
        r1=list(set(r))
        r1.sort()
        if len(r1)>=2:
            return r1[1]
        else:
            return -1
