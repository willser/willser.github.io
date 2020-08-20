---
title: two-sum
date: 2020-08-20 22:18:45
tags: leetcode
---
## 问题
Given an array of integers, return indices of the two numbers such that they add up to a specific target.

You may assume that each input would have exactly one solution, and you may not use the same element twice.

Example:

Given nums = [2, 7, 11, 15], target = 9,

Because nums[0] + nums[1] = 2 + 7 = 9,
return [0, 1].


## 解决
````java
class Solution {
    public int[] twoSum(int[] nums, int target) {
        int left = 0;
        int temp = 1;
        
        while(true){
            
            if(nums[left] + nums[temp] == target){
                return new int[]{left,temp};
            }
            
            temp++;
                
            if(temp == nums.length){
                left ++;
                temp = left + 1;
            }
        }
    }
}

````
## 后续
之所以速度不如hashmap大法是因为hashmap大法仅用循环一次数组。