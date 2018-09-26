## 问题描述：
从arr[1, n]这n个数中，找出最大的k个数，这就是经典的TopK问题。

## 案例：
从arr[1, 12]={5,3,7,1,8,2,9,4,7,2,6,6} 这n=12个数中，找出最大的k=5个。 

> 9、8、7、7、6

## 解决思路

首先，我们脑袋最先想到的是现将这个数组进行排序，然后在取得k个数即可。

### 方案一：排序

将数组进行从大到小排序后，获取k个数

```java
public static List<Integer> topKFrequent(int[] nums, int k) {
    Arrays.sort(nums);//使用jdk内置的双轴快速排序

    //采用apache lang的ArrayUtils工具包
    List<Integer> list = Arrays.asList(ArrayUtils.toObject(nums));

    return list.subList(0,k);
}
```

但是仔细分析下，我们其实只需要k个数，所以这里可以将全局排序优化为部分排序。

那么如何优化呢？想想最基本的算法中是如何排序的？

例如快速排序是将一组数字划分为2，那么是否可以直接找到topk中末尾的那个数，然后只需要获取一边的数据呢？

再比如冒泡排序，是否可以优化为冒k次泡？



### 方案二：冒k次泡进行局部排序



### 方案三：

### 延伸

> 从20亿个数字的文本中，找出最大的前100个。 