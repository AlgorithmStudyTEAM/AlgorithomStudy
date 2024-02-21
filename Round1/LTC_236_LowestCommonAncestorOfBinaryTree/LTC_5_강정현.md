#  LTC_5_lowest-common-ancestor-of-a-binary-tree/description 강정현 [2/21 수요일] </br>
문제 주소: https://leetcode.com/problems/lowest-common-ancestor-of-a-binary-tree/description/ </br>
푼 시간:  </br>

<접근법>
```
공통 조상 노드 하위에 p, q가 모두 들어있어야 하기 때문에 루트를 기준으로 시작하여 공통 조상 노드를 찾는다.
(재귀사용)
```


```java
class Solution {
    public TreeNode lowestCommonAncestor(TreeNode root, TreeNode p, TreeNode q) {
        if (root == null) {
            return null;
        }
        if (root == p || root == q) {
            return root;
        }

        TreeNode left = lowestCommonAncestor(root.left, p, q);
        TreeNode right = lowestCommonAncestor(root.right, p, q);

        if (left != null && right != null) {
            return root;
        }
        return (left != null) ? left : right;
    }
}
```
