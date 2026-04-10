## Inorder Traversal
```
public List<Integer> inorderTraversal(TreeNode root) {
        List<Integer> ans  = new ArrayList<>();
        inorder(root,ans);
        return ans;
    }

    public void inorder(TreeNode root , List<Integer> ans){
        if(root == null){
            return;
        }
        inorder(root.left , ans);
        ans.add(root.val);
        inorder(root.right , ans);
    }
```

## Mode(Max occuring) element in BST
```
public int[] findMode(TreeNode root) {
        HashMap<Integer,Integer> map = new HashMap<>();
        dfs(root,map);
        int max = 0;
        // max freq
        for(int val : map.values()){
            if(val > max){
                max = val;
            }
        }
        //Collect answere
        List<Integer> list = new ArrayList<>();
        for(int key : map.keySet()){
            if(map.get(key) == max){
                list.add(key);
            }
        }
        //COnvert to Array
        int[] res = new int[list.size()];
        for(int i = 0 ; i < list.size() ; i++){
            res[i] = list.get(i);
        }
        return res;
    }
    public void dfs(TreeNode node , HashMap<Integer,Integer> map){
        if(node == null){
            return;
        }
        map.put(node.val , map.getOrDefault(node.val,0) + 1);
        dfs(node.left,map);
        dfs(node.right,map);
    }
```

## Find minimum difference between any two nodes in a BST
**Do inorder traversal
Keep:
prev → previous value
minDiff → answer
For each node:
diff = current - prev
update minDiff**
```
class Solution {
    int minD = Integer.MAX_VALUE;
    int prev = -1;
    public int getMinimumDifference(TreeNode root) {
        inorder(root);
        return minD;
    }
    public void inorder(TreeNode root){
        if(root == null){
            return;
        }
        inorder(root.left);
        if(prev != -1){
            minD = Math.min(minD , root.val - prev);
        }
        prev = root.val;
        inorder(root.right);
    }
}
```

## Find the k-th smallest element in a BST
**Inorder traversal = sorted order
So:
1 → 2 → 3 → 4 → 5 ...
 k-th element = answe**
 ```
 class Solution {
    int count = 0;
    int ans = 0;
    public int kthSmallest(TreeNode root, int k) {
        inorder(root,k);
        return ans;
    }

    public void inorder(TreeNode root , int k){
        if(root == null){
            return;
        }
        inorder(root.left , k);
        count++;
        if(count == k){
            ans = root.val;
            return;
        }
        inorder(root.right , k);
    }
}
 ```

## Leetcode 98(Check if this tree is BST)
**Pass a range (min, max)
Node must be:
min < node.val < max**
```
class Solution {
    public boolean isValidBST(TreeNode root) {
        return check(root,null,null);
    }
    public boolean check(TreeNode node, Integer min , Integer max){
        if(node == null){
            return true;
        }
        if(min != null && node.val <= min) return false;
        if(max != null && node.val >= max) return false;
        return check(node.left,min,node.val) && 
        check(node.right , node.val , max);
    }
}
```