## [(This question needs to revisited and revised again )](#topics)

<img src="https://github.com/PrathameshBhagat/LeetCodePratice/assets/90595097/f27feb78-3e28-4f6c-b91c-946a8aeab870" style="height:45vh;width:80vw">

``` java
// The commented code at the end is just the brue force approach
// It works but as is slow get unaccepted.    
import java.util.*;
class Solution {
    public int findMaxLength(int[] n) {
       int i=0;
        for (;i<n.length;i++)
         if(n[i]==0)n[i]=-1;
        int s=0,r=0;        
        Map<Integer,Integer> m=new HashMap<>();
        m.put(0,-1);
         for (i=0;i<=n.length-1;i++){
             s=s+n[i];
             if(m.containsKey(s))
                 r=Math.max(r,i- m.get(s));
            else  m.put(s,i); 
         }
        return r;
   }
} 
// The commented code at below is just the brue force approach
// It works but as is slow get unaccepted.    
/*  int o =0,z=0,r=0,i=0,l=0;
         for (;i<=n.length-1;i++){
            for(int j=i;j<n.length;j++){
                   if(n[j]==1)o++;
                   else z++;
                   if(o==z&&o!=0)r=Math.max(r,o+z);       
            }
                o=0;z=0;
        }
return r;
*/
```
# Topics 
  ##  Map ,Hash Maps 
no description needed can do it else were
