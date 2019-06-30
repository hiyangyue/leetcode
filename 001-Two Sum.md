# 两数之和
### 题目地址
https://leetcode-cn.com/problems/two-sum/
### 题目描述
Given an array of integers, return indices of the two numbers such that they add up to a specific target.

You may assume that each input would have exactly one solution, and you may not use the same element twice.

> Example:
> Given nums = [2, 7, 11, 15], target = 9,
> Because nums[0] + nums[1] = 2 + 7 = 9,
> return [0, 1].

### 思路
* 要找到数组nums中想要两个整数，实际上就是查找在i位置时候，nums中是否存在一个值等于target - nums[i]。
* 要找到这个期望的值，等同于检测数组中是否存在指定的元素，如果存在就找到对应的索引
* 优化点：插入的同时回头检查是否已经存在对应的目标元素

### 代码

```
 public int[] twoSum(int[] nums, int target) {        
        if(nums == null) return null;
        Map<Integer, Integer> map = new HashMap<>();
        for(int i = 0 ; i < nums.length ; i ++) {
            int needValue = target - nums[i];
            if(map.containsKey(needValue)) {
                return new int[] {map.get(needValue), i};
            }
            map.put(nums[i], i);
        }
        return null;
    }
```
