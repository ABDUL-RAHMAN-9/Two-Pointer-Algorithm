# Two-Pointer-Algorithm

Two pointers is really an easy and effective technique that is typically used for Two Sum in Sorted Arrays, Closest Two Sum, Three Sum, Four Sum, Trapping Rain Water and many other popular interview questions. Given a sorted array arr (sorted in ascending order) and a target, find if there exists any pair of elements (arr[i], arr[j]) such that their sum is equal to the target.

## Illustration :

```
Input: arr[] = {10, 20, 35, 50}, target =70
Output:  Yes
Explanation : There is a pair (20, 50) with given target.


Input: arr[] = {10, 20, 30}, target =70
Output :  No
Explanation : There is no pair with sum 70


Input: arr[] = {-8, 1, 4, 6, 10, 45], target = 16
Output: Yes
Explanation : There is a pair (6, 10) with given target
```

## Two-Pointer Technique – O(n) time and O(1) space
The idea of this technique is to begin with two corners of the given array. We use two index variables left and right to traverse from both corners.

Initialize: left = 0, right = n – 1
Run a loop while left < right, do the following inside the loop

Compute current sum, sum = arr[left] + arr[right]
If the sum equals the target, we’ve found the pair.
If the sum is less than the target, move the left pointer to the right to increase the sum.
If the sum is greater than the target, move the right pointer to the left to decrease the sum.

# Code:

````
// CPP program demonstrate working of the two
// pointer technique
#include <bits/stdc++.h>
using namespace std;

bool twoSum(vector<int> &arr, int target){

    int left = 0, right = arr.size() - 1;
    while (left < right){
        int sum = arr[left] + arr[right];

        if (sum == target)
            return true;
        
        // Move toward a higher sum
        else if (sum < target)
            left++; 
      
        // Move toward a lower sum
        else
            right--; 
    }
  
    // If no pair found
    return false;
}

int main(){
    vector<int> arr = {-3, -1, 0, 1, 2};
    int target = -2;
    if (twoSum(arr, target))
        cout << "true";
    else
        cout << "false";

    return 0;
}

Output: true

```

Time Complexity: O(n)
<br>
Auxiliary Space: O(1)
