[![Review Assignment Due Date](https://classroom.github.com/assets/deadline-readme-button-22041afd0340ce965d47ae6ef1cefeee28c7c493a6346c4f15d667ab976d596c.svg)](https://classroom.github.com/a/AqLe5c87)
# Climbing Stairs
```
class Solution {
public:
    int climbStairs(int n) {
        if (n == 1) return 1;
        if (n == 2) return 2;
        
        int prev1 = 2, prev2 = 1, curr;
        
        for (int i = 3; i <= n; i++) {
            curr = prev1 + prev2;
            prev2 = prev1;
            prev1 = curr;
        }
        
        return curr;
    }
};

```
# Output
![image](https://github.com/user-attachments/assets/f20aaacc-8157-4574-9af1-a71115d5f9b3)


# Maximum Subarrays
```
class Solution {
    public static int maxSubArray(int[] nums) {
        int maxSum = nums[0]; // Initialize maxSum with first element
        int currSum = 0;

        for (int num : nums) {
            currSum += num; // Add current element to the subarray sum
            maxSum = Math.max(maxSum, currSum); // Update max sum
            if (currSum < 0) currSum = 0; // Reset if sum becomes negative
        }
        
        return maxSum;
    }

    public static void main(String[] args) {
        int[] nums = {-2, 1, -3, 4, -1, 2, 1, -5, 4};
        System.out.println(maxSubArray(nums)); // Output: 6
    }
}

```
# Output
![image](https://github.com/user-attachments/assets/22afc24d-4883-4b54-bc25-3b918ab1fe3a)


# House Robber
```
class Solution {
public:
    int rob(vector<int>& nums) {
        int prev1 = 0, prev2 = 0; // prev1: dp[i-1], prev2: dp[i-2]
        
        for (int num : nums) {
            int curr = max(prev1, prev2 + num); // Choose max of skipping or robbing this house
            prev2 = prev1;
            prev1 = curr;
        }
        
        return prev1;
    }
};

```
# Output
![image](https://github.com/user-attachments/assets/5a0323a5-e530-4ad4-9064-aa1035cbe3e8)

