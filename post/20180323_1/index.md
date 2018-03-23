<!--more-->


# 整体思路

-   当前滑动窗口保持[i,j)  之间不重复
-   当s[j]依旧不重复，则j++
-   当s[j]发生重复，需要变动i。使得新的滑动窗口内不重复。


# 如何判断重复

- set // go中用map[byte]struct{} 模拟set
- 在保持循环不变式中，i右滑时，注意删除“划过去的元素”。（因为set保存的是[i,j)之间的不重复元素，也是个不变式）

note：循环不变式，有助于写出正确的算法，包括边界。

时间复杂度O(n),注意循环不变式[i,j) 时刻保持当前滑动窗口不重复。

```go
func lengthOfLongestSubstring(s string) int {
  //[)
  i, j := 0, 0
  cl := 0
  ml := 0 
  // 模拟set
  set := make(map[byte]struct{})
  for j < len(s){
    if _, ok := set[s[j]]; !ok{
      set[s[j]] =  struct{}{}
      j++
      cl = j-i
      if cl > ml{
        ml = cl
      }
    }else{
      if s[i] != s[j]{
        delete(set, s[i])
      }else{
        j++
      }
      i++
    }
		
  }
  return ml
}


```
