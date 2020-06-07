# Shuffle the array
## https://leetcode.com/problems/shuffle-the-array


# Implementation 1 : Extra Space
```java
class Solution {
    public int[] shuffle(int[] nums, int n) {
        if(nums == null || nums.length <= 2)
            return nums;
        int[] shuffle = new int[nums.length];
        List<Integer> first = new ArrayList<>();
        List<Integer> second = new ArrayList<>();
        
        for(int i = 0; i < n; i++) {
            first.add(nums[i]);
            second.add(nums[n+i]);
        }
        int index = 0;
        for(int i = 0; i < n; i++) {
            shuffle[index++] = first.get(i);
            shuffle[index++] = second.get(i); 
        }
        return shuffle;
    }
}
```

# Implementation 2 : No Extra space
```java
class Solution {
    public int[] shuffle(int[] nums, int n) {
        if(nums == null || nums.length <= 2)
            return nums;
        
        int[] shuffle = new int[nums.length]; 
        int index = 0;
        for(int i = 0; i < n; i++) {
            shuffle[index++] = nums[i];
            shuffle[index++] = nums[n+i];
        }
        
        return shuffle;
    }
}
```


