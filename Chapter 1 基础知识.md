## Chpter 1 Python的基础知识
在深入学习Pandas前需要了解的Python基本语句，教程参考DataWhale：https://datawhalechina.github.io/joyful-pandas/build/html/%E7%9B%AE%E5%BD%95/ch1.html

### 1. 列表推导式与条件赋值
对循环和```if...else...```的直观简写形式
```Python
[expression if condition else for var in list]
```
e.g.:
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
e.g.:
``` Python
Lambda x: x*2
```
Map函数起到映射作用
``` Python
map(lambda var: expression, list)
```
注意Map函数得到的结果是一个对象，且var可以是var1，var2...

### 3. Zip函数和Enumerate函数
Zip函数：元素打包。*可用于解压
``` Python
a,b,c=[1,2,3],[4,5,6],[7,8,9]
zip(a,b,c)
```
Enumerate函数：元素打包，同时输出对应序号

### 4. Numpy基础知识
记录几个重要或不熟悉的函数
#### 数组构造与变形
``` Python
np.array(); 
np.linspace(start, end, n); #end-include
np.arange(start, end, step); #end-exclude
np.zeros();
np.eye();
np.full();
np.random #rand(), randn(), randint(), choice(), seed();
reshape();
```

#### 常见函数
``` Python
np.where(condition, a, b);
np.argmax(), np.argmin(), np.nonzero(); #return to index
np.cumprod(), np.cumsum(); #cumulated production/sum
np.diff()
```

#### 向量和矩阵乘法
``` Python
a.dot(b)
A@B
```

### 5. Exercise
#### EX1
``` Python
M1=np.random.rand(2,3)
M2=np.random.rand(3,4)
M=[sum(M1[i][k]*M2[k][j] for k in range(0,3)) for i in range(0,2) for j in range(0,4)]
M=np.array(M).reshape(2,4)
M
```
*最好根据实例把range(,)里面部分换成 M1.shape()等*

#### EX2
``` Python
A=np.full((3,3),([1,2,3],[4,5,6],[7,8,9]))
A1=1/A
(A1.sum(1)*A.T).T
```
*有两点需要注意：1）创建矩阵用reshape很简单；2）把行通过reshape转成列！！详见答案*

#### EX3
``` Python
np.random.seed(0)
A=np.random.randint(10,20,(8,5))
B=A.sum(0)*A.sum(1).reshape(-1,1)/A.sum()
((A-B)**2/B).sum()
```

#### EX4
``` Python
np.random.seed(0)
m,n,p=100,80,50
B=np.random.randint(0,2,(m,p))
U=np.random.randint(0,2,(p,n))
Z=np.random.randint(0,2,(m,n))
np.array([sum((B[i,:]-U[:,j])**2)*Z[i][j] for i in range(Z.shape[0]) for j in range(Z.shape[1])]).sum()
```
*看了参考答案可以考虑把数学公式拆解开然后用矩阵乘法*

#### EX5
``` Python
np.random.seed(1)
a=np.random.randint(0,11,20)
b=np.diff(np.nonzero(np.where(np.diff(a)!=1,1,0)))
np.max(b)
```
*看了参考答案应该手动增加首尾值，并且题目要求是输入函数，所以应该用函数的方式编写*

整个预备知识对于我来说还是非常有用的，由于经常不用Python许多语法细节总是记得不准确，希望通过完整的学习过程我能达到一定的熟练度。





