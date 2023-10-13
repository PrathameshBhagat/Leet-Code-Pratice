## [(topics revised)](#java-data-types)

<img src="https://github.com/PrathameshBhagat/LeetCodePratice/assets/90595097/268fd4c4-5335-42b4-bbff-9b708be44081" style="height:45vh;width:80vw">

``` java  
import java.util.*;
class Solution {
    static LinkedHashMap<Integer,Integer> M=new LinkedHashMap<Integer,Integer>();  
    
     public int arrayNesting(int[] nums) {
         boolean[] v=new boolean[nums.length];
        int len=0;
        for(int i=0;i<nums.length;i++){
           len=Math.max(len,ListLen(i,nums,v));
      }
       return len;        
    }
    int ListLen(int k , int[] a,boolean [] v) { 
        ArrayList<Integer> s = new ArrayList<Integer>();   
        int j=k;
        while(true)  {
            if(v[a[j]])return 0;
            s.add(a[j]);
            v[a[j]]=true;
            j=a[j];
            if(j==k) break;
            
        }
        return s.size();
    }
}
```
# Topics Brushed 
  ## LinkedList 
  ## ArrayList 
  ## Map HashMap 
  ## LinkedhashMap(just an ordered Map)
