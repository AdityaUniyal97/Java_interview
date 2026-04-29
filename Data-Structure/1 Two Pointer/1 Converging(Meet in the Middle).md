### Sqaure of the Sorted Array
**Input:** nums = [-4,-1,0,3,10]
**Output:** [0,1,9,16,100]

```
class Solution {
    public int[] sortedSquares(int[] nums) {
        int res[] = new int[nums.length];
        int left = 0;
        int right = nums.length - 1;
        int i = nums.length - 1;
        while(left <= right){
            int l = nums[left] * nums[left];
            int r = nums[right] * nums[right];
            if(l > r){
                res[i] = l;
                left++;
            }
            else{
                res[i] = r;
                right--;
            }
            i--;
        }
        return res;
    }
}
```

Time = O(n) , Space = O(n)

## Two SumII
**Input:** numbers = [2,7,11,15], target = 9
**Output:** [1,2]
```
class Solution {
    public int[] twoSum(int[] numbers, int target) {
        int left = 0;
        int right = numbers.length - 1;
        while(left < right){
            int sum = numbers[left] + numbers[right];
            if(sum == target){
                return new int[]{left + 1 , right  + 1};
            }
            else if(sum < target){
                left++;
            }
            else{
                right--;
            }
        }
        return new int[]{-1,-1};
    }
}
```

## Container with the Most water

```
class Solution {
    public int maxArea(int[] height) {
        int l = 0;
        int r = height.length - 1;
        int ma = 0;
        while(l < r){
            int h = Math.min(height[l] , height[r]);
            int w = r - l;
            int area = h * w;
            ma = Math.max(ma , area);
            if(height[left] < height[right]){
                left++;
            }
            else{
                right--;
            }
        }
        return ma;
    }
}
```

### Boats to save people
**Input:** people = [1,2], limit = 3
**Output:** 1
**Explanation:** 1 boat (1, 2)

🧠 Thinking (short)
👉 Sort → smallest & largest
👉 Take heavy (right)
👉 Check: light + heavy ≤ limit?
→ YES → left++
→ NO → heavy alone
👉 Always right--
👉 boats++
```
class Solution {
    public int numRescueBoats(int[] people, int limit) {
        Arrays.sort(people);
        int left = 0;
        int right = people.length - 1;
        int boats = 0;
        while(left <= right){
            if(people[left] + people[right] <= limit){
                left++;
            }
            right--;
            boats++;
        }
        return boats;
    }
}
```
Time = O(n log n) shorting takes (n log n)
Space = O(1)

## 3 Sum

Input: nums = [-1,0,1,2,-1,-4]
Output: [[-1,-1,2],[-1,0,1]]

Explanation: Because nums[0] + nums[1] == 9, we return [0, 1].
👉 Sort array
👉 Fix one number (i)
👉 Find pair using two pointers
👉 sum = nums[i] + left + right
sum < 0 → left++
sum > 0 → right--
sum == 0 → save + move both
👉 skip duplicates
```
class Solution {
    public List<List<Integer>> threeSum(int[] nums) {
        Arrays.sort(nums);
        List<List<Integer>> res = new ArrayList<>();
        for(int i = 0 ; i < nums.length - 2; i ++){
            if(i > 0 && nums[i] == nums[i - 1]) continue;
            int left = i + 1;
            int right = nums.length - 1;
            while(left < right){
                int sum = nums[i] + nums[left] + nums[right];
                if(sum == 0){
                    res.add(Arrays.asList(nums[i],nums[left],nums[right]));
                    left++;
                    right--;

                    while(left < right && nums[left] == nums[left - 1]) left++;
                    while(left < right && nums[right] == nums[right+1]) right--;
                }
                else if(sum < 0){
                    left++;
                }
                else{
                    right--;
                }
            }
        }
        return res;
    }
}
```

Time = o(n^2) Space = O(1)

## 3 Sum Closest
**Input:** nums = [-1,2,1,-4], target = 1
**Output:** 2
**Explanation:** The sum that is closest to the target is 2. (-1 + 2 + 1 = 2).
**Thinking**
Sort  
👉 Fix one (i)  
👉 Use two pointers
👉 Track **closest sum**
- sum < target → left++
- sum > target → right--
- update closest every time
```
class Solution {
    public int threeSumClosest(int[] nums, int target) {
        Arrays.sort(nums);
        int close = nums[0] + nums[1] + nums[2];
        for(int i = 0 ; i < nums.length - 2 ; i++){
            int left = i + 1;
            int right = nums.length - 1;
            while(left < right){
                int sum = nums[i] + nums[left] + nums[right];
                if(Math.abs(sum - target) < Math.abs(close - target)){
                    close = sum;
                }
                if(sum < target){
                    left++;
                }
                else if(sum > target){
                    right--;
                }
                else{
                    return sum;
                }
            }
        }
        return close;
    }
}
```

👉 Time: O(n²)  
👉 Space: O(1)

## 4 Sum
```
class Solution {
    public List<List<Integer>> fourSum(int[] nums, int target) {
        Arrays.sort(nums);
        List<List<Integer>> res = new ArrayList<>();
        for(int i = 0 ; i < nums.length ; i++){
            if(i > 0 && nums[i] == nums[i - 1]) continue;
            for(int j = i + 1; j < nums.length ; j++){
                if(j > i+1 && nums[j] == nums[j - 1]) continue;
                int l = j + 1;
                int r = nums.length - 1;
                while(l < r){
                    long sum = (long)nums[i]+nums[l]+nums[r]+nums[j];
                    if(sum == target){
                        res.add(Arrays.asList(nums[i],nums[j],nums[l],nums[r]));
                        while(l<r && nums[l] == nums[l + 1]) l++;
                        while(l<r && nums[r] == nums[r - 1]) r--;
                        l++;
                        r--;
                    }
                    else if(sum < target) l++;
                    else r--;
                }
            }
        }
        return res;
    }
}
```
Time= O(n^3) , Spacec = O(1)