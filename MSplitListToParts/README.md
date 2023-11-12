## [Topic revised and other approach](#topics)

<img src="https://github.com/PrathameshBhagat/LeetCodePratice/assets/90595097/fdc7a13c-c860-474f-8c0b-cd126619cdca" style="height:45vh;width:80vw"></img>
# Our Approach 
```java
/*Split LinkedList To Parts in required manner*/
class Solution {
    public ListNode[] splitListToParts(ListNode head, int k) {
        ListNode[] result = new ListNode[k];
        ListNode p=head;int count=0;
        while(p!=null)p=(++count<0)?p:p.next;
        int i=0;
        if(count<=k){ 
            while(head!=null){
                result[i++]=head;
                ListNode t=head;
                head=head.next;
                t.next= null;
            }
        }else {
             int m=count%k;
            for(i=0;i<k;++i){
                result[i]=head;
                int o=count/k-1;
                if(i<m)o++;
                for(int j=0;j<o;j++)
                    head=head.next;
                ListNode t=head;
                head=head.next;
                t.next=null;
            }
        }       
      return result;
    }
}
```  
> **This line creates a node, moves next and then moves pointer**  
> `write = write.next = new ListNode(cur.val);`  
# Other Approach 
```java
class Solution {
    public ListNode[] splitListToParts(ListNode head, int k) {
        ListNode cur = head; int N = 0;
        while (cur != null) {cur = cur.next;N++;}
        int width = N / k, rem = N % k;
        ListNode[] ans = new ListNode[k];
        cur = head;
        for (int i = 0; i < k; ++i) {
            ListNode head1 = new ListNode(0), write = head1;
            for (int j = 0; j < width + (i < rem ? 1 : 0); ++j) {
                write = write.next = new ListNode(cur.val);
                if (cur != null) cur = cur.next;
            }
            ans[i] = head1.next;
        }
        return ans; 
    }
}
```
# GCD And LCM
12 => _**2**_ x _**2**_ x 3 ||  
8  => _**2**_ x _**2**_ x 2 x 2 ||  
Greatest Common Factor/Divisor(GCD) => 4 (2x2) || Least Common Multiple => 24 (2x2x3x2) 
# GCD Methords
```java
// No 1 :
int x = 12, y = 8, gcd = 1;  
for(int i = 1; i <= x && i <= y; i++)
  if(x%i==0 && y%i==0)  gcd = i;
// No 2 (possible with recursion) :
int n1=50, n2=60;  
while(n1!=n2)   
if(n1>n2) n1=n1-n2;  
else  n2=n2-n1;
//No 3 :
static int findGCD(int a, int b){
if (b == 0) return a;     
return findGCD(b, a % b);   
} 
```
