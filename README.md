# python-面试通关宝典
秋招的小伙伴，有面Python开发方向的，看这一个repo就够啦😘
### 语言特性

1.谈谈对 Python 和其他语言的区别

```markdown
Python属于解释型语言，当程序运行时，是一行一行的解释，并运行，所以调式代码很方便，开发效率高，
还有龟叔给Python定位是任其自由发展、优雅、明确、简单，所以在每个领域都有建树，所有它有着非常强大的第三方库，
特点：
语法简洁优美，功能强大，标准库与第三方库都非常强大，而且应用领域也非常广
可移植性，可扩展性，可嵌入性
缺点：
　　运行速度慢，

- 解释型
    - python/php
- 编译型
    - c/java/c#
        
- Python弱类型
```

2.简述解释型和编译型编程语言

```markdown
解释型：就是边解释边执行（Python，php）
编译型：编译后再执行（c、java、c#）
```

3.Python 的解释器种类以及相关特点？

```markdown
CPython

是官方版本的解释器：CPython。是使用C语言开发的，所以叫CPython。在命令行下运行python就是启动CPython解释器。
CPython是使用最广的Python解释器。教程的所有代码也都在CPython下执行。

IPython
IPython是基于CPython之上的一个交互式解释器，也就是说，IPython只是在交互方式上有所增强，但是执行Python代码的功能和CPython是完全一样的。CPython用>>>作为提示符，而IPython用In [序号]:作为提示符。
PyPy

由Python写的解释器，它的执行速度是最快。PyPy采用JIT技术，对Python代码进行动态编译（注意不是解释），
绝大部分Python代码都可以在PyPy下运行，但是PyPy和CPython有一些是不同的，这就导致相同的Python代码在两种解释器下执行可能会有不同的结果。

Jython
Jython是运行在Java平台上的Python解释器，可以直接把Python代码编译成Java字节码执行。

IronPython
IronPython和Jython类似，只不过IronPython是运行在.Net平台上的Python解释器，可以直接把Python代码编译成.Net的字节码。

小结：
　　Python的解释器很多，但使用最广泛的还是CPython。如果要和Java或.Net平台交互，最好的办法不是用Jython或IronPython，而是通过网络调用来交互，确保各程序之间的独立性。
```

4.说说你知道的Python3 和 Python2 之间的区别？

```markdown
1：打印时，py2需要可以不需要加括号，py3 需要
python 2 ：print ('lili')   ,   print 'lili'
python 3 : print ('lili')   
python3 必须加括号

exec语句被python3废弃，统一使用exec函数

2：内涵
Python2：1，臃肿，源码的重复量很多。
          　  2，语法不清晰，掺杂着C，php，Java，的一些陋习。
Python3：几乎是重构后的源码，规范，清晰，优美。

3、输出中文的区别
python2：要输出中文 需加 # -*- encoding:utf-8 -*-
Python3 ： 直接搞

4：input不同
python2 ：raw_input
python3 ：input 统一使用input函数

5：指定字节
python2在编译安装时，可以通过参数-----enable-unicode=ucs2 或-----enable-unicode=ucs4分别用于指定使用2个字节、4个字节表示一个unicode；
python3无法进行选择，默认使用 ucs4
查看当前python中表示unicode字符串时占用的空间：

impor sys
print（sys.maxunicode）
#如果值是65535，则表示使用usc2标准，即：2个字节表示
#如果值是1114111，则表示使用usc4标准，即：4个字节表示

6：
py2：xrange
　　　　range
py3：range  统一使用range，Python3中range的机制也进行修改并提高了大数据集生成效率

7：在包的知识点里
包：一群模块文件的集合 + __init__
区别：py2 ： 必须有__init__
　　　py3：不是必须的了

8：不相等操作符"<>"被Python3废弃，统一使用"!="

9：long整数类型被Python3废弃，统一使用int

10：迭代器iterator的next()函数被Python3废弃，统一使用next(iterator)

11：异常StandardError 被Python3废弃，统一使用Exception

12：字典变量的has_key函数被Python废弃，统一使用in关键词

13：file函数被Python3废弃，统一使用open来处理文件，可以通过io.IOBase检查文件类型
```

5.Python3 和 Python2 中 int 和 long 区别？

```markdown
在python3里，只有一种整数类型int,大多数情况下，和python２中的长整型类似。
```

6.xrange 和 range 的区别？

```markdown
xrange用法与range完全相同，所不同的是生成的不是一个数组，而是一个生成器。
要生成很大的数字序列的时候，用xrange会比range性能优很多，因为不需要一上来就开辟一块很大的内存空间，这两个基本上都是在循环的时候用。

在 Python 3 中，range() 是像 xrange() 那样实现，xrange()被抛弃。
```



