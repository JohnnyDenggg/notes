# 教程

https://www.bilibili.com/video/BV1wD4y1o7AS?p=26

重看了：从P107-134

回顾：P119，121，134

# 方向

![image-20200914111124211](markdownImg/Python/image-20200914111124211.png)

![image-20200914111149679](markdownImg/Python/image-20200914111149679.png)

![image-20200914111219756](markdownImg/Python/image-20200914111219756.png)

# 工具

安装anaconda(参考md（neural network）)

Pycharm（免费）

https://www.jetbrains.com/zh-cn/pycharm/download/#section=windows

# 注意点

##### 随机数

```
import random
a = random.randint(20,35)
```

```
import random
b = random.random()	#取0-1间的随机小数
```

##### 显示命令的源码

```
Ctrl + B
```

##### 取小数位数

1、round

```
a = 32.3423566
b = round(a,2)	#取两位小数
print(b)	#32.34
```

2、round.0-1间的小数，取三位小数

```

a = round(random.random(),3)
```

3、"%.2f"

```

a = "%.2f"%random.random()
```

##### 按键等于某个字母

```
#用户按下q键，退出
while True:
	if ord('q') == cv.waitKey(0):
		break
```

### 字符串拼接

```
print('%s %s' % ('Hello', 'world'))
>>> Hello world
```

```
# 简洁版
s1 = 'Hello {}! My name is {}.'.format('World', 'Python猫')
print(s1)
>>>Hello World! My name is Python猫.
 
# 对号入座版
s2 = 'Hello {0}! My name is {1}.'.format('World', 'Python猫')
s3 = 'Hello {name1}! My name is {name2}.'.format(name1='World', name2='Python猫')
print(s2)
>>>Hello World! My name is Python猫.
print(s3)
>>>Hello World! My name is Python猫.
```

```
str_list = ['Hello', 'world']
str_join1 = ' '.join(str_list)
str_join2 = '-'.join(str_list)
print(str_join1) >>>Hello world
print(str_join2) >>>Hello-world
```

我比较喜欢这个方法f

```
name ='world'
myname ='python_cat'
words =f'Hello {name}. My name is {myname}.'
print(words)
>>> Hello world. My name is python_cat.
```

# 使用DOS运行

#### 使用DOS直接运行

1. 输入python回车
2. 输入运行代码，如1 + 1，回车
3. exit() 退出

#### DOS运行Python文件

1. cd desktop  `要运行的Python文件目录`
2. python text.py

# 注释

单行注释：`#空格`，`选中按Ctrl+/`

多行注释：`'''前后三个单引号，或者前后三个双引号'''`

# 二进制0b

8bit=1byte     #8位等于1字节，1bit可能是1也可能是0

1024byte=1kb   #千字节

1024kb=1MB

1024MB=1GB

1024GB=1TB

==二进制前面加0b==

==八进制前面加0o==

==十六进制前面加0x==

# 标识符和保留字

![image-20200914130729765](markdownImg/Python/image-20200914130729765.png)

# 变量

name='马丽亚'

print(name)

1. 变量为储存数据的盒子
2. 变量包括id,type,value

![image-20200914131959560](markdownImg/Python/image-20200914131959560.png)

# 数据类型

![image-20200914132334695](markdownImg/Python/image-20200914132334695.png)

### 整数类型

![image-20200914132516747](markdownImg/Python/image-20200914132516747.png)

n1=90

print(n1,type(n1))

### 浮点类型

![image-20200914133546475](markdownImg/Python/image-20200914133546475.png)

from decimal import Decimal

