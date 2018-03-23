<!--more-->


# twoSum


> 题目大意：给定数组和target，判断数组中是否存在索引 i，j：
> -   s[i] + s[j] == target
> -   i != j



> 分析： a + b = target，如何遍历得到 a和b 。

## 解法一：暴力
- 定义 (i, j)， j  > i. i &isin; [0,len(s)), j &isin; [i+1, len(s))
- 暴力，二重循环，时间复杂度O(n<sup>2</sup>) 

```go
func twoSum(nums []int, target int) []int {
    for i := 0; i < len(nums); i++{
        for j := i+1; j < len(nums); j++{
            if a[i] + a[j] == target{
                return []int{i, j}
            }
        }
    }
    return []{-1,-1}
}
```
## 解法二：查找表
在无序数组中查找元素，遍历，解法一就是在[i+1,len(s))中查找是否存在target-s[i],如果该查找时间复杂度优化为O(1),则总时间复杂度为O(n)

- 使用map存 [i+1, len(s)]中 的元素，查找target-s[i]
- 也可以map存 [0,i) 中元素，查询target-s[i]

```golang
func twoSum(nums []int, target int) []int
    m := make(map[int]int)
    for i := 0; i < len(nums); i++{
        // [0, i]
        if v, ok := m[target - nums[i]]; ok{
            return []int{v,i}
        }
        m[nums[i]]=i
    }
    return []int{-1,-1
}
```

## 解法三：排序 游标
考虑 a + b， a < b， b是数组中最大的元素， a是数组中最小的元素
- 若 a + b < target, 则a大一点则可能a+b = target
- 若 a + b > target, 则b小一点则可能a+b = target

可以考虑游标，有序数组上控制[i,j]，使得当前范围内,s[i]最小，s[j]最大
```go
func twoSum(nums []int, target int){
    sort.Ints(nums)
    for i, j := 0, len(nums)-1; i < j; {
        if nums[i] + nums[j] == target{
            return []int{i, j}
        }else if nums[i] + nums[j] < target{
            i++
        }else{
            j--
        }
    }
    return []int{-1, -1}
}
```
时间复杂O(nlogn)

