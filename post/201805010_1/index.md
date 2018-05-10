<!--more-->

> Given a 32-bit signed integer, reverse digits of an integer.

题目简单，注意溢出处理，同时看golang minint32 maxint32等如何使用

```go
func reverse(x int) int {
    sign := 1
    if x < 0{
        sign = -1
        x = -x
    }
    ret := int64(0)
    for x != 0{
        ret = ret *10 + int64(x % 10)
        x /= 10
    }
    ret *= int64(sign)
    if ret > math.MaxInt32 || ret < math.MinInt32{
        return 0
    }
    return int(ret)
}

// 强烈推荐看复仇者联盟3
```
