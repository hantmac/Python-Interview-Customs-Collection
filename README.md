# python-面试通关宝典
秋招的小伙伴，有面Python开发方向的，看这一个repo就够啦😘
### 语言特性

1.**谈谈对 Python 和其他语言的区别**

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

2.**简述解释型和编译型编程语言**

```markdown
解释型：就是边解释边执行（Python，php）
编译型：编译后再执行（c、java、c#）
```

3.**Python 的解释器种类以及相关特点？**

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

4.**说说你知道的Python3 和 Python2 之间的区别？**

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

5.**Python3 和 Python2 中 int 和 long 区别？**

```markdown
在python3里，只有一种整数类型int,大多数情况下，和python２中的长整型类似。
```

6.**xrange 和 range 的区别？**

```markdown
xrange用法与range完全相同，所不同的是生成的不是一个数组，而是一个生成器。
要生成很大的数字序列的时候，用xrange会比range性能优很多，因为不需要一上来就开辟一块很大的内存空间，这两个基本上都是在循环的时候用。

在 Python 3 中，range() 是像 xrange() 那样实现，xrange()被抛弃。
```



### 编码规范

7.**什么是 PEP8?**

```markdown
PEP是 Python Enhancement Proposal 的缩写，翻译过来就是 Python增强建议书
简单说就是一种编码规范，是为了让代码“更好看”，更容易被阅读
具体可参考：
https://www.python.org/dev/peps/pep-0008/
```

8.**了解 Python 之禅么？**

```markdown
import this
```

9.**了解 dosctring 么？**

```markdown
Python有一个很奇妙的特性，称为 文档字符串 ，它通常被简称为 docstrings 。DocStrings是一个重要的工具，由于它帮助你的程序文档更加简单易懂，你应该尽量使用它。你甚至可以在程序运行的时候，从函数恢复文档字符串。
使用魔法方法'__doc__'可以打印docstring的内容
```

10.**了解类型注解么？**

```markdown
def add(x:int, y:int) -> int:
    return x + y
用 : 类型 的形式指定函数的参数类型，用 -> 类型 的形式指定函数的返回值类型
```

11.**例举你知道 Python 对象的命名规范，例如方法或者类等**

```
类名都使用首字母大写开头(Pascal命名风格)的规范；
全局变量全用大写字母，单词之间用 _分割；
普通变量用小写字母，单词之间用 _分割；
普通函数和普通变量一样；
私有函数以 __ 开头（2个下划线），其他和普通函数一样；

```

12.**Python 中的注释有几种？**

```markdown
单行注释，多行注释，docstring注释
```

13.**如何优雅的给一个函数加注释？**

```markdown
在函数逻辑行的首行使用""" xxx """给函数添加注释，注释中可包含函数参数的说明，返回值说明等
def foo(bar):
    """
    This is an example.
    :param bar: explain param bar
    """
    return bar
```

14.**如何给变量加注释？**

```python
参数注释：以冒号（:）标记
返回值注释：以 -> 标记
示例：
def add(x:int, y:int) -> int:
    return x + y
```

15.**Python 代码缩进中是否支持 Tab 键和空格混用。**

```markdown
支持，Python 并没有强制要求你用Tab缩进或者用空格缩进，但在 PEP8中，建议使用4个空格来缩进
```

16.**是否可以在一句 import 中导入多个库?**

```python
可以的
import json,random,requests
```

17.**在给 Py 文件命名的时候需要注意什么?**

```markdown
全小写，单词之间使用下划线分隔
```

18.**例举几个规范 Python 代码风格的工具**

```markdown
pylint,black,pycharm也带有pep8的代码规范工具
```



### 数据类型

#### 字符串

19.**列举 Python 中的基本数据类型？**

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

20.**如何区别可变数据类型和不可变数据类型**

```markdown
Python3 的六个标准数据类型中：

不可变数据（3 个）：Number（数字）、String（字符串）、Tuple（元组）；
可变数据（3 个）：List（列表）、Dictionary（字典）、Set（集合）。
```

21.**将"hello world"转换为首字母大写"Hello World"**

```python
z = 'hello world'
[s.capitalize() for s in z.split(' ')]
```

22.**如何检测字符串中只含有数字?**

```python
# 分为两种情况
# 1.不包含正负号 +-
a = '32323'
a.isdigit()
# 2.含有正负号
import re
re.match(r'[+-]?\d+$',a)
```

23.**将字符串"ilovechina"进行反转**

```python
s = 'ilovechina'
x = list(s)
x.reverse()
''.join(x)
```

24.**Python 中的字符串格式化方式你知道哪些？**

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

25.**有一个字符串开头和末尾都有空格，比如“ adabdw ”,要求写一个函数把这个字符串的前后空格都去掉。**

```python
s = " adabdw "
s.strip()
```

26.**获取字符串”123456“最后的两个字符。**

```python
s = '123456'

print(s[-2:])
```

