### Searching problems list solved from geeksforgeeks

### 1. Value equal to index value 

* Given an array arr. Your task is to find the elements whose value is equal to that of its index value ( Consider 1-based indexing ).

* Note: There can be more than one element in the array which have the same value as its index. You need to include every such element's index. Follows 1-based indexing of the array.
```
class Solution {
    public List<Integer> valueEqualToIndex(List<Integer> nums) {
        int n=nums.size();
        List<Integer> l=new ArrayList<>();
        for(int i=1; i<=n; i++){
            if(nums.get(i-1)==i){
                l.add(i);
            }
        }
        return l;
    }
}
"""
Input: arr[] = [15, 2, 45, 4 , 7]
Output: 2 , 4
Explanation: 
Here, arr[2] = 2 exists here.
and arr[4] = 4 exists here.
"""
```
