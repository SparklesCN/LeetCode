# LeetCode-1 Two Sum

## Problem ##

Given an array of integers, return indices of the two numbers such that they add up to a specific target.

You may assume that each input would have exactly one solution, and you may not use the same element twice.

**Example:** 

`Given nums = [2, 7, 11, 15], target = 9,`

`Because nums[0] + nums[1] = 2 + 7 = 9, return [0, 1].`

## Strategy ##

Uses a HashMap to record all the key: nums, and value: index

## Code ##

<code>public int[] twoSum(int[] nums, int target) {
        HashMap<Integer, Integer> hashMap= new HashMap<Integer, Integer>();
        int[] res = new int[2];
        for (int i = 0; i < nums.length; i++) {
            int diff = (target - nums[i]);
            if  (hashMap.containsKey(diff)) {
                res[0] = hashMap.get(diff);
                res[1] = i;
                return res;
            }
            hashMap.put(nums[i], i);
        }
        return null;
    }</code>