print(Decimal('1.1')+Decimal('2.2')）

### 布尔类型

![image-20200914135413293](markdownImg/Python/image-20200914135413293.png)

### 字符串类型

![image-20200914135555568](markdownImg/Python/image-20200914135555568.png)

# 数据类型转换

![image-20200914140219249](markdownImg/Python/image-20200914140219249.png)

age=20  

name='张三'

print('我叫'+name+'今年'+str(age)+'岁')        #str(age) 将整数类型转换为字符串类型，才能相连不会报错

# 代码

### print

print(520)

print ('hello world')

print(3+1)

print('hello','world')   #不进行换行输出，同行输出

# 将文件输出到文件中

1. 所指定的盘符存在
2. 使用file=  的形式
3. a+  #如果文件不存在就创建，存在就在文件后追加 

fp=open('D:/text.txt','a+')

print('helloworld',file=fp)

fp.close()

# 转义字符

![image-20200914123946221](C:\Users\zhonghua.deng\AppData\Roaming\Typora\typora-user-images\image-20200914123946221.png)

print('hello==\n==world')     #换行

print('hello==\t==world')      #四个空格位置，四个四个排列自动补空格位

print('hello==\r==world')      #回车，输出为world，world将hello覆盖了

print('hello==\b==world')     #退一格

`print('http:\\\\www.baidu.com') `   #其中两个\为转义符

print('老师说：\‘大家好\’')    #为了输出‘，需要在前面加转义符\

# 原字符

1. 不希望字符串中的转义字符起作用，就在字符串前加r或R
2. 最后一个字符不能是反斜线，如print(r'hello\nworld==\\==')报错

print(==r=='hello\nworld')     #转义字符\n不再起作用

# 第三章

### input

![image-20200914143732030](markdownImg/Python/image-20200914143732030.png)

![image-20200914144027753](C:\Users\zhonghua.deng\AppData\Roaming\Typora\typora-user-images\image-20200914144027753.png)

a=int(input('请输入第一个加数：'))

b=int(input('请输入第二个加数：'))

print(a+b)

### 运算符

![image-20200914144706599](markdownImg/Python/image-20200914144706599.png)

##### 算术运算符

![image-20200914144756293](markdownImg/Python/image-20200914144756293.png)

print(11//2)    #5，整除

print(-9//4)    #-3，==一正一负向下取整==

print(11%2)    #1，取余

print(2**3)     #8，2的3次方

print(9%-4)     #-3   ==余数=被除数-除数*商==

print(-9%4)     #3    ==余数=被除数-除数*商==

![image-20200914151144007](markdownImg/Python/image-20200914151144007.png)

##### 赋值运算符

![image-20200914200336526](markdownImg/Python/image-20200914200336526.png)

a=20 

a+=30             #即a=a+30

print(a)           #50

==交换值==    a,b=b,a                   #解包赋值

##### 比较运算符

![image-20200914202039957](markdownImg/Python/image-20200914202039957.png)

#####  布尔运算符

![image-20200914202708424](markdownImg/Python/image-20200914202708424.png)

![image-20200914202720688](markdownImg/Python/image-20200914202720688.png)

s='helloworld'

print('w' in s)             #True

##### 位运算符

![image-20200914203114920](markdownImg/Python/image-20200914203114920.png)

print(4<<1)             #8，向左移动一位相当于乘以一次2

print(4>>2)             #1，向右移动两位，相当于除以两次2

##### 运算符的优先级

![image-20200914204121187](markdownImg/Python/image-20200914204121187.png)

算术运算》位运算》比较运算》布尔运算》赋值运算符     ==有括号先算括号内==

# 第四章

### 对象的布尔值

![image-20200914204836978](markdownImg/Python/image-20200914204836978.png)

### 程序的组织结构

![image-20200914204421384](markdownImg/Python/image-20200914204421384.png)

##### 顺序结构

![image-20200914204534325](markdownImg/Python/image-20200914204534325.png)

##### 选择结构 

![image-20200914205326928](markdownImg/Python/image-20200914205326928.png)

###### 单分支结构

![image-20200914205500618](markdownImg/Python/image-20200914205500618.png)

![image-20200914205704529](markdownImg/Python/image-20200914205704529.png)

###### 双分支结构

![image-20200914205746259](markdownImg/Python/image-20200914205746259.png)

![image-20200914210022060](markdownImg/Python/image-20200914210022060.png)

###### 多分支结构

![image-20200914210212707](markdownImg/Python/image-20200914210212707.png)

![image-20200914210908309](markdownImg/Python/image-20200914210908309.png)

# 第五章

### 内置函数range()

![image-20200914213704057](markdownImg/Python/image-20200914213704057.png)

r=range(1,10,2)

print(list(r))      #[1,3,5,7,9]

### while循环

![image-20200914215418872](markdownImg/Python/image-20200914215418872.png)

##### while循环执行流程

![image-20200914222304089](markdownImg/Python/image-20200914222304089.png)

###### 1到100偶数和

```
sum=0
a=1
while a<=100：
​    if a%2==0:
​    sum+=a
a+=1
print('1-100偶数和'，sum)
```

### for-in循环

![image-20200914223230332](markdownImg/Python/image-20200914223230332.png)

```
for i in range(10):
print(i)            #   输出0,1,2,3,4,5,6,7，8,9    每个数字一行

for _ in range(5):
print('我是帅哥')    #输出5行  我是帅哥

sum=1
for item in range(1,101):
​    if item%2==0:
​        sum+=item
print('1到100之间的偶数和为:',sum)
```



### break语句

![image-20200914225608455](markdownImg/Python/image-20200914225608455.png)

![image-20200914225940818](markdownImg/Python/image-20200914225940818.png)

### continue语句

![image-20200914230034214](markdownImg/Python/image-20200914230034214.png)

![image-20200914230231701](markdownImg/Python/image-20200914230231701.png)

### else语句

 ![image-20200914230417030](markdownImg/Python/image-20200914230417030.png)

### 嵌套循环

![image-20200915103100220](markdownImg/Python/image-20200915103100220.png)

###### 99乘法表

```python
for i in range(1,10):
    for j in range(1,i+1):
        print(i,'*',j,'=',i*j,end='\t')
    print()
```

### 总结

![image-20200915105823925](markdownImg/Python/image-20200915105823925.png)

# 第六章(列表)

### 列表取步长

```
list1 = [1,3,5,3,4,4,3,7,3]
list2 = list1[::3]	//每三个间隔取一个值
```



### 列表的创建

第一种方法

```python
lst=['hello','world',98]
```

第二种方法

```
lst2=lis(['hello','world',98])
```

### 列表的特点

![image-20200915111954850](markdownImg/Python/image-20200915111954850.png)

### 列表的查询

![image-20200915112324930](markdownImg/Python/image-20200915112324930.png)

```python
lst=['hello','world',98,'hello']
print(lst.index('hello'))
print(lst.index('hello',1,4))
```

### 列表的切片操作

![image-20200915114424144](markdownImg/Python/image-20200915114424144.png)

### 列表元素的增加

![image-20200915114915882](markdownImg/Python/image-20200915114915882.png)

### 列表元素的删除

![image-20200915115534580](markdownImg/Python/image-20200915115534580.png)

###### 切片删除

```python
lst=['hello','world',98,'nihao']
new_lst=lst[1:3]
print(new_lst)       #['world', 98]
lst[1:3]=[]
print(lst)       #['hello', 'nihao']
```

###### 清除列表所有元素

```
lst=['hello','world',98,'nihao']
lst.clear()
print(lst)
```

###### 将列表对象删除del

```
lst=['hello','world',98,'nihao']
del lst
print(lst)        #无对象，报错
```

### 列表元素的修改

指定位置修改

```
lst=['hello','world',98,'nihao']
lst[3]=100
print(lst)        #['hello', 'world', 98, 100]
```

切片修改

```
lst=['hello','world',98,'nihao']
lst[1:2]=[10,20]
print(lst)        #['hello', 10, 20, 98, 'nihao']
```

### 列表排序

![image-20200916085341614](markdownImg/Python/image-20200916085341614.png)

###### 不产生新对象（新id）,sort()

```
lst=[50,40,60,10,90]
lst.sort()
print(lst)      #[10, 40, 50, 60, 90]
```

```
lst=[50,40,60,10,90]
lst.sort(reverse=True)
print(lst)      #[90, 60, 50, 40, 10]
```

###### 产生对象（新id)，sorted()

```
lst=[50,40,60,10,90]
new_lst=sorted(lst)
print(new_lst)      #[10, 40, 50, 60, 90]
```

```
lst=[50,40,60,10,90]
desc_lst=sorted(lst,reverse=True)
print(desc_lst)      #[90, 60, 50, 40, 10]
```

### 列表生成式

![image-20200916090622934](markdownImg/Python/image-20200916090622934.png)

```
lst=[i*i for i in range(1,10)]
print(lst)   #[1, 4, 9, 16, 25, 36, 49, 64, 81]
```

### 总结

![image-20200916091024470](markdownImg/Python/image-20200916091024470.png)

# 第七章(字典)

### 字典

![image-20200916091209314](markdownImg/Python/image-20200916091209314.png)

![image-20200916091453350](markdownImg/Python/image-20200916091453350.png)

### 字典创建

![image-20200916091901768](markdownImg/Python/image-20200916091901768.png)

```
scores={'张三':100,'李四':98,'王五':60}
print(scores)
```

```
student=dict(name='jack',age=20)
print(student)
```

### 字典的常用操作

![image-20200916092507191](markdownImg/Python/image-20200916092507191.png)

```
scores={'张三':100,'李四':98,'王五':60}
print(scores['张三'])     #100 若查无结果报错
```

```
scores={'张三':100,'李四':98,'王五':60}
print(scores.get('张三'))   #100 若查无结果显示None
```

![image-20200916093010421](markdownImg/Python/image-20200916093010421.png)

```
scores={'张三':100,'李四':98,'王五':60}
print('张三' in scores)  #True  判断
```

```
scores={'张三':100,'李四':98,'王五':60}
del scores['张三']
print(scores)  #{'李四': 98, '王五': 60} 删除
```

```
scores={'张三':100,'李四':98,'王五':60}
scores['陈六']=150
print(scores)  #{'张三': 100, '李四': 98, '王五': 60, '陈六': 150}  新增
```

```
scores={'张三':100,'李四':98,'王五':60}
scores['陈六']=150
print(scores)
scores['陈六']=180
print(scores) #{'张三': 100, '李四': 98, '王五': 60, '陈六': 180}  修改
```

![image-20200916095419108](markdownImg/Python/image-20200916095419108.png)

```
scores={'张三':100,'李四':98,'王五':60}
keys=scores.keys()
print(keys) #['张三', '李四', '王五']
```

![image-20200916095903608](markdownImg/Python/image-20200916095903608.png)

### 字典的特点

![image-20200916100046379](markdownImg/Python/image-20200916100046379.png)

### 字典生成式???

![image-20200916100654009](markdownImg/Python/image-20200916100654009.png)

```
items=['Apple','Banana','Pear']
prices=[20,40,30]
d={item:price for item,price in zip(items,prices)}
print(d)  #{'Apple': 20, 'Banana': 40, 'Pear': 30}
```

### 总结

![image-20200916101256571](markdownImg/Python/image-20200916101256571.png)

# 第八章(元组、集合)

### 元组的创建

![image-20200916121809406](markdownImg/Python/image-20200916121809406.png)

### 元组遍历

![image-20200916122726609](markdownImg/Python/image-20200916122726609.png)

### 集合

![image-20200916122850387](markdownImg/Python/image-20200916122850387.png)

==集合内的元素不允许重复==

==集合内的元素是无序的==

### 集合的创建

![image-20200916123029833](markdownImg/Python/image-20200916123029833.png)

### 集合的相关操作

![image-20200916151742640](markdownImg/Python/image-20200916151742640.png)

```
print(100 in s)
```

```
s.pop()
```

### 集合间的关系

![image-20200916152111480](markdownImg/Python/image-20200916152111480.png)

```
s1={1,3,5,7,8,9}
s2={1,3,5}
s3={1,3,10}
print(s2.issubset(s1))   #True    子集
print(s1.issuperset(s2)) #True    超集
print(s2.isdisjoint(s3)) #False   是否没有交集
print(s2.intersection(s3)) #{1, 3}  交集
print(s2 & s3) ##{1, 3}  交集，等同intersection
print(s2.union(s3)) #{1, 3, 5, 10} 并集
print(s2 | s3) #{1, 3, 5, 10} 并集,等同union
print(s2.difference(s3)) #{5} 差集
print(s2 - s3) #{5} 差集,等同difference
print(s2.symmetric_difference(s3)) #{10, 5} 对称差集
print(s2 ^ s3) #{10, 5} 对称差集,等同symmetric_difference
```

### 集合生成式

![image-20200916154536443](markdownImg/Python/image-20200916154536443.png)

### 总结

![image-20200916155037588](markdownImg/Python/image-20200916155037588.png)

# 列表、字典、元组、集合总结（6-8章）

![image-20200916154832524](markdownImg/Python/image-20200916154832524.png)

# 第九章

### 字符串的驻留机制

![image-20200916200847303](markdownImg/Python/image-20200916200847303.png)

###### 字符串驻留机制的优缺点

![image-20200916200943587](markdownImg/Python/image-20200916200943587.png)

### 字符串的常用操作

###### 查询

![image-20200916201145173](markdownImg/Python/image-20200916201145173.png)

###### 大小写转换

![image-20200916201605126](markdownImg/Python/image-20200916201605126.png)

###### 内容对齐

![image-20200916203117708](markdownImg/Python/image-20200916203117708.png)

```
s='hello,Python'
print(s.center(20,'*')) #****hello,Python****
```

###### 劈分操作

![image-20200916211223229](markdownImg/Python/image-20200916211223229.png)

```
s='hello world Python'
lst=s.split()
print(lst) #['hello', 'world', 'Python']
```

```
s='hello|world|Python'
print(s.split(sep='|')) #['hello', 'world', 'Python']
```

```
s='hello|world|Python'
print(s.split(sep='|',maxsplit=1)) #['hello', 'world|Python']
```

###### 判断

![image-20200916211954600](markdownImg/Python/image-20200916211954600.png)

###### 替换、合并

![image-20200916212449240](markdownImg/Python/image-20200916212449240.png)

```
s='hello,world,world,world'
print(s.replace('world','nihao',2)) #hello,nihao,nihao,world
```

```
s=['hello','world','world']
print('|'.join(s)) #hello|world|world
```

###### 字符串的比较

![image-20200916213518966](markdownImg/Python/image-20200916213518966.png)

###### 字符串的切片操作

![image-20200916214849794](markdownImg/Python/image-20200916214849794.png)

### 格式化字符串,占位符{}

![image-20200916221959239](markdownImg/Python/image-20200916221959239.png)

```
x_labels = ["{}Year".format(i) for i in range(10,20)]
```

```
name='张三'
age=20
print('我叫%s,今年%d岁'%(name,age)) #我叫张三,今年20岁
```

```
name='张三'
age=20
print('我叫{0},今年{1}岁'.format(name,age)) #我叫张三,今年20岁
```

```
name='张三'
age=20
print(f'我叫{name},今年{age}岁') #我叫张三,今年20岁
```

```
print('%10d' % 99) #10为宽度
print('%.3f' % 3.1415926) #3.142   .3保留三位小数
```

```
print('{0:.3}'.format(3.1415926)) #3.14  .3表示的是一共三位数
print('{0:.3f}'.format(3.1415926)) #3.142  .3f表示三位小数
print('{:10.3f}'.format(3.1415926)) #     3.142  10位，位小数???
```

### 字符串编码转换

![image-20200916223407344](markdownImg/Python/image-20200916223407344.png)

###### 编码

```
s='天涯共此时'
print(s.encode(encoding='GBK')) #GBK一个中文占两字节
print(s.encode(encoding='UTF-8')) #UTF-8 一个中文占三个字节
```

###### 解码

```
s='天涯共此时'
byte=s.encode(encoding='GBK')  #编码
print(byte.decode(encoding='GBK')) #解码
```

### 总结

![image-20200916224209662](markdownImg/Python/image-20200916224209662.png)

# 第十章

### 函数的创建和调用

![image-20200917083458935](markdownImg/Python/image-20200917083458935.png)

![image-20200917083744662](markdownImg/Python/image-20200917083744662.png)

### 函数的参数传递

![image-20200917084012342](markdownImg/Python/image-20200917084012342.png)

==在函数调用过程中，进行参数的传递==

==如果是不可变对象，在函数体的修改不会影响实参的值,如n1=89==

==如果是可变对象，在函数体的修改会影响实参的值，如n2=[10.20.30]==

### 函数的返回值

![image-20200917085520656](markdownImg/Python/image-20200917085520656.png)

### 函数的参数定义

![image-20200917090753454](markdownImg/Python/image-20200917090753454.png)

![image-20200917091106803](markdownImg/Python/image-20200917091106803.png)

### 函数的参数总结

![image-20200917091841004](markdownImg/Python/image-20200917091841004.png)

```
def fun1(a,b,*,c,d):  #在*之后的参数，只能采用关键字参数传递
```

### 变量的作用域

![image-20200917093840800](markdownImg/Python/image-20200917093840800.png)

```
def fun1():
    global  age #函数内变量使用global声明，就变了全局变量
```

### 递归函数

![image-20200917094921402](markdownImg/Python/image-20200917094921402.png)

![image-20200917095055394](markdownImg/Python/image-20200917095055394.png)

```
def fac(n):
    if n==1:
        return 1
    else:
        return n*fac(n-1)
print(fac(6)) #720
```

### 总结

###### 斐波那契数列

```
def fib(n):
    if n==1:
        return 1
    elif n==2:
        return 1
    else:
        return fib(n-1)+fib(n-2)
print(fib(6)) #8
```

![image-20200917101323344](markdownImg/Python/image-20200917101323344.png)

# 第十一章

### Bug的分类

###### 语法错误

![image-20200917102111902](markdownImg/Python/image-20200917102111902.png)

![image-20200917102540366](markdownImg/Python/image-20200917102540366.png)

###### 思路不清

![image-20200917102725664](markdownImg/Python/image-20200917102725664.png)

![image-20200917103754222](markdownImg/Python/image-20200917103754222.png)

###### 被动掉坑

![image-20200917104018584](markdownImg/Python/image-20200917104018584.png)

![image-20200917104241807](markdownImg/Python/image-20200917104241807.png)

![image-20200917104603992](markdownImg/Python/image-20200917104603992.png)

```
try:
    a=int(input('请输入第一个整数：'))
    b=int(input('请输入第二个整数：'))
    result=a/b
    print('结果为：',result)
except ZeroDivisionError
    print('对不起，除数不允许为0')
except ValueError
    print('只能输入数字串')
```

### 异常处理机制

###### try...except..else

![image-20200917105138174](markdownImg/Python/image-20200917105138174.png)

```
try:
    a=int(input('请输入第一个整数：'))
    b=int(input('请输入第二个整数：'))
    result=a/b
except BaseException as e:
    print('出错了',e)
else:
    print('结果为：',result)
```

###### try...except...else...finally

![image-20200917105511234](markdownImg/Python/image-20200917105511234.png)

###### traceback模块

![image-20200917110221590](markdownImg/Python/image-20200917110221590.png)

### Bug自查

![image-20200917102358516](markdownImg/Python/image-20200917102358516.png)

### 常见的异常类型

![image-20200917105842722](markdownImg/Python/image-20200917105842722.png)

### Pycharm开发环境调试

![image-20200917110458183](markdownImg/Python/image-20200917110458183.png)

### 总结

![image-20200917110757974](markdownImg/Python/image-20200917110757974.png)

# 第十二章

### 编程思想

![image-20200917110927710](markdownImg/Python/image-20200917110927710.png)

### 类与对象type

![image-20200917111419262](markdownImg/Python/image-20200917111419262.png)

### *类的创建

![image-20200917111559980](markdownImg/Python/image-20200917111559980.png)

==类首字母大写==

### *对象的创建

![image-20200917120338058](markdownImg/Python/image-20200917120338058.png)

### *类属性、类方法、静态方法

![image-20200917120958040](markdownImg/Python/image-20200917120958040.png)

### 动态绑定属性和方法

![image-20200917121503588](markdownImg/Python/image-20200917121503588.png)

### 总结

![image-20200917122319216](markdownImg/Python/image-20200917122319216.png)

# 第十三章

### 面向对象的三大特征

### 封装

![image-20200917122557200](markdownImg/Python/image-20200917122557200.png)

![image-20200917123054023](markdownImg/Python/image-20200917123054023.png)

### 继承

![image-20200917123431884](markdownImg/Python/image-20200917123431884.png)

![image-20200917123836667](markdownImg/Python/image-20200917123836667.png)

### 方法重写

![image-20200917142057175](markdownImg/Python/image-20200917142057175.png)

### object类

![image-20200917143243723](markdownImg/Python/image-20200917143243723.png)

### 多态

![image-20200917143826279](markdownImg/Python/image-20200917143826279.png)

### 静态语言与动态语言

![image-20200917144558380](markdownImg/Python/image-20200917144558380.png)

### 特殊方法和特殊属性

![image-20200917144920969](markdownImg/Python/image-20200917144920969.png)

### 类的浅拷贝与深拷贝

```
copy2 = copy.copy(PC1)
copy3 = copy.deepcopy(PC1)
```

![image-20200917151521430](markdownImg/Python/image-20200917151521430.png)

### 总结

![image-20200917160251137](markdownImg/Python/image-20200917160251137.png)

# 第十四章

### 模块

![image-20200917160618251](markdownImg/Python/image-20200917160618251.png)

### 模块创建与导入

![image-20200917161016421](markdownImg/Python/image-20200917161016421.png)

### 以主程序形式运行

只有在此函数自己的模块中运行才会运行。

### ![image-20200917162044798](markdownImg/Python/image-20200917162044798.png)

```
if __name__ == '__main__':
```

# Python中的包

![image-20200917163807262](markdownImg/Python/image-20200917163807262.png)

Python中常用的内置模块

![image-20200917164411081](markdownImg/Python/image-20200917164411081.png)

### 第三方模块的安装与应用

![image-20200917164835627](markdownImg/Python/image-20200917164835627.png)

### 模块schedule

1. cmd--pip install schedule

```
import schedule
import time

def job():
	print('哈哈')

schedule.every(3).seconds.do(job)	#每隔3秒运行一次job函数
while True:
	schedule.run_pending()
	time.sleep(1)		#休眠一秒
```



### 总结

![image-20200917165123501](markdownImg/Python/image-20200917165123501.png)

### 编码格式

![image-20200917184229436](markdownImg/Python/image-20200917184229436.png)

### 修改编码格式

比如在*.py最上面添加 #encoding#gbk ，即可把文件变为gbk的编码格式文件

![image-20200917184453362](markdownImg/Python/image-20200917184453362.png)

![image-20200917184719417](markdownImg/Python/image-20200917184719417.png)

```
file=open('a.txt','r')
print(file.readlines())
file.close()
```

### 常用的文件打开模式

![image-20200917185219003](markdownImg/Python/image-20200917185219003.png)

```
file=open('a.txt','w')
file.write('Python')
file.close()
```

### 文件对象的常用方法

![image-20200917185804794](markdownImg/Python/image-20200917185804794.png)

### with语句（上下文管理器）

![image-20200917190958960](markdownImg/Python/image-20200917190958960.png)

```
with open('a.txt','r') as file
    print(file.read())
```

### 目录操作（OS模块）

![image-20200917192001842](markdownImg/Python/image-20200917192001842.png)

```
import os
os.system('notepad.exe')
```

```
import os
os.startfile('C:\\ProgramData\\Microsoft\\Windows\\Start Menu\\Programs\\微信\\微信.exe')
```

### OS模块操作目录相关函数

![image-20200917193506406](markdownImg/Python/image-20200917193506406.png)

==listdir(path),办公自动化==

### os.path模块操作目录相关函数

![image-20200917194309265](markdownImg/Python/image-20200917194309265.png)

```
import os.path
print(os.path.basename((E:\\SDFS\\SDSDF\\SDFSDF\\ER\\demo13.py)))
```

```
#列出制定目录下的所有py文件
import os
path=os.getcwd()
lst=os.listdir(path)
for filename in lst:
    if filename.endswith('.py'):
        print(filename)
```

### walk

遍历当前目录和子目录  P134

### 总结

![image-20200917200737585](markdownImg/Python/image-20200917200737585.png)

# 案例：学生信息录入系统

### 录入学生信息功能

![image-20200918093931111](markdownImg/Python/image-20200918093931111.png)

###### 业务流程

![image-20200918094022012](markdownImg/Python/image-20200918094022012.png)

### 删除学生信息功能

![image-20200918104612053](markdownImg/Python/image-20200918104612053.png)

![image-20200918104651081](markdownImg/Python/image-20200918104651081.png)

### 修改学生信息功能

![image-20200918110740456](markdownImg/Python/image-20200918110740456.png)

![image-20200918110841939](markdownImg/Python/image-20200918110841939.png)

![image-20200918110957009](markdownImg/Python/image-20200918110957009.png)

# 格式

###### 颜色

![image-20200918122627939](markdownImg/Python/image-20200918122627939.png)

![image-20200918122707059](markdownImg/Python/image-20200918122707059.png)

###### 小数点个数

![image-20200918122925890](markdownImg/Python/image-20200918122925890.png)

# 案例

![image-20200918123944997](markdownImg/Python/image-20200918123944997.png)

![image-20200918124150265](markdownImg/Python/image-20200918124150265.png)

任务3   random

![image-20200918124312562](markdownImg/Python/image-20200918124312562.png)

![image-20200918124629902](markdownImg/Python/image-20200918124629902.png)

![image-20200918125202720](markdownImg/Python/image-20200918125202720.png)

任务4

![image-20200918125755062](markdownImg/Python/image-20200918125755062.png)

![image-20200918125821417](markdownImg/Python/image-20200918125821417.png)

# 爬虫

pip install requests

###### UA伪装：反反爬策略

###### 抓取sougou的搜索页面

```
import requests
if __name__=="__main__":
    #UA伪装，将对应的User-Agent封装到一个字典中
    headers = {
        'user-agent':'Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/85.0.4183.102 Safari/537.36'
    }
    #url='https://www.sogou.com/web?query=%E9%82%93%E4%B8%AD%E5%8D%8E'
    url = 'https://www.sogou.com/web'
    #处理URL携带的参数，封装到字典中
    kw = input('enter a word:')
    param = {
        'query':kw
    }
    #对指定URL发起的请求对应的url是携带参数的，并且请求过程中处理了参数
    response = requests.get(url=url,params=param,headers=headers) #UA伪装
    page_text = response.text
    filename = kw+'.html'
    with open(filename,'w',encoding='utf=8') as fp:
        fp.write(page_text)
    print(filename,'保存成功！')
```

###### 百度翻译

```
import requests
import json
if __name__=="__main__":
    post_url = 'https://fanyi.baidu.com/sug'
    headers = {
        'user-agent': 'Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/85.0.4183.102 Safari/537.36'
    }
    #post请求参数处理，与get请求一致
    word = input('enter a word:')
    data = {
        'kw':wordha
    }
    #请求发送
    response = requests.post(url=post_url,data=data,headers=headers)
    #获取相应数据：json(）方法返回的是obj（如果确认相应数据为json类型的才可以使用.json()
    dic_obj = response.json()
    #持久化存储
    filename = word+'.json'
    fp = open(filename,'w',encoding='utf-8')
    json.dump(dic_obj,fp=fp,ensure_ascii=False)
    print('Over!!!')
```