### 编码规范

7.什么是 PEP8?

```markdown
PEP是 Python Enhancement Proposal 的缩写，翻译过来就是 Python增强建议书
简单说就是一种编码规范，是为了让代码“更好看”，更容易被阅读
具体可参考：
https://www.python.org/dev/peps/pep-0008/
```

8.了解 Python 之禅么？

```markdown
import this
```

9.了解 dosctring 么？

```markdown
Python有一个很奇妙的特性，称为 文档字符串 ，它通常被简称为 docstrings 。DocStrings是一个重要的工具，由于它帮助你的程序文档更加简单易懂，你应该尽量使用它。你甚至可以在程序运行的时候，从函数恢复文档字符串。
使用魔法方法'__doc__'可以打印docstring的内容
```

10.了解类型注解么？

```markdown
def add(x:int, y:int) -> int:
    return x + y
用 : 类型 的形式指定函数的参数类型，用 -> 类型 的形式指定函数的返回值类型
```

11.例举你知道 Python 对象的命名规范，例如方法或者类等

```
类名都使用首字母大写开头(Pascal命名风格)的规范；
全局变量全用大写字母，单词之间用 _分割；
普通变量用小写字母，单词之间用 _分割；
普通函数和普通变量一样；
私有函数以 __ 开头（2个下划线），其他和普通函数一样；

```

12.Python 中的注释有几种？

```markdown
单行注释，多行注释，docstring注释
```

13.如何优雅的给一个函数加注释？

```markdown
在函数逻辑行的首行使用""" xxx """给函数添加注释，注释中可包含函数参数的说明，返回值说明等
def foo(bar):
    """
    This is an example.
    :param bar: explain param bar
    """
    return bar
```

14.如何给变量加注释？

```python
参数注释：以冒号（:）标记
返回值注释：以 -> 标记
示例：
def add(x:int, y:int) -> int:
    return x + y
```

15.Python 代码缩进中是否支持 Tab 键和空格混用。

```markdown
支持，Python 并没有强制要求你用Tab缩进或者用空格缩进，但在 PEP8中，建议使用4个空格来缩进
```

16.是否可以在一句 import 中导入多个库?

```python
可以的
import json,random,requests
```

17.在给 Py 文件命名的时候需要注意什么?

```markdown
全小写，单词之间使用下划线分隔
```

18.例举几个规范 Python 代码风格的工具

```markdown
pylint,black,pycharm也带有pep8的代码规范工具
```



### 数据类型

#### 字符串

19.列举 Python 中的基本数据类型？

```markdown
Python3 中有六个标准的数据类型：

Number（数字）
String（字符串）
List（列表）
Tuple（元组）
Set（集合）
Dictionary（字典）
Python3 的六个标准数据类型中：

不可变数据（3 个）：Number（数字）、String（字符串）、Tuple（元组）；
可变数据（3 个）：List（列表）、Dictionary（字典）、Set（集合）。
```

20.如何区别可变数据类型和不可变数据类型

```markdown
Python3 的六个标准数据类型中：

不可变数据（3 个）：Number（数字）、String（字符串）、Tuple（元组）；
可变数据（3 个）：List（列表）、Dictionary（字典）、Set（集合）。
```

21.将"hello world"转换为首字母大写"Hello World"

```python
z = 'hello world'
[s.capitalize() for s in z.split(' ')]
```

22.如何检测字符串中只含有数字?

```python
# 分为两种情况
# 1.不包含正负号 +-
a = '32323'
a.isdigit()
# 2.含有正负号
import re
re.match(r'[+-]?\d+$',a)
```

23.将字符串"ilovechina"进行反转

```python
s = 'ilovechina'
x = list(s)
''.join(x)
```

24.Python 中的字符串格式化方式你知道哪些？

```python
# Python3.6之后的版本提供了三种字符串格式化的方式
# 1. %s占位符
def foo(name):
  return 'hello %s' % name
# 2. format() 
def foo(name):
  return 'hello {}'.format(name)
# f-string
def foo(name):
  return f'hello {name}'
```

25.有一个字符串开头和末尾都有空格，比如“ adabdw ”,要求写一个函数把这个字符串的前后空格都去掉。

```python
s = " adabdw "
s.strip()
```

26.获取字符串”123456“最后的两个字符。

```python
s = '123456'

print(s[-2:])
```

27.一个编码为 GBK 的字符串 S，要将其转成 UTF-8 编码的字符串，应如何操作？

