[TOC]

# 算法

## 查找算法

### 快速排序

#### 思路

首先选一个值，将其他值与之比较，小的放左边大的放右边；然后递归排序左边和右边的。

#### 代码

- 代码1

```python
def qsort(x):
    if len(x) <= 1:
        return x
    else:
        p = x[0]
        return qsort([i for in x[1:] if i < p] + [p] + [i for i in x[1:] if i >= p])
```

### 插入排序

#### 思路

想象成扑克牌，手里的牌是排好序的（列表左边），桌上的牌是待排序的（列表右边）。

#### 代码

- 代码1

```python
def insert_sort(x):
    n = len(x)
    for i in range(1, n):
        for j in range(i, 0, -1):
            if x[j-1] > x[j] and j > 0:
                x[j],x[j-1] = x[j-1],x[j]
    return x

```

### 二分查找

#### 思路

目标t在列表x中，那么t肯定满足x[l] <= t <= x[u]，（l=0，u=n-1，n = len(x)）。当l == u时，x[l] == t == x[u]，就能找到t。

#### 代码

- 代码1

```python
def foo(x, t):
    n = len(x)
    l = -1
    u = n

    if l > u:
        return -1  #不存在
    while l + 1 != u:
        m = (l + u) // 2
        if x[m] < t:
            l = m
        else:
            u = m
    p = u  #p为t的位置索引
    if p > n or x[p] != t:
        p = -1
    return p
```



## 排序算法

