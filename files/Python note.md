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



## 课时21：













END;