```python
s.encode('utf-8')
```

28.s="info:xiaoZhang 33 shandong",用正则切分字符串输出['info', 'xiaoZhang', '33', 'shandong']

```python
import re
s="info:xiaoZhang 33 shandong"
re.split(r'[:\s]',s)
```

27.怎样将字符串转换为小写？

```python
b = 'HHH'
b.lower()
```

28.单引号、双引号、三引号的区别？

```python
s = 'hello'
s= "hello"
单引号与双引号没有区别，
三引号可以用来加注释，所加注释可以使用__doc__查看
```

29.a = "你好     中国  ",去除多余空格只留一个空格。

```python
a = "你好     中国  "
s = ' '.join(a.strip().split())
```



#### 列表

30.已知 AList = [1,2,3,1,2],对 AList 列表元素去重，写出具体过程。

```python
a_list = [1,2,3,1,2]
ss = set(a_list)
```

31.如何实现 "1,2,3" 变成 ["1","2","3"]

```python
s = "1,2,3"
s.split(',')
```

32.给定两个 list，A 和 B，找出相同元素和不同元素

```python
# 最直接的方法
list_a = [1,2,3,4,5,6]
list_b = [2,3,6]
same_l = []
not_same = []
for i in list_a:
    if i not in list_b:
        not_same.append(i)
for j in list_b:
    if j not in list_a:
        not_same.append(j)
for x in list_a:
  if x in list_b:
       same_l.append(x)
# 奇技淫巧
list_a = [1,2,3,4,5,6]
list_b = [2,3,6]
set1 = set(list_a)
set2 = set(list_b)
# 相同元素
print(set1&set2)
# 不同元素
print(set1^set2)
```

33.[[1,2],[3,4],[5,6]]一行代码展开该列表，得出[1,2,3,4,5,6]

```python
mm = [[1,2],[3,4],[5,6]]
[j for a in mm for j in a]
```

34.合并列表[1,5,7,9]和[2,2,6,8]

```python
a = [1,5,7,9]
b = [2,2,6,8]
# 方法1
a.extend(b)
# 方法2
a[0:0] = b
```

35.如何打乱一个列表的元素？

```python
import random
a = [1,5,7,9]
random.shuffle(a)
```



#### 字典

36.字典操作中 del 和 pop 有什么区别

```markdown
del 操作删除键值对，不返回值；
pop 操作删除键值对的同时，返回键所对应的值。
```

37.按照字典的内的年龄排序

```Python
d1 = [
    {'name':'alice', 'age':38},
    {'name':'bob', 'age':18},
    {'name':'Carl', 'age':28},
]
```

```python
sorted(d1,key=lambda x:x['age'])
```

38.请合并下面两个字典 a = {"A":1,"B":2},b = {"C":3,"D":4}

```python
# python3合并字典有三种方式
# 1.
a = {'a':1,'b':2}
b = {'c':3,'d':4}
c = {}
c.update(a)
c.update(b)
# 2.
c = dict(a,**b)
# 3.
c = {**a,**b} # 官方推荐这种方式
```

39.如何使用生成式的方式生成一个字典，写一段功能代码。

```python
{x:x*x for x in range(6)}
```

40.如何把元组("a","b")和元组(1,2)，变为字典{"a":1,"b":2}

```python
a = ('a','b')
b = (1,2)
z=zip(a,b)
c = dict(z)
```



#### 综合

41.Python 常用的数据结构的类型及其特性？

```markdown
List,tuple,dict,set是比较常用的数据结构，queue,heap,deque,ProrityQueue，multiprocessing.Queue等进阶的数据结构类型。特性就去查查吧，写在这里太长了。
```

42.如何将元组("A","B")和元组(1,2),合并成字典{"A":1,"B":2}

```Python
a = ('A','B')
b = (1,2)
z=zip(a,b)
c = dict(z)
```

43.Python 里面如何实现 tuple 和 list 的转换？

```python
tuple(list) # tuple转list
list(tuple) # list 转tuple
```

44.我们知道对于列表可以使用切片操作进行部分元素的选择，那么如何对生成器类型的对象实现相同的功能呢？

```python
使用自带的itertools库进行实现，具体实现方式 itertools.islice(生成器对象，起始位置，结束位置)，即可实现切片功能。
```

45.请将[i for i in range(3)]改成生成器

```python
(i for i in range(3))
```

46.a="hello"和 b="你好"编码成 bytes 类型

```python
a.encode()
b.encode()
```

47.下面的代码输出结果是什么？

