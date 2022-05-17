---
# **数据结构&算法**
---

### 排序算法

#### 冒泡排序
```java
public void sort(int[] nums) {
    int n = nums.length;

    // 判断长度，长度为1 提前退出
    if (n <= 1) return;

    // 开始冒泡，从第一个开始，将整列最大移动到最后一个
    for (int i = 0; i < n; i++) {
        // 优化点，新增一个标志位，如果这一轮没有数字移动，则证明整个数组有序
        boolean flag = false;
        for (int j = 0; j < n - i - 1; j++) {
            if (nums[j] > nums[j+1]) {
                int tmp = nums[j];
                nums[j] = nums[j+1];
                nums[j+1] = tmp;
                flag = true;
            }
        }
        if (!flag) break;
    }
}
```

冒泡排序的特点
1. 冒泡排序为原地排序算法，空间复杂度为O(1)
2. 冒泡排序是稳定排序算法，相邻两个相等元素，不做交换
3. 时间复杂度，最好为O(n)，最差为O(n<sup>2</sup>)，平均是 O(n<sup>2</sup>)


#### 插入排序

```java
public void sort(int[] nums) {
    int n = nums.length;

    // 判断长度，长度为1 提前退出
    if (n <= 1) return;

    // 左边为已排序，右边为未排序
    for (int i = 1; i < n; i++) {
        int value = nums[i];
        // 查找插入的位置
        int j = i - 1;
        for (; j >= 0; j--) {
            if (nums[j] > value) {
                nums[j + 1] = nums[j];
            } else {
                break;
            }
        }
        nums[j + 1] = value;
    }
}
```

插入排序的特点
1. 插入排序为原地排序算法，空间复杂度为O(1)
2. 插入排序是稳定排序算法，对于值相等的元素，可以选择将后面出现的元素插入到后面
3. 时间复杂度，最好为O(n)，最差为O(n<sup>2</sup>)，平均是 O(n<sup>2</sup>)