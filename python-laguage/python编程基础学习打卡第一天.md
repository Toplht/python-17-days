# 变量、运算符与数据类型


## 1. 注释
- 在 Python 中,单行注释用 **#**，多行注释用 **''' '''**

```python
#【例子】单行注释
print("Hello world!")

#Hello world!

#【例子】多行注释

'''
  飞流直下三千尺
  疑是银河落九天
'''
```
## 2. __name__属性的作用

Python中的模块（.py文件）在创建之初会自动加载一些内建变量，__name__就是其中之一。Python模块中通常会定义很多变量和函数，这些变量和函数相当于模块中的一个功能，模块被导入到别的文件中，可以调用这些变量和函数。那么这时 \_\_name\_\_ 的作用就彰显了，它可以标识模块的名字，可以显示一个模块的某功能是被自己执行还是被别的文件调用执行，假设模块A、B，模块A自己定义了功能C,模块B调用模块A，现在功能C被执行了：

如果C被A自己执行，也就是说模块执行了自己定义的功能，那么 \_\_name\_\_=='\_\_main\_\_'

如果C被B调用执行，也就是说当前模块调用执行了别的模块的功能，那么__name__=='A'（被调用模块的名字）

其实换一种说法也就是表示**当前程序运行在哪一个模块中**
## 3. 运算符

Python支持多种运算符，例如：算术运算符、比较运算符、逻辑运算符、位运算符、成员运算符、身份运算符、赋值运算符

|**运算符**|**功能说明**|
:-:|:-:
|[]、[:]|下标、切片|
|+|算术加法，列表、元组、字符串合并与连接，正号|
|-|算术减法，集合差集，相反数|
|\*|算术乘法，集合交集|
|/|算术除法|
|//|求整商，如果操作数中有实数，结果为实数形式的整数|
|%|求余数，字符串格式化|
|\*\*|幂运算|
|<、<=、>、>=、==、!=|（值）大小比较，集合包含关系比较|
|or、and、not|逻辑或、逻辑与、逻辑非|
|in、not in|成员测试|
|is、is not|对象同一性测试，即测试是否为同一个对象或内存地址是否相同|
|\|、^、&、<<、>>、~|位或、位异或、位与、左移位、右移位、位求反|
|&、\|、^|集合交集、集合并集、对称差集|
|@|矩阵相乘运算符|
- 赋值运算符

**赋值运算符应该是最为常见的运算符，它的作用是将右边的值赋给左边的变量。下面的例子演示了赋值运算符和复合赋值运算符的使用。**
```python
#赋值运算符和复合运算符

a = 10
b = 3
a += b        # 相当于：a = a + b
a *= a + 2    # 相当于：a = a * (a + 2)
print(a)      # 算一下这里会输出什么，答案是：13*15=195
```
- 比较运算符

比较运算符有时也称为关系运算符，包括==、!=、<、>、<=、>=，没有什么好解释的，大家一看就能懂，唯一需要提醒的是比较相等用的是==，请注意这个地方是两个等号，因为 **=是赋值运算符**，我们在上面刚刚讲到过，==才是比较相等的比较运算符。比较运算符会产生布尔值，要么是True要么是False。

- 逻辑运算符

逻辑运算符有三个，分别是and、or和not。and字面意思是“而且”，所以and运算符会连接两个布尔值，如果两个布尔值都是True，那么运算的结果就是True；左右两边的布尔值有一个是False，最终的运算结果就是False。相信大家已经想到了，如果and左边的布尔值是False，不管右边的布尔值是什么，最终的结果都是False，所以在做运算的时候右边的值会被跳过（短路处理），这也就意味着在and运算符左边为False的情况下，右边的表达式根本不会执行。or字面意思是“或者”，所以or运算符也会连接两个布尔值，如果两个布尔值有任意一个是True，那么最终的结果就是True。当然，or运算符也是有短路功能的，在它左边的布尔值为True的情况下，右边的表达式根本不会执行。not运算符的后面会跟上一个布尔值，它的作用是得到与该布尔值相反的值，也就是说，后面的布尔值如果是True运算结果就是False，而后面的布尔值如果是False则运算结果就是True。

```python
#比较运算符和逻辑运算符的使用

flag0 = 1 == 1
flag1 = 3 > 2
flag2 = 2 < 1
flag3 = flag1 and flag2
flag4 = flag1 or flag2
flag5 = not (1 != 2)
print(flag0)    #  True
print(flag1)    #  True
print(flag2)    #  False
print(flag3)    #  False
print(flag4)    #  True
print(flag5)    #  False
```
> **说明：比较运算符的优先级高于赋值运算符，所以flag0 = 1 == 1先做1 == 1产生布尔值True，再将这个值赋值给变量flag0。print函数可以输出多个值，多个值之间可以用,进行分隔，输出的内容之间默认以空格分开。**
- 三元运算符


