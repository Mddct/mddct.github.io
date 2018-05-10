<!--more-->

- The string "PAYPALISHIRING" is written in a zigzag pattern on a given number of rows like this: (you may want to display this pattern in a fixed font for better legibility)
```

P   A   H   N
A P L S I I G
Y   I   R
```

And then read line by line: "PAHNAPLSIIGYIR"

```go
func convert(s string, numRows int) string {
    if numRows == 1 || numRows >= len(s){
        return s
    }
    ret := ""
    first, second := 2 * numRows-2, 0
    for cr := 0; cr < numRows; cr ++{
        ret += fmt.Sprintf("%c", s[cr])
        for i := cr+first;  i < len(s) ; {
            if first != 0{
                ret += fmt.Sprintf("%c", s[i])   
            }
            if second != 0{
               i += second
                 if i >= len(s){
                  break
            }
            ret += fmt.Sprintf("%c", s[i]) 
            }


            // next 
            i += first
        } 
        first -= 2
        second += 2
        //fmt.Println()
    }
    return ret
}
/*
PAYPALISHIRING
0     6       12       18   // 6 0
1   5 7    11 13    17 19   // 4 2
2 4   8 10    14 16         // 2 4
3     9       15            // 0 6

0   4   8     12          // 4 0
1 3 5 7 9  11 13          // 2 2 
2   6   10                // 0 4 


0     8               // 8 0
1   7 9        15        // 6 2
2  6  10    14             // 4 4 
3 5   11 13
4     12 
*/


// 复仇者联盟3真好看
```
