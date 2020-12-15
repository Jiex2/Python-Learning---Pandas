## Chpter 1 Python的基础知识
在深入学习Pandas前需要了解的Python基本语句

### 1. 列表推导式与条件赋值
对循环和```if...else...```的直观简写形式
```Python
[expression if condition else for var in list]
```
For Example:
``` Python 
[x*2 if x>2 else x for x in [1,2,3,4,5] ]
```
但是不可以写成
```Python
[expression for var in list if condition else]
```
个人猜测是由于语句顺序的问题，当condition满足以后会直接运算expression，所以else部分会报错。


###2. 匿名函数和Map函数
匿名函数：
