# 条件循坏结构


## 1.分支结构


迄今为止，我们写的Python代码都是按顺序一条一条执行的，这种结构通常称之为顺序结构。然而顺序结构并不能实现所有业务逻辑，当出现需要先判断再执行的问题时，往往会产生两个不同的分支但只有一个分支会被执行。类似的情况还有很多，我们将这种结构称之为“**选择结构**”或“**分支结构**”。

- 单分支选择结构-if语句的使用

```python
if 表达式:
    result
```
上述代码只有当条件表达式**表达式**结果为真时即条件满足**表达式**时，`result`才能顺利执行，否则将跳过 `result`直接执行紧跟在此代码块后面的语句。
> 注：1.**表达式后面的 “`:`”不可缺少**，并且语句块必须做相应的缩进。2.条件表达式中不允许使用赋值运算符 “`=`”，避免误将关系运算符 “`==`”写成赋值运算符所带来的麻烦。在条件表达式中使用赋值运算符 “`=`”将抛出异常。
【例子】
```python
if a>b:
    a,b = b,a
print(a,b)
```

- 双分支选择结构-if - else语句

```python
if 表达式:
    result1
else:
    result2
```
Python提供与if搭配使用的else，当表达式的值为 `True` 或其他等价值时，执行 **result1**，否则执行 **result2**，两个语句块
总有一个被执行，然后执行后面的代码。

【例子】

```python
number = int(input("请输入密码："))
if number == 2020520:
    print("密码正确")
else:
    print("密码错误，请重新输入")
```
- 多分支选择你结构

```python
if 表达式 1:
    result1
elif 表达式 2:
    result2
elif 表达式 3:
    result3
.
.
.
else:
    resultn
```

【例子】
```python
score = float(input('请输入成绩: '))
if score >= 90:
    grade = 'A'
elif score >= 80:
    grade = 'B'
elif score >= 70:
    grade = 'C'
elif score >= 60:
    grade = 'D'
else:
    grade = 'E'
print('对应的等级是:', grade)
```

- 选择结构的嵌套

选择结构可以通过嵌套来实现复杂的业务逻辑，语法如下：
```python
if 表达式 1:
    result1
    if 表达式 2:
        result2
    else:
        result3
else:
    if 表达式 4：
        result4
```
> 注：使用嵌套选择结构时，一定要严格控制好不同级别代码块的缩进量

- assert关键词

assert 这个关键词我们称之为断言，当关键词后边的条件结果为 False 时，程序自动崩溃并抛出AssertionError异常。
【例子】
```python
assert 1 < 0   # AssertionError
```

##  循环结构

Python主要有for循环和while循坏两种形式的循环结构，多个循环可以嵌套使用，并且还经常和选择结构嵌套使用来实现复杂的业务逻辑。

- While循环结构

完整语法形式如下：

```python
while 条件表达式:
    需要被重复执行的语句
```
> `while` 循环直到条件表达式的值为 `False` 才会跳出循环执行后面的语句。**当条件表达式为0时不执行循环（0 == False）**。
【例子】
'''pyhton
#计算1+2+3+……+100的结果

sum = i =0
while i <= 100:
    sum+=1
    i+=1
print(sum)          # 5050
'''
- while - else 循环

如果循环因为条件表达式不成立或序列遍历结结束且是自然结束时则执行else结构的语句。
```python
while 条件表达式:
    需要被重复执行的语句
else:
    result
```
> 如果while循环执行了break函数，将不再执行else中代码块的内容。
【例子】
```python
sum = i =0
while i <= 100:
    sum+=1
    i+=1
else:
    print(sum)          # 5050
```
> ** `while` 循环一般用于循环次数不确定的情况**
- for循环结构

for循环一般用于循环次数确定的情况，**尤其适用于枚举或遍历序列或迭代对象中的元素**。
```python
for 迭代变量 in 可迭代对象:
    代码块
```
> 每次循环，迭代变量被设置为可迭代对象的当前元素，提供给代码块使用。
【例子】
```python
for i in [1,2,3]:
    print(i)

# 1
# 2
# 3
```
- for - else 循环

```python
for 迭代变量 in 可迭代对象:
    代码块
else:
    代码块
```
> 同 `while` 语句一样，正常退出循环时则执行。

- range（）函数
    - range(101)可以产生一个0到100的整数序列。
    - range(1, 100)可以产生一个1到99的整数序列。
    - range(1, 100, 2)可以产生一个1到99的奇数序列，其中2是步长，即数值序列的增量。

- break语句与continue语句

`break` 和 `continue` 语句在 while 和 for 循环中都可以使用且一般与选择结构或异常处理结构结合使用，`break`语句执行后将提前结束所属层次循环。`continue` 语句的作用是提前结束本次循环，忽略`continue`之后的所有语句，提前进入下一次循环。

## 练习题

1.编写一个Python程序来查找那些既可以被7整除又可以被5整除的数字，介于1500和2700之间。
```python
for i in range(1500,2701):
    if (i % 5 == 0) & (i % 7 == 0):
         print(i)
```
