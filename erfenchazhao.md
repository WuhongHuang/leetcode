# 有序数组二分查找目标值&找不到则返回需要插入下标
##问题描述：给定一个排序数组和一个目标值，在数组中找到目标值，并返回其索引。如果目标值不存在于数组中，返回它将会被按顺序插入的位置。

请必须使用时间复杂度为 O(log n) 的算法

来源：力扣（LeetCode）

链接：https://leetcode-cn.com/problems/search-insert-position

著作权归领扣网络所有。商业转载请联系官方授权，非商业转载请注明出处。
---
##python算法求解思路

利用二分查找，设置左右界限，不断逼近目标值。若未找到则，返回l。
---

class Solution:
  def searChInsert(self, nums:List[int],target:int) -> int:
  n = len(nums)
  l,r = 0, n-1
  while l<= r:
    mid = l + (r-l)//2
    if nums[mid] < target:
      l = mid + 1
    elif nums[mid] > target:
      r = mid - 1
    else:
      return mid
   return l
