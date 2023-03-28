# Dynanic Solutions Innovator

**Task #1**
## Missing Number (LEETCODE 268)
> Sample Input Output

Given an array nums containing n distinct numbers in the range [0, n], 
return the only number in the range that is missing from the array.
```
Input: nums = [9,6,4,2,3,5,7,0,1]
Output: 8
Explanation: n = 9 since there are 9 numbers, so all numbers are in the range [0,9]. 
8 is the missing number in the range since it does not appear in nums.

```
> Math Solution
```
// Using Math
class Solution {
public:
    int missingNumber(vector<int>& nums) {
    int numSum=0,n=nums.size();
    for(int i=0; i<n; i++)
        numSum+=nums[i];
        
    int sum=(n*(n+1))/2;
    
    return sum-numSum;
    }
};
```
> XOR Solution
```
class Solution {
public:
    int missingNumber(vector<int>& nums) {
    int xr=nums.size();
    
    for(int i=0; i<nums.size(); i++)
    {
        xr= xr ^ nums[i]; // we add nums in XOR
        xr= xr ^ i;       // to cancel the number to XOR, we add i, where all number included.
                          // like sum in above solution 
    }
    return xr;
    }
};
```
> Binary Search
```
class Solution {
public:
    int missingNumber(vector<int>& nums) {
    sort(nums.begin(), nums.end());
    int low=0, high=nums.size()-1;
    
    while(low<=high)
    {
        int mid = low+(high-low)/2;

        if(nums[mid] > mid) high= mid-1;

        else low = mid+1;
    }

    return low;
    }
};
```
**Task #2**
## 242. Valid Anagram
Given two strings s and t, return true if t is an anagram of s, and false otherwise.

An Anagram is a word or phrase formed by rearranging the letters of a different word or phrase, 
typically using all the original letters exactly once.
> Sample Input Output
```
Input: s = "anagram", t = "nagaram"
Output: true
```
> My Code - Hash table
```
class Solution {
public:
    bool isAnagram(string s, string t) {
        int a = s.size();
        int b = t.size();
        if (a != b) return false;

        vector<int> arr(256, 0);

        for (int i = 0; i < a; i++) {
            arr[s[i]]++;
        }

        for (int j = 0; j < b; j++) {
            arr[t[j]]--;
            if (arr[t[j]] < 0) return false;
        }

        return true;
    }
};
```
> Using Sorting function
```
class Solution {
public:
    bool isAnagram(string s, string t) {
        sort(s.begin(),s.end());
        sort(t.begin(),t.end());
        
        if(s==t)
            return true;
        else
            return false;
    }
};
```
**Task #1**
## 
> Sample Input Output
```


```
> My Code
```

```
>Best Code
```

```
