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
```

### 7. Sort a String
* Given a string consisting of lowercase letters, arrange all its letters in ascending order.
```
class Solution 
{ 
    String sort(String s) 
    {
        char[] arr=s.toCharArray();
        Arrays.sort(arr);
        String res=new String(arr);
        return res;
    }
}
"""
Input:
S = "edcab"
Output: "abcde"
Explanation: characters are in ascending
order in "abcde".
"""
```

### 8. Minimum Product of k Integers
```
class Solution {
    int minProduct(int arr[], int k) {
        Arrays.sort(arr);
        int n=arr.length;
        long product=1;
        for(int i=0; i<k && i<n; i++){
            product=(product*arr[i]) % 1000000007;
        }
        return (int)product;
    }
}
"""
Input: arr[] = [1, 2, 3, 4, 5] and k = 2
Output: 2
Explanation: We will get the minimum product after multiplying 1 and 2 that is 2. So, the answer is 2.
"""
```

### 9. Count pair sum
* Given two sorted arrays arr1 and arr2 of distinct elements. Given a value x. The problem is to count all pairs from both arrays whose sum equals x.
```
class Solution {
    static int countPairs(int arr1[], int arr2[], int x) {
        int count=0;
        for(int i=0; i<arr1.length; i++){
            for(int j=0; j<arr2.length; j++){
                int sum=arr1[i]+arr2[j];
                if(sum == x){
                    count++;
                }
            }
        }
        return count;
    }
}
"""
Input: x = 10, arr1[] = [1, 3, 5, 7], arr2[] = [2, 3, 5, 8] 
Output: 2
Explanation: The pairs are: (5, 5) and (7, 3).
"""
```

### 10. Alternative Sorting

* Given an array arr of distinct integers. Rearrange the array in such a way that the first element is the largest and the second element is the smallest, the third element is the second largest and the fourth element is the second smallest, and so on.

```
import java.util.Arrays;

public class Main{
    public static void main(String[] args){
        int[] arr={7,1,2,3,4,5,6};
        Arrays.sort(arr);
        int n=arr.length;
        int l=n-1, s=0;
        int[] res=new int[n];
        int index=0;
        while(s<=l){
            if(index<n){
            res[index++]=arr[l];
            }
            if(index<n){
            res[index++]=arr[s];
            }
            s++;
            l--;
        }
        for(int i=0; i<n; i++){
            System.out.printf("%d ", res[i]);
        }
    }
}
"""
Input: arr[] = [7, 1, 2, 3, 4, 5, 6]
Output: [7, 1, 6, 2, 5, 3, 4]
"""
```
