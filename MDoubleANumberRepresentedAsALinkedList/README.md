## [Very Important Problem has 3 good approaches (Ternary Operator perfect use)]()
<img src="https://github.com/PrathameshBhagat/LeetCodePratice/assets/90595097/049631ad-fa09-4c19-8a15-e9311fabcd3c" style="height:45vh;width:80vw">

### 1st Approach
```java
/*
You are given the head of a non-empty linked list representing a non-negative integer 
Return the head of the linked list after doubling it.(no leading zeroes in list)*/
class Solution {
    public ListNode doubleIt(ListNode head) {
        return f(head)==1? new ListNode(1, head): head;}
    private int f(ListNode n) {
        return n==null? 0: ((n.val=n.val*2+f(n.next))-(n.val%=10))/10;}
}
```
### 2nd Approach / Our Approach 
```java

class Solution {
    public ListNode doubleIt(ListNode h) {
        int carry=0,a=0;
        ListNode p=rev(h),q=p,r=null;
        while(p!=null){
            a=p.val*2;     
            p.val = a % 10 + carry;
            r=p;  p=p.next;    carry=a/10;
        }  
        if(carry!=0){
            r.next=new ListNode(carry);
            r=r.next;}
        return rev(q);
    }
    
    ListNode rev(ListNode h){
        ListNode p=null,n=null,c=h;
        while(c!=null){
            n=c.next;
            c.next=p;
            p=c;
            c=n;
        } 
        return p; 
    }
}
```
### 3rd (Fastest) Approach  
```java

class Solution {
     public ListNode doubleIt(ListNode head) {
        if (head.val > 4) {
            head = new ListNode(0, head);
        }
        ListNode temp = head;
        while (temp != null) {
            temp.val = (temp.val * 2) % 10;
            if (temp.next != null && temp.next.val > 4) {
                temp.val++;
            }
            temp = temp.next;
        }
        return head;
    }
}
```
