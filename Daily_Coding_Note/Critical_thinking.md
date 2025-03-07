
### Longest Increasing Subarray
```
class Solution {
    public int lenOfLongIncSubArr(List<Integer> arr) {
        int maxLen=1, currLen=1;
        for(int i=1; i<arr.size(); i++){
            if(arr.get(i) > arr.get(i-1)){
                currLen++;
                maxLen=Math.max(currLen, maxLen);
            }
            else{
                currLen=1;
            }
        }
        return maxLen;
        
    }
}
"""
Input: arr[] = [5, 6, 3, 5, 7, 8, 9, 1, 2]
Output: 5
"""
```
