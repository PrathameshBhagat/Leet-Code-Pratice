<img src="https://github.com/PrathameshBhagat/LeetCodePratice/assets/90595097/7d1eefeb-c4d4-400f-98c3-9101e6ed5fa3" style="height:45vh;width:80vw">

```java

class Solution   {
    public void setZeroes(int[][] M) {
     int [] blockColumn=new int [M[0].length];
        for (int i=0;i<blockColumn.length-1;i++)
              blockColumn[i]=0;
     int [] blockRow=new int [M.length];
        for (int i=0;i<blockRow.length-1;i++)
              blockRow[i]=0;
//Mark The blocking columns & rows
     for (int i=0;i<M.length;i++){
       for(int j=0;j<M[0].length;j++)
         if (M[i][j]==0){blockColumn[j]=1;blockRow[i]=1;}
//Set the blocking row values to 0
    for (int i=0;i<M.length;i++){
                if(blockRow[i]==1)
                    for (int j=0;j<M[0].length;j++)
                        M[i][j]=0;
            }
//Set the blocking columns values to 0
            for (int j=0;j<M[0].length;j++){
                if(blockColumn[j]==1)
                    for (int i=0;i<M.length;i++)
                        M[i][j]=0;
            }
    }
}
```
