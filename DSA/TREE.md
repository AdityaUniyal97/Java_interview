## Inorder Traversal(Left->data->Right)
Recusive:->
```
class Solution {
    public List<Integer> inorder(TreeNode root) {
        List<Integer> arr = new ArrayList<>();
        recursiveInorder(root,arr);
        return arr;
    }
    public void recursiveInorder(TreeNode root , List<Integer> arr){
        if(root == null){
            return;
        }
        recursiveInorder(root.left,arr);
        arr.add(root.data);
        recursiveInorder(root.right,arr);
    }
}
```

Iterative->
```
class Soluton {
    public List<Integer> inorder(TreeNode root) {
        Stack<TreeNode> st = new Stack<>();
        TreeNode node = root;
        List<Integer> inorder = new ArrayList<>();
        while(true){
            if(node != null){
               st.push(node);
                node = node.left;
            }
            else{
                if(st.isEmpty()){
                    break;
                }
                node = st.pop();
                inorder.add(node.data);
                node = node.right;
            }
        }
        return inorder;
    }
}
```

## PostOrder Traversal 
Recursive-> 
```
void recursivePostorder(TreeNode root, List<Integer> result) {
    if (root == null) return;
    recursivePostorder(root.left, result);
    recursivePostorder(root.right, result);
    result.add(root.data);
}
```
Iterative:->
```
public List<Integer> postorder(TreeNode root) {
        List<Integer> result = new ArrayList<>();
        Stack<TreeNode> nodeStack = new Stack<>();
        if(root != null){
            nodeStack.push(root);
        }
        while(!nodeStack.isEmpty()){
            TreeNode node = nodeStack.pop();
            result.add(node.data);
            if(node.left != null){
                nodeStack.push(node.left);
            }
            if(node.right != null){
                nodeStack.push(node.right);
            }
        }
        Collections.reverse(result);
        return result;
    }

```

