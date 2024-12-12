### Searching problems list solved from geeksforgeeks

### Methods used:
* arr.indexOf(k) --> return index of k
* solution.isSubset(a, b) --> 1st create an object **Solution solution = new Solution();**
* set.contains(value) --> return index of that value

   
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

### 2. Binary Search

* Given a sorted array arr and an integer k, find the position(0-based indexing) at which k is present in the array using binary search.

* Note: If multiple occurrences are there, please return the smallest index.
```
class Solution {
    public int binarysearch(int[] arr, int k) {
        // Code Here
        boolean found=false;
        int result=0;
       for(int i=0; i<arr.length; i++){
           if(!found){
           if(arr[i]==k){
               result=i;
               found=true;
           }
           }
       }
       return found? result : -1;
    }
}
"""
Input: arr[] = [1, 2, 3, 4, 5], k = 4
Output: 3
Explanation: 4 appears at index 3.
Input: arr[] = [11, 22, 33, 44, 55], k = 445
Output: -1
Explanation: 445 is not present.
Input: arr[] = [1, 1, 1, 1, 2], k = 1
Output: 0
Explanation: 1 appears at index 0.
"""
```

### 3. Array Search
* Given an array, arr of n integers, and an integer element x, find whether element x is present in the array. Return the index of the first occurrence of x in the array, or -1 if it doesn't exist.
```
class Solution {

    static int search(int arr[], int x) {

      int n=arr.length;
      boolean found=false;
      int result=0;
      for(int i=0; i<n; i++){
          if(!found){
          if(arr[i] == x){
              result=i;
              found=true;
          }
          }
      }
      return found ? result: -1;
    }
}
"""
Input: arr[] = [1, 2, 3, 4], x = 3
Output: 2
Explanation: There is one test case with array as [1, 2, 3 4] and element to be searched as 3. Since 3 is present at index 2, the output is 2.
Input: arr[] = [10, 8, 30, 4, 5], x = 5
Output: 4
Explanation: For array [1, 2, 3, 4, 5], the element to be searched is 5 and it is at index 4. So, the output is 4.
Input: arr[] = [10, 8, 30], x = 6
Output: -1
Explanation: The element to be searched is 6 and its not present, so we return -1.
"""
```

### 4. Array Subset

* Given two arrays: a[] and b[], where both arrays may contain duplicate elements. The task is to determine whether array b is a subset of array a. It's important to note that both arrays can be unsorted. Additionally, each occurrence of a duplicate element within an array is considered as a separate element of the set.
```
class Solution {
    public boolean isSubset(int a[], int b[]) {
        // Your code here
        int n1=a.length;
        int n2=b.length;
        if(n2>n1) return false;
        for(int i=0; i<n2; i++){
            boolean found=false;
            for(int j=0; j<n1; j++){
                if(b[i] == a[j]){
                    found=true;
                    break;
                }
            }
            if(!found){
                return false;
            }
        }
    return true;
}
}
```
```
class Solution {
    public boolean isSubset(int a[], int b[]) {
Solution solution=new Solution();
return soultion(isSubset(s, b));
}
}
```
* optimized one
```
class Solution {
    public boolean isSubset(int a[], int b[]) {
        // Your code here
       boolean result=solution.isSubset(a, b);
        return result;
}
}
"""
Input: a[] = [11, 7, 1, 13, 21, 3, 7, 3], b[] = [11, 3, 7, 1, 7]
Output: Yes
Explanation: b[] is a subset of a[]
Input: a[] = [1, 2, 3, 4, 4, 5, 6], b[] = [1, 2, 4]
Output: Yes
Explanation: b[] is a subset of a[]
Input: a[] = [10, 5, 2, 23, 19], b[] = [19, 5, 3]
Output: No
Explanation: b[] is not a subset of a[]
"""
```

### 5. Sorted Array Search
* Given an array, arr[] sorted in ascending order and an integer k. Return true if k is present in the array, otherwise, false.
```
class Solution {
    static boolean searchInSorted(int arr[], int k) {
        // Your code here
        HashSet<Integer> set=new HashSet<>();
        for(int num:arr){
            set.add(num);
        }
        return set.contains(k) ? true : false;
    }
}
"""
Input: arr[] = [1, 2, 3, 4, 6], k = 6
Output: true
Exlpanation: Since, 6 is present in the array at index 4 (0-based indexing), output is true.
Input: arr[] = [1, 2, 4, 5, 6], k = 3
Output: false
Exlpanation: Since, 3 is not present in the array, output is false.
Input: arr[] = [2, 3, 5, 6], k = 1
Output: false
"""
```
