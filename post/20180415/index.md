<!--more-->


> Given a string s, find the longest palindromic substring in s. You may assume that the maximum length of s is 1000. 
# Table of Contents


-   暴力：[i, j] ，遍历i， j O(n<sup>2</sup>), 判断[i,j]回文O(n<sup>2</sup>), 总时间复杂度O(n<sup>3</sup>)
-   优化一： 对于第i个元素，考虑以i为中心的元素是否为回文（[l,i] [i, r] ）；或者[l,i] [i+1, r] 回文。时间复杂度O(n<sup>2</sup>)
```go
func maxPalindrome(s string, left, right int) (int, int) {
        for left >= 0 && right < len(s) {
                if s[left] == s[right] {
                        left--
                        right++
                }else{
                        break
                }
        }
        // [left, right]
        return left + 1, right - 1
}
func longestPalindrome(s string) string {
        l, r := 0, 0
        for i := 0; i < len(s); i++ {
                // [0, s)
                nl, nr := maxPalindrome(s, i, i)
                if nr-nl > r-l {
                        l = nl
                        r = nr
                }
    nl, nr = maxPalindrome(s, i, i+1)
    if nr-nl > r-l {
                        l = nl
                        r = nr
    }
        }
        return s[l : r+1]
}


```


-   优化二 [Manacher’s algorithm](https://articles.leetcode.com/longest-palindromic-substring-part-ii/)
```go


func preProcess(s string) string {
	if len(s) == 0 {
		return "^$"
	}
	ret := "^"
	for i := 0; i < len(s); i++ {
		ret += "#" + fmt.Sprintf("%c", s[i])
	}
	ret += "#$"
	return ret

}
func longestPalindrome(s string) string {
	T := preProcess(s)
	p := make([]int, len(T))
	C, r := 0, 0
	for i := 1; i < len(T)-1; i++ {
		iMirror := 2*C - i
		if r-i > 0 {
			p[i] = p[iMirror]
			if p[i] > r-i {
				p[i] = r - i
			}
		}
		// else p[i] = 0
		for T[i+p[i]+1] == T[i-p[i]-1] {
			p[i]++
		}

		if i+p[i] > r {
			r = i + p[i]
			C = i
		}
	}
	maxLen := 0
	curIndex := 0
	for i := 0; i < len(p); i++ {
		if maxLen < p[i] {
			maxLen = p[i]
			curIndex = i
		}
	}
    start := (curIndex - 1- maxLen) /2
    return s[start:start+maxLen]

}

```
-   动态规划 时间复杂度O(n<sup>2</sup>)

dp[i][j] = dp[i+1][j-1] `= 1 && s[i] =` s[j]
遍历整个二维数组，找出max（j-i）and dp[i][j] == 1
```go
```


