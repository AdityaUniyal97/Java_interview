
```
class Solution {
    public int[] plusOne(int[] digits) {
        for(int i = digits.length - 1; i >= 0 ; i--){
            if(digits[i] < 9){
                digits[i] = digits[i] + 1;
                return digits;
            }
        }
        int res[] = new int[digits.length + 1];
        res[0] = 1;
        return res;
    }
}
```

## Add to Arrat arr = [1,2] k = 2  op = [1,4] 
```
class Solution {
    public List<Integer> addToArrayForm(int[] num, int k) {
        List<Integer> res = new ArrayList<>();
        int i = num.length - 1;
        while(i >= 0 ||  k > 0){
            int digit = 0;
            if(i >= 0){
                digit = num[i];
                i--;
            }
            int ans = k % 10;
            k = k / 10;
            
            int sum = digit + ans;
            if(sum < 10){
                res.add(sum);
            }
            else{
                res.add(sum % 10);
                k = k + (sum / 10);
            }
        }
        Collections.reverse(res);
        return res;
    }
}
```