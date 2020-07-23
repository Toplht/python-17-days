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
#猜数字游戏

from random import randint
number = int(input("请输入数字："))
answer = randint(0,100)
if number > answer:
    print("大了点")
elif number <answer:
    print("小了点")
elif 0 < abs(number - answer) < 10:
    print("很接近了！")
else:
    print("恭喜你答对了！")
```
