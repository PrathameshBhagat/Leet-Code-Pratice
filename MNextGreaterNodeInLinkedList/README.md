## [(2 Approaches but very similar)](#Topics)

<img src="https://github.com/PrathameshBhagat/LeetCodePratice/assets/90595097/038e34cf-cd69-4b77-99ff-fc831fdf2a94" style="height:45vh;width:80vw"> 

# 1st Approach (slower execution + self coded)
```java
/*For each node in the list, find the value of the next (strictly) greater node.
Return an integer array answer where answer[i] is the value of the next greater node.
If no greater node answer[i]=0 for that i. */
class Solution {
    public int[] nextLargerNodes(ListNode head) {
         ArrayList<Integer> l=new ArrayList<Integer>();int a=0;
        while(head!=null){
        ListNode p=head.next;
            while(p!=null){
                if(p.val>head.val){a=p.val;break;}
                p=p.next;   
            }
            l.add(a);a=0;
            head=head.next;
        } 
        int[] i= l.stream().mapToInt(Integer::intValue).toArray();
        return i;    
    }
}
```
# 2nd Approach (Same Logic different Data Structure)
```java
class Solution {
    public int[] nextLargerNodes(ListNode head) {
        ArrayList<Integer> A = new ArrayList<>();
        for (ListNode node = head; node != null; node = node.next)
            A.add(node.val);
        int[] res = new int[A.size()];
        Stack<Integer> stack = new Stack<>();
        for (int i = 0; i < A.size(); ++i) {
            while (!stack.isEmpty() && A.get(stack.peek()) < A.get(i))
                res[stack.pop()] = A.get(i);
            stack.push(i);
        }
        return res;
    }
}
```
