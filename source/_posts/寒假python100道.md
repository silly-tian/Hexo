---
title: 寒假python100道
date: 2019-01-18 23:04:05
tags:
---

# 寒假python100道
---
##	题目1：有四个数字：1、2、3、4，能组成多少个互不相同且无重复数字的三位数？各是多少?
```
count = 0
for i1 in range(1, 5):
    for i2 in range(1, 5):
        for i3 in range(1, 5):
            if i1 != i2 and i1 != i3 and i2 != i3:
                i = i1 * 100 + i2 * 10 + i3
                print(i)
                count += 1
print("一共有%d个数" %count)
```
## 题目2：企业发放的奖金根据利润提成。利润(I)低于或等于10万元时，奖金可提10%;利润高于10万元，低于20万元时，低于10万元的部分按10%提成，高于10万元的部分，可提成7.5%；20万到40万之间时，高于20万元的部分，可提成5%；40万到60万之间时高于40万元的部分，可提成3%；60万到100万之间时，高于60万元的部分，可提成1.5%，高于100万元时，超过100万元的部分按1%提成，从键盘输入当月利润I，求应发放奖金总数？

```
#t为奖金
I = int(input("请输入当月红利I="))
if I > 10 ** 5:
    if I > 2 * 10 ** 5:
        if I > 4 * 10 ** 5:
            if I > 6 * 10 ** 5:
                if I > 10 ** 6:
                    t = 10 ** 5 * 0.1 + 10 ** 5 * 0.075 + 2 * 10 ** 5 * 0.05 + 2 * 10 ** 5 * 0.03 + 4 * 10 ** 5 * 0.015 + (I - 10 ** 6) * 0.01
                else:
                    t = 10 ** 5 * 0.1 + 10 ** 5 * 0.075 + 2 * 10 ** 5 * 0.05 + 2 * 10 ** 5 * 0.03 + (I - 6 * 10 ** 5) * 0.015
            else:
                t = 10 ** 5 * 0.1 + 10 ** 5 * 0.075 + 2 * 10 ** 5 * 0.05 + (I - 4 * 10 ** 5) * 0.03
        else:
                t = 10 ** 5 * 0.1 + 10 ** 5 * 0.075 + (I - 2 * 10 ** 5) * 0.05
    else:
        t = 10 ** 5 * 0.1 + (I - 10 ** 5) * 0.075
else:
    t = I * 0.1
print("应发奖金总数为%f" %t)
```
## 题目3：一个整数，它加上100后是一个完全平方数，再加上168又是一个完全平方数，请问该数是多少？
```
#这个是半成品，错的
#import math
#for i in range(1, 9999):
#    if math.sqrt((i + 100)) // 1 == 0 and math.sqrt((i + 168)) // 1 == 0:
#        print(i)
#        break

for i in range(1, 100):
    for j in range(1, 100):
        if i ** 2 - j ** 2 == 168:
           x = j ** 2 - 100
           print(x)
```
## 题目4：输入某年某月某日，判断这一天是这一年的第几天？
```
y = int(input("请输入年份"))
m = int(input("请输入月份"))
d = int(input("请输入日份"))
md = [0, 31, 59, 90, 120, 151, 181, 212, 243, 273, 304, 334]
if 0 < m < 13 and 0 < d < 32 and y > 0:
    x = md[m - 1] + d
else:
    print("输入错误")
if y % 4 == 0 and m > 1:
    x += 1
print("这一天是这一年的第%d天" %x)
```
## 题目5：输入三个整数x,y,z，请把这三个数由小到大输出。
```
n = []
for i in range(0, 3):
    x = int(input("请输入一个数"))
    n.append(x)
n.sort()
print(n)
```
## 题目6： 斐波那契数列。 0, 1, 1, 2, 3, 5, 8, 13, 21......
```
def fbn(n):
    if n == 1:
        return [1]
    if n == 2:
        return [1, 1]
    fbns = [1, 1]
    for i in range(2, n):
        fbns.append(fbns[-1] + fbns[-2])
    return fbns

print(fbn(10))
```
## 题目7： 将一个列表的数据复制到另一个列表中。
```
a = [1, 2, 3, 4, 5]
b = a[:]
print(b)
```
## 题目8： 输出 9*9 乘法口诀表。
```
for i in range(1, 10):
    for j in range(1, 10):
        if i >= j:
            print("%d * %d = %.2d  " %(i, j, i * j), end = "")
    print()
```