## Level Order traversal 
**Input :** root = [3, 9, 20, null, null, 15, 7]
**Output :** [ [3] , [9, 20] , [15, 7] ]
**Explanation :**
![](https://static.takeuforward.org/content/ProblemSetter-rPjEzBZp)
Time O(n) 
Space O(n) 
```
public List<List<Integer>>levelOrder(TreeNode root) {
      List<List<Integer>> ans = new ArrayList<>();
        if(root == null){
            return ans;
        }
       Queue<TreeNode> q = new LinkedList<>();
        q.add(root);
        while(!q.isEmpty()){
            int size = q.size();
            List<Integer> level = new ArrayList<>();
            for(int i = 0 ; i < size ; i++){
                TreeNode node = q.poll();
                level.add(node.data);
                if(node.left != null){
                    q.add(node.left);
                }
                if(node.right != null){
                    q.add(node.right);
                }
            }
            ans.add(level);
        }
       return ans;
    }
```
## **Height of the Binary Tree**
**Input :** root = [1, 2, 3, null, null, null , 6]
**Output :** 3
**Explanation :** The path from root node 1 to node with value 6 has maximum depth with 3 nodes along path.

![](https://static.takeuforward.org/content/ProblemSetter-iaO2S02r)
```
 int maxDepth(TreeNode* root) {
        if(root == NULL){
            return 0;
        }
        int left = maxDepth(root->left);
        int right = maxDepth(root->right);
        return (1 + max(left,right));
    }
```


## Right/Left View of BT
**Input :** root = [1, 2, 3, null, 5, null, 4]
**Output :** [1, 3, 4]
**Explanation :**
![](https://static.takeuforward.org/content/ProblemSetter-Pc0hbDIa)
```
public:
   vector<int> rightSideView(TreeNode* root) {
       vector<int> res;
        rightView(root,0,res);
        return res;
    }
    public:
  void rightView(TreeNode *root , int level , vector<int> &res){
        if(root == NULL){
            return;
        }
        if(res.size() == level){
            res.push_back(root->data);
        }
        rightView(root->right,level+1,res);
        rightView(root->left,level+1,res);
    }
```

## **Check for balanced Binary Tree**
**Input :** [3, 9, 20, null, null, 15, 7]
**Output :** Yes
**Explanation :** If the difference between the left subtree and right subtree is smaller equal to 1 than balanced
![](https://static.takeuforward.org/content/ProblemSetter-MQ-fF3Hv)
==Brute== 
Time = O(n^2)
Space = O(n)
```
 public boolean isBalanced(TreeNode root) {
        if(root == null){
            return true;
        }
        int leftHeight = getHeight(root.left);
        int rightHeight = getHeight(root.right);
        if(Math.abs(leftHeight - rightHeight) <= 1 &&    isBalanced(root.left) && isBalanced(root.right)){
            return true;
        }
        return false;
    }

    public int getHeight(TreeNode root){
        if(root == null){
            return 0;
        }
        int left = getHeight(root.left);
        int right = getHeight(root.right);
        return Math.max(left,right) + 1;
    }
```
==Optimised==
Time = O(n)
Space = O(n)
```
public boolean isBalanced(TreeNode root) {
        return dfsHeight(root) != -1;
    }
    private int dfsHeight(TreeNode root){
        if(root == null){
            return 0;
        }
        int left = dfsHeight(root.left);
        if(left == -1){return -1;}
        int right = dfsHeight(root.right);
        if(right == -1){return -1;}
        if(Math.abs(left - right) > 1){
            return -1;
        }
        return Math.max(left,right)+1;
    }
```

## **Check if two trees are identical**
Input : p = [1, 2, 3] , q = [1, 2, 3]
**Output :** true
**Explanation :** Both trees images are shown below

![](https://static.takeuforward.org/content/ProblemSetter-hF_hLlOD)
```
public boolean isSameTree(TreeNode p, TreeNode q) {
        if(p == null && q == null){
            return true;
        }
        if(p == null || q == null){
            return false;
        }
        if(p.data != q.data){
            return false;
        }
        return isSameTree(p.left,q.left) && isSameTree(p.right,q.right);
    }
```

## **Check if Tree is Symetric Or Not**
**Input :** root = [1, 2, 2, 3, 4, 4, 3]
**Output :** true
**Explanation :**

![](https://static.takeuforward.org/content/ProblemSetter-xz280fOG)
```
public boolean isSymmetric(TreeNode root) {
        if(root == null){
            return true;
        return symetry(root.left , root.right);
    }

    public boolean symetry(TreeNode left , TreeNode right){
        if(left == null && right == null){
            return true;
        if(left == null || right == null){
            return false;
        if(left.data != right.data){
            return false;
        }
        return symetry(left.left , right.right) &&  symetry(left.right , right.left);
    }
```

## **Diameter of a Binary Tree**
**Input :** root = [1, 2, 3, 4, 5]
**Output :** 3
**Explanation :** The path length between node 4 and 3 is of length 3.
![](https://static.takeuforward.org/content/ProblemSetter-PtG_ttvW)
![[Pasted image 20250619165829.png]]
```
int diameter = 0;
    public int diameterOfBinaryTree(TreeNode root) {  
        height(root);
        return diameter;
    }
    private int height(TreeNode node){
        if(node == null){
            return 0;
        }
        int left = height(node.left);
        int right = height(node.right);
        diameter = Math.max(diameter,left + right);
        return 1 + Math.max(left,right);
    }
```


## **Binary Tree ZigZag Level Order Traversal**
![](https://assets.leetcode.com/uploads/2021/02/19/tree1.jpg)

**Input:** root = [3,9,20,null,null,15,7]
**Output:** [[3],[20,9],[15,7]]
```
 public List<List<Integer>> zigzagLevelOrder(TreeNode root) {
        List<List<Integer>> result = new ArrayList<>();
        if(root == null)
            return result;
        Queue<TreeNode> nq = new LinkedList<>();
        nq.add(root);
        boolean lr = true;
        while(!nq.isEmpty()){
            int size = nq.size();
            List<Integer> row = new ArrayList<>(Collections.nCopies(size , 0));
            for(int i = 0 ; i < size ; i++){
               TreeNode node = nq.poll();
                int index = lr ? i : (size - 1 - i);
                row.set(index , node.val);
                if(node.left != null){
                    nq.add(node.left);
                }
                if(node.right != null){
                   nq.add(node.right);
                }

            }

            result.add(row);

            lr = !lr;

        }
        return result;
    }
```