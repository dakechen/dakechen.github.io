

### 概念
在函数的定义中使用**自身**的方法
形式例如  fn(n)=f(n-1)+1   
**递归是分治处理问题的方法分为两部分**
**递**：自上而下，分解问题
**归**：自下而上收集计算处理结果

**递归算法的三要素**：
1.大问题可以拆分为若干小问题；
2.原问题与子问题除数据规模不同，求解思路相同；
3.存在递归终止条件。

**递归使用场景**
当一个功能被重复使用，而每一次使用该功能时的**参数不确定**，都由**上次**的功能元素结果来确定时候使用
如：求n的阶乘、斐波那契数列、求n个数的最大、青蛙跳台阶问题和汉诺塔问、数制转换、求最大公约数都属于简单递归。
### 目的
将大问题逐步拆解为不能再拆的小问题
### 题目
1 假设一个楼梯有n个台阶，一次只能上一个台阶/两个台阶，请问到一个人走到最后一个台阶这个过程，有几种方式？
解： **重要的是确认拆解终止条件**
![用递归方式解题](https://i-blog.csdnimg.cn/blog_migrate/c3958f75dbc49cdb2f6038ab7bddd40d.jpeg#pic_center)代码

```python
def f(n):
    if n == 1:
        return 1
    if n == 2:
        return 2
    return f(n-1) + f(n-2)

print(f(6))
```
执行结果

```python
13
```
2 求n的阶乘

```python
def f(n):
    if n == 1:
        return 1
    if n == 2:
        return 2
    return n*f(n-1)    # 注意：函数的定义中使用本身，文章开始就强调

print(f(4))
```
执行结果

```python
24
```
3 斐波那契数列
每一项都等于前两项之和

```python
def f(n):
    if n == 1:
        return 1
    if n == 2:
        return 1
    return f(n-1)+f(n-2)
print(f(4))
```
执行结果
```python
3
```
4 求列表最大数

```python
def f(lis, n):
    if n == 1:
        return lis[0]
    return max(lis[n-1], f(lis, n-1))
print(f([1,4,3,6], 4))
```
执行结果

```python
6
```

### 讲的很好的b站视频🔗
https://www.bilibili.com/video/BV1ks421w7cA/?spm_id_from=333.1007.tianma.23-4-90.click&vd_source=de99d52601b26541c249cca20da81364