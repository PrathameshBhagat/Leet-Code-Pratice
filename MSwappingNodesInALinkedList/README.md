## [(Looping and its end point correction was revised)]()

<img src="https://github.com/PrathameshBhagat/LeetCodePratice/assets/90595097/da477762-91c4-458e-9164-d3472e181628" style="height:45vh;width:80vw">

```java
/*Return the head of the linked list after swapping the values
kth node from the beginning and the kth node from the end needs to be swapped
(first node(head) is indexed 1).*/
class Solution {
    public ListNode swapNodes(ListNode head, int k) {
        ListNode s,e,p;s=head;
        for(int i=1;i<k;i++)
        s=s.next;
        e=head;p=s;
        while(p.next!=null){
            e=e.next;
            p=p.next;}
        
        int tem=s.val;
        s.val=e.val;
        e.val=tem;
        return head;
    }
}
```
