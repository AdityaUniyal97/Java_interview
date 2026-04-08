```
class Solution {
    public int maxScore(int[] cardScore, int k) {
        int n = cardScore.length;
        int sum = 0;
        for(int i = 0 ; i < k ; i++){
            sum += cardScore[i];
        }
        int ans = sum;
        int right = cardScore.length - 1;
        for(int i = k - 1; i >= 0 ; i--){
            sum -= cardScore[i];
            sum += cardScore[right];
            right--;
            ans = Math.max(ans , sum);
        }
        return ans;
    }
}
```