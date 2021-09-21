LeetCode912 快速排序

```java
public static void quickSort(int[] arr,int low,int high){
        System.out.println("low:"+low+"high:"+high);
        int i,j,temp,t;
        if(low>=high){
            return;
        }
        i=low;//不能是low+1,low可能本来就是最小的
        j=high;
        //temp就是基准位
        temp = arr[low];
 
        while (i<j) {
            //先看右边，依次往左递减 // 顺序很重要，先从右边开始往左找，直到找到比base值小的数
            //因为最后停下来的位置上的数要在左区，换到最前面
            while (temp<=arr[j]&&i<j) {
                j--;
            }
            //再看左边，依次往右递增
            while (temp>=arr[i]&&i<j) {
                i++;
            }
            //如果满足条件则交换
            if (i<j) {
                t = arr[j];
                arr[j] = arr[i];
                arr[i] = t;
            }
 
        }
        //最后将基准为与i和j相等位置的数字交换
         arr[low] = arr[i];
         arr[i] = temp;
        //递归调用左半数组
        System.out.println(Arrays.toString(arr));
        quickSort(arr, low, j-1);
        //递归调用右半数组
        quickSort(arr, j+1, high);
    }

```

