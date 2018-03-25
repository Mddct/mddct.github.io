> 题目
There are two sorted arrays nums1 and nums2 of size m and n respectively.
<!--more-->

Find the median of the two sorted arrays. The overall run time complexity should be O(log (m+n)).

首先不考虑时间复杂度：

-   中位数可能是一个，也可能是两个数求平均值
-   找到第K个数，可以使用归并思路，归并的过程数第几个数。时间复杂度O(n)
-   如果将两个数组合并为一个，转换为在数组中寻找中位数，可以使用快排或随机partition快排。平均时间复杂度O(n+logn)=O(n)

# 归并
```go
func findMedianSortedArrays(nums1 []int, nums2 []int) float64 {
  l := len(nums1) + len(nums2)
  if l&1 == 0 { // l is even
    return (float64(findKthSortedArrays(nums1, nums2, l/2)) +
      float64(findKthSortedArrays(nums1, nums2, l/2+1))) / 2
  }
  return func findMedianSortedArrays(nums1 []int, nums2 []int) float64 {
    l := len(float64(findKthSortedArrays(nums1, nums2, l/2+1))
}
func findKthSortedArrays(nums1, nums2 []int, k int) int {
  l := len(nums1) + len(nums2)
  if k > l {
    panic("wrong k")
  }
  n := 0
  i, j := 0, 0
  ret := 0
  for ; n < k; n++ {
    if i == len(nums1) {
      return nums2[k-(i+j)+j-1]
    } else if j == len(nums2) {
      return nums1[k-(i+j)+i-1]
    } else if nums1[i] > nums2[j] {
      j++
      ret = nums2[j-1]
    } else {
      i++
      ret = nums1[i-1]
    }
  }
  return ret
}

```
# 二分
题目提示log级别，考虑“二分”，l = len(nums1) + len(nums2), p1 = \frac{l}{2}, p2 =l-p1 

-   l 可能为奇数 偶数， 则实现发现第k大的数：findKthSortedArrays
-   nums1[p1-1] <= nums1[p2-1] 则可以考虑扔掉p1之前的元素，findKthSortedArrays（nums1[p1:], nums2, k-p1）
-   nums1[p1-1] >= nums2[p2-1] 则可以考虑扔掉p2之前的元素，findKthSortedArrays(num1, nums2[p2:], k-p2)
-   当扔掉k-1个元素时候，就可以知道第k个元素在哪

需要注意数组下标的合法性。
```go
func findMedianSortedArrays(nums1 []int, nums2 []int) float64 {
  l := len(nums1) + len(nums2)
  if l&1 == 0 { // l is even
    return (float64(findKthSortedArrays(nums1, nums2, l/2)) +
      float64(findKthSortedArrays(nums1, nums2, l/2+1))) / 2
  }
  return float64(findKthSortedArrays(nums1, nums2, l/2+1))

}
func findKthSortedArrays(nums1, nums2 []int, k int) int {
  l1 := len(nums1)
  l2 := len(nums2)
  if l1 > l2 { // assume l1 < l2
    return findKthSortedArrays(nums2, nums1, k)
  }
  if l1 == 0 {
    return nums2[k-1]
  }
  if k == 1 {
    if nums1[0] > nums2[0] {
      return nums2[0]
    }
    return nums1[0]
  }

  l := k
  left := l / 2
  if l/2 > l1 {
    left = l1
  }

  right := l - left
  if nums1[left-1] <= nums2[right-1] {
    return findKthSortedArrays(nums1[left:], nums2, k-left)
  } else {
    return findKthSortedArrays(nums1, nums2[right:], k-right)
  }
}

```
