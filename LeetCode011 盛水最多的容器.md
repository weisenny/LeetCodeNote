LeetCode011 盛水最多的容器

![leetcode_11-1](https://img-blog.csdnimg.cn/2021021514584396.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L2phY2tsb3ZlbW9uaWNh,size_16,color_FFFFFF,t_70)**双指针法**
设置两个指针start和end，分别放在头尾;在设置一个max来存放最大的值。area存放本次位置的值。如图1：

指针的移动规则：指针所在位置的值小的向大的方向移动

无论移动那个指针，很坐标都是会减1；
如果是移动指针位置大的值向小的移动，那么横坐标的长度减1，但是高度还是看指针值短的，如图2：

