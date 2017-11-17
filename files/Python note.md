# Python

## 课时1：python

1,python是什么类型的语言？
Python是一种面向对象、解释型、动态类型计算机程序设计语言
解释型：程序无需编译成二进制代码，而是在执行时对语句一条一条编译
动态类型：在程序执行过程中，可以改变变量的类型
它常被昵称为胶水语言，能够把用其他语言制作的各种模块（尤其是C/C++）很轻松地联结在一起

## 课时2：BIF

2.BIF(Build-in-functions)内置函数，Python一共有68个内置函数
dir(__buitins__) 查看Python里面的内置函数
help(内置函数名称) 查看内置函数的作用和用法

## 课时3：引号

3,在字符中打印引号，用/”输出引号

## 课时4：IDLE

4，IDLE是一个Python shell，shell的意思就是“外壳”，基本上来说，就是一个通过键入文本与程序交互的途径！像我们Windows那个cmd窗口，像Linux那个黑乎乎的命令窗口，他们都是shell，利用他们，我们就可以给操作系统下达命令。同样的，我们可以利用IDLE这个shell与Python进行互动。

## 课时5：特设变量

5，设置你的操作系统的环境变量，以便可以轻松进入Python环境

Python特设变量：

teacher = 'zxp'
print(teacher)
zxp
teacher = 'zxp1'
print(teacher)
zxp1
first = 3
second = 8
third = first + second
print(third)
11
myteacher = 'zxp'
yourteacher = 'he'
ourteacher = myteacher + yourteacher
print(ourteacher)
zxphe
使用变量之前，要对变量赋值
变量名不能以数字开头，变量名可以包括字母，数字，下划线
最好给变量取一个专业一点的名字

字符串（文本）
‘5’+’8’=’58’
打印’Let\'s go'   转义字符  \
"Let's go"
打印：C：\now
str=‘C:\\now’    print(str)
原始字符串：在字符串前面加一个r，比如： r’C:\now’
注意原始字符串结尾不能加反斜杠‘\’
三重引号字符串：str="""abcd"""

str
'\na\nb\nc\nd'
print(str)
a
b
c
d
条件分支：
if 条件：
else：
while 条件：
引入外援
random模块
import random
secret = randint(1,10)
randint（）会返回一个随机的整数

## 课时6：快捷键

6，快捷键
Alt+N：把上面的语句复制
Alt+P: 把下面的语句复制

## 课时7：逻辑操作符

7，逻辑操作符：
3<4 and 4>5  等价于 3<4<5 两种都可以实现
​                  or
​                 not          
第五节 数据类型：
整型
浮点型
布尔类型 (bool):True 、False
e记法：科学计数法（不是数据类型）1.5e11是浮点型  



## 课时8：类型转换

8，类型转换
int()     int(5.99)=5
float()  float(520)=520.0
str()    str(5.99)=’5.99’



## 课时9：数据类型

9,type(a)得到a的数据类型
   isinstance()

a = 'zxp'
isinstance(a,str)
True

## 课时10：算数操作符

10,算数操作符
10//8=1
10/8=1.25
取余数 % 5%2
幂运算：3**3=27
-3**2=-9
优先级：**



## 课时11：条件操作符

11,条件操作符
elif = else if
悬挂else：else与if同一个缩进
三元操作符：
if x<y
   Small=x;
else
   Small=y;
等价于：small=x  if x<y  else y
断言(assert):当关键字后边的条件为假时，程序自动崩溃并抛出AssertionError的异常
for循环：
for 目标 in  表达式：
​        循环体
range():生成一个数列start到stop默认步长为1
Range([start,] stop [,step=1])中括号中的参数可以省略, step为步长
Rang(1,4)
break ：终止循环并跳出循环
continue ：终止本轮循环并开始下轮循环

## 课时12：列表

12,列表
普通列表
混合列表mix=[1,3,14,’xiaojiayu’,[1,2,3]]
空列表empty=[];
向列表添加元素：
append()把元素添加到列表尾，只能添加一个参数
mix.append(‘小平’)
extend():以一个列表作为参数，可以添加多个参数
mix.extend([‘xiaoping’,’xiaojiayu’])
insert()：有两个参数，添加的元素和添加的位置
mix.insert(‘小平’，0)放在列表头
number*：从列表中获取第i个元素number.remove(‘小平’)：从列表中删除’小平’元素del语句：del number 或者 del number (删除这个列表)number.pop()：返回最后一个元素number.pop(i):返回列表中第i个元素列表分片：number[i : j]拷贝列表中第i个元素到第j-1个元素               *

*number[ : j]拷贝列表中第0个元素到第j-1个元素     number[i : ]拷贝列表中第i个元素到最后一个元素注：原列表不发生变化count：number.count(‘小平’)index:number.index(‘小平’)number.index(‘小平’，起始位置，结束位置)reverse：number.reverse()sort：number.sort(func，key，reverse)用指定的方式（func）对列表进行排序func、key是默认的一般不考虑reverse =false是默认的，reverse=true逆置copy：list1=list2对list2进行操作时，list1跟着变化list1=list2[ : ]（分片）对list2进行操作是，list1不会变化*

## 课时13：元组

*13，元组*

元组里面元素不能修改！创建和访问一个元组：tuple1=(1,2,3,4,5,6,7,8)或者tuple1=1，2，3，4，5，6，7temp =(1)是一个整型数据，temp=(1,)是一个元组数据8\*(1,)=(1,1,1,1,1,1,1,1)更新和删除一个元组：temp=(1,2,3,4,6,7,8)temp=temp[:5]+(5,)+temp[5:]del temp*







## 课时16：序列