```Python
a = (1,2,3,[4,5,6,7],8)
a[2] = 2
报错，元组是不可变对象，不支持修改
```

48.下面的代码输出的结果是什么?

```Python
a = (1,2,3,[4,5,6,7],8)
a[5] = 2
报错，元组是不可变对象，下标越界
```

### 操作类题目

49.Python 交换两个变量的值

```python
a,b = b,a
```

50.在读文件操作的时候会使用 read、readline 或者 readlines，简述它们各自的作用

```python
read将整个文本都读取为一个字符串，占用内存大，readline读取为一个生成器，支持遍历和迭代，占用空间小。readlines将文本读取为列表，占用空间大
```

51.json 序列化时，可以处理的数据类型有哪些？如何定制支持 datetime 类型？

```markdown
字符串、数字（整数和浮点数）、字典、列表、布尔值、None。使用strftime将datetime格式化为标准字符串类型即可。
```

52.json 序列化时，默认遇到中文会转换成 unicode，如果想要保留中文怎么办？

```
使用json.dumps函数时，添加参数ensure_ascii=False，如果想显示的更美观，可以添加indent=2参数，会在每个key值前添加两个空格。
```

53.有两个磁盘文件 A 和 B，各存放一行字母，要求把这两个文件中的信息合并(按字母顺序排列)，输出到一个新文件 C 中。

```python
with open('A.txt','r') as f:
    a = f.readlines()[0]
with open('B.txt','r') as f:
    b = f.readlines()[0]
    a.extend(b).sort()
with open('C.txt','w') as f:
    for i in a:
        f.write(i)
```

54.如果当前的日期为 20190530，要求写一个函数输出 N 天后的日期，(比如 N 为 2，则输出 20190601)。

```python
import datetime
def getday(n):
    y,m,d = 2019,5,30
    the_date = datetime.datetime(y,m,d)
    result_date = the_date + datetime.timedelta(days=n)
    target_date = result_date.strftime('%Y%m%d')
    return target_date
```

55.写一个函数，接收整数参数 n，返回一个函数，函数的功能是把函数的参数和 n 相乘并把结果返回。

```python
def mul(n):
  def wrapper(m):
    return n*m
  return wrapper
    
 # 闭包的基本操作
```

56.下面代码会存在什么问题，如何改进？

```Python
def strappend(num):
    str='first'
    for i in range(num):
        str+=str(i)
    return str
  # 将str(i)改为str[i]
```

57.一行代码输出 1-100 之间的所有偶数。

```python
[x for x in range(101) if x %2 ==0]
```

58.with 语句的作用，写一段代码？

```python
# with语句用来管理资源，及时关闭文件等操作，避免资源的泄漏
with open('a.txt','r') as f:
    f.read()
```

59.python 字典和 json 字符串相互转化方法

```python
json.dumps()   将Python中的对象转换为JSON中的字符串对象
json.loads()   将JSON中的字符串对象转换为Python中的对象
```

60.请写一个 Python 逻辑，计算一个文件中的大写字母数量

```python
import re
with open('a.txt','r') as f:
    f_content = f.read()
    len_cap = len(re.compile(r'[A-Z]').findall(f_content))
```



### 高级特效

70.函数装饰器有什么作用？请列举说明？

71.Python 垃圾回收机制？

72.魔法函数 __call__怎么使用?

73.如何判断一个对象是函数还是方法？

74.@classmethod 和@staticmethod 用法和区别

75.Python 中的接口如何实现？

76.Python 中的反射了解么?

77.metaclass 作用？以及应用场景？

78.hasattr() getattr() setattr()的用法

79.请列举你知道的 Python 的魔法方法及用途。

80.如何知道一个 Python 对象的类型？

81.Python 的传参是传值还是传址？

82.Python 中的元类(metaclass)使用举例

83.简述 any()和 all()方法

84.filter 方法求出列表所有奇数并构造新列表，a =  [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]

85.什么是猴子补丁？

86.在 Python 中是如何管理内存的？

87.当退出 Python 时是否释放所有内存分配？

### 正则表达式

88.使用正则表达式匹配```<html><h1>www.baidu.com</html>```中的地址

```python
import re
s = '<html><h1>www.baidu.com</html>'
p = re.compile(r'<html><h1>(.*?)</html>')
result = re.findall(p,s)[0]
```

a="张明 98 分"，用 re.sub，将 98 替换为 100

```python
import re
a="张明 98 分"
pa = re.compile(r'\d+')
re.sub(pa,'100',a)
```

89.正则表达式匹配中(.*)和(.**?)匹配区别？

