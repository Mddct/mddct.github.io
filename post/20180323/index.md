<!--more-->



# 思路

当前构造的节点 node.Val = l1.Val + l2.Val + carry :

- 如果 carry `= 0 && l| =` nil && l2 == nil, 则不需要构造节点，已经算到了最后一位
- 表示当前节点：prev.Next (使用dummy head; 第一次也有了前驱节点）

时间复杂度: l1长度m，l2长度n。 O(m+n)=O(max(m,n))

```go
/**
 * Definition for singly-linked list.
 * type ListNode struct {
 *     Val int
 *     Next *ListNode
 * }
 */
func addTwoNumbers(l1 *ListNode, l2 *ListNode) *ListNode {
	
  carry := 0

  // dummy head
  var head  ListNode
  p := &head
  for {
		
    if carry == 0 && l1 == nil && l2 == nil{
      break
    }
		
    var ns int
    ns += carry
    if l1 != nil{
      ns += l1.Val
      l1 = l1.Next
    }
    if l2 != nil{
      ns += l2.Val
      l2 = l2.Next
    }
		
    if ns >= 10{
      ns -= 10
      carry = 1
    }else{
      carry = 0
    }
		
    p.Next = &ListNode{
      Val: ns,
    }
    p = p.Next
		
  }
  return head.Next
}
```
