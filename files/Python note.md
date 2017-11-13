# Python

## 课时1：







## 课时18：函数的方法

复杂的东西简单化，程序代码简单分为越来越小的部分：函数、对象、模块

函数：完成某一部分功能的代码块

**定义函数：：**

```python
def myfirstfunction()：
    print('我爱你')
    print('我爱你')
```

**调用函数：：**

```python
myfirstfunction()
```

我爱你

**函数的参数：：**

```python
def mysecondfunction(name):
    print(name + '我爱你')
```

```python
def add(num1, num2):
    result = num1 + num2
    print(result)
```

**调用：：**

```
mysecondfunction('小小')
```

小小我爱你

```
add(1,2)
```

3

函数的参数一般不要太多，要注意写好注释



**函数的返回值：：**

```python
def add(num1 + num2)
    return (num1 + num2)
```

```
print(add(5,6))
```

11



## 课时19：函数的参数

评论一款语言是否高级是看是否灵活。

**形参（parameter）和实参(argument)：：**

parameter: def myfirstfunction(name):

argument: myfirstfunction('小小')

**函数文档：：**

写函数文档是为了让别人更好的理解我们的意思

```python
def myfirstfunction(name):
    '函数定义过程中的name是形参'
    #因为ta知识一个形式，表示占据一个参数位置
    print('传递进来的' + name + '叫做实参，因为ta是具体的参数值')
```

```python
myfirstfunction('小小')
```

传递进来的小小叫做实参，因为ta是具体的参数值

```python
myfirstfunction.__doc__
```

'函数定义过程中的name是形参'

```python
help(myfirstfunction)
```



**关键字函数：：**

```python
def saysome(name, words):
    print(name + '>' + words)
```

```
saysome(words='改变世界', name='小小')
```

小小 > 改变世界

**默认参数：：**

    def saysome(name='小小', words='改变世界'):
        print(name + '>' + words)

```
saysome()
```

小小>改变世界

```
saysome('蒼井空')
```

蒼井空>改變世界

**收集（count）參數：：**

```python
def test(*params):
    print('參數的長度是：', len(params));
    print('第二個參數是：', params[1]);
```

```
test(1,2,3,4,5,6,7)
```

参数的长度是：7

第二个参数是：2

## 课时20：函数与过程

函数（function）：是有返回值的

过程（procedure）：是简单、特殊并且没有返回值的

**python严格来说只有函数，没有过程**

```python
def hello():
    print('hello world')
```

```
temp = hello()
```

函数变量的作用域：全局（global variable）或局部（local variable）

```python
def discounts(price, rate):
    final_price = price * rate
    return final_price
    
old_price = float(input('请输入原价：'))
rate = float(input('请输入折扣率：'))
new_price = discounts(old_price, rate)
print('原始价格是：', old_price)
print('折扣后价格是：', new_price)
```

**final_price = price * rate   就是局部变量**

**old_price  就是全局变量**



## 课时21：内嵌函数和闭包

**global 关键字**

如果尝试修改全局变量，python会自动创建一个同名的局域变量，shadowing功能

```python
count = 5
def myfun():
    global count
    count = 10
    print(10)
```

这里的global count ，是强行在函数中修改全局变量

**内嵌函数：**

python是支持函数的嵌套：

```python
def fun1():
    print('fun1' downloading...)
    def fun2():
    	print('fun2' downloading...)
    fun2()
```

嵌套内的函数，不能进行全局调用

**闭包：**

如果在一个内部函数里的变量

```python
def fun1():
	x = 5
	def fun2():
         nonlocal x
		x**2 = x
		return x
	return fun2()
```

这里的nonlocal，是允许内嵌函数使用外部变量

## 课时22：lambda表达式

**匿名函数**

```python
def ds(x):
	return 2* x + 1
	
g = lambda x: 2 * x + 1

```

不用考虑申请和释放资源的问题

```python
def add(x, y):
	return x + y

g = lambda x, y : x + y

```



**lambda表达式的重要意义**

使用lambda可以让代码更简单，

不用def直接调用，

只调用一两次的函数，不用起名字直接使用即可，

**BIF**

filter()

```
help(filter)
```



```python
list(filter(none, [1, 0, False, Ture]))
```



```python
def odd(x):
	return x % 2
	
temp = range(10)
show = filter(odd, temp)
list(show)
```

```python
list(filter(lambda x : x % 2, range(10)))
```

map()

```python
list(map(lambda x : x * 2, range(10)))
```



## 课时23：递归

普通程序员用迭代，天才程序员用递归。

**汉若塔**

函数调用自身，python默认定义调用100层

```
import sys
sys.
```



```python
def recursion():
	return recursion()
```

**递归求阶乘**

```python
def factorial(n):
	result = n
	for i in range(1, n):
		result *= i
		
	return result
	
number = int(input('please input a number:'))
result = factorial(number)
print("%d 的阶乘是：%d" % (number, result))
```



```python
def factorial(n):
	if n ==1:
		return 1
	else:
		return n * factorial(n-1)
		
number = int(input('input a int:'))
result = factorial(number)
print("%d 的阶乘是：%d" % (number, result))
```



**递归：有调用自身的行为，有一个正确的返回条件**

## 课时24：递归例子

**Fibonacci递归例子**

如果兔子在出生的两个月之后就拥有了繁殖能力，假设所有兔子都不会死去，一年之后能繁殖多少兔子。

斐波那契数列的迭代实现：0.618:1

| 月数   | 1    | 2    | 3    | 4    | 5    | 6    | 7    | 8    | 9    | 10   | 11   | 12   |
| ---- | ---- | ---- | ---- | ---- | ---- | ---- | ---- | ---- | ---- | ---- | ---- | ---- |
| 兔子对数 | 1    | 1    | 2    | 3    | 5    | 8    | 13   | 21   | 34   | 55   | 89   | 144  |

数据函数定义：

```
F(n) = 1, when n = 1
           2, when n = 2
           F(n-1)+F(n-2), when n>2
```

求出经历20个月后：

```python
def fab(n):
	n1 = 1
	n2 = 1
	n3 = 1
	
	if n < 1:
		print('error!')
		return -1
		
	while(n-2) > 0:
		n3 = n2 + n1
		n1 = n2
		n2 = n3
		n -= 1
		
	return n3
	
number = int(input('input a int:'))
result = fab(number)
if result != -1:
	print('%d total:' % result)
```

![pytyonnote_fab](D:\markdown\image\pytyonnote_fab.JPG)







END;