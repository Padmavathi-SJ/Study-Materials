### 1. Given an array arr of distinct elements, the task is to return an array of all elements except the two greatest elements in sorted order.
```
class Solution {
    public long[] findElements(long arr[]) {
        Arrays.sort(arr);
        int n=arr.length;
        long max1=arr[n-1];
        long max2=arr[n-2];
        long[] res=new long[n-2];
        int index=0;
        for(int i=0; i<n; i++){
            if(arr[i]!=max1 && arr[i]!=max2){
                res[index++]=arr[i];
            }
        }
        return res;
    }
}
"""
Input: arr[] = [2, 8, 7, 1, 5]
Output: [1, 2, 5]
"""
```

### 2. Given two arrays arr1 and arr2 of equal size, the task is to find whether the given arrays are equal. Two arrays are said to be equal if both contain the same set of elements, arrangements (or permutations) of elements may be different though.
Note: If there are repetitions, then counts of repeated elements must also be the same for two arrays to be equal.

```
class Solution {
    // Function to check if two arrays are equal or not.
    public static boolean check(int[] arr1, int[] arr2) {
        Arrays.sort(arr1);
        Arrays.sort(arr2);
        return Arrays.equals(arr1, arr2);
        
    }

"""
Input: arr1[] = [1, 2, 5, 4, 0], arr2[] = [2, 4, 5, 0, 1]
Output: true
"""
```
