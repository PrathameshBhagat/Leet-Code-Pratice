## [(Topics revised)](#Topics)

<img src="https://github.com/PrathameshBhagat/LeetCodePratice/assets/90595097/61e94ca1-8bdb-46f5-9005-80a5814fa8e3" style="height:45vh;width:80vw">
 
```java
/*Given a string s, return the longest palindromic substring in s.*/
class Solution {
    String a="";
    public String longestPalindrome(String s) {
   if(s.length()==1)return s;
        a=s;
        for (int i=s.length();i>0;i--){
            for (int j=0;j<=s.length()-i;j++){
                if(CheckPallindrome(j,i+j)==true){
                 return s.substring(j,i+j);
                }
            }
        } 
       return "";
    }
    boolean CheckPallindrome(int z, int y) {
        y=y-1;
        for (;z<y;){
            if(a.charAt(z)!=a.charAt(y))
            return false;
            z++;y--;
        }
        return true;
}
}
```
# Topics 
### Two Pointer Approach
- M A D A M   
- i &emsp;&emsp;&emsp;&ensp; j   >>> if char(i)==char(j) continue  i++ & j--
### Normal Approach
- M A D A M  >>> reverse & compare with original string if  **a.equals(rev(a))** return true  
- (not a==rev(a) gives error)
