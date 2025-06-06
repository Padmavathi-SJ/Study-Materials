### Searching problems list solved from geeksforgeeks

### Methods used:
* arr.indexOf(k) --> return index of k
* solution.isSubset(a, b) --> 1st create an object **Solution solution = new Solution();**
* set.contains(value) --> return index of that value
* str.lastIndexOf('1') --> returns the last occurence of that character from the given string
* lastIndexOf method is available for only **string** and **arrayList**
* indexOf(value) --> returns first occurence of that value , and also available for only **strings** and **arrayList**

   
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

### 6. Searching a number

* Given an integer k and array arr. Your task is to return the position of the first occurrence of k in the given array and if element k is not present in the array then return -1.

* Note: 1-based indexing is followed here.
```
class Solution {
    public int search(int k, ArrayList<Integer> arr) {
        // code here
        int result=arr.indexOf(k);
        return result!=-1 ? result+1 : -1;
    }
}
"""
Input: k = 16 , arr = [9, 7, 16, 16, 4]
Output: 3
Explanation: The value 16 is found in the given array at positions 3 and 4, with position 3 being the first occurrence.
Input: k=98 , arr = [1, 22, 57, 47, 34, 18, 66]
Output: -1
Explanation: k = 98 isn't found in the given array.
"""
```

### 7. Last index of One
* Given a string s consisting of only '0's and '1's,  find the last index of the '1' present.

 * Note: If '1' is not present, return "-1"
```
class Solution {
    public int lastIndex(String s) {
        int index=s.lastIndexOf('1');
        return index!=-1 ? index : -1;
    }
}
"""
Input: s = 00001
Output: 4
Explanation: Last index of  1 in given string is 4.
Input: s = 0
Output: -1
Explanation: Since, 1 is not present, so output is -1.
"""
```

### 8. Elements in the Range
* Given an array arr[] containing positive elements. A and B are two numbers defining a range. The task is to check if the array contains all elements in the given range (inclusive).

* Note: If the array contains all elements in the given range return true otherwise return false.
```
class Solution {
    boolean check_elements(int arr[], int n, int A, int B) {
        HashSet<Integer> set=new HashSet<>();
        for(int num : arr){
            set.add(num);
        }
        for(int i=A; i<=B; i++){
            if(!set.contains(i)){
                return false;
            }
        }
        return true;
    }
}
"""
Input: n = 7, A = 2, B = 5, arr[] =  {1, 4, 5, 2, 7, 8, 3}
Output: True
Explanation: It has all elements between range 2-5 i.e 2,3,4,5.
Input: n = 7, A = 2, B = 6, arr[] = {1, 4, 5, 2, 7, 8, 3}
Output: False
Explanation: The array does not contain 6 hence it do not contains all elements in the range 2-6, the output is No.
"""
```

### 9. First and last occurrences of x

* Given an element x and a sorted array, arr[], find the indices of first and last occurrences of the x's in the array.

* Note: If the number x is not found in the array, return an array containing -1 only.
```
class Solution {
    public ArrayList<Integer> firstAndLast(int x, int arr[]) {
        // Code here
        ArrayList<Integer> l=new ArrayList<>();
        int first=-1;
        int last=-1;
        for(int i=0; i<arr.length; i++){
            if(arr[i] == x){
                if(first==-1){
                    first=i;
                }
                last=i;
            }
        }
        if(first!=-1) {
            l.add(first);
            l.add(last);
        }
        else{
            l.add(-1);
        }
        return l;
    }
}
"""
Input: x = 3, arr[] = [1, 3, 3, 4]
Output: [1, 2]
Explanation: The first occurrence of X = 3 is at index = 1 and the last at index = 2.
Input: x = 5, arr[] = [1, 2, 3, 4]
Output: [-1]
Explanation: 5 is not present, so the answer is -1.
"""
```

### 10. Doubling the value

* Given an array and an integer B, traverse the array (from the beginning) and if the element in array is B, double B and continue traversal. Find the value of B after the complete traversal.
```
class Solution
{
    long solve(int n, long A[], long b)
    {
        for(int i=0; i<n; i++){
            if(A[i] == b){
                b = 2*b;
            }
        }
        return b;
    }
}
"""
Input:
N = 5, B = 2
arr[] = {1 2 3 4 8}
Output: 16
Explanation: B is initially 2. We get 2 at
the 1st index, hence B becomes 4. 
Next, we get B at the 3rd index, hence B 
becomes 8. Next, we get B at 4-th index, 
hence B becomes 16.
Example 1:

Input:
N = 5, B = 3
arr[] = {1 2 3 4 8}
Output: 6
Explanation: B is initially 3. We get 3 at
the 2nd index, hence B becomes 6.
"""
```

### 11. Count zeros in a sorted matrix

*Given a N X N binary Square Matrix where each row and column of the matrix is sorted in ascending order. Find the total number of zeros present in the matrix.
```
class GfG
{
    /*you are required to complete this method*/
    int countZeros(int A[][], int N)
    {
        int zeros_count=0;
        for(int i=0; i<N; i++){
            for(int j=0; j<N; j++){
                if(A[i][j] == 0){
                    zeros_count++;
                }
            }
        }
        return zeros_count;
    }
}
"""
Input:
N = 3
A = {{0, 0, 0},
     {0, 0, 1},
     {0, 1, 1}}
Output: 6
Explanation: 
The first, second and third row contains 3, 2 and 1
zeroes respectively.
Example 2:

Input:
N = 2
A = {{1, 1},
     {1, 1}}
Output: 0
Explanation:
There are no zeroes in any of the rows.
"""
```

### 12. Remove consonants from a string

* Given a string S, remove all consonants and print the modified string that contains vowels only.
```
class Solution
{
    public String removeConsonants(String s)
    {
        StringBuilder sb=new StringBuilder();
        for(int i=0; i<s.length(); i++){
            if(s.charAt(i) == 'a' || s.charAt(i) == 'e' || s.charAt(i) == 'i'
               || s.charAt(i) == 'o' || s.charAt(i) == 'u' ||
               s.charAt(i) == 'A' || s.charAt(i) == 'E' || s.charAt(i) == 'I'
               || s.charAt(i) == 'O' || s.charAt(i) == 'U'){
                   sb.append(s.charAt(i));
               }
        }
        return sb.length() == 0 ? "No Vowel" : sb.toString();
    }
    
}
"""
Input
S = "abEkipo"
Output
aEio
Explanation : a, E, i, o are only vowels in the string.
Example 2:

Input
S = "rrty"
Output
No Vowel
Explanation: There are no vowels.
"""
```

