Tree is Used to organise the Data in the Hierarchical Order

### Basic Template
```
public class Main{
    static class Node{
    int value;
    Node left;
    Node right;
    Node(int value){
        this.value = value;
        this.left = null;
        this.right = null;
    }
}
    public static void main(String args[]){
        Node root = new Node(10);
        Node a = new Node(5);
        Node b = new Node(15);
        Node c = new Node(3);
        Node d = new Node(7);
        root.left = a;
        root.right = b;
        a.left = c;
        a.right = d;
        System.out.println(countNode(root));
    }
```
### Inorder Traversal
```
public static void inorder(Node root){
        if(root == null){
            return;
        }
        inorder(root.left);
        System.out.println(root.value+" ");
        inorder(root.right);
    }
```

## Height of the tree

```
        10          ← level 0
       /  \
      5    15       ← level 1
     / \
    3   7           ← level 2
```

```
 public static int height(Node root){
        if(root == null){
            return -1;
        }
        int left = height(root.left);
        int right = height(root.right);
        return Math.max(left,right) + 1;
    }
```

```
height(3) = 1 + max(-1, -1) = 0
height(7) = 1 + max(-1, -1) = 0
height(5) = 1 + max(0, 0)   = 1
height(15)= 1 + max(-1, -1) = 0
height(10)= 1 + max(1, 0)   = 2  
```

### Count the Nodes of the tree
```
public static int countNode(Node root){
        if(root == null) return 0;
        int left = countNode(root.left);
        int right = countNode(root.right);
        return left + right + 1;
    }
```

```
        10          ← level 0
       /  \
      5    15       ← level 1
     / \
    3   7           ← level 2
```

```
countNodes(3)  = 0 + 0 + 1 = 1
countNodes(7)  = 0 + 0 + 1 = 1
countNodes(5)  = 1 + 1 + 1 = 3
countNodes(15) = 0 + 0 + 1 = 1
countNodes(10) = 3 + 1 + 1 = 5 ✅
```

## Maximum Depth of the Binary Tree
**same as the Height of the Tree there return -1 because counting the edges and here we will return 0 because counting the nodes**
```
class Solution {
    public int maxDepth(TreeNode root) {
       if(root == null){
        return 0;
       } 
       int left = maxDepth(root.left);
       int right = maxDepth(root.right);
       return Math.max(left ,right) + 1;
    }
}
```

# Minimum Depth of the Binary Tree
instaead of directly giving one , if left is empt we will forcefully call right 
```
    public int minDepth(TreeNode root) {
        if(root == null){
            return 0;
        }
        if(root.left == null){
            return minDepth(root.right) + 1;
        }
        if(root.right == null){
            return minDepth(root.left) + 1;
        }
        int left = minDepth(root.left);
        int right = minDepth(root.right);
        return Math.min(left , right) + 1;
    }
```


## Diameter of a Binary Tree
```
lass Solution {
    int maxD = 0;
    public int diameterOfBinaryTree(TreeNode root) {
        height(root);
        return maxD;
    }
    private int height(TreeNode root){
        if(root == null){
            return 0;
        }
        int left = height(root.left);
        int right = height(root.right);
        if(left + right > maxD){
            maxD = left + right;
        }
        return Math.max(left,right) + 1;
    }
}
```

## Same Tree 
```
public boolean isSameTree(TreeNode p, TreeNode q) {
        if(p == null && q == null){
            return true;
        }
        if(p == null || q == null){
            return false;
        }
        if(p.val != q.val){
            return false;
        }
        return isSameTree(p.left , q.left) 
        && isSameTree(p.right , q.right);
    }
```

## Invert The B tree
```
 public TreeNode invertTree(TreeNode root) {
        if(root == null){
            return root;
        }
        TreeNode temp = root.left;
        root.left = root.right;
        root.right = temp;
        invertTree(root.left);
        invertTree(root.right);
        return root;
    }
```

## Symmetric Tree
```
public boolean isSymmetric(TreeNode root) {
        if(helper(root.left , root.right)){
            return true;
        }
        return false;
    }
    private boolean helper(TreeNode left , TreeNode right){
        if(left == null && right == null){
            return true;
        }
        if(left == null || right == null){
            return false;
        }
        if(left.val != right.val){
            return false;
        }
        return helper(left.left,right.right) && helper(left.right , right.left);
    }
}
```

## Has Path Sum == target
```
 public boolean hasPathSum(TreeNode root, int targetSum) {
        if(root == null){
            return false;
        }
        if(root.left == null && root.right == null){
            return root.val == targetSum;
        }
        return hasPathSum(root.left,targetSum - root.val) || 
        hasPathSum(root.right,targetSum - root.val);
    }
```

## Flatten The Binary tree to a LL
**Pehle left aur right ko seedha chain bana, phir left ko right me chipka aur purana right end pe laga**
```
 public void flatten(TreeNode root) {
        if(root == null){
            return ;
        }
        flatten(root.left);
        flatten(root.right);
        TreeNode temp = root.right;
        root.right = root.left;
        root.left = null;
        TreeNode curr = root;
        while(curr.right != null){
            curr = curr.right;
        }
        curr.right = temp;
    }
```

## Smallest String Starting from Leaf
**DFS karo, char ko front me add karo, leaf pe string compare karo, smallest update karo**

```
class Solution {
    String ans = "~";
    public String smallestFromLeaf(TreeNode root) {
        dfs(root,"");
        return ans;
    }

    public void dfs(TreeNode node , String curr){
        if(node == null){
            return;
        }
        char ch = (char)(node.val + 'a');
        curr = ch + curr;
        if(node.left == null && node.right == null){
            if(curr.compareTo(ans) < 0){
                ans = curr;
            }
        }
        dfs(node.left,curr);
        dfs(node.right,curr);
    }
}
```

