### Methods:
*  __Arrays.stream(arr)__ --> to convert the array to __stream of integers__ to allow perform operations like filter.
* __Arrays.stream(arr).filter(i -> i<0).toArray()__; --> to filter negative elements from an array and put into our newly created array(toArray());
* In collections to sort an array --> __Collections.sort(arr)__
* In collections to find array length --> __arr.size()__
* In collections convert from Ingeter type to int type --> __Arrays.stream(arr).mapToInt(Integer::intValue).toArray();__

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

### 11.The problem of identical arrays

* Check whether given two arrays arr1[], arr2[] are identical or not. Two arrays are called identical arrays if they contain the same element with the same count, regardless of the order of elements.
```
class Solution {
    public boolean isIdentical(List<Integer> arr1, List<Integer> arr2) {
        if(arr1.size() != arr2.size()){
            return false;
        }
        List<Integer> newArr1=new ArrayList<>(arr1);
        List<Integer> newArr2=new ArrayList<>(arr2);
        Collections.sort(newArr1);
        Collections.sort(newArr2);
        boolean res=newArr1.equals(newArr2);
        return res;
    }
}
"""
Input: arr1[] = [1, 2, 3, 4, 5], arr2[] = [3, 4, 1, 2, 5]
Output: true
"""
```

### 12. Mega Sale

* Mr. Geek is a greedy seller. He has a stock of some laptops comprising both useful and useless laptops. Now, he wants to organize a sale to clear his stock of useless laptops. The prices of laptops are arri each consisting of positive and negative integers (-ve denoting useless laptops). In a day, he can sell almost m laptops. Mr. Geek, a greedy seller, wants to earn maximum profit from this sale and sell useless laptops. So, help him maximize his profit by selling useless laptops.
* 
```
class Solution {
    public int maxProfit(int m, int[] arr) {
        int[] ul=Arrays.stream(arr).filter(i -> i < 0).toArray();
        Arrays.sort(ul);
        int profit=0;
        for(int i=0; i<Math.min(m, ul.length); i++){
            profit+=-ul[i];
        }
        return profit;
    }
}
"""
Input: m=3, arr[] = [-6, 0, 35, 4]
Output: 6
Explanation: Geek sells the laptops with price -6 and earns Rs. 6 as profit.
"""
```
* here, Arrays.stream(arr) --> to convert the array to __stream of integers__ to allow perform operations like filter.
* Arrays.stream(arr).filter(i -> i<0).toArray(); --> to filter negative elements from an array and put into our newly created array(toArray());

### 13. Triplet Family
* Given an array arr of integers. First sort the array then find whether three numbers are such that the sum of two elements equals the third element.
  
```
class Solution {
    public boolean findTriplet(int[] arr) {
        Arrays.sort(arr);
        for(int i=arr.length-1; i>=0; i--){
            if(hasPairWithSum(arr, i)){
                return true;
            }
        }
        return false;
    }
    private boolean hasPairWithSum(int[] arr, int index){
        int target=arr[index];
        int left=0;
        int right=index-1;
        while(left < right){
            int sum=arr[left]+arr[right];
            if(sum == target){
                return true;
            }
            else if(sum < target){
                left++;
            }
            else{
                right--;
            }
        }
        return false;
    }
}
"""
Input: arr[] = [1, 2, 3, 4, 5]
Output: true
"""
```

### 14. Sorting Employees based on their salaries, if same salary, sort their names by alphabetical order
```
class Solution {
    public List<String> sortRecords(List<String> employee, List<Integer> salary) {
        List<Pair> records=new ArrayList<>();
        for(int i=0; i<employee.size(); i++){
            records.add(new Pair(salary.get(i), employee.get(i)));
        }
        Collections.sort(records, (a, b) -> {
            if(a.salary == b.salary){
                return a.name.compareTo(b.name);
            }
            return Integer.compare(a.salary, b.salary);
        });
        
        List<String> sortedEmployees = new ArrayList<>();
        for(Pair record: records){
            sortedEmployees.add(record.name);
        }
        return sortedEmployees;
    }
    static class Pair{
        int salary;
        String name;
        Pair(int salary, String name){
            this.salary = salary;
            this.name = name;
        }
    }
}
"""
Input: employee = ["chef", "geek"], salary = [100, 50]
Output: ["geek", "chef"]
Explanation: "geek" has a lower salary (50) than "chef" (100), so "geek" comes first.
"""
```

### 15. Merge and sort
* Given two arrays arr1 and arr2, return the merged array in ascending order containing unique elements.
  
```
class Solution {
    public int[] mergeNsort(int[] arr, int[] brr) {
        Set<Integer> set=new HashSet<>();
        for(int num : arr){
            set.add(num);
        }
        for(int num : brr){
            set.add(num);
        }
        Integer[] temp=set.toArray(new Integer[0]);
        int[] res=Arrays.stream(temp).mapToInt(Integer::intValue).toArray();
        Arrays.sort(res);
        return res;
    }
}
"""
Input: arr1[] = [11, 1, 8], arr2[] = [10, 11]
Output: [1, 8, 10, 11]
Explanation: The ouput array after merging both the arrays and removing duplicates is [1 8, 10, 11]
"""
```

