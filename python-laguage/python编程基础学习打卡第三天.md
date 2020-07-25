# 猜数字游戏


题目描述:


电脑产生一个零到100之间的随机数字，然后让用户来猜，如果用户猜的数字比这个数字大，提示太大，否则提示太小，当用户正好猜中电脑会提示，"恭喜你猜到了这个数是......"。在用户每次猜测之前程序会输出用户是第几次猜测，如果用户输入的根本不是一个数字，程序会告诉用户"输入无效"。

【答案】
```python

from random import randint

answer = randint(0,100)
counter = 0
while True:
    try:
        counter += 1
        print("第%d次猜，"%counter,end='')
        number = int(input('请输入一个0~100之间的整数: '))
    except ValueError:
        print("输入无效，请输入0~100之间的整数！")
    else:
        if number < answer:
            print('大一点')
        elif number > answer:
            print('小一点')
        else:
            print('恭喜你猜到了这个数是%d!'%number)
            break
```
