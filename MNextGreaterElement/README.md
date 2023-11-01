## [( This is quite simple solved without hitting any major topic)]()

<img src="https://github.com/PrathameshBhagat/LeetCodePratice/assets/90595097/a1aaaa10-6f71-4518-a393-d8105a6d2786" style="height:45vh;width:80vw">

```java
/*The next greater element is the first greater element that is to the right of x in the same array.
For each 0 <= i < nums1.length, find j such that n1[i] == n2[j] 
Also get the next greater element of n2[j] in n2.
If not found the query returns -1.*/

class Solution {
    public int[] nextGreaterElement(int[] nums1, int[] nums2) {
       int [] a=new int[nums1.length];int c=0,j=0;boolean k=false;
        for (int i=0;i<=nums1.length-1;i++ ){
            for ( ;j<=nums2.length-1;j++ ){
                if(nums1[i]==nums2[j]){c=nums2[j];break;}
            }j++ ;
             for (;j<=nums2.length-1;){
                if( nums2[j]>c){k=true;break;}j++ ;
            }
            if(k&&j!=nums2.length)a[i]=nums2[j];
            else a[i]=-1; 
            j=0;
        }return a;    
    }
}
```