介绍的几种方法：
1.list()
将对象转换成列表
如:>>> b = 'I LOVE FISHC'
​    >>>b = list(b)
​    >>>b
['I','L','O','V','E','F','I','S','H','C']
2.tuple()
将对象转换成元组
用法同1
3.str()
将对象转换成字符串
4.len()
计算对象的长度并返回
5.max()
计算对象的最大值并返回
6.min()
max的相反方法
7.sum(iterable[,start=0])
将对象的数据（只限整数与浮点数）相加，加入可选参数会相加
8.sorted()
讲对象按照从小到大的顺序排序
不会改变序列，只是将排序号的拷贝一份并返回，原来的对象不变
9.reversed()
逆袭。讲对象翻转
与sorted联合使用可以实现从大到小的排序
他返回的是一个迭代器对象而不是一个列表
但可以用list()方法将他迭代成列表
10.enumerate()
将对象的每一个元素加上索引值组成一个元组
并且将所有元组组成一个列表
11.zip(a,b)
把a和b的索引值相同的元素组成一个元组，并将所有元组组成一个列表



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
result = fab(number
if result != -1:
	print('%d total:' % result)
```



```python
def fab(n):
	if n < 1:
		print('error')
		return -1
	
	if n == 1 or n == 2:
		return 1
	else:
		return fab(n-1) + fab(n-2)
		
result = fab(20)
if result != -1:
	print('%d total:' % result)
```

递归算法可以理解为：分治思想

效率问题来说：迭代效率更高，

## 课时25：递归汉诺塔

**递归求解汉诺塔**

|  1   |      |      |
| :--: | :--: | :--: |
|  2   |      |      |
|  3   |      |      |
|  4   |      |      |
|  5   |      |      |
|  6   |      |      |
|  7   |      |      |
|  X   |  Y   |  Z   |

思路分解：先把1-6从X移动到Y,再把7移动至Z，最后把1-6从Y移动到Z。

拆解问题：

```python
def hanoi(n, x, y, z):
	if n == 1:
		print(x, '-->', z)
	else:
		hanoi(n-1, x, z, y)#将前n-1个盘子从x移动到y上
		print(x, '-->', z) #将最底下的最后一个盘子从X移动到z上
		hanoi(n-1, y, x, z)#将y上的n-1个盘子移动到z上
		
n = int(input('input hanoi level:'))
hanoi(n, 'x', 'y', 'z')
```



## 课时26：字典

**唯一的映射类型=字典: 这里的字典可以理解为 mapping**

**键（key = string）  值（value）**

映射：数集A： 数集B 一对一的关系或一对多的关系，俗称映射

**如何创建和访问字典**

```
brand = ['李宁','耐克','阿迪','鱼C']
```

```
slogan = ['一切皆有可能','Just do it','impossible is nothing','让编程改变世界']
```

```
print('鱼C的口号是', slogan[brand.index('鱼C')])
```

创建字典：

```
dict1 = {'李宁':'一切皆有可能','耐克':'Just do it','阿迪':'impossible is nothing','鱼C':'让编程改变世界'}
```

```
print('鱼C的口号是', dict1['鱼C'])
```

```
dict1['李宁'] = '一切皆不可能' #变更数据value
```

```
dict1['王宁'] = '一切皆不可能' #数组中查询不到则新建
```

```
dict1
```



## 课时27：字典

字典会自动添加新键

工厂函数（类型）:::  str(), int(), list(), tuple()

例如 ： fromkeys(...)

```
dict1 = {}
```

```
dict1.fromkeys((1,2,3), 'Number')# 只能附加一个值
```

访问字典的几种方法：keys(), values(), items()

```python
dict1 = {}
dict1 = dict1.fromkeys(range(32), 'nice')
```

```python
for eachkey in dict1.keys():
	print(eachkey)
```

```python
for eachvalue in dict1.values():
	print(eachvalue)
```

```python
for eachitem in dict1.items():
	print(eachitem)
```

```
dict1
```

```python
dict1.get(31, 'none!')
```

```python
dict1.get(32, 'none!')
```

清空字典： a.clean()      或   dict1 = {}   #这种方式有隐患

```python
dir(dict)
```

copy() 和赋值的区别，copy()是创建新的ID，类似clone，赋值是同ID不同标签

## 课时28：集合

字典的表亲：集合

num = {}   num被定义为字典  dict

num2 = {1, 2, 3, 4}  被定义为集合，

集合唯一的作用就是 定义唯一

num2 = {1, 2, 3, 3, 2, 1}   

num2      {1, 2, 3}

集合不支持索引     num2[2]  X   #不支持

**不使用集合，如何去重？？**

```
num1 = [1, 2, 3, 4, 4, 2, 1, 0]
```

```
temp = []
```

```python
for each in num1:
	if each not in temp:
		temp.append(each)
```

```
temp  #查看
```

**用集合去重**

```python
num1 = list(set(num1))  
```

用set得到的集合，顺序是无序的

**如何向集合添加值：**

```
num2.add(6)
```

```
num2.remove(6)
```

**不可变集合：**   frozen set

```
num3 = frozenset([1, 2, 3, 4, 5])
```

```
num3.add(6) #结果返回：不能添加
```



## 课时29：文件

输入>>处理>>输出

**打开文件：**

```python
f = open('e:\\record.txt')

f.read()

f.tell()

f.seek(0, 0)

for each_line in f:
	print(each_line)
```

**文件写入：**

```python
f = open('e:\\test.txt','w')

f.write('I love fish')

f.close()

```



    'r'       open for reading (default)
    'w'       open for writing, truncating the file first
    'x'       create a new file and open it for writing
    'a'       open for writing, appending to the end of the file if it exists
    'b'       binary mode
    't'       text mode (default)
    '+'       open a disk file for updating (reading and writing)
    'U'       universal newline mode (deprecated)
**file的读写方法：**

| F.read([size])          | #size为读取的长度，以byte为单位                     |
| ----------------------- | ---------------------------------------- |
| F.readline([size])      | \#读一行，如果定义了size，有可能返回的只是一行的一部分           |
| F.readlines([size])     | \#把文件每一行作为一个list的一个成员，并返回这个list。其实它的内部是通过循环调用readline()来实现的。如果提供size参数，size是表示读取内容的总长，也就是说可能只读到文件的一部分。 |
| F.write(str)            | \#把str写到文件中，write()并不会在str后加上一个换行符       |
| F.writelines(seq)       | \#把seq的内容全部写到文件中。这个函数也只是忠实地写入，不会在每行后面加上任何东西。 |
| F.close()               | \#关闭文件。python会在一个文件不用后自动关闭文件，不过这一功能没有保证，最好还是养成自己关闭的习惯。如果一个文件在关闭后还对其进行操作会产生ValueError |
| F.tell()                | 返回文件操作标记的当前位置，以文件的开头为原点                  |
| F.seek(offset[,whence]) | 将文件打操作标记移到offset的位置。这个offset一般是相对于文件的开头来计算的，一般为正数。但如果提供了whence参数就不一定了，whence可以为0表示从头开始计算，1表示以当前位置为原点计算。2表示以文件末尾为原点进行计算。需要注意，如果文件以a或a+的模式打开，每次进行写操作时，文件操作标记会自动返回到文件末尾。 |



## 课时30：分割文件

提前下载一个txt的 客户对话文档

```python
def save_file(boy, girl, count):
    file_name_boy = 'boy_' +str(count) + '.txt'
	file_name_girl = 'girl_' +str(count) + '.txt'
		
	boy_file = open(file_name_boy, 'w')
	girl_file = open(file_name_girl, 'w')
		
	boy_file.writelines(boy)
	girl_file.writelines(girl)
        
	boy_file.close()
     girl_file.close()

def split_file(file_name):
    f = open('record.txt')

	boy = []
	girl = []
	count = 1

	for each_line in f:
		if each_line[:6] !='======'
		#进行字符串分割
			(role, line_spoken) = each_line.split(':', 1)
			if role == 'fish':
				boy.append(line_spoken)
			if role == 'xiaokefu'
				girl.append(line_spoken)
		else:
		#文件的分别保存操作
			save_file(boy, girl, count)

			boy = []
			girl = []
			count += 1
        
	save_file(boy, girl, count)

	f.close()
    
split_file('record.txt')  #主程序
```

## 课时31： os模块-文件操作

模块就是代码块的打包  .py

模块可以被程序导入  import

**OS 模块**

import os    可以对系统进行操作

os.path  模块

## 课时32：





END;



# 小玩意

## 天气

```python
import urllib.request

import gzip

import json

print('------天气查询------')

def get_weather_data() :

    city_name = input('请输入要查询的城市名称：')
    url1 = 'http://wthrcdn.etouch.cn/weather_mini?city='+urllib.parse.quote(city_name)
    url2 = 'http://wthrcdn.etouch.cn/weather_mini?citykey=101010100'
    #网址1只需要输入城市名，网址2需要输入城市代码
    #print(url1)
    weather_data = urllib.request.urlopen(url1).read()
    #读取网页数据
    weather_data = gzip.decompress(weather_data).decode('utf-8')
    #解压网页数据
    weather_dict = json.loads(weather_data)
    #将json数据转换为dict数据
    return weather_dict

def show_weather(weather_data):

    weather_dict = weather_data 
    #将json数据转换为dict数据
    if weather_dict.get('desc') == 'invilad-citykey':
        print('你输入的城市名有误，或者天气中心未收录你所在城市')
    elif weather_dict.get('desc') =='OK':
        forecast = weather_dict.get('data').get('forecast')
        print('城市：',weather_dict.get('data').get('city'))
        print('温度：',weather_dict.get('data').get('wendu')+'℃ ')
        print('感冒：',weather_dict.get('data').get('ganmao'))
        print('风向：',forecast[0].get('fengxiang'))
        print('风级：',forecast[0].get('fengli'))
        print('高温：',forecast[0].get('high'))
        print('低温：',forecast[0].get('low'))
        print('天气：',forecast[0].get('type'))
        print('日期：',forecast[0].get('date'))
        print('*******************************')
        four_day_forecast =input('是否要显示未来四天天气，是/否：')
        if four_day_forecast == '是' or 'Y' or 'y':
            for i in range(1,5):
                print('日期：',forecast[i].get('date'))
                print('风向：',forecast[i].get('fengxiang'))
                print('风级：',forecast[i].get('fengli'))
                print('高温：',forecast[i].get('high'))
                print('低温：',forecast[i].get('low'))
                print('天气：',forecast[i].get('type'))
                print('--------------------------')
    print('***********************************')

show_weather(get_weather_data())

```





## 百度地图查距离

```python
import json

import requests as rs

def geturl():

    print ("请输入起点所在的城市：")
    origin_region = input(">>>")
    print ("请输入起点位置：")
    origin = input(">>>")
    print ("请输入终点点所在的城市：")
    destination_region = input(">>>")
    print ("请输入终点位置：")
    destination = input(">>>")
    ak="mQOS9IMeEUNiiclPzSVCntdOXCZLjyD7"
    url = "http://api.map.baidu.com/direction/v1?mode=transit&origin=%s&destination=%s&origin_region=%s&&destination_region=%s&output=json&ak=%s" % (origin,destination,origin_region,destination_region,ak)
    return (url,origin_region,origin,destination_region,destination)

def getres(url):

    res = rs.get(url)
    js = json.loads(res.text)
    if js["status"] == 0:
        try:
            if js["result"]["error"] == 0:
                return js["result"]["taxi"]
        except:
            return 0
    return 0

print ('''

---

     Welcome to Location Searching System!       

---

''')

url = geturl()

result = getres(url[0])

if result == 0:

    print ("Error: Cannot find the place!")

else:

    print ("起点： %s  %s" % (url[1],url[2]))
    print ("终点： %s  %s" % (url[3],url[4]))
    print ("距离： %.1f  公里，开车大约需要%d分钟 " % (result["distance"]/1000,result["duration"]/60+1))  
```

## 百度爬虫

```python
import requests

from bs4 import BeautifulSoup

from datetime import datetime

import pandas

import re



data=[]

for k in range(1,33):

    

    date=[]
    media=[]
    title=[]
    link=[]
    newsurl='http://news.baidu.com/ns?word=%28%E6%B7%B1%E5%BA%B7%E4%BD%B3A%2C%E5%BA%B7%E4%BD%B3%E9%9B%86%E5%9B%A2%E8%82%A1%E4%BB%BD%E6%9C%89%E9%99%90%E5%85%AC%E5%8F%B8%2C%E5%BA%B7%E4%BD%B3%E9%9B%86%E5%9B%A2%29&pn='+str((k-1)*20)+'&cl=2&ct=1&tn=newsdy&rn=20&ie=utf-8&bt=1293811200&et=1451577599'
    kv={"User-Agent":"Mozilla/5.0 "}
    res=requests.get(newsurl,headers=kv)
    res.encoding='utf-8'
    soup=BeautifulSoup(res.text,'html.parser')
    for i in range(20):
        news=soup.find_all( 'div', { 'class', 'result'})[i]
    
        h3=news.find( name= "a", attrs={ "target": re.compile( "_blank")})#取出每则新闻的标题
        title.append(h3.text)
    
        m=news.find( name= "p", attrs={ "class": re.compile( "c-author")})#取出每则新闻的发布媒体
        m1=m.text.split()[0]
        media.append(m1)
                
        t=m.text.split()[1]#取出每则新闻的发布时间
        dt=datetime.strptime(t,'%Y年%m月%d日')
        d=dt.strftime('%Y-%m-%d')
        date.append(d)
        
        href=news.h3.a['href']
        link.append(href)
        
        data.append((date[i], title[i], media[i],link[i]))



    print("第" + str(k) + "页完成")

df=pandas.DataFrame(data)

df.to_excel('000016深康佳.xlsx')
```

## 汉诺塔

```python
def hanoi(n, x, y, z):

    if n == 1:
    	print(x, '-->', z)
    else:
    	hanoi(n-1, x, z, y)#将前n-1个盘子从x移动到y上
    	print(x, '-->', z) #将最底下的最后一个盘子从X移动到z上
    	hanoi(n-1, y, x, z)#将y上的n-1个盘子移动到z上

n = int(input('input hanoi level:'))

hanoi(n, 'x', 'y', 'z')
```

## 图片爬虫

```python
import urllib.request

import urllib.error

import os

import sys

import http.server

import http.client

import time

import re

import random

import math

home = 'http://jandan.net/ooxx'

data = None

headers = {'User-Agent':'Mozilla/5.0 (Windows NT 6.1; WOW64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/31.0.1650.63 Safari/537.36'}

enctype = 'utf-8'

proxies = []

error = None

max_error_times = 5        #最多允许失败5次，否则放弃该图片下载

def create_localhost():

    number = int((math.sqrt(5)-1)/2) * len(proxies)
    for x in range(number):
        proxies.append(None)

def get_response(req):

    error_time = 0
    while True:
        try:
            if error_time == max_error_times:
                print('失败次数达%d次......放弃操作' % max_error_times)
                return None
            error_time += 1
            response = urllib.request.urlopen(req)
        except urllib.error.URLError as e:
            if hasattr(e,'code'):         
                print(e.code,e.reason)
                change_proxy()
                continue
            elif hasattr(e,'reason'):
                print(e)
                change_proxy()
                continue
        except (ConnectionResetError,http.client.BadStatusLine) as e:
            print(e)
            change_proxy()
            continue
        except TimeoutError as e:
            print(e)
            print('服务器长时间无响应，自动切换代理.....')
            change_proxy()
            continue
        return response

def get_proxy():

    global data,headers,proxies
    req = urllib.request.Request('http://www.xici.net.co',None,headers)
    response = get_response(req)
    html = response.read().decode('utf-8')
    p = re.compile(r'''<tr\sclass[^>]*>\s+
                                    <td>.+</td>\s+
                                    <td>(.*)?</td>\s+
                                    <td>(.*)?</td>\s+
                                    <td>(.*)?</td>\s+
                                    <td>(.*)?</td>\s+
                                    <td>(.*)?</td>\s+
                                    <td>(.*)?</td>\s+
                                </tr>''',re.VERBOSE)
    proxy_list = p.findall(html)
    for each_proxy in proxy_list[1:]:
        if each_proxy[4] == 'HTTP':
            proxies.append(each_proxy[0]+':'+each_proxy[1])

def change_proxy():

    proxy = random.choice(proxies)
    if proxy == None:
        proxy_support = proxy_support = urllib.request.ProxyHandler({})
    else:
        proxy_support = urllib.request.ProxyHandler({'http':proxy})
    opener = urllib.request.build_opener(proxy_support)
    opener.addheaders = [('User-Agent',headers['User-Agent'])]
    urllib.request.install_opener(opener)
    print('智能切换代理：%s' % ('本机' if proxy==None else proxy))

def get_pic(page):      #生成器，返回一个图片链接

    global data,headers,enctype
    while True:
        url = 'https://yande.re/post?page=%d&tags=rating:e' % page
        print('当前页面：%d' % page)
        req = urllib.request.Request(url,data,headers)
        response = get_response(req)
        if response == None:
            print('获取页面失败.....')
            sys.exit()
        html = response.read().decode(enctype)
        pic = re.compile(r'''<a\s+
                                            class="directlink\s+largeimg"\s+
                                                href="
                                                    (https://files.yande.re/.+?\.jpg)
                                                         "
                                      >''',re.VERBOSE)
        for pic_url in pic.findall(html):
            if re.match(r'https?://files.yande.re.+\.je?pg



[/hide]

,pic_url):      #检测是否是正确的html格式

                yield pic_url
        time.sleep(5)
        page += 1

save_path = 'D:\图片\马克思主义'

def download():

    count = 1
    global data,headers
    for pic_url in get_pic(1):         #get_pic(1)表示从第1页开始下载
        file_name = os.path.split(pic_url)[1]
        if not os.path.isdir(save_path):    #目录不存在就创建
            os.makedirs(save_path)
        with open('%s\\%s' % (save_path , file_name) , 'wb') as f:
            req = urllib.request.Request(pic_url,data,headers)
            response = get_response(req)
            if response == None:
                continue
            f.write(response.read())
            print('本次成功下载第%d个图片! %s' % (count , pic_url))
            count += 1

if name == 'main':

    get_proxy()
    create_localhost()
    download()
```


## 糗事百科抓取

```python
#糗事百科---利用urllib库和正则表达式
import urllib.request
import re
headers = ("User-Agent","Mozilla/5.0 (Windows NT 10.0; WOW64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/49.0.2623.221 Safari/537.36 SE 2.X MetaSr 1.0")
opener = urllib.request.build_opener()
opener.addheaders = [headers]
urllib.request.install_opener(opener)
for k in range(0,10):
    url = "http://www.qiushibaike.com/8hr/page/"+ str(k)
    data = opener.open(url).read().decode('utf-8','ignore')
    pat = '<div class="content">\s*?<span>(.*?)</span>.*?</div>'
    rst = re.compile(pat,re.S).findall(data)
    for i in range(0,len(rst)):
        print(rst[i])
        print("----------------")
        
        
```

## 乌龟吃鱼小游戏

```python
# 游戏场景为范围（x,y）：0 <= x <= 10   ,   0 <= y <= 10
# 游戏生成 1 只乌龟(tortoise)和 10 条鱼。
# 它们的移动方向随机。
# 乌龟的最大移动能力是 2 （Ta可以随机选择移动 1 还是 2 ），鱼的最大移动能力是 1
# 当移动到场景边缘，自动向反方向移动
# 乌龟的初始化体力为100（上限）
# 乌龟每移动一次消耗体力 1 
# 当乌龟和鱼坐标重叠，乌龟吃掉鱼，乌龟体力增加20
# 鱼暂不计算体力
# 当乌龟体力值为 0 （挂掉）或者鱼儿的数量为 0 时，游戏结束。
import random as r



# ---------------------------------------------------------------------------
axis_x = [0,100]      # 设定游戏场地的坐标值范围，圈定边界
axis_y = [0,100]      # 因为在其他函数内部只需要引用不需要修改，所以定义为全局变量
# ---------------------------------------------------------------------------


# 乌龟类，初始化乌龟的坐标和体力值
class Tortoise:
    def __init__(self):
        # 初始化乌龟体力值和位置
        self.energy = 100
        self.tt_x = 5
        self.tt_y = 5

    def ttMoving(self):
        # 乌龟移动方法
        new_x = self.tt_x + (r.choice([-1,1]) * r.randint(1,2))
        new_y = self.tt_y + (r.choice([-1,1]) * r.randint(1,2))

        # 检查移动后乌龟的x坐标是否超越边界
        if new_x < axis_x[0]:
            self.tt_x = axis_x[0] - (new_x - axis_x[0])
        elif new_x > axis_x[1]:
            self.tt_x = axis_x[1] - (new_x - axis_x[1])
        else:
            self.tt_x = new_x

        # 然后检查移动后乌龟的y坐标是否超越边界
        if new_y < axis_y[0]:
            self.tt_y = axis_y[0] - (new_y - axis_y[0])
        elif new_y > axis_y[1]:
            self.tt_y = axis_y[1] - (new_y - axis_y[1])
        else:
            self.tt_y = new_y

        # 每次调用移动方法，乌龟体力值减 1 
        # 调整好乌龟移动后的坐标后，返回x和y坐标的值
        self.energy -= 1
        return (self.tt_x,self.tt_y)

    # 乌龟吃鱼时的操作
    def eat_Fish(self):
        self.energy += 1
        if self.energy > 100:
            self.energy = 100


# 鱼儿类，初始化鱼儿的位置，和移动能力
class Fish:
    def __init__(self):
        # 初始化鱼儿的位置
        self.fs_x = 0
        self.fs_y = 0
        self.step = 1

    def fsMoving(self):
        # 鱼儿移动方法
        new_x = self.fs_x + (r.choice([-1,1]) * self.step)
        new_y = self.fs_y + (r.choice([-1,1]) * self.step)

        # 然后检查鱼儿移动后x坐标是否超越边界
        if new_x < axis_x[0]:
            self.fs_x = axis_x[0] - (new_x - axis_x[0])
        elif new_x > axis_x[1]:
            self.fs_x = axis_x[1] - (new_x - axis_x[1])
        else:
            self.fs_x = new_x

        # 再检查鱼儿移动后y坐标是否超越边界
        if new_y < axis_y[0]:
            self.fs_y = axis_y[0] - (new_y - axis_y[0])
        elif new_y > axis_y[1]:
            self.fs_y = axis_y[1] - (new_y - axis_y[1])
        else:
            self.fs_y = new_y

        # 调整好鱼儿移动后的坐标后，返回x和y坐标的值
        return (self.fs_x,self.fs_y)


# 游戏启动函数，生成乌龟BOSS和十条鱼儿对象
def playground():
    # 生成乌龟的实例化对象
    Boss = Tortoise()

    # 生成十条鱼儿的实例化对象
    fishs = []
    for i in range(10):
        new_fish = Fish()
        fishs.append(new_fish)
    # 启动游戏
    while True:
        if len(fishs) == 0:
            print("Game Over\n鱼儿被乌龟吃完了，游戏结束！")
            break
        if Boss.energy == 0:
            print("Game Over\n乌龟累死了，游戏结束！")
            break

        pos = Boss.ttMoving()
        for each_fish in fishs[:]:
            if each_fish.fsMoving() == pos:
                Boss.eat_Fish()
                fishs.remove(each_fish)
                print("有一条鱼儿被吃掉了...")
```



## 煎蛋网妹子图的爬取

```python
from selenium import webdriver
import os
from selenium.webdriver.common.by import By
from selenium.webdriver.support.ui import WebDriverWait
import urllib.request
from selenium.webdriver.support import expected_conditions as EC
import re
import socket


socket.setdefaulttimeout(10.0)
# 缓存
browser = webdriver.PhantomJS(service_args=['--disk-cache=true'])

wait = WebDriverWait(browser, 10)


# --disk-cache=true
#模仿点击事件
def search():
    try:
        submit = WebDriverWait(browser, 10).until(
                EC.element_to_be_clickable(
                        (By.CSS_SELECTOR, '#comments > div:nth-child(4) > div > a.previous-comment-page')))
        submit.click()

    except:
        pass

#初始界面的页码
def get_pagenum(url):
    html = open_url(url).decode('UTF-8')
    p = re.compile(r'.*?current-comment-page">\[(.*?)]</span>', re.S)
    num = re.findall(p, html)[0]
    return num

#保存图片
def saveimage(floder, imageattr):
    for each in imageattr:
        filename = each.split('/')[-1]
        print('正在保存图片%s' % filename)
        try:
            urllib.request.urlretrieve(each, filename, schedule)
        except:
            pass

#下载图片的过程用xx%表示
def schedule(a, b, c):
    """
    :param a:已经下载的数据块
    :param b: 数据块的大小
    :param c: 远程文件的大小
    :return:返回百分数
    """
    per = 100.0 * a * b / c
    if per > 100:
        per = 100
    print('%.2f%%' % per)

#利用获取的html利用正则搜索到图片地址并放到列表中
def find_images(html):
    try:
        p = re.compile('<p>.*?<img src="(.*?\.jpg)".*?</p>', re.S)
        imagelist = re.findall(p, html)
        imageattr = []
        for each in imagelist:
            imagelist = 'http:' + each
            imageattr.append(imagelist)
        return imageattr
    except:
        pass

#打开url返回源代码
def open_url(url):
    # 读取url
    req = urllib.request.Request(url)
    req.add_header('User_Agent',
                   'Mozilla/5.0 (Windows NT 6.1; WOW64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/45.0.2454.101 Safari/537.36')
    try:
        response = urllib.request.urlopen(url)
        html = response.read()
        return html
    except:
        pass

#主函数，os.chdir后面自己建一个文件夹自己命名。
def main():
    os.chdir('picture2')
    url = 'http://jandan.net/ooxx/'
    browser.get(url)
    pagenumber = int(get_pagenum(url))
    a = pagenumber
    for i in range(pagenumber - 1):
        print('第%d页内容正在加载' % (a - i))
        html = browser.page_source
        imageattr = find_images(html)
        saveimage('picture2', imageattr)
        search()


if __name__ == '__main__':
    main()
    
```

## MP3 程序拷贝

**故事：**

家里老爸老妈买了一个广场舞那种音箱，想插U盘听歌，好不容易教会了他们用百度音乐下载mp3音乐，但一直没教会他们如何把下载的mp3文件拷到U盘去，所以借着学习python练手，写了这么一个小东东。

**功能：**

​	1、把指定目录下的后缀名为mp3的文件拷贝到指定的U盘上去

​	2、可以对用本程序拷贝的文件在界面进行查看和单曲删除，删除时如果设定的下载目录有同名文件，也一并删除

​	3、歌名进行排序，每个进行编号（为了让老年人在放的时候，可以直接根据顺序号来定位找歌）
**操作：**
​    1、打开程序会自动识别U盘，如果有多个，需手工选择盘符
​    2、U盘初始化（写配置数据）
​    3、下载目录设置：设置电脑上的mp3所在目录
​    4、一键拷贝：将上步设置的目录下所有后缀名为mp3的文件，拷入U盘，并排序编号。
​    5、歌曲查看：查看U盘上的mp3文件
​    6、单曲删除：删除U盘上的mp3文件，如果电脑上设置mp3所在目录也有该文件，一并删除。

```python
__author__ = 'my.cl'
# -*- coding:Utf-8 -*-
import pickle
from tkinter import ttk
from tkinter.messagebox import *
from tkinter.filedialog import *
import win32file
import wmi
import sys


def read_cfg_file():
    s=os.path.join((w.get() + os.sep), 'UDiskMp3.cfg')
    if os.path.isfile(os.path.join(s)):
        with open(s, 'rb') as f1:
            temp_1=pickle.load(f1)
            temp_2=pickle.load(f1)
            temp_3=pickle.load(f1)
        return [temp_1, temp_2, temp_3]
    else:
        showwarning('', 'U盘选择错误，请重新选择！')
        return False


def write_cfg_file(temp_1, temp_2, temp_3):
    s=os.path.join((w.get() + os.sep), 'UDiskMp3.cfg')
    with open(s, 'wb') as f1:
        pickle.dump(temp_1, f1)
        pickle.dump(temp_2, f1)
        pickle.dump(temp_3, f1)


def get_fs_info():
    """
    获取文件系统信息。
    包含分区的大小、已用量、可用量、使用率、挂载点信息。
    """
    c = wmi.WMI()
    tmpdict = {}
    for physical_disk in c.Win32_DiskDrive():
        for partition in physical_disk.associators("Win32_DiskDriveToDiskPartition"):
            for logical_disk in partition.associators("Win32_LogicalDiskToPartition"):
                tmpdict[logical_disk.Caption] = int(int(logical_disk.Size) / 1024 / 1024 / 1024)
    return tmpdict


def is_UDisk(drives):
    """
    检则小于指定容量的分区并返回列表。
    """
    UDisk=[]
    for item in drives:
        if drives[item]<40:
            UDisk.append(item)
    return UDisk


def cfg_key_check():
    """
    检测U盘配置文件keys
    """
    try:
        rcf=read_cfg_file()
        if not rcf:
            return False
        elif rcf[0]=='224002':
            return True
        else:
            return False
    except pickle.UnpicklingError:
        # showerror('配置文件检测', message='U盘配置文件损坏，请重新进行U盘初始化后操作！')
        return False


def check_free_space(source_file):
    """
    检查文件是否小于U盘容量，注意U盘位置需修改为变量进行检查
    """
    sectorsPerCluster, bytesPerSector, numFreeClusters, totalNumClusters = win32file.GetDiskFreeSpace("f:/")
    disk_free_space= (numFreeClusters * sectorsPerCluster * bytesPerSector) / (1024 * 1024)
    file_size=(os.path.getsize(source_file)) / (1024 * 1024)
    if disk_free_space > file_size + 5:
        return True
    else:
        return False


def check_front_str(num):
    if len(str(num)) == 1:
        str_num = '000' + str(num)
    elif len(str(num)) == 2:
        str_num = '00' + str(num)
    elif len(str(num)) == 3:
        str_num = '0' + str(num)
    else:
        str_num = str(num)
    return str_num


def disk_check():
    """
    U盘检测
    """
    global udisk_path
    fs=is_UDisk(get_fs_info())
    if len(fs)<1:  # 一个盘符也没找到
        showwarning('', '请检查U盘是否插好，没找到U盘呢！')
    else:  # 找到1个及以上盘符
        udisk_path=tuple(fs)
        exit_path=[]
        for each in udisk_path:  # 把每个有UDiskMp3.cfg的盘符添加到exip_path
            s=os.path.join((each + os.sep), 'UDiskMp3.cfg')
            if os.path.isfile(os.path.join(s)):
                exit_path.append(each)
        if len(exit_path)>0:  # 如果有UDiskMp3.cfg的盘符大于等于1个
            buttonDiskInitial['state']=NORMAL
            buttonMp3FileView['state']=NORMAL
            buttonMp3PathSet['state']=NORMAL
            buttonOneKeyCopy['state']=NORMAL
            w['values']=exit_path
        else:
            w['values']=tuple(fs)
            buttonDiskInitial['state']=NORMAL
            showwarning(title='U盘检测', message='请选择U盘，进行初始化！')


def isrename(soucre_name_all, dec_path):  # f_name_all如果去掉前四位在U盘上存在，则将U盘上的文件重命名f_name_all
    dec_mp3=os.listdir(dec_path)
    for each in dec_mp3:
        if os.path.splitext(each)[5:]==soucre_name_all:
            return True
    return False


def one_key_copy():
    global mp3_path
    rcf=read_cfg_file()
    mp3_path=rcf[1]
    usb_path=w.get() + os.sep
    list_mp3=[]
    if mp3_path=='' or (not os.path.exists(mp3_path)):
        showwarning(title='文件拷贝', message='文件源目录没设置，请先设置！')
        return False
    list_comper_mp3=os.listdir(mp3_path)
    dict_mp3=rcf[2]
    list_mp3_temp=list(dict_mp3)
    list_mp3_temp.remove('last_num')
    # 让U盘文件与字典保持一致，字典排序后重命名U盘文件
    for each in list_mp3_temp:  # 字典文件中存在
        if os.path.isfile(os.path.join(usb_path, check_front_str(dict_mp3[each]) + '_' + each + '.mp3')):  # U盘带序号文件存在
            list_mp3.append(os.path.splitext(each)[0])
        elif isrename(each, usb_path):  # U盘文件存在，序号不同
            list_mp3.append(os.path.splitext(each)[0])
        else:  # U盘文件不存在
            dict_mp3.pop(each)
    # 存在的文件排序后重新编号
    list_mp3.sort()
    for i in range(0, len(list_mp3)):
        dict_mp3[list_mp3[i]]=i + 1
    dict_mp3['last_num']=len(list_mp3) + 1
    for each in dict_mp3:  # 根据排序编号后的内容重命名
        if each == 'last_num':
            pass
        elif os.path.exists(os.path.join(usb_path, check_front_str(dict_mp3[each]) + '_' + each + '.mp3')):  # U盘带序号文件存在
            pass
        else:
            dec_mp3=os.listdir(usb_path)
            for each_one in dec_mp3:
                if os.path.splitext(each_one)[0][5:] in dict_mp3:
                    os.rename(usb_path + each_one, usb_path +
                              check_front_str(dict_mp3[os.path.splitext(each_one)[0][5:]]) + '_' + each_one[5:])
    write_cfg_file(rcf[0], rcf[1], dict_mp3)

    if 'last_num' in dict_mp3:
        last_num=dict_mp3['last_num']
    else:
        last_num=1
    for each_file in list_comper_mp3:  # 对每个拷贝的源文件
        if os.path.splitext(each_file)[1] != '.mp3':  # 后缀名不是.mp3的不拷贝
            pass
        elif not check_free_space(os.path.join(mp3_path, each_file)):  # 磁盘空间不足的提示
            showwarning(title='文件拷贝', message='U盘空间已满，无法再写入更多文件，请删除部分文件再进行拷贝！')
            break
        elif os.path.splitext(each_file)[0] in dict_mp3:  # 已拷贝过的
            pass  # 目标文件存在，不处理
        else:  # 新增的拷贝
            str_num=check_front_str(last_num)
            open(os.path.join(w.get() + os.sep, str_num + "_" +
                              each_file), "wb").write(open(os.path.join(mp3_path, each_file), "rb").read())
            dict_mp3[os.path.splitext(each_file)[0]] = last_num
            last_num +=1

    dict_mp3['last_num']=len(list_mp3)
    write_cfg_file(rcf[0], rcf[1], dict_mp3)
    mp3_file_view()
    buttonMp3FileView['state']=NORMAL
    showinfo(title='文件拷贝', message='文件拷贝完成！')


def one_file_del():

    try:
        select_item=treeMp3All.item(treeMp3All.selection()[0], "values")
        usb_path=w.get() + os.sep
        filename = usb_path + check_front_str(int(select_item[0])) + '_' + select_item[1] + '.mp3'

        if os.path.exists(filename):
            os.remove(filename)
            rcf=read_cfg_file()
            mp3_in_path=rcf[1]
            comper_mp3_name=os.path.join(mp3_in_path, select_item[1] + '.mp3')
            if os.path.exists(comper_mp3_name):
                os.remove(comper_mp3_name)
            mp3_file_view()
    except IndexError:
        showwarning(title='单曲删除', message='请先选择需删除的文件，再进行删除！')


def mp3_file_view():
    rcf=read_cfg_file()
    usb_path=w.get() + os.sep
    list_mp3=[]
    dict_mp3=rcf[2]
    list_mp3_temp=list(dict_mp3)
    list_mp3_temp.remove('last_num')
    # 让U盘文件与字典保持一致，字典排序后重命名U盘文件
    for each in list_mp3_temp:  # 字典文件中存在
        if os.path.isfile(os.path.join(usb_path, check_front_str(dict_mp3[each]) + '_' + each + '.mp3')):  # U盘带序号文件存在
            list_mp3.append(os.path.splitext(each)[0])
        elif isrename(each, usb_path):  # U盘文件存在，序号不同
            list_mp3.append(os.path.splitext(each)[0])
        else:  # U盘文件不存在
            dict_mp3.pop(each)
    # 存在的文件排序后重新编号
    list_mp3.sort()
    for i in range(0, len(list_mp3)):
        dict_mp3[list_mp3[i]]=i + 1
    dict_mp3['last_num']=len(list_mp3) + 1
    for each in dict_mp3:  # 根据排序编号后的内容重命名
        if each == 'last_num':
            pass
        elif os.path.exists(os.path.join(usb_path, check_front_str(dict_mp3[each]) + '_' + each + '.mp3')):  # U盘带序号文件存在
            pass
        else:
            dec_mp3=os.listdir(usb_path)
            for each_one in dec_mp3:
                if os.path.splitext(each_one)[0][5:] in dict_mp3:
                    os.rename(usb_path + each_one, usb_path +
                              check_front_str(dict_mp3[os.path.splitext(each_one)[0][5:]]) + '_' + each_one[5:])
    write_cfg_file(rcf[0], rcf[1], dict_mp3)

    rcf=read_cfg_file()
    dict_mp3_in=rcf[2]
    items=[]
    for each in dict_mp3_in:
        if each != 'last_num':
            items.append([dict_mp3_in[each], each])
    items.sort()
    x = treeMp3All.get_children()
    for item in x:
        treeMp3All.delete(item)
    for item in items:
        treeMp3All.insert('', item[0], values=item)
    sb = Scrollbar(root)
    sb.grid(row=2, column=3, rowspan=4, sticky='ns', padx=5, pady=5)
    treeMp3All['yscrollcommand']=sb.set
    sb.config(command=treeMp3All.yview)

    buttonOneFileDel['state']=NORMAL


def mp3_path_set():
    rcf=read_cfg_file()
    if rcf[1]=='':
        in_mp3_path = askdirectory()
        if in_mp3_path=='':
            showerror(title='目录设置', message='你没选择目录，请重新设置！')
        else:
            write_cfg_file(rcf[0], in_mp3_path, rcf[2])
            buttonOneKeyCopy['state']=NORMAL
            showinfo(title='目录设置', message='目录设置成功！可开始一键拷贝!')
    else:
        aq=askyesno(title='目录设置', message='目录已设置为%s,你需要修改吗？' % rcf[1])
        if aq:
            in_mp3_path = askdirectory()
            if in_mp3_path=='':
                showerror(title='目录设置', message='你没选择目录，请重新设置！')
            else:
                write_cfg_file(rcf[0], in_mp3_path, rcf[2])
                showinfo(title='目录设置', message='目录设置成功！可开始一键拷贝!')


def disk_initial():
    s=os.path.join((w.get() + os.sep), 'UDiskMp3.cfg')
    d={}
    d['last_num']=1
    if os.path.isfile(os.path.join(s)):
        if cfg_key_check():
            ask_initial=askyesno(title='U盘初始化确认！',
                                 message='U盘已初始化，重新初始化后可能会导致歌曲顺序混乱，你是否需要重新进行初始化？')
            if ask_initial:
                write_cfg_file('224002', '', d)
                showinfo(title='初始化', message='初始化成功，请设置Mp3下载目录！')
            else:
                pass
        else:
            showinfo('U盘初始化', message='U盘已初始化，但配置文件损坏，将进行初始化！')
            write_cfg_file('224002', '', d)
            showinfo(title='初始化', message='初始化成功，请设置Mp3下载目录！！')
    else:
        write_cfg_file('224002', '', d)
        buttonMp3PathSet['state']=NORMAL
        showinfo(title='初始化', message='初始化成功，请设置Mp3下载目录！！')


def quit_app():
    sys.exit()


def about():
    showinfo(title='关于', message='软件版本：0.9beat\n\n软件作者：老忘\n\nEmail: mycl@qq.com')

root = Tk()

root.withdraw()  # 隐藏
# 移到屏幕外，避免闪烁
root.geometry('+%d+%d' % (root.winfo_screenwidth() + 100, root.winfo_screenheight() + 100))

root.title('下载Mp3音乐文件U盘管理【老年人专用】')
udisk_path=()
mp3_path=''

buttonDistCheck = Button(root, text='U盘检测', command=disk_check)
buttonDistCheck.grid(row=0, column=2, padx=5, pady=5)
buttonDiskInitial = Button(root, text='U盘初始化', state=DISABLED, command=disk_initial)
buttonDiskInitial.grid(row=0, column=1, padx=5, pady=5)
buttonMp3PathSet = Button(root, text='设置Mp3目录 ', state=DISABLED, command=mp3_path_set)
buttonMp3PathSet.grid(row=6, column=1, padx=5, pady=5)
buttonOneKeyCopy = Button(root, text='一键拷贝', state=DISABLED, command=one_key_copy)
buttonOneKeyCopy.grid(row=2, column=0, padx=5, pady=5)
buttonOneFileDel = Button(root, text='单曲删除', state=DISABLED, command=one_file_del)
buttonOneFileDel.grid(row=3, column=0, padx=5, pady=5)

labelUDisk=Label(root, text='操作U盘盘符：')
labelUDisk.grid(row=1, column=1, padx=5, pady=0)

w=Spinbox(root, values=udisk_path)
w.grid(row=1, column=2, padx=5, pady=0)

treeMp3All = ttk.Treeview(root, show="headings", columns=('col1', 'col2'))
treeMp3All.grid(row=2, column=1, rowspan=4, columnspan=2, padx=5, pady=5)
treeMp3All.column('col1', width=50, anchor='center')
treeMp3All.column('col2', width=300, anchor='center')
treeMp3All.heading('col1', text='序号')
treeMp3All.heading('col2', text='歌名')

buttonMp3FileView = Button(root, text='U盘歌曲查看', state=DISABLED, command=mp3_file_view)
buttonMp3FileView.grid(row=4, column=0, padx=5, pady=5)

buttonQuitApp = Button(root, text='退出程序', command=quit_app)
buttonQuitApp.grid(row=6, column=2, padx=5, pady=5)

menubar = Menu(root)

filemenu = Menu(menubar, tearoff=False)
musicmenu = Menu(menubar, tearoff=False)
filemenu.add_separator()
filemenu.add_command(label='U盘检测', command=disk_check)
filemenu.add_command(label='U盘初始', command=disk_initial)
filemenu.add_command(label='下载目录设置', command=mp3_path_set)
filemenu.add_separator()
filemenu.add_command(label='退出', command=quit_app)
musicmenu.add_separator()
musicmenu.add_command(label='一键拷贝', command=one_key_copy)
musicmenu.add_command(label='U盘歌曲查看', command=mp3_file_view)
musicmenu.add_command(label='单曲删除', command=one_file_del)
menubar.add_cascade(label='开始', menu=filemenu)
menubar.add_cascade(label='歌曲', menu=musicmenu)
menubar.add_command(label='关于', command=about)
root.config(menu=menubar)


root.update()  # 刷新
root.deiconify()  # 显示，使窗口尺寸属性可用
root.withdraw()  # 再隐藏
app_left = (root.winfo_screenwidth() - root.winfo_width()) // 2  # root.winfo_screenwidth()屏幕宽， root.winfo_width()程序宽
app_top = (root.winfo_screenheight() - root.winfo_height()) // 2 - 50
# 屏幕居中
root.geometry('+%d+%d' % (app_left, app_top))
root.deiconify()    # 显示
root.resizable(False, False)

disk_check()
root.mainloop()
```



# tkinter





## 学习资源

****Python基本安装：

    * http://www.python.org/ 官方标准Python开发包和支持环境，同时也是Python的官方网站；
    * http://www.activestate.com/ 集成多个有用插件的强大非官方版本，特别是针对Windows环境有不少改进；

Python文档：

    * http://www.python.org/doc/current/lib/lib.html Python库参考手册。
    * http://www.byteofpython.info/ 可以代替Tutorial使用，有中文译版的入门书籍。
    * http://diveintopython.org/ 一本比较全面易懂的入门书，中文版翻译最近进步为很及时的5.4了。
    * http://www.python.org/peps/pep-0008.html 建议采用的Python编码风格。
    * http://doc.zoomquiet.org/ 包括Python内容的一个挺全面的文档集。

常用插件：

    * http://www.pfdubois.com/numpy/ Python的数学运算库，有时候一些别的库也会调用里面的一些功能，比如数组什么的；
    * http://www.pythonware.com/products/pil/ Python下著名的图像处理库Pil；
    * http://simpy.sourceforge.net/ 利用Python进行仿真、模拟的解决方案；
    * Matplotlib 据说是一个用来绘制二维图形的Python模块，它克隆了许多Matlab中的函数， 用以帮助Python用户轻松获得高质量(达到出版水平)的二维图形；
    * http://www.amk.ca/python/code/crypto python的加解密扩展模块；
    * http://cjkpython.i18n.org/ 提供与python有关的CJK语言支持功能：转码、显示之类。
    * Psyco、Pyrex：两个用于提高Python代码运行效率的解决方案；
    * Pyflakes、PyChecker、PyLint：都是用来做Python代码语法检查的工具。
    * http://wxpython.sourceforge.net/ 基于wxWindows的易用且强大的图形界面开发包wxPython；
    * http://www.pygame.org/ 用Python帮助开发游戏的库，也可以用这个来播放视频或者音频什么的，大概依靠的是SDL；
    * http://starship.python.net/crew/theller/py2exe/ win下将Python程序编译为可执行程序的工具，是一个让程序脱离Python运行环境的办法，也可以生成Windows服务或者COM组件。其他能完成Python脚本到可执行文件这个工作的还有Gordon McMillan's Installer、Linux专用的freeze以及py2app、setuptools等。不过此类工具难免与一些模块有一些兼容性的问题，需要现用现测一下。
    * 嵌入式数据库：BerkeleyDB的Python版，当然还有其他的好多。
    * PEAK提供一些关于超轻量线程框架等基础性重要类库实现。

部分常用工具：

    * http://www.scons.org/ Java有Ant这个巨火的构建工具，Python的特性允许我们构建更新类型的构建工具，就是scons了。
    * Python Sidebar for Mozilla FireFox的一个插件，提供一个用来查看Python文档、函数库的侧边栏。
    * IPython 很好用的Python Shell。wxPython发行版还自带了PyCrust、PyShell、PyAlaCarte和PyAlaMode等几个工具，分别是图形界面Shell和代码编辑器等，分别具有不同特点可以根据自己的需要选用。
    * Easy Install 快速安装Python模块的易用性解决方案。

推荐资源：

    * Parnassus山的拱顶 巨大的Python代码库，包罗万象。既可以从上面下载代码参考学习，同时也是与Python有关程序的大列表。
    * Python号星际旅行船 著名Python社区，代码、文档、高人这里都有。
    * faqts.com的Python程序设计知识数据库 Python程序设计知识库，都是与Python有关的程序设计问题及解决方法。
    * 啄木鸟 Pythonic 开源社区 著名的（也可以说是最好的）国内Python开源社区。

代码示例：

    * http://newedit.tigris.org/technical.htm Limodou的NewEdit编辑器的技术手册，讨论了一些关于插件接口实现、i18实现、wxPython使用有关的问题，值得参考。

其他东西：

    * http://www.forum.nokia.com/main/0,,034-821,00.html Nokia居然发布了在Series 60系统上运行Python程序（图形界面用wxPython）的库，还有一个Wiki页是关于这个的：http://www.postneo.com/postwiki/moin.cgi/PythonForSeries60 。Python4Symbian这个页面是记录的我的使用经验。
    * pyre：使用Python完成高性能计算需求的包，真的可以做到么？还没研究。
    * Parallel Python：纯Python的并行计算解决方案。相关中文参考页面
    * Pexpect：用Python作为外壳控制其他命令行程序的工具（比如Linux下标准的ftp、telnet程序什么的），还没有测试可用程度如何。
    * pyjamas：Google GWT的Python克隆，还处在早期版本阶段。
    * Durus：Python的对象数据库。

有意思的东西：

    * Howie：用Python实现的MSN对话机器人。
    * Cankiri：用一个Python脚本实现的屏幕录像机。

参考资料

    * ZDNET文章：学习Python语言必备的资源
    * Pythonic Web 应用平台对比
    * 在wxPython下进行图像处理的经验 （其实，仅使用wxPython也可以完成很多比较基础的图像处理工作，具体可以参照《wxPython in Action》一书的第12节）
    * 通过win32扩展接口使用Python获得系统进程列表的方法
    * 如何获得Python脚本所在的目录位置
    * Python的缩进问题
    * py2exe使用中遇到的问题
    * idle的中文支持问题
    * 序列化存储 Python 对象

Python IDE

我的IDE选择经验

    * http://www.xored.com Trustudio 一个基于Eclipse的、同时支持Python和PHP的插件，曾经是我最喜欢的Python IDE环境，功能相当全了，不过有些细节不完善以致不大好用。
    * http://pydev.sourceforge.net/ 另一个基于Eclipse的，非常棒的Python环境，改进速度非常快，现在是我最喜欢的IDE。
    * http://www-900.ibm.com/developerWorks/cn/opensource/os-ecant/index.shtml 用 Eclipse 和 Ant 进行 Python 开发
    * http://www.die-offenbachs.de/detlev/eric3.html ERIC3 基于QT实现的不错的PYTHON IDE,支持调试，支持自动补全，甚至也支持重构，曾经在Debian下用它，但图形界面开发主要辅助qt，我倾向wxpython，所以最后还是放弃了这个。
    * http://www.scintilla.org/ 同时支持Win和Linux的源代码编辑器，似乎支持Python文件的编辑。
    * http://boa-constructor.sourceforge.net/ 著名的基于WxPython的GUI快速生成用的Python IDE，但是开发进度实在太差了……
    * http://pype.sourceforge.net/ 成熟的Python代码编辑器，号称功能介于EMACS和IDLE之间的编辑器。
    * http://www.stani.be/python/spe SPE：号称是一个Full Featured编辑器，集成WxGlade支持GUI设计。