27.**一个编码为 GBK 的字符串 S，要将其转成 UTF-8 编码的字符串，应如何操作？**

```python
s.encode('utf-8')
```

28.**s="info:xiaoZhang 33 shandong",用正则切分字符串输出['info', 'xiaoZhang', '33', 'shandong']**

```python
import re
s="info:xiaoZhang 33 shandong"
re.split(r'[:\s]',s)
```

27.**怎样将字符串转换为小写？**

```python
b = 'HHH'
b.lower()
```

28.**单引号、双引号、三引号的区别？**

```python
s = 'hello'
s= "hello"
单引号与双引号没有区别，
三引号可以用来加注释，所加注释可以使用__doc__查看
```

29.**a = "你好     中国  ",去除多余空格只留一个空格。**

```python
a = "你好     中国  "
s = ' '.join(a.strip().split())
```



#### 列表

30.**已知 AList = [1,2,3,1,2],对 AList 列表元素去重，写出具体过程。**

```python
a_list = [1,2,3,1,2]
ss = set(a_list)
```

31.**如何实现 "1,2,3" 变成 ["1","2","3"]**

```python
s = "1,2,3"
s.split(',')
```

32.**给定两个 list，A 和 B，找出相同元素和不同元素**

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

33.**[[1,2],[3,4],[5,6]]一行代码展开该列表，得出[1,2,3,4,5,6]**

```python
mm = [[1,2],[3,4],[5,6]]
[j for a in mm for j in a]
```

34.**合并列表[1,5,7,9]和[2,2,6,8]**

```python
a = [1,5,7,9]
b = [2,2,6,8]
# 方法1
a.extend(b)
# 方法2
a[0:0] = b
```

35.**如何打乱一个列表的元素？**

```python
import random
a = [1,5,7,9]
random.shuffle(a)
```



#### 字典

36.**字典操作中 del 和 pop 有什么区别**

```markdown
del 操作删除键值对，不返回值；
pop 操作删除键值对的同时，返回键所对应的值。
```

37.**按照字典的内的年龄排序**

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

38.**请合并下面两个字典 a = {"A":1,"B":2},b = {"C":3,"D":4}**

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

39.**如何使用生成式的方式生成一个字典，写一段功能代码。**

```python
{x:x*x for x in range(6)}
```

40.**如何把元组("a","b")和元组(1,2)，变为字典{"a":1,"b":2}**

```python
a = ('a','b')
b = (1,2)
z=zip(a,b)
c = dict(z)
```



#### 综合

41.**Python 常用的数据结构的类型及其特性？**

```markdown
List,tuple,dict,set是比较常用的数据结构，queue,heap,deque,ProrityQueue，multiprocessing.Queue等进阶的数据结构类型。特性就去查查吧，写在这里太长了。
```

42.**如何将元组("A","B")和元组(1,2),合并成字典{"A":1,"B":2}**

```Python
a = ('A','B')
b = (1,2)
z=zip(a,b)
c = dict(z)
```

43.**Python 里面如何实现 tuple 和 list 的转换？**

```python
tuple(list) # tuple转list
list(tuple) # list 转tuple
```

44.**我们知道对于列表可以使用切片操作进行部分元素的选择，那么如何对生成器类型的对象实现相同的功能呢？**

```python
使用自带的itertools库进行实现，具体实现方式 itertools.islice(生成器对象，起始位置，结束位置)，即可实现切片功能。
```

45.**请将[i for i in range(3)]改成生成器**

```python
(i for i in range(3))
```

46.**a="hello"和 b="你好"编码成 bytes 类型**

```python
a.encode()
b.encode()
```

47.**下面的代码输出结果是什么？**

```Python
a = (1,2,3,[4,5,6,7],8)
a[2] = 2
报错，元组是不可变对象，不支持修改
```

48.**下面的代码输出的结果是什么?**

```Python
a = (1,2,3,[4,5,6,7],8)
a[5] = 2
报错，元组是不可变对象，下标越界
```

### 操作类题目

49.**Python 交换两个变量的值**

```python
a,b = b,a
```

50.**在读文件操作的时候会使用 read、readline 或者 readlines，简述它们各自的作用**

```python
read将整个文本都读取为一个字符串，占用内存大，readline读取为一个生成器，支持遍历和迭代，占用空间小。readlines将文本读取为列表，占用空间大
```

51.**json 序列化时，可以处理的数据类型有哪些？如何定制支持 datetime 类型？**

```markdown
字符串、数字（整数和浮点数）、字典、列表、布尔值、None。使用strftime将datetime格式化为标准字符串类型即可。
```

52.**json 序列化时，默认遇到中文会转换成 unicode，如果想要保留中文怎么办？**

```
使用json.dumps函数时，添加参数ensure_ascii=False，如果想显示的更美观，可以添加indent=2参数，会在每个key值前添加两个空格。
```

53.**有两个磁盘文件 A 和 B，各存放一行字母，要求把这两个文件中的信息合并(按字母顺序排列)，输出到一个新文件 C 中。**

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

54.**如果当前的日期为 20190530，要求写一个函数输出 N 天后的日期，(比如 N 为 2，则输出 20190601)。**

```python
import datetime
def getday(n):
    y,m,d = 2019,5,30
    the_date = datetime.datetime(y,m,d)
    result_date = the_date + datetime.timedelta(days=n)
    target_date = result_date.strftime('%Y%m%d')
    return target_date
```

55.**写一个函数，接收整数参数 n，返回一个函数，函数的功能是把函数的参数和 n 相乘并把结果返回。**

```python
def mul(n):
  def wrapper(m):
    return n*m
  return wrapper
    
 # 闭包的基本操作
```

56.**下面代码会存在什么问题，如何改进？**

```Python
def strappend(num):
    str='first'
    for i in range(num):
        str+=str(i)
    return str
  # 将str(i)改为str[i]
```

57.**一行代码输出 1-100 之间的所有偶数。**

```python
[x for x in range(101) if x %2 ==0]
```

58.**with 语句的作用，写一段代码？**

```python
# with语句用来管理资源，及时关闭文件等操作，避免资源的泄漏
with open('a.txt','r') as f:
    f.read()
```

59.**python 字典和 json 字符串相互转化方法**

```python
json.dumps()   将Python中的对象转换为JSON中的字符串对象
json.loads()   将JSON中的字符串对象转换为Python中的对象
```

60.**请写一个 Python 逻辑，计算一个文件中的大写字母数量**

```python
import re
with open('a.txt','r') as f:
    f_content = f.read()
    len_cap = len(re.compile(r'[A-Z]').findall(f_content))
```



### 高级特效

70.**函数装饰器有什么作用？请列举说明？**

```python
函数装饰器可以在不修改原函数的条件下，为原函数添加额外的功能，例如记录日志，运行性能，缓存等
以记录函数运行时间为例，实现一个装饰器
import time
def time_it(func):
    def wrapper(func):
        start_time = time.time()
        res = func()
        end_time = time.time()
        return start_time - end_time
    return wrapper
    
```

71.**Python 垃圾回收机制？**

```python
引用计数机制：
python里每一个东西都是对象，它们的核心就是一个结构体：PyObject
 typedef struct_object {
 int ob_refcnt;
 struct_typeobject *ob_type;
} PyObject;

PyObject是每个对象必有的内容，其中ob_refcnt就是做为引用计数。当一个对象有新的引用时，它的ob_refcnt就会增加，当引用它的对象被删除，它的ob_refcnt就会减少
#define Py_INCREF(op)   ((op)->ob_refcnt++) //增加计数
#define Py_DECREF(op) \ //减少计数
    if (--(op)->ob_refcnt != 0) \
        ; \
    else \
        __Py_Dealloc((PyObject *)(op))

当引用计数为0时，该对象生命就结束了。
引用计数机制的优点：

简单
实时性：一旦没有引用，内存就直接释放了。不用像其他机制等到特定时机。实时性还带来一个好处：处理回收内存的时间分摊到了平时

```

72.**魔法函数 __call__怎么使用?**

```python
class Bar:
    def __call__(self, *args, **kwargs):
        print('i am instance method')

b = Bar()  # 实例化
b()  # 实例对象b 可以作为函数调用 等同于b.__call__ 使用


# OUT: i am instance method



# 带参数的类装饰器
class Bar:

    def __init__(self, p1):
        self.p1 = p1

    def __call__(self, func):
        def wrapper():
            print("Starting", func.__name__)
            print("p1=", self.p1)
            func()
            print("Ending", func.__name__)
        return wrapper


@Bar("foo bar")
def hello():
    print("Hello")
```

73.**如何判断一个对象是函数还是方法？**

```Python
判断对象是函数或方法应该使用type(obj)
```

74.**@classmethod 和@staticmethod 用法和区别**

```python
一般来说，要使用某个类的方法，需要先实例化一个对象再调用方法。

而使用@staticmethod或@classmethod，就可以不需要实例化，直接类名.方法名()来调用。

这有利于组织代码，把某些应该属于某个类的函数给放到那个类里去，同时有利于命名空间的整洁。



既然@staticmethod和@classmethod都可以直接类名.方法名()来调用，那他们有什么区别呢

从它们的使用上来看,
@staticmethod不需要表示自身对象的self和自身类的cls参数，就跟使用函数一样。
@classmethod也不需要self参数，但第一个参数需要是表示自身类的cls参数。
如果在@staticmethod中要调用到这个类的一些属性方法，只能直接类名.属性名或类名.方法名。

而@classmethod因为持有cls参数，可以来调用类的属性，类的方法，实例化对象等，避免硬编码
class A(object):
    bar = 1
    def foo(self):
        print 'foo'
 
    @staticmethod
    def static_foo():
        print 'static_foo'
        print A.bar
 
    @classmethod
    def class_foo(cls):
        print 'class_foo'
        print cls.bar
        cls().foo()
 
A.static_foo()
A.class_foo()
```

75.**Python 中的接口如何实现？**

```python
#抽象类加抽象方法就等于面向对象编程中的接口
from abc import ABCMeta,abstractmethod

class interface(object):
    __metaclass__ = ABCMeta #指定这是一个抽象类
    @abstractmethod  #抽象方法
    def Lee(self):
        pass

    def Marlon(self):
        pass


class RelalizeInterfaceLee(interface):#必须实现interface中的所有函数，否则会编译错误
    def __init__(self):    
        print '这是接口interface的实现'
    def Lee(self):
        print '实现Lee功能'        
    def Marlon(self):
        pass   
```

76.**Python 中的反射了解么?**

```python
通过字符串映射object对象的方法或者属性
hasattr(obj,name_str): 判断objec是否有name_str这个方法或者属性
getattr(obj,name_str): 获取object对象中与name_str同名的方法或者函数
setattr(obj,name_str,value): 为object对象设置一个以name_str为名的value方法或者属性
delattr(obj,name_str): 删除object对象中的name_str方法或者属性

举个栗子
import requests

class Http(object):


    def get(self,url):
        res = requests.get(url)
        response = res.text
        return response

    def post(self,url):
        res = requests.post(url)
        response = res.text
        return response

# 使用反射后
url = "https://www.jianshu.com/u/14140bf8f6c7"
method = input("请求方法>>>:")
h = Http()

if hasattr(h,method):
    func = getattr(h,method)
    res = func(url)
    print(res)
else:
    print("你的请求方式有误...")
```

77.**metaclass 作用？以及应用场景？**

```
metaclass我没怎么用过，不能乱说误人子弟，可以看下这篇博文https://www.cnblogs.com/xybaby/p/7927407.html
```

78.**hasattr() getattr() setattr()的用法**

```python
hasattr(obj,name_str): 判断objec是否有name_str这个方法或者属性
getattr(obj,name_str): 获取object对象中与name_str同名的方法或者函数
setattr(obj,name_str,value): 为object对象设置一个以name_str为名的value方法或者属性
delattr(obj,name_str): 删除object对象中的name_str方法或者属性
```

79.**请列举你知道的 Python 的魔法方法及用途。**

```
1. __call__:允许一个类的实例像函数一样被调用。实质上说，这意味着 x() 与 x._call_() 是相同的
2.__init__:显示初始化属性
3.__str__,__repr__,定义类的时候，重写这两个方法可以让类更清晰
再就是__setattr__,__getattr__,__delattr__等等
```

80.**如何知道一个 Python 对象的类型？**

```
type(obj)
```

81.**Python 的传参是传值还是传址？**

```
说传值或者传引用都不准确。非要安一个确切的叫法的话，叫传对象（call by object）
具体可以参考这篇文章：https://foofish.net/python-function-args.html
```

82.**Python 中的元类(metaclass)使用举例**

```
参考77.
```

83.**简述 any()和 all()方法**

```python
#any(x)判断x对象是否为空对象，如果都为空、0、false，则返回false，如果不都为空、0、false，则返回true

#all(x)如果all(x)参数x对象的所有元素不为0、''、False或者x为空对象，则返回True，否则返回False
>>> any('123')
True
>>> any([0,1])
True
>>> any([0,'0',''])
True
>>> any([0,''])
False
>>> any([0,'','false'])
True
>>> any([0,'',bool('false')])
True
>>> any([0,'',False])
False
>>> any(('a','b','c'))
True
>>> any(('a','b',''))
True
>>> any((0,False,''))
False
>>> any([])
False
>>> any(())
False
>>> all(['a', 'b', 'c', 'd'])  #列表list，
True
>>> all(['a', 'b', 'c', 'd'])  #列表list，元素都不为空或0
True
>>> all(['a', 'b', '', 'd'])  #列表list，存在一个为空的元素
False
>>> all([0, 1,2, 3])  #列表list，存在一个为0的元素
False
>>> all(('a', 'b', 'c', 'd'))  #元组tuple，元素都不为空或0
True
>>> all(('a', 'b', '', 'd'))  #元组tuple，存在一个为空的元素
False
>>> all((0, 1,2, 3))  #元组tuple，存在一个为0的元素
False
>>> all([]) # 空列表
True
>>> all(()) # 空元组
True
>>> #注意：空元组、空列表返回值为True，这里要特别注意
```

84.**filter 方法求出列表所有奇数并构造新列表，a =  [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]**

```python
list(filter(lambda x: x%2==1,a))
```

85.**什么是猴子补丁？**

```markdown
猴子补丁是一个概念，不是python中发明的，其他动态语言也有这么个概念。 《松本行弘的程序世界》这本书，里面专门有一章讲了猴子补丁的设计，所谓的猴子补丁的含义是指在动态语言中，不去改变源码而对功能进行追加和变更
```

86.**在 Python 中是如何管理内存的？**

```
参考71.
```

87.**当退出 Python 时是否释放所有内存分配？**

```
答案是否定的。那些具有对象循环引用或者全局命名空间引用的变量，在 Python 退出是往往不会被释放

另外不会释放 C 库保留的部分内容。
```


### 正则表达式

88.**使用正则表达式匹配```<html><h1>www.baidu.com</html>```中的地址**

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

89.**正则表达式匹配中(.*)和(.**?)匹配区别？**

```
加？会将贪婪模式改成懒惰模式,如果有问号的话，则表示匹配0个或1个问号前面的表达式
```

90.**写一段匹配邮箱的正则表达式**

```python
r'[0-9a-zA-Z_]*@.+\.(com|cn|net)$'
```



### 其他内容

91.**解释一下 python 中 pass 语句的作用？**

```markdown
Python pass 是空语句，是为了保持程序结构的完整性。

pass 不做任何事情，一般用做占位语句。
```

92.**简述你对 input()函数的理解**

```
在python3中，input()获取用户输入，不论用户输入的是什么，获取到的都是字符串类型的。
```

93.**python 中的 is 和==**

```markdown
is比较的是两个对象的id值是否相等，也就是比较两个对象是否为同一个实例对象，是否指向同一个内存地址。

==比较的是两个对象的内容是否相等，默认会调用对象的__eq__()方法。
```

94.**Python 中的作用域**

```python
L （Local） 局部作用域
E （Enclosing） 闭包函数外的函数中
G （Global） 全局作用域
B （Built-in） 内建作用域
```

95.**三元运算写法和应用场景？**

```python
条件语句比较简单时可以使用三元运算符，最常见的就是 
res = 'test True' if expression is True else 'test False'
```

96.**了解 enumerate 么？**

```python
# 遍历列表时候，携带索引index
a = ['a','b','c']
for index,item in a:
    print(index,item)
```

97.**列举 5 个 Python 中的标准模块**

```python
json,re,random,datetime,codecs
```

98.**如何在函数中设置一个全局变量**

```Python
使用global关键字
```

99.**pathlib 的用法举例**

```python
from pathlib import Path

data_folder = Path("source_data/text_files/")

file_to_open = data_folder / "raw_data.txt"

f = open(file_to_open)

print(f.read())
```

100.**Python 中的异常处理，写一个简单的应用场景**

```Python
class NameTooShortError(ValueError): 
    pass
def validate(name):
    if len(name) < 10:
        raise NameTooShortError(name)
        
# 使用自定义异常类，使得发生异常时的错误更容易排查
```

101.**Python 中递归的最大次数，那如何突破呢？**

```pyhton
python解释器限制最大的递归深度是999，可以通过
import sys
sys.setrecursionlimit(10000)  # set the maximum depth as 10000
重新设置最大递归深度
```

102.**什么是面向对象的 mro**

```
对于支持继承的编程语言来说，其方法（属性）可能定义在当前类，也可能来自于基类，所以在方法调用时就需要对当前类和基类进行搜索以确定方法所在的位置。而搜索的顺序就是所谓的「方法解析顺序」（Method Resolution Order，或MRO）。对于只支持单继承的语言来说，MRO 一般比较简单；而对于 Python 这种支持多继承的语言来说，MRO 就复杂很多。
```

103.**isinstance 作用以及应用场景？**

```python
来判断一个对象是否是一个已知的类型
举个栗子：
 p= 'sfa'
 isinstance(p,str)
 True
```

104.**什么是断言？应用场景？**

```python
Python 的断言语句是一种调试工具，用来测试某个断言条件。如果断言条件 为真，则程序将继续正常执行;但如果条件为假，则会引发 AssertionError 异常并显示相关 的错误消息。
```

105.**lambda 表达式格式以及应用场景？**

```python
d = {'a':2,'b':1,'c':3,'d':'4'}
sorted(d,key=lambda x :x[1]) 
# 将字典d按照值排序
```

106.**新式类和旧式类的区别**

```
Python 有两种类：经典类（classic class）和新式类（new-style class）。两者的不同之处在于新式类继承自 object。在 Python 2.1 以前，经典类是唯一可用的形式；Python 2.2 引入了新式类，使得类和内置类型更加统一；在 Python 3 中，新式类是唯一支持的类。
```

107.**dir()是干什么用的？**

```
dir() 函数不带参数时，返回当前范围内的变量、方法和定义的类型列表；带参数时，返回参数的属性、方法列表。如果参数包含方法__dir__()，该方法将被调用。如果参数不包含__dir__()，该方法将最大限度地收集参数信息。
```

108.**一个包里有三个模块，demo1.py, demo2.py, demo3.py，但使用 from tools import *导入模块时，如何保证只有 demo1、demo3 被导入了。**

```python
但若想使用from pacakge_1 import *这种形式的写法，需在  init.py中加上：   all = [‘file_a’, ‘file_b’] #package_1下有file_a.py和file_b.py，在导入时init.py文件将被执行。 
但不建议在 init.py中写模块，以保证该文件简单。不过可在init.py导入我们需要的模块，以便避免一个个导入、方便使用。
```

109.**列举 5 个 Python 中的异常类型以及其含义**

```
1. ArithmeticError 此基类用于派生针对各种算术类错误而引发的内置异常: OverflowError, ZeroDivisionError, FloatingPointError
2. BufferError 当与 缓冲区 相关的操作无法执行时将被引发。
3. LookupError 此基类用于派生当映射或序列所使用的键或索引无效时引发的异常: IndexError, KeyError。 这可以通过 codecs.lookup() 来直接引发
4. ImportError 当 import 语句尝试加载模块遇到麻烦时将被引发。 并且当 from ... import 中的 "from list" 存在无法找到的名称时也会被引发
5. IndexError 当序列抽取超出范围时将被引发。 （切片索引会被静默截短到允许的范围；如果指定索引不是整数则 TypeError 会被引发
```

110.**copy 和 deepcopy 的区别是什么？**

```python
copy 即所谓的浅拷贝，赋值的时候非递归地复制子对象的引用；
deepcopy 即所谓的深拷贝，赋值的时候递归复制子对象。
举个栗子，
xs = [1,2,[2,3,4],3]
ys = xs # 浅拷贝
zs = deepcopy(xs) # 深拷贝
xs[2][0] = 5
print(ys)
[1,2,[2,3,4],3]
print(xs)
[1,2,[5,3,4],3]

print(zs)
[1,2,[5,3,4],3] # 由于深拷贝已经递归复制了子对象，所以内部的List也发生改变

```

111.**代码中经常遇到的*args, **kwargs 含义及用法。**

```
这两个是python中的可变参数。*args表示任何多个位置参数，它是一个tuple；**kwargs表示关键字参数，它是一个dict。并且同时使用*args和**kwargs时，必须*args参数列要在**kwargs前
```

112.**Python 中会有函数或成员变量包含单下划线前缀和结尾，和双下划线前缀结尾，区别是什么?**

```python
前置单下划线_var:命名约定，用来表示该名称仅在内部使用。一般对 Python 解释器没 有特殊含义(通配符导入除外)，只能作为对程序员的提示。
后置单下划线 var_:命名约定，用于避免与 Python 关键字发生命名冲突。
前置双下划线__var:在类环境中使用时会触发名称改写，对 Python 解释器有特殊含义。
前后双下划线__var__:表示由 Python 语言定义的特殊方法。在自定义的属性中要避免
使用这种命名方式。
```

113.**w、a+、wb 文件写入模式的区别**

```
w:写入时会覆盖上一次的写入
a+:追加写入
wb:以二进制文件形式写入
```

114.**举例 sort 和 sorted 的区别**

```
sort()与sorted()的不同在于，sort是在原位重新排列列表，而sorted()是产生一个新的列表
```

115.**什么是负索引？**

```
负索引和正索引不同，它是从右边开始检索。例如：使用负索引取出列表的最后一个数
lis[-1] # 取出列表的最后一个元素
lis[-2] # 取出列表的倒数第二个元素
```

116.**pprint 模块是干什么的？**

```
print()和pprint()都是python的打印模块，功能基本一样，唯一的区别就是pprint()模块打印出来的数据结构更加完整，每行为一个数据结构，更加方便阅读打印输出结果。特别是对于特别长的数据打印，print()输出结果都在一行，不方便查看，而pprint()采用分行打印输出，所以对于数据结构比较复杂、数据长度较长的数据，适合采用pprint()打印方式
```

117.**解释一下 Python 中的赋值运算符**

```
在python中，使用 = 可以给变量赋值。
在算术运算时，为了简化代码的编写，Python还提供了一系列与算术运算符对应的赋值运算符
例如，c += a 等效于 c=c+a

```

118.**解释一下 Python 中的逻辑运算符**

```
and, or, not
```

119.**讲讲 Python 中的位运算符**

```
&	按位与运算符：参与运算的两个值,如果两个相应位都为1,则该位的结果为1,否则为0	(a & b) 输出结果 12 ，二进制解释： 0000 1100
|	按位或运算符：只要对应的二个二进位有一个为1时，结果位就为1	(a | b) 输出结果 61 ，二进制解释： 0011 1101
^	按位异或运算符：当两对应的二进位相异时，结果为1	(a ^ b) 输出结果 49 ，二进制解释： 0011 0001
~	按位取反运算符：对数据的每个二进制位取反,即把1变为0,把0变为1	(~a ) 输出结果 -61 ，二进制解释： 1100 0011， 在一个有符号二进制数的补码形式。
<<	左移动运算符：运算数的各二进位全部左移若干位，由”<<”右边的数指定移动的位数，高位丢弃，低位补0	a << 2 输出结果 240 ，二进制解释： 1111 0000
>>	右移动运算符：把”>>”左边的运算数的各二进位全部右移若干位，”>>”右边的数指定移动的位数	a >> 2 输出结果 15 ，二进制解释： 0000 1111
```