【例子】
```python
#初始代码

x, y = 4, 5
if x < y:
    small = x
else:
    small = y

print(small)  # 4

#三元操作符的条件表达式

x, y = 4, 5
small = x if x < y else y
print(small)  # 4
```
> **说明：类似于C语言中的三目运算符，条件成立即执行if前语句反之执行else后语句**
- 身份运算符


【例子】
```python
#比较的两个变量均指向不可变类型

a = "hello"
b = "hello"
print(a is b, a == b)  # True True
print(a is not b, a != b)  # False False

#比较的两个变量均指向可变类型。

a = ["hello"]
b = ["hello"]
print(a is b, a == b)  # False True
print(a is not b, a != b)  # True False
```
> **说明：is, is not 对比的是两个变量的内存地址，==, != 对比的是两个变量的值。
比较的两个变量，指向的都是地址不可变的类型（str等），那么is，is not 和 ==，！= 是完全等价的。
对比的两个变量，指向的是地址可变的类型（list，dict，tuple等），则两者是有区别的。【如果两个对象是同一个，两者具有相同的内存地址】**
- 位运算符

**位运算符只能用与整数，**其内部执行过程为**：整数转换为二进制数，然后右对齐，必要时左侧补0，按位进行运算，最后把运算结果转换为十进制数返回。**
|位运算|运算规则|
:-:|:-:
|位与|1&1=1、1&0=0、0&1=0、0&0=0|
|位或|1\|1=1、1\|0=1、0\|1=1、0\|0=0|
|位异或|1^1=0、1^0=1、0^1=1、0^0=0|
> **说明：左移位时右侧补0，每左移一位相当于乘以2；右移位时左侧补0，每右移一位相当于整除以2。**


【例子】
```python
print(3<<2)     #把3左移2位，结果为12
print(3&7)      # 3
print(3 | 8)    # 11
print(3 ^ 5)    # 6
```
- 运算符优先级

运算符的优先级指的是多个运算符同时出现时，先做什么运算然后再做什么运算。
优先级顺序基本满足：强制运算符‘ **()** ’>算术运算符>位运算符>比较运算符>身份运算符>成员运算符>逻辑运算符>赋值运算符
> **注：幂运算符>位求反运算符、正负号>其他算术运算符，先移位运算后位运算（先位与运算）。**
`在实际开发中，如果搞不清楚运算符的优先级，可以使用括号来确保运行的执行顺序`

## 4.变量和赋值

在程序设计中，变量是一种存储数据的载体。计算机中的变量是实际存在的数据或者说是存储器中存储数据的一块内存空间，变量的值可以被读取和修改，这是所有计算和控制的基础。
- 硬性规则
  - 变量名由字母（广义的Unicode字符，不包括特殊字符）、数字和下划线构成，数字不能开头。
  - 大小写敏感（大写的`a`和小写的`A`是两个不同的变量）。
  - 不要跟关键字（有特殊含义的单词，后面会讲到）和系统保留字（如函数、模块等的名字）冲突。
- PEP 8要求：
  - 用小写字母拼写，多个单词用下划线连接。
  - 受保护的实例属性用单个下划线开头（后面会讲到）。
  - 私有的实例属性用两个下划线开头（后面会讲到）。
  
在Python中可以使用 `type` 函数和 `isinstance(object, classinfo)` 判断一个对象是否是一个已知的类型。对变量的类型进行检查。程序设计中函数的概念跟数学上函数的概念是一致的，数学上的函数相信大家并不陌生，它包括了函数名、自变量和因变量。如果暂时不理解这个概念也不要紧，我们会在后续的章节中专门讲解函数的定义和使用。

【例子】
```Python
student = "John"
print(student)      # John

a = 1
b = 6
c = a + b
print(c)            # 7

schoolboy = "John"
schoolgirl = "Lily"
allstudents = schoolboy + ' and ' + schoolgird
print(allstudents)  # John and Lily

#使用type()检查变量的类型

a = 100
b = 12.345
c = 1 + 5j
d = 'hello, world'
e = True
print(type(a))      # <class 'int'>
print(type(b))      # <class 'float'>
print(type(c))      # <class 'complex'>
print(type(d))      # <class 'str'>
print(type(e))      # <class 'bool'>

#使用isinstance(object, classinfo) 判断一个对象是否是一个已知的类型。
print(isinstance(1, int))  # True
print(isinstance(5.2, float))  # True
print(isinstance(True, bool))  # True
print(isinstance('5.2', str))  # True

```
## 5.数据类型与转换

计算机能处理的数据有很多种类型，除了数值之外还可以处理文本、图形、音频、视频等各种各样的数据，那么不同的数据就需要定义不同的存储类型。Python中的数据类型很多，而且也允许我们自定义新的数据类型（这一点在后面会讲到），我们先介绍几种常用的数据类型。
类型|名称|示例
:-:|:-:|:-:
int|整型|-876, 10
float|浮点型|3.149, 11.11
bool|布尔型|True, False
- 整型：Python中可以处理任意大小的整数（Python 2.x中有int和long两种类型的整数，但这种区分对Python来说意义不大，因此在Python 3.x中整数只有int这一种了），而且支持二进制（如***0b100***，换算成十进制是**4**）、八进制（如***0o100***，换算成十进制是**64**）、十进制（**100**）和十六进制（***0x100***，换算成十进制是***256***）的表示法。


