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