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

## 课时28：













END;



# 小玩意

## 天气

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



## 百度地图查距离

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
************************************************
     Welcome to Location Searching System!       
************************************************
''')

url = geturl()
result = getres(url[0])
if result == 0:
    print ("Error: Cannot find the place!")
else:
```python
print ("起点： %s  %s" % (url[1],url[2]))
print ("终点： %s  %s" % (url[3],url[4]))
print ("距离： %.1f  公里，开车大约需要%d分钟 " % (result["distance"]/1000,result["duration"]/60+1))  
```
## 百度爬虫

import requests
from bs4 import BeautifulSoup
from datetime import datetime
import pandas
import re



data=[]

for k in range(1,33):
​    
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



## 汉诺塔

def hanoi(n, x, y, z):

	if n == 1:
		print(x, '-->', z)
	else:
		hanoi(n-1, x, z, y)#将前n-1个盘子从x移动到y上
		print(x, '-->', z) #将最底下的最后一个盘子从X移动到z上
		hanoi(n-1, y, x, z)#将y上的n-1个盘子移动到z上

n = int(input('input hanoi level:'))
hanoi(n, 'x', 'y', 'z')