【例子】
```python
a = 1031
print(bin(a))  # 0b10000000111
```
- 浮点型：浮点数也就是小数，之所以称为浮点数，是因为按照科学记数法表示时，一个浮点数的小数点位置是可变的，浮点数除了数学写法（如**123.456**）之外还支持科学计数法（如**1.23456e2**）。


【例子】
```pytohn
a = 0.00000023
b = 2.3e-7
print(a)  # 2.3e-07
print(b)  # 2.3e-07
```
有时候我们想保留浮点型的小数点后 **n** 位。可以用 **decimal** 包里的 **Decimal** 对象和 **getcontext()** 方法来实现。

【例子】
```pytohn
import decimal
from decimal import Decimal

b = Decimal(1) / Decimal(3)
print(b)        # 0.3333333333333333333333333333


#使 1/3 保留 4 位，用 getcontext().prec 来调整精度。

decimal.getcontext().prec = 4
c = Decimal(1) / Decimal(3)
print(c)        ## 0.3333

```
- 布尔型：布尔值只有**True**、**False**两种值，当把布尔型变量用在数字运算中，用 1 和 0 代表 True 和 False。在Python中，可以直接用**True**、**False**表示布尔值（请注意大小写），也可以通过布尔运算计算出来（例如**3 < 5**会产生布尔值**True**，而**2 == 1**会产生布尔值**False**）。

【例子】
```python
print(True + True)  # 2
print(True + False)  # 1
print(True * False)  # 0

#bool()为python中的函数类似于type()

print(type(0), bool(0), bool(1))    # <class 'int'> False True

#bool()作用在容器类型变量：X 只要不是空的变量，bool(X) 就是 True，其余就是 False。

print(type(''), bool(''), bool('python'))     # <class 'str'> False True
print(type([]), bool([]), bool([1, 2]))       # <class 'list'> False True
```
> 确定bool(X) 的值是 True 还是 False，就看 X 是不是空，空的话就是 False，不空的话就是 True。
对于数值变量，0, 0.0 都可认为是空的。
对于容器变量，里面没元素就是空的。
- 字符串型：字符串是以单引号或双引号括起来的任意文本，比如'hello'和"hello",字符串还有原始字符串表示法、字节字符串表示法、Unicode字符串表示法，而且可以书写成多行的形式（用三个单引号或三个双引号开头，三个单引号或三个双引号结尾）。

- 类型转换

转换为整型 int(x, base=10)
转换为字符串 str(object='')
转换为浮点型 float(x)

【例子】
```python
print(int('520'))  # 520
print(int(520.52))  # 520
print(float('520.52'))  # 520.52
print(float(520))  # 520.0
print(str(10 + 10))  # 20
print(str(10.1 + 5.2))  # 15.3
```
## 6.print()函数

print() 函数是Python中的基本输出函数，用来把数据按指定格式输出到标准工具台或指定的文件对象。

内置函数print()的语法格式为：

`print(value, sep=' ', end='\n', file=sys.stdout, flush=False)`
- 数据以字符串表示的方式格式化输出到流文件对象file里。其中所有非关键字参数都按str()方式进行转换为字符串输出；
- 关键字参数sep是实现分隔符，比如多个参数输出时想要输出中间的分隔字符；
- 关键字参数end是输出结束时的字符，默认是换行符\n；
- 关键字参数file是定义流输出的文件，可以是标准的系统输出sys.stdout，也可以重定义为别的文件；
- 关键字参数flush是立即把内容输出到流文件，不作缓存。


【例子】
```python
# 默认每次输出后都会换行
shoplist = ['apple', 'mango', 'carrot', 'banana']
print("This is printed without 'end'and 'sep'.")
for item in shoplist:
    print(item)

# This is printed without 'end'and 'sep'.
# apple
# mango
# carrot
# banana

#每次输出结束都用end设置的参数&结尾，并没有默认换行。
shoplist = ['apple', 'mango', 'carrot', 'banana']
print("This is printed with 'end='&''.")
for item in shoplist:
    print(item, end='&')
print('hello world')

# This is printed with 'end='&''.
# apple&mango&carrot&banana&hello world

#item值与'another string'两个值之间用sep设置的参数&分割。由于end参数没有设置，因此默认是输出解释后换行，即end参数的默认值为\n。

shoplist = ['apple', 'mango', 'carrot', 'banana']
print("This is printed with 'sep='&''.")
for item in shoplist:
    print(item, 'another string', sep='&')

# This is printed with 'sep='&''.
# apple&another string
# mango&another string
# carrot&another string
# banana&another string
