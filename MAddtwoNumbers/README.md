# Needs tobe updated
## [(topics revised)](#java-data-types)

<img src="https://github.com/PrathameshBhagat/LeetCodePratice/assets/90595097/268fd4c4-5335-42b4-bbff-9b708be44081" style="height:45vh;width:80vw">
```java
import java.math.*;
class Solution {
    public ListNode addTwoNumbers(ListNode l1, ListNode l2) {
        
        l1=rev(l1);l2=rev(l2);
        BigInteger a=num(l1),b=num(l2);
        return rev(Link(a.add(b)));
    }
    ListNode rev(ListNode l){
        ListNode  L=l,T=null,end=null;//T is temp end nxt
        while(L!=null){
            end=L.next;L.next=T;
            T=L;L=end;}   
        return T;
    }
    BigInteger num(ListNode l){
        String s="";ListNode tem=l;
        while(tem!=null) {
            s=s+String.valueOf(tem.val);
            tem=tem.next;
        }
        return new BigInteger(s);
    }
    ListNode Link(BigInteger l){
        String s=String.valueOf(l);
        ListNode head=null,T=null,tail=null;
            for(int i=0;i<s.length();i++)
            {
                T=new ListNode(Integer.parseInt(s.charAt(i)+""));
                if(i==0){ head=T;tail=T;continue;}
                tail.next=T;
                tail=T;
            }
        return head;
    }    
}

```
