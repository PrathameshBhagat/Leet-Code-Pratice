## [Click Here to get Datatypes at the End](#java-data-types)

<img src="https://github.com/PrathameshBhagat/LeetCodePratice/assets/90595097/c557e13f-119a-4fa5-9970-23e43f4d0a43" style="height:45vh;width:80vw">

### My Multi Word Header
Update
```java
class Solution {
      public  int myAtoi(String s) {
       boolean found=false,Nfound=false,Pfound=false,Zfound=false;int i =0;String s1="";
        for (;i<s.length();i++)
        {
            if (s.charAt(i)==' '&&!Zfound&&!found&&!Pfound&&!Nfound)
                continue;
            else if(s.charAt(i)=='-'&&!Zfound&&!found&&!Pfound&&!Nfound){
                    Nfound=true;
                    continue;
            }
            else if(s.charAt(i)=='+'&&!Zfound&&!found&&!Pfound&&!Nfound){
                   Pfound=true;
                    continue;
            }
            else if (s.charAt(i)=='0'&&!Zfound&&!found){
                Zfound=true;
                while(i<s.length()){
                    if (s.charAt(i)=='0'){i++;continue;}
                    else if(s.charAt(i)>'0'&&s.charAt(i)<='9'){
                     s1=s1+s.charAt(i);found=true;
                     break;
                    }
                    else {i--;break;}
                }
            }
            else if(s.charAt(i)>='0'&&s.charAt(i)<='9'){
                s1=s1+s.charAt(i);found=true;
            }
            else {
                if(!found)s1=s1+'0';
                break;
            }
        }

        if(s1=="-"||s1=="")return 0;
        if (Nfound==true)
            s1="-"+s1;
        if (s1.length()<13){
        long f=Long.parseLong(s1); 
        if (f>2147483647l)return 2147483647;
        if (f<-2147483648l)return -2147483648;
        return (int)Integer.parseInt(s1);
        }
        if (Nfound==true)return -2147483648;
       return 2147483647;
    }
}
```
# Java Data types
##  Char
16-bit(2 bytes)	Stores a single character/letter or ASCII values
## Byte  
8-bit(1 byte) signed two's complement integer **-128 to 127 (inclusive)( -2^7 to 2^7 -1 inc)**  
Default: 0,  E.g: byte a = 100, byte b = -50  
## Short
16-bit(2 byte) signed two's complement integer **-32,768 to 32,767 (inclusive) (-2^15 to 2^15 -1 inc)**  
Default: 0 ,E.g: short s = 10000, short r = -20000
## INT
32-bit(4 byte) signed two's complement integer **-2,147,483,648 to 2,147,483,647(inclusive) (-2^31 to 2^31 -1 inc)**  
Default :0, E.g: int a = 100000, int b = -200000
## Long
64-bit(8 byte) signed two's complement integer and has Long class   
**-9,223,372,036,854,775,808 to 9,223,372,036,854,775,807 (inclusive)(-2^63 to 2^63 -1)**  
Default value is **0L** , E.g : long a = 100000L, long b = -200000L
> From Float onwards we will loose precision and wont be exact  
> **never be used for precise values**  
> Now you can use decimals and **E or e** too 
## Float
_32bit (4 byte)_ **single-precision** IEEE 754 floating point  
Allow 6 digit precision after decimal **-2^-149 to (2-2^-23)·2^127**
Default value is 0.0f, E.g: float f1 = 234.5**f**  
## Double
 _64bit (8 byte)_ **double-precision** IEEE 754 floating point  
Allow up to 15 digit precision after decimal **-2^-1074 to (2-2^-52)·2^1023**  
Default value is 0.0d ,E.g: double d1 = 123.4  **no need of 'd' a decimal point defaults it**
# my multi word header