```
加？会将贪婪模式改成懒惰模式,如果有问号的话，则表示匹配0个或1个问号前面的表达式
```

90.写一段匹配邮箱的正则表达式

```python
r'[0-9a-zA-Z_]*@.+\.(com|cn|net)$'
```



### 其他内容

91.解释一下 python 中 pass 语句的作用？

92.简述你对 input()函数的理解

93.python 中的 is 和==

94.Python 中的作用域

95.三元运算写法和应用场景？

96.了解 enumerate 么？

97.列举 5 个 Python 中的标准模块

98.如何在函数中设置一个全局变量

99.pathlib 的用法举例

100.Python 中的异常处理，写一个简单的应用场景

101.Python 中递归的最大次数，那如何突破呢？

102.什么是面向对象的 mro

103.isinstance 作用以及应用场景？

104.什么是断言？应用场景？

105.lambda 表达式格式以及应用场景？

106.新式类和旧式类的区别

107.dir()是干什么用的？

108.一个包里有三个模块，demo1.py, demo2.py, demo3.py，但使用 from tools import *导入模块时，如何保证只有 demo1、demo3 被导入了。

109.列举 5 个 Python 中的异常类型以及其含义

110.copy 和 deepcopy 的区别是什么？

111.代码中经常遇到的*args, **kwargs 含义及用法。

112.Python 中会有函数或成员变量包含单下划线前缀和结尾，和双下划线前缀结尾，区别是什么?

113.w、a+、wb 文件写入模式的区别

114.举例 sort 和 sorted 的区别

115.什么是负索引？

116.pprint 模块是干什么的？

117.解释一下 Python 中的赋值运算符

118.解释一下 Python 中的逻辑运算符

119.讲讲 Python 中的位运算符

120.在 Python 中如何使用多进制数字？

121.怎样声明多个变量并赋值？

### 算法和数据结构

122.已知：

```Python
AList = [1,2,3]
BSet = {1,2,3}
```

(1) 从 AList 和 BSet 中 查找 4，最坏时间复杂度那个大？

(2) 从 AList 和 BSet 中 插入 4，最坏时间复杂度那个大？

123.用 Python 实现一个二分查找的函数

124.python 单例模式的实现方法

125.使用 Python 实现一个斐波那契数列

126.找出列表中的重复数字

127.找出列表中的单个数字

128.写一个冒泡排序

129.写一个快速排序

130.写一个拓扑排序

131.python 实现一个二进制计算

132.有一组“+”和“-”符号，要求将“+”排到左边，“-”排到右边，写出具体的实现方法。

133.单链表反转

134.交叉链表求交点

135.用队列实现栈

136.找出数据流的中位数

137.二叉搜索树中第 K 小的元素

### 爬虫相关

138.在 requests 模块中，requests.content 和 requests.text 什么区别

139.简要写一下 lxml 模块的使用方法框架

140.说一说 scrapy 的工作流程

141.scrapy 的去重原理

142.scrapy 中间件有几种类，你用过哪些中间件

143.你写爬虫的时候都遇到过什么？反爬虫措施，你是怎么解决的？

144.为什么会用到代理？

145.代理失效了怎么处理？

146.列出你知道 header 的内容以及信息

147.说一说打开浏览器访问 www.baidu.com 获取到结果，整个流程。

148.爬取速度过快出现了验证码怎么处理

149.scrapy 和 scrapy-redis 有什么区别？为什么选择 redis 数据库？

150.分布式爬虫主要解决什么问题

151.写爬虫是用多进程好？还是多线程好？ 为什么？

152.解析网页的解析器使用最多的是哪几个

153.需要登录的网页，如何解决同时限制 ip，cookie,session（其中有一些是动态生成的）在不使用动态爬取的情况下？

154.验证码的解决（简单的：对图像做处理后可以得到的，困难的：验证码是点击，拖动等动态进行的？）

155.使用最多的数据库（mysql，mongodb，redis 等），对他的理解？

### 网络编程

156.TCP 和 UDP 的区别？

157.简要介绍三次握手和四次挥手

158.什么是粘包？ socket 中造成粘包的原因是什么？ 哪些情况会发生粘包现象？

### 并发

159.举例说明 conccurent.future 的中线程池的用法

160.说一说多线程，多进程和协程的区别。

161.简述 GIL

162.进程之间如何通信

163.IO 多路复用的作用？

164.select、poll、epoll 模型的区别？

165.什么是并发和并行？

167.解释什么是异步非阻塞？

168.threading.local 的作用？

### Git 面试题

169.说说你知道的 git 命令

170.git 如何查看某次提交修改的内容x
