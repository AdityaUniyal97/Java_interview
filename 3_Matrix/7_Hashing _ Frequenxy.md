## Two Sum
```
class Solution {
    public int[] twoSum(int[] nums, int target) {
        HashMap<Integer,Integer> map = new HashMap<>();
        for(int i = 0 ; i < nums.length ; i++){
            int sum = target - nums[i];
            if(map.containsKey(sum)){
                return new int[]{map.get(sum),i};
            }
            map.put(nums[i],i);
        }
        return new int[]{-1,-1};
    }
}
```

## Valid Anagram
```
class Solution {
    public boolean isAnagram(String s, String t) {
        if(s.length() != t.length()){
            return false;
        }
        int count[] = new int[26];
        for(int i = 0 ; i < s.length() ; i++){
            count[s.charAt(i) -'a']++;
            count[t.charAt(i) -'a']--;
        }
        for(int i = 0 ; i < 26 ; i++){
            if(count[i] != 0){
                return false;
            }
        }
        return true;
    }
}
```