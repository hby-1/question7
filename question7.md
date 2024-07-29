# 数组中不等三元组的数目

给你一个下标从 0 开始的正整数数组 `nums` 。请你找出并统计满足下述条件的三元组 `(i, j, k)` 的数目：

- `0 <= i < j < k < nums.length`
- `nums[i]`、`nums[j]` 和 `nums[k]` **两两不同** 。
- 换句话说：`nums[i] != nums[j]` 且 `nums[i] != nums[k]` 且 `nums[j] != nums[k]`

## 示例 ：

>### 输入：
>nums = [4,4,2,4,3]
>### 输出：
>3
>### 解释:
>下面列出的三元组 (0, 2, 4)、(1, 2, 4) 和 (1, 2, 4) 都满足题目要求。

## 代码 ：

1.

    public class Solution {
        public int UnequalTriplets(int[] nums) {
            int triplets = 0;
            int n = nums.Length;
            for (int i = 0; i < n; i++) {
                for (int j = i + 1; j < n; j++) {
                    if (nums[j] == nums[i]) {
                        continue;
                    }
                    for (int k = j + 1; k < n; k++) {
                        if (nums[k] != nums[i] && nums[k] != nums[j]) {
                            triplets++;
                        }
                    }
                }
            }
            return triplets;
        }
    }

2.

    public class Solution {
        public int UnequalTriplets(int[] nums) {
            int num=0;
            for(int i=0;i<nums.Length;i++){
                for(int n=i+1;n<nums.Length;n++){
                    for(int m=n+1;m<nums.Length;m++){
                        if(nums[i]!=nums[n] && nums[i]!=nums[m] && nums[n]!=nums[m]){
                            num++;
                        }
                    }
                }
            }
            return num;
        }
    }