120.**在 Python 中如何使用多进制数字？**

```
1、二进制数字由0和1组成，我们使用0b或0B前缀表示二进制数

print(int(0b1010))#10
2、使用bin()函数将一个数字转换为它的二进制形式

print(bin(0xf))#0b1111
3、八进制数由数字0-7组成，用前缀0o或0O表示8进制数

print(oct(8))#0o10
4、十六进数由数字0-15组成，用前缀0x或者0X表示16进制数

print(hex(16))#0x10
print(hex(15))#0xf
 
```

121.**怎样声明多个变量并赋值？**

```python
a,b = 1,2
```


### 算法和数据结构

122.*已知：*

```Python
AList = [1,2,3]
BSet = {1,2,3}
```

(1) *从 AList 和 BSet 中 查找 4，最坏时间复杂度那个大？*

```
查找列表最坏时间复杂度是O(n),查找字典是O(1)，因为字典的数据结构是散列表
```

(2) *从 AList 和 BSet 中 插入 4，最坏时间复杂度那个大？*

```
插入的操作都是O(1)
```

123.*用 Python 实现一个二分查找的函数*

```python
def binary_search(item,arr):
    start = 0
    end = len(arr) - 1
    while start < end:
        mid = (start + end) // 2
        if item = arr[mid]:
            return True
        elif item < arr[mid]:
            end = mid - 1
        else:
            start = mid + 1
array = [1,2,3,4,5,6]
print(binary_search(2,array))
```

124.*python 单例模式的实现方法*

```python
单例模式（Singleton Pattern）是一种常用的软件设计模式，该模式的主要目的是确保某一个类只有一个实例存在。当你希望在整个系统中，某个类只能出现一个实例时，单例对象就能派上用场。

比如，某个服务器程序的配置信息存放在一个文件中，客户端通过一个 AppConfig 的类来读取配置文件的信息。如果在程序运行期间，有很多地方都需要使用配置文件的内容，也就是说，很多地方都需要创建 AppConfig 对象的实例，这就导致系统中存在多个 AppConfig 的实例对象，而这样会严重浪费内存资源，尤其是在配置文件内容很多的情况下。事实上，类似 AppConfig 这样的类，我们希望在程序运行期间只存在一个实例对象
1.使用装饰器实现单例模式
def singleton(cls):
    _instance = {}
    def _singleton(*args,**kargs):
        if cls not in _instance:
            _instance[cls] = cls(*args,**args)
        return _instance[cls]
    return _singleton
  
2.使用类实现单例模式
import threading
class Singleton(object):
    _instance_lock = threading.Lock()

    def __init__(self):
        pass


    def __new__(cls, *args, **kwargs):
        if not hasattr(Singleton, "_instance"):
            with Singleton._instance_lock:
                if not hasattr(Singleton, "_instance"):
                    Singleton._instance = object.__new__(cls)  
        return Singleton._instanc
```

125.*使用 Python 实现一个斐波那契数列*

```Python
# 很多人上来就写下面这种解法
def fibnaqie(n):
    if n < 2:
        return n
    return fibnaqie(n - 1) + fibnaqie(n - 2)
# 这种解法时间复杂度高，而且一般不是面试官最想要的答案

# 下面这种优化的版本
def fib2(n):
    fib_n = 0
    fib_one = 1
    fib_two = 0
    res = [0, 1]
    if n < 2:
        return res[n]
    for i in range(2, n + 1):
        fib_n = fib_one + fib_two
        fib_two = fib_one
        fib_one = fib_n
    return fib_n
# 所以适当地选择递归还是迭代，要看具体情况，处理树，或者图的遍历的时候，递归还是比迭代优先考虑的
```

126.*找出列表中的重复数字*

```python
def find_duplicate(arr):
    not_dup = set()
    dup = set()
    for x in arr:
        if x not in not_dup:
            not_dup.add(x)
        else:
            dup.add(x)
    return dup


if __name__ == '__main__':
    array = [1, 2, 3, 4, 4, 4, 4]
    print(find_duplicate(array))
```

127.*找出列表中的单个数字*

```python
a = ['a', 1, 2, 'b']
for x in a:
    if str(x).isdigit():
        print(x)
```

128.*写一个冒泡排序*

```python
def bubble_sort(arr):
    n = len(arr)
    if len(arr) < 2:
        return arr
    for i in range(n - 1):
        count = 0
        for j in range(n - i - 1):
            if arr[j] > arr[j + 1]:
                arr[j], arr[j + 1] = arr[j + 1], arr[j]
                count += 1
        if count == 0:
            return arr
    return arr


if __name__ == '__main__':
    arr = [2, 1, 5, 3, 6]
    arr1 = [1, 2, 3, 4, 5]
    print(bubble_sort(arr1))
```

129.*写一个快速排序*

