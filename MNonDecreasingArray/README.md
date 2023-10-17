# [_Click Here to get To the Topic left to revise_](#topic-to-learn)
<img src="https://github.com/PrathameshBhagat/LeetCodePratice/assets/90595097/d542f89e-8a7b-4d8c-a450-804890d1fd07" style="height:45vh;width:80vw">

```java 
class Solution {
    public boolean checkPossibility(int[] n) {
       boolean f=false;
        for( int i=0;i<n.length-1;i++)
            if(!(n[i]<=n[i+1])&&!f){
                if(i>0&&n[i-1]>n[i+1]&&i<n.length-2&&n[i+2]<n[i])
                        return false;  
                f=true;
                continue;
            }
            else if(n[i]<=n[i+1])
                continue;
            else return false;
        return true;
    }
}

```

# Topic to learn 

### fast wapping numbers x=x^ y ^ ...  
## woking of if ? && || **for**
