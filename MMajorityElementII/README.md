## [(Topics revised)](#Topics)

<img src="https://github.com/PrathameshBhagat/LeetCodePratice/assets/90595097/7f9630c0-4dc6-4faa-af15-cf74e8a0080c" style="height:45vh;width:80vw">

```java
/*Given an integer array of size n, find all elements that appear more than ⌊ n/3 ⌋ times.
E.g:Input: nums = [3,2,3] Output: [3]*/
class Solution {
    public List<Integer> majorityElement(int[] nums) {
       List<Integer>R = new ArrayList<Integer>(); 
         List<Integer>r = new ArrayList<Integer>(); 
        int count =0,l=nums.length,p=Math.floorDiv(l,3);
       for (int i=0;i<l;i++){
           if(r.contains(nums[i]))continue;
         for (int j=0;j<l;j++){
          if(nums[i]==nums[j])count++;
          }
          if (count>p)R.add(nums[i]);
          count=0;
          r.add(nums[i]);
        }
        return R.stream().distinct().collect(Collectors.toList());
    }
}
```
# Topics 
### Math.floorDiv(10,3)
> Floor of divion
### R.stream().distinct().collect(Collectors.toList());
> Removes the duplicate elements in ArrayList (Or any List/Collection) 