```python
def quick_sort(arr):
    if len(arr) < 2:
        return arr
    else:
        pivot = arr[0]
        less = [i for i in arr[1:] if i <= pivot]
        more = [i for i in arr[1:] if i > pivot]
    return quick_sort(less) + [pivot] + quick_sort(more)


if __name__ == '__main__':
    array = [2, 1, 6, 3, 4, 5]
    print(quick_sort(array))

```

130.*写一个拓扑排序*

```python
# 使用循环进行拓扑排序
def topoSort(G):
    # 初始化计算被指向节点的字典
    cnt = dict((u, 0) for u in G.keys())
    import pdb;pdb.set_trace()
    # 若某节点被其他节点指向，该节点计算量+1
    for u in G:
        for v in G[u]:
            cnt[v] += 1
    # 收集被指向数为0的节点,此时Q只有一个节点，即起始节点a
    Q = [u for u in cnt.keys() if cnt[u] == 0]
    # 记录结果
    seq = []
    while Q:
        s = Q.pop()
        seq.append(s)
        for u in G[s]:
            cnt[u] -= 1
            if cnt[u] == 0:
                Q.append(u)
    return seq


# 有向无环图的邻接字典
G = {
    'a': {'b', 'f'},
    'b': {'c', 'd', 'f'},
    'c': {'d'},
    'd': {'e', 'f'},
    'e': {'f'},
    'f': {}
}

res = topoSort(G)
print(res)

```

131.*python 实现一个二进制计算*

```python
'''
以实现二进制加法为例
给定两个二进制字符串，返回他们的和（用二进制表示）。
输入为非空字符串且只包含数字 1 和 0。
输入: a = “11”, b = “1”
输出: “100”
'''


def binary_plus(a, b):
    a, b = int('0b' + a, 2), int('0b'+b, 2)
    return bin(a + b)[2:]


if __name__ == '__main__':
    a = '11'
    b = '1'
    print(binary_plus(a, b))

# 解释一下，class int(x, base) 
x–字符串或数字 
base–进制数，默认十进制。 
bin()函数返回一个整型int或者长整数long int的二进制表示，bin()运算返回的是二进制。所以前两位是二进制的标志，需要[2:]去除
```

132.*有一组“+”和“-”符号，要求将“+”排到左边，“-”排到右边，写出具体的实现方法。*

```python
def some_sort(arr):
    list_a = []
    list_b = []
    for x in arr:
        if x == '+':
            list_a.append(x)
        else:
            list_b.append(x)
    list_a.extend(list_b)
    print(list_a)
    return list_a
```

133.*单链表反转*

```python
class ListNode:
    def __init__(self, val):
        self.val = val
        self.next = None


def reverse_node(head):
    p = head
    q = head.next
    head.next = None
    while q:
        r = q.next
        q.next = p
        p = q
        q = r
    head = p
    return head


if __name__ == '__main__':
    l1 = ListNode(3)
    l1.next = ListNode(2)
    l1.next.next = ListNode(1)

    l = reverse_node(l1)
    print(l.val, l.next.val, l.next.next.val)
# 1,2,3
```

134.*交叉链表求交点*

```python
'''先遍历两个链表，获知两个链表各自的长度，往后调整较长链表的指针，使之与较短链表的起始指针对齐，然后两个链表同时往后扫描，直至二者的节点相同，证明该节点是相交节点，否则返回 None，表明两个链表不相交，时间复杂度o(n),空间复杂度0(1)'''
class ListNode:
    def __init__(self, val):
        self.val = val
        self.next = None


def solution(head_a, head_b):
    def get_list_length(head):
        len = 0
        while head:
            len += 1
            head = head.next
        return head

    def forward_long_list(long_len, short_len, head):
        delta = long_len - short_len
        while delta and head:
            head = head.next
            delta -= 1
        return head

    def main_func(head_a, head_b):
        head_a_len = get_list_length(head_a)
        head_b_len = get_list_length(head_b)
        if head_a_len > head_b_len:
            head_a = forward_long_list(head_a_len, head_b_len, head_a)
        else:
            head_b = forward_long_list(head_a_len, head_b_len, head_b)
        while head_a and head_b:
            if head_a == head_b:
                return head_a
            head_a = head_a.next
            head_b = head_b.next
        return None

    return main_func(head_a, head_b)


```

135.*用队列实现栈*

```python
class Stack:
    def __init__(self):
        self.queue_a = []
        self.queue_b = []

    def push(self, val):
        self.queue_a.append(val)

    def pop(self):
        if len(self.queue_a) == 0:
            return None
          # 核心思想就是留一个元素在队列a中，最后交换队列a,b，再从b中取栈顶元素
        while len(self.queue_a) != 1:
            self.queue_b.append(self.queue_a.pop(0))
        self.queue_a, self.queue_b = self.queue_b, self.queue_a
        return self.queue_b.pop()


test_stack = Stack()
for i in range(5):
    test_stack.push(i)
for i in range(5):
    print(test_stack.pop())

```

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
