## [(Topics revised)](#swapping-array-rotating-array)

<img src="https://github.com/PrathameshBhagat/LeetCodePratice/assets/90595097/af1e7be5-daf4-4335-8803-70410d2901fa" style="height:45vh;width:80vw">
 
``` java  
class Solution {
    public void rotate(int[] N, int k) {
        if(N.length<2)return ;
        if(k>=N.length){
            for(int j=0;j<k;j++){
                int l=N[N.length-1];
                for(int z=N.length-1;z>=1 ;z--)
                    N[z]=N[z-1]; 
                N[0]=l;
            }
            return;
        }
        int []I=new int[k];
        for (int i=N.length-1,j=k-1;i>((N.length-k)-1);i--,j-- )
            I[j]=N[i]; 
        for(int z=N.length-1;z>=k;z--)
                N[z]=N[z-k];  
        for(int y=0;y<k;y++)
        N[y]=I[y];
    }
}
```
# Topics Brushed 
  ##  swapping-array-rotating-array 
