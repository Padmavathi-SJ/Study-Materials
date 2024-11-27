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

* **Arrays.equals(arr1, arr2)**
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

### 3. Given a random array arr of numbers, please return them in ascending sorted order.
```
class Solution {
    void sortArr(int[] arr) {
        Arrays.sort(arr);
    }
}
"""
Input: arr[] = [1, 5, 3, 2]
Output: [1, 2, 3, 5]
"""
```

### 4. Sort in specific order
* Given an array arr[] of positive integers. Your task is to sort them so that the first part of the array contains odd numbers sorted in descending order, and the rest of the portion contains even numbers sorted in ascending order.
  
```
class Solution {

    public void sortIt(Long arr[]) {
        int n=arr.length;
        long[] odd=new long[n];
        long[] even=new long[n];
        int oddIndex=0;
        int evenIndex=0;
        for(int i=0; i<n; i++){
            if(arr[i]%2!=0){
                odd[oddIndex++]=arr[i];
            }
            else{
                even[evenIndex++]=arr[i];
            }
        }
        Arrays.sort(odd, 0, oddIndex);
        Arrays.sort(even, 0, evenIndex);
        for(int i=0; i<oddIndex/2; i++){
            long temp=odd[i];
            odd[i]=odd[oddIndex-1-i];
            odd[oddIndex-1-i]=temp;
        }
        
        long[] res=new long[n];
        int index=0;
        for(int i=0; i<oddIndex; i++){
            res[index++]=odd[i];
        }
        for(int i=0; i<evenIndex; i++){
            res[index++]=even[i];
        }
        for(int i=0; i<n; i++){
            arr[i]=res[i];
        }
    }
}
"""
Input: arr[] = [1, 2, 3, 5, 4, 7, 10]
Output: [7, 5, 3, 1, 2, 4, 10]
"""
```

### 5. Maximum product of two numbers
* Given an array arr of non-negative integers, return the maximum product of two numbers possible.
  
```
class Solution {
    public static int maxProduct(int[] arr) {
        Arrays.sort(arr);
        int n=arr.length;
        int max1=arr[n-1];
        int max2=arr[n-2];
        return max1*max2;
    }
}
"""
Input: arr[] = [1, 4, 3, 6, 7, 0] 
Output: 42
Explanation: 6 and 7 have the maximum product
"""
```

### 6. Minimum difference pair
* Given an unsorted array, find the minimum difference between any pair in given array.
```
class Solution
{
    public int minimum_difference(int[] nums)
    {
        int n=nums.length;
        Arrays.sort(nums);
        int minDiff=Integer.MAX_VALUE;
        for(int i=1; i<n; i++){
            int currDiff = nums[i]-nums[i-1];
            minDiff=Math.min(minDiff, currDiff);
        }
        return minDiff;
    }
    
}
"""
Input: nums = [2, 4, 5, 9, 7]
Output: 1
Explanation: Difference between 5 and 4 is 1.
"""

