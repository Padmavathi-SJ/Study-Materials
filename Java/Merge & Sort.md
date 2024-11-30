### built-in methods:

### 1. Merge and Sort
* Given two arrays arr1 and arr2, return the merged array in ascending order containing unique elements.

```
class Solution {
    public int[] mergeNsort(int[] arr, int[] brr) {
        Set<Integer> set=new HashSet<>();
        for(int i=0; i<arr.length; i++){
            set.add(arr[i]);
        }
        for(int i=0; i<brr.length; i++){
            set.add(brr[i]);
        }
        List<Integer> l=new ArrayList<>(set);
        Collections.sort(l);
        int[] res=l.stream().mapToInt(Integer::intValue).toArray();
        return res;
    }
}
"""
Input: arr1[] = [11, 1, 8], arr2[] = [10, 11]
Output: [1, 8, 10, 11]
Explanation: The ouput array after merging both the arrays and removing duplicates is [1 8, 10, 11]
"""
```
