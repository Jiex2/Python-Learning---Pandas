## Chpter 1 Python的基础知识
在深入学习Pandas前需要了解的Python基本语句

### 1. 列表推导式与条件赋值
对循环和```if...else...```的直观简写形式
```Python
[expression if condition else for var in list]
```
EX:
``` Python 
[x*2 if x>2 else x for x in [1,2,3,4,5] ]
```
但是不可以写成
```Python
[expression for var in list if condition else]
```
个人猜测是由于语句顺序的问题，当condition满足以后会直接运算expression，所以else部分会报错。


### 2. 匿名函数和Map函数
匿名函数：
``` Python
Lambda var: expression
```
EX:
``` Python
Lambda x: x*2
```
Map函数起到映射作用
``` Python
map(lambda var: expression, list)
```
注意Map函数得到的结果是一个对象，且var可以是var1，var2...

### 3. Zip函数和
