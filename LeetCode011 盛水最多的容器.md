LeetCode011 盛水最多的容器

![leetcode_11-1](https://img-blog.csdnimg.cn/2021021514584396.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L2phY2tsb3ZlbW9uaWNh,size_16,color_FFFFFF,t_70)**双指针法**
设置两个指针left和right，分别放在头尾;在设置一个res来存放最大的值。

指针的移动规则：指针所在位置的值小的向大的方向移动

```java
    public int maxArea(int[] height) {
        int left = 0;
        int right = height.length - 1;
        
        int high;
        int res = 0;
        int size, temp;
        while (left < right) {
            size = right - left;
            if (height[left] < height[right]) {/ 短的往长的移动
                high = height[left];
                //while (height[left] <= high&&left < right)//加速，左小右大，如果左边下一个更短，高度降低，长度减小，总结果一定更小
                                               
                    left++;
                                               

            } else {
                high = height[right];
                while (height[right] <= high&&left < right)
                    right--;//&&left < right 8,2,2,8 如果没有这个条件，right直接滑到-1的位置
/*更好的写法

high = height[right];
right--;
 while (height[right] <high)
   right--;                 
*/
                
            }
            temp = high * size;
            if (temp > res)
                res = temp;

        }

        return res;
    }
```

