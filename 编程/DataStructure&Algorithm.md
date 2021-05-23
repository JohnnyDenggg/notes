+ 程序 = 数据结构 + 算法

![image-20210425080658406](markdownImg/DataStructure&Algorithm/image-20210425080658406.png)

![image-20210425102138283](markdownImg/DataStructure&Algorithm/image-20210425102138283.png)

# 教程

https://www.bilibili.com/video/BV1nJ411V7bd

# 注意点

### 引用符号

&

### 取地址

```
&a
```

### 存储密度

![image-20210425202707017](markdownImg/DataStructure&Algorithm/image-20210425202707017.png)

# 类c语言补充

## C语言

### 数组定义

![image-20210425112326808](markdownImg/DataStructure&Algorithm/image-20210425112326808.png)

### 内存动态分配

![image-20210425112521423](markdownImg/DataStructure&Algorithm/image-20210425112521423.png)

## 类C语言

![image-20210425123049647](markdownImg/DataStructure&Algorithm/image-20210425123049647.png)

![image-20210425123204729](markdownImg/DataStructure&Algorithm/image-20210425123204729.png)

### 传值方式

#### 传实参（形参变、实参不发生变化）

![image-20210425123638555](markdownImg/DataStructure&Algorithm/image-20210425123638555.png)

#### 传指针（形参变、实参发生变化）

+ 交换m、n地址指向的内容

![image-20210425124040302](markdownImg/DataStructure&Algorithm/image-20210425124040302.png)

#### 传指针（形参变、实参不发生变化）

+ 交换m、n指向的地址

![image-20210425124238106](markdownImg/DataStructure&Algorithm/image-20210425124238106.png)

#### 数组名作参数（形参变、实参发生变化）

![image-20210425124535973](markdownImg/DataStructure&Algorithm/image-20210425124535973.png)

#### 引用类型作参数（形参变、实参发生变化）

+ 引用符号&

![image-20210425124708421](markdownImg/DataStructure&Algorithm/image-20210425124708421.png)

![image-20210425124807820](markdownImg/DataStructure&Algorithm/image-20210425124807820.png)

# 预定义常量和类型

![image-20210425130143588](markdownImg/DataStructure&Algorithm/image-20210425130143588.png)

+ 例子

![image-20210425130551044](markdownImg/DataStructure&Algorithm/image-20210425130551044.png)

# 数据

### 抽象数据（ADT）

![image-20210425080936445](markdownImg/DataStructure&Algorithm/image-20210425080936445.png)

# ==逻辑结构==

对象的特性及关系

# 1. 线性表

![image-20210425102503868](markdownImg/DataStructure&Algorithm/image-20210425102503868.png)

#### 线性表的操作

![image-20210425130029605](markdownImg/DataStructure&Algorithm/image-20210425130029605.png)

![image-20210425104604235](markdownImg/DataStructure&Algorithm/image-20210425104604235.png)

![image-20210425104641664](markdownImg/DataStructure&Algorithm/image-20210425104641664.png)

![image-20210425104850725](markdownImg/DataStructure&Algorithm/image-20210425104850725.png)

![image-20210425104950232](markdownImg/DataStructure&Algorithm/image-20210425104950232.png)

![image-20210425105132757](markdownImg/DataStructure&Algorithm/image-20210425105132757.png)

![image-20210425105238168](markdownImg/DataStructure&Algorithm/image-20210425105238168.png)

#### 定义线性表的模板

![image-20210425110608263](markdownImg/DataStructure&Algorithm/image-20210425110608263.png)

![image-20210425110847736](markdownImg/DataStructure&Algorithm/image-20210425110847736.png)

+ 例子

![image-20210425111014034](markdownImg/DataStructure&Algorithm/image-20210425111014034.png)

## 1.1 顺序表

包括线性表、链表

### 操作顺序表

![image-20210425125933830](markdownImg/DataStructure&Algorithm/image-20210425125933830.png)

### 顺序表的优缺点

![image-20210425135256337](markdownImg/DataStructure&Algorithm/image-20210425135256337.png)

### 顺序表的算法

#### 顺序表的初始化

![image-20210425130438022](markdownImg/DataStructure&Algorithm/image-20210425130438022.png)

#### 销毁顺序表

![image-20210425130706492](markdownImg/DataStructure&Algorithm/image-20210425130706492.png)

#### 清空顺序表

![image-20210425130728703](markdownImg/DataStructure&Algorithm/image-20210425130728703.png)

#### 求顺序表长度

![image-20210425130832459](markdownImg/DataStructure&Algorithm/image-20210425130832459.png)

#### 判断顺序表是否为空

![image-20210425130854743](markdownImg/DataStructure&Algorithm/image-20210425130854743.png)

#### 顺序表的取值

![image-20210425130928013](markdownImg/DataStructure&Algorithm/image-20210425130928013.png)

#### 顺序表按值查找

+ if

![image-20210425131544800](markdownImg/DataStructure&Algorithm/image-20210425131544800.png)

+ while

![image-20210425131753563](markdownImg/DataStructure&Algorithm/image-20210425131753563.png)

#### 顺序表的插入

![image-20210425133228032](markdownImg/DataStructure&Algorithm/image-20210425133228032.png)

![image-20210425133452601](markdownImg/DataStructure&Algorithm/image-20210425133452601.png)

##### 插入的平均移动次数

![image-20210425133853994](markdownImg/DataStructure&Algorithm/image-20210425133853994.png)

#### 顺序表的删除

![image-20210425134525307](markdownImg/DataStructure&Algorithm/image-20210425134525307.png)

![image-20210425134638198](markdownImg/DataStructure&Algorithm/image-20210425134638198.png)

##### 平均删除次数

![image-20210425135010184](markdownImg/DataStructure&Algorithm/image-20210425135010184.png)

## 1.2 链表

![image-20210425141543656](markdownImg/DataStructure&Algorithm/image-20210425141543656.png)

### 链表术语

![image-20210425141916081](markdownImg/DataStructure&Algorithm/image-20210425141916081.png)

![image-20210425142037629](markdownImg/DataStructure&Algorithm/image-20210425142037629.png)

![image-20210425142150339](markdownImg/DataStructure&Algorithm/image-20210425142150339.png)

### 链表的特点

![image-20210425142655675](markdownImg/DataStructure&Algorithm/image-20210425142655675.png)

## 1.2.1 单链表

![image-20210425143119932](markdownImg/DataStructure&Algorithm/image-20210425143119932.png)

### 单链表的定义和表示

![image-20210425143729445](markdownImg/DataStructure&Algorithm/image-20210425143729445.png)

### 单链表的存储结构

![image-20210425144218025](markdownImg/DataStructure&Algorithm/image-20210425144218025.png)

### 例子

![image-20210425144510194](markdownImg/DataStructure&Algorithm/image-20210425144510194.png)

### ==单链表算法！！！==

#### 单链表初始化（空链表）

![image-20210425145625652](markdownImg/DataStructure&Algorithm/image-20210425145625652.png)

#### 判断单链表是否为空

![image-20210425145758372](markdownImg/DataStructure&Algorithm/image-20210425145758372.png)

#### 销毁单链表

![image-20210425150642588](markdownImg/DataStructure&Algorithm/image-20210425150642588.png)

![image-20210425150753934](markdownImg/DataStructure&Algorithm/image-20210425150753934.png)

#### 清空单链表

![image-20210425153716733](markdownImg/DataStructure&Algorithm/image-20210425153716733.png)

![image-20210425153759273](markdownImg/DataStructure&Algorithm/image-20210425153759273.png)

#### 求单链表的表长

![image-20210425154259801](markdownImg/DataStructure&Algorithm/image-20210425154259801.png)

#### 取单链表第i个元素

![image-20210425155559636](markdownImg/DataStructure&Algorithm/image-20210425155559636.png)

#### 单链表查找（按值查）

+ 获取该数据所在的位置（地址）

![image-20210425160049162](markdownImg/DataStructure&Algorithm/image-20210425160049162.png)

+ 获取该数据所在的位置序号

![image-20210425160202823](markdownImg/DataStructure&Algorithm/image-20210425160202823.png)

#### 单链表插入

![image-20210425160925159](markdownImg/DataStructure&Algorithm/image-20210425160925159.png)

![image-20210425161114695](markdownImg/DataStructure&Algorithm/image-20210425161114695.png)

#### 单链表删除第i个结点

![image-20210425161546784](markdownImg/DataStructure&Algorithm/image-20210425161546784.png)

![image-20210425161601424](markdownImg/DataStructure&Algorithm/image-20210425161601424.png)

#### 单链表的建立

##### 头插法

![image-20210425162656309](markdownImg/DataStructure&Algorithm/image-20210425162656309.png)

![image-20210425163137820](markdownImg/DataStructure&Algorithm/image-20210425163137820.png)

![image-20210425164408312](markdownImg/DataStructure&Algorithm/image-20210425164408312.png)

##### 尾插法

![image-20210425164057006](markdownImg/DataStructure&Algorithm/image-20210425164057006.png)

![image-20210425164328583](markdownImg/DataStructure&Algorithm/image-20210425164328583.png)

### 单链表操作的时间效率

![image-20210425162324533](markdownImg/DataStructure&Algorithm/image-20210425162324533.png)

## 1.2.2 循环链表

![image-20210425164724128](markdownImg/DataStructure&Algorithm/image-20210425164724128.png)

### 找头结点、尾结点

![image-20210425164944352](markdownImg/DataStructure&Algorithm/image-20210425164944352.png)

### 循环链表的合并

![image-20210425165243412](markdownImg/DataStructure&Algorithm/image-20210425165243412.png)

![image-20210425165347035](markdownImg/DataStructure&Algorithm/image-20210425165347035.png)

## 1.2.3 双向链表

### 定义

![image-20210425184518787](markdownImg/DataStructure&Algorithm/image-20210425184518787.png)

### 双向链表的插入

![image-20210425201323575](markdownImg/DataStructure&Algorithm/image-20210425201323575.png)

![image-20210425201332685](markdownImg/DataStructure&Algorithm/image-20210425201332685.png)

### 双向链表的删除

![image-20210425201607008](markdownImg/DataStructure&Algorithm/image-20210425201607008.png)

![image-20210425201614105](markdownImg/DataStructure&Algorithm/image-20210425201614105.png)

## 单链表、循环链表和双链表的时间效率比较

![image-20210425201847000](markdownImg/DataStructure&Algorithm/image-20210425201847000.png)

##  顺序表和链表的比较

![image-20210425202909743](markdownImg/DataStructure&Algorithm/image-20210425202909743.png)

## 线性表的应用

### 线性表的合并

![image-20210425203242920](markdownImg/DataStructure&Algorithm/image-20210425203242920.png)

![image-20210425203251598](markdownImg/DataStructure&Algorithm/image-20210425203251598.png)

![image-20210425203442300](markdownImg/DataStructure&Algorithm/image-20210425203442300.png)

### 有序表的合并（顺序表实现）

![image-20210425205404872](markdownImg/DataStructure&Algorithm/image-20210425205404872.png)

![image-20210425205801481](markdownImg/DataStructure&Algorithm/image-20210425205801481.png)

![image-20210425205853706](markdownImg/DataStructure&Algorithm/image-20210425205853706.png)

### 有序表合并（链表实现）

![image-20210425211221696](markdownImg/DataStructure&Algorithm/image-20210425211221696.png)

![image-20210425210823570](markdownImg/DataStructure&Algorithm/image-20210425210823570.png)

## 多项式运算

### 一元多项式运算

![image-20210425212201668](markdownImg/DataStructure&Algorithm/image-20210425212201668.png)

### 稀疏多项式的运算

![image-20210425212730811](markdownImg/DataStructure&Algorithm/image-20210425212730811.png)

![image-20210425213114829](markdownImg/DataStructure&Algorithm/image-20210425213114829.png)

## 案例：图书信息管理系统

![image-20210425213425003](markdownImg/DataStructure&Algorithm/image-20210425213425003.png)

# 2. 栈（stack）

+ 特殊的线性表（操作受限）

+ 后进先出(Last in first out)（LIFO）

### 定义

![image-20210426084509311](markdownImg/DataStructure&Algorithm/image-20210426084509311.png)

![image-20210426085430550](markdownImg/DataStructure&Algorithm/image-20210426085430550.png)

### 栈案例：进制转换

![image-20210426091407391](markdownImg/DataStructure&Algorithm/image-20210426091407391.png)

### 栈案例：括号匹配检验

![image-20210426091834817](markdownImg/DataStructure&Algorithm/image-20210426091834817.png)

### 栈案例：表达式求值

![image-20210426092312270](markdownImg/DataStructure&Algorithm/image-20210426092312270.png)

![image-20210426093508207](markdownImg/DataStructure&Algorithm/image-20210426093508207.png)

### 栈的抽象数据类型定义

![image-20210426093825220](markdownImg/DataStructure&Algorithm/image-20210426093825220.png)

### 栈的操作

![image-20210426094152433](markdownImg/DataStructure&Algorithm/image-20210426094152433.png)

### 栈的存储方式

![image-20210426094919013](markdownImg/DataStructure&Algorithm/image-20210426094919013.png)

空栈、满栈

![image-20210426095316553](markdownImg/DataStructure&Algorithm/image-20210426095316553.png)

上溢、下溢

![image-20210426095548432](markdownImg/DataStructure&Algorithm/image-20210426095548432.png)

### 顺序栈的算法

#### 顺序栈的定义

![image-20210426095704776](markdownImg/DataStructure&Algorithm/image-20210426095704776.png)

#### 顺序栈的初始化

![image-20210426100443055](markdownImg/DataStructure&Algorithm/image-20210426100443055.png)

#### 顺序栈是否为空

![image-20210426100518571](markdownImg/DataStructure&Algorithm/image-20210426100518571.png)

#### 顺序栈长度

![image-20210426100628073](markdownImg/DataStructure&Algorithm/image-20210426100628073.png)

#### 顺序栈清空

![image-20210426100722408](markdownImg/DataStructure&Algorithm/image-20210426100722408.png)

#### 顺序栈的销毁

![image-20210426100842447](markdownImg/DataStructure&Algorithm/image-20210426100842447.png)

#### 顺序栈的入栈

![image-20210426103620210](markdownImg/DataStructure&Algorithm/image-20210426103620210.png)

#### 顺序栈的出栈

![image-20210426103932049](markdownImg/DataStructure&Algorithm/image-20210426103932049.png)

### 链栈的定义

![image-20210426104747629](markdownImg/DataStructure&Algorithm/image-20210426104747629.png)

### 链栈的算法

#### 链栈初始化

![image-20210426104834843](markdownImg/DataStructure&Algorithm/image-20210426104834843.png)

#### 链栈是否为空

![image-20210426104851764](markdownImg/DataStructure&Algorithm/image-20210426104851764.png)

#### 链栈入栈

![image-20210426105034267](markdownImg/DataStructure&Algorithm/image-20210426105034267.png)

#### 链栈出栈

![image-20210426105204306](markdownImg/DataStructure&Algorithm/image-20210426105204306.png)

#### 链栈取栈顶元素

![image-20210426105342878](markdownImg/DataStructure&Algorithm/image-20210426105342878.png)

### 递归

#### 递归的定义

![image-20210426105534607](markdownImg/DataStructure&Algorithm/image-20210426105534607.png)

#### 递归问题：分治法

![image-20210426110323243](markdownImg/DataStructure&Algorithm/image-20210426110323243.png)

![image-20210426110420049](markdownImg/DataStructure&Algorithm/image-20210426110420049.png)

#### 递归的优缺点

![image-20210426111636022](markdownImg/DataStructure&Algorithm/image-20210426111636022.png)

#### 函数的调用过程

![image-20210426110626240](markdownImg/DataStructure&Algorithm/image-20210426110626240.png)

### 栈与递归

![image-20210426111723283](markdownImg/DataStructure&Algorithm/image-20210426111723283.png)

![image-20210426111506122](markdownImg/DataStructure&Algorithm/image-20210426111506122.png)

# 3. 队列（queue）

+ 特殊的线性表（操作受限）

+ 先进先出(First in first out)（FIFO）

### 定义

![image-20210426112033678](markdownImg/DataStructure&Algorithm/image-20210426112033678.png)

![image-20210426085821111](markdownImg/DataStructure&Algorithm/image-20210426085821111.png)

### 队列应用

![image-20210426112125008](markdownImg/DataStructure&Algorithm/image-20210426112125008.png)

### 队列的抽象数据类型定义

![image-20210426112220964](markdownImg/DataStructure&Algorithm/image-20210426112220964.png)

### 顺序队列（base）

![image-20210426112826301](markdownImg/DataStructure&Algorithm/image-20210426112826301.png)

### 循环队列

真溢出、假溢出

![image-20210426122347827](markdownImg/DataStructure&Algorithm/image-20210426122347827.png)

![image-20210426122747435](markdownImg/DataStructure&Algorithm/image-20210426122747435.png)

### 循环队列判断队空、队满

![image-20210426125158721](markdownImg/DataStructure&Algorithm/image-20210426125158721.png)

### 循环队列算法

#### 循环队列类型定义

![image-20210426125412642](markdownImg/DataStructure&Algorithm/image-20210426125412642.png)

#### 循环队列初始化

![image-20210426125658612](markdownImg/DataStructure&Algorithm/image-20210426125658612.png)

#### 循环队列的长度

![image-20210426125952813](markdownImg/DataStructure&Algorithm/image-20210426125952813.png)

#### 循环队列的入队

![image-20210426130147046](markdownImg/DataStructure&Algorithm/image-20210426130147046.png)

#### 循环队列的出队

![image-20210426130259222](markdownImg/DataStructure&Algorithm/image-20210426130259222.png)

#### 取队头元素

![image-20210426130434390](markdownImg/DataStructure&Algorithm/image-20210426130434390.png)

### 链队列

![image-20210426131002350](markdownImg/DataStructure&Algorithm/image-20210426131002350.png)

### 链队列算法

#### 链队列定义

![image-20210426130940619](markdownImg/DataStructure&Algorithm/image-20210426130940619.png)

#### 链队列初始化

![image-20210426131607008](markdownImg/DataStructure&Algorithm/image-20210426131607008.png)

#### 链队列销毁

![image-20210426131848042](markdownImg/DataStructure&Algorithm/image-20210426131848042.png)

#### 链队列的入队

![image-20210426132240581](markdownImg/DataStructure&Algorithm/image-20210426132240581.png)

#### 链队列出队

![image-20210426132634709](markdownImg/DataStructure&Algorithm/image-20210426132634709.png)

#### 链队列队头元素

![image-20210426132712290](markdownImg/DataStructure&Algorithm/image-20210426132712290.png)

# 串

+ 内容受限的线性表
+ 内容只能为字符

### 串的定义

![image-20210426133309644](markdownImg/DataStructure&Algorithm/image-20210426133309644.png)

+ 子串、真子串、空格串

![image-20210426133701553](markdownImg/DataStructure&Algorithm/image-20210426133701553.png)

+ 串相等

![image-20210426133759069](markdownImg/DataStructure&Algorithm/image-20210426133759069.png)

### 串的类型定义、运算

![image-20210426134318542](markdownImg/DataStructure&Algorithm/image-20210426134318542.png)

![image-20210426134338572](markdownImg/DataStructure&Algorithm/image-20210426134338572.png)

### 串顺序存储（教常用）

+ 第一个位置不存储字符
+ 便于查找

![image-20210426135037767](markdownImg/DataStructure&Algorithm/image-20210426135037767.png)

### 串链式存储

+ 便于修改

![image-20210426135329491](markdownImg/DataStructure&Algorithm/image-20210426135329491.png)

![image-20210426135359871](markdownImg/DataStructure&Algorithm/image-20210426135359871.png)

### 串的模式匹配算法

![image-20210426135913609](markdownImg/DataStructure&Algorithm/image-20210426135913609.png)

#### BF算法

![image-20210426140231809](markdownImg/DataStructure&Algorithm/image-20210426140231809.png)

![image-20210426141549648](markdownImg/DataStructure&Algorithm/image-20210426141549648.png)

![image-20210426141613850](markdownImg/DataStructure&Algorithm/image-20210426141613850.png)

##### BF算法时间复杂度

![image-20210426141909491](markdownImg/DataStructure&Algorithm/image-20210426141909491.png)

### KMP算法

+ i不需要回溯，主串一直往下读

![image-20210426151121575](markdownImg/DataStructure&Algorithm/image-20210426151121575.png)

![image-20210426152304517](markdownImg/DataStructure&Algorithm/image-20210426152304517.png)

+ next改进（nextval）

![image-20210426152206960](markdownImg/DataStructure&Algorithm/image-20210426152206960.png)

![image-20210426151441925](markdownImg/DataStructure&Algorithm/image-20210426151441925.png)

![image-20210426151515661](markdownImg/DataStructure&Algorithm/image-20210426151515661.png)

# 数组

+ 线性结构的推广（严格来说是非线性结构）

### 二维数组

![image-20210426152748264](markdownImg/DataStructure&Algorithm/image-20210426152748264.png)

![image-20210426152940464](markdownImg/DataStructure&Algorithm/image-20210426152940464.png)

### 数组的抽象数据类型定义

![image-20210426153414585](markdownImg/DataStructure&Algorithm/image-20210426153414585.png)

![image-20210426154004131](markdownImg/DataStructure&Algorithm/image-20210426154004131.png)

### 二维数组存储位置

![image-20210426155242787](markdownImg/DataStructure&Algorithm/image-20210426155242787.png)

### 对称矩阵的压缩存储

### 对角矩阵的压缩存储

### 稀疏矩阵的压缩存储

#### 三元组方法

![image-20210426162306337](markdownImg/DataStructure&Algorithm/image-20210426162306337.png)

#### 十字链表方法

![image-20210426162736161](markdownImg/DataStructure&Algorithm/image-20210426162736161.png)

# 广义表

### 广义表定义

+ 线性结构的推广（严格来说是非线性结构）

+ 每个元素可能是原子，也可能是一个广义表

![image-20210426163857920](markdownImg/DataStructure&Algorithm/image-20210426163857920.png)

![image-20210426164157257](markdownImg/DataStructure&Algorithm/image-20210426164157257.png)

### 广义表性质

![image-20210426164714258](markdownImg/DataStructure&Algorithm/image-20210426164714258.png)

![image-20210426164808945](markdownImg/DataStructure&Algorithm/image-20210426164808945.png)

# 树

### 树的基本术语

![image-20210427090047772](markdownImg/DataStructure&Algorithm/image-20210427090047772.png)

## 二叉树

### 二叉树抽象数据类型定义

![image-20210427093520629](markdownImg/DataStructure&Algorithm/image-20210427093520629.png)

![image-20210427093745232](markdownImg/DataStructure&Algorithm/image-20210427093745232.png)

### 二叉树性质

![image-20210427094329533](markdownImg/DataStructure&Algorithm/image-20210427094329533.png)

![image-20210427094440849](markdownImg/DataStructure&Algorithm/image-20210427094440849.png)

![image-20210427094839046](markdownImg/DataStructure&Algorithm/image-20210427094839046.png)

## 满二叉树

![image-20210427100841774](markdownImg/DataStructure&Algorithm/image-20210427100841774.png)

## 完全二叉树

![image-20210427101127848](markdownImg/DataStructure&Algorithm/image-20210427101127848.png)

![image-20210427101407561](markdownImg/DataStructure&Algorithm/image-20210427101407561.png)

![image-20210427103253008](markdownImg/DataStructure&Algorithm/image-20210427103253008.png)

![image-20210427103540233](markdownImg/DataStructure&Algorithm/image-20210427103540233.png)

## 二叉树的存储结构

### 二叉树的顺序存储

![image-20210427103957213](markdownImg/DataStructure&Algorithm/image-20210427103957213.png)

+ 例子

![image-20210427104256242](markdownImg/DataStructure&Algorithm/image-20210427104256242.png)

![image-20210427104751944](markdownImg/DataStructure&Algorithm/image-20210427104751944.png)

### 二叉树的链式存储

![image-20210427105419713](markdownImg/DataStructure&Algorithm/image-20210427105419713.png)

![image-20210427105609455](markdownImg/DataStructure&Algorithm/image-20210427105609455.png)

![image-20210427105738760](markdownImg/DataStructure&Algorithm/image-20210427105738760.png)

![image-20210427110116412](markdownImg/DataStructure&Algorithm/image-20210427110116412.png)

### 三叉链表

![image-20210427110311119](markdownImg/DataStructure&Algorithm/image-20210427110311119.png)

## 遍历二叉树

![image-20210427111045261](markdownImg/DataStructure&Algorithm/image-20210427111045261.png)

![image-20210427111214771](markdownImg/DataStructure&Algorithm/image-20210427111214771.png)

### 先序遍历

![image-20210427111712383](markdownImg/DataStructure&Algorithm/image-20210427111712383.png)

### 例子：写出三种遍历（先序，中序，后序）

![image-20210427112109923](markdownImg/DataStructure&Algorithm/image-20210427112109923.png)

## 二叉树算法

### 先序遍历（递归）

![image-20210427121907503](markdownImg/DataStructure&Algorithm/image-20210427121907503.png)

![image-20210427122231161](markdownImg/DataStructure&Algorithm/image-20210427122231161.png)

![image-20210427122642293](markdownImg/DataStructure&Algorithm/image-20210427122642293.png)

### 中序遍历（递归）

![image-20210427122417302](markdownImg/DataStructure&Algorithm/image-20210427122417302.png)

### 中序遍历（栈）

![image-20210427123626444](markdownImg/DataStructure&Algorithm/image-20210427123626444.png)

### 后序遍历（递归）

![image-20210427122447619](markdownImg/DataStructure&Algorithm/image-20210427122447619.png)

### 层次遍历

![image-20210427124047683](markdownImg/DataStructure&Algorithm/image-20210427124047683.png)

![image-20210427124059975](markdownImg/DataStructure&Algorithm/image-20210427124059975.png)

### 建立二叉树（先序遍历）

![image-20210427125836393](markdownImg/DataStructure&Algorithm/image-20210427125836393.png)

### 复制二叉树（先序遍历）

![image-20210427132546269](markdownImg/DataStructure&Algorithm/image-20210427132546269.png)

### 计算二叉树深度

![image-20210427132836377](markdownImg/DataStructure&Algorithm/image-20210427132836377.png)

### 计算二叉树结点总数

![image-20210427133349922](markdownImg/DataStructure&Algorithm/image-20210427133349922.png)

### 计算二叉树叶子结点数

![image-20210427133954940](markdownImg/DataStructure&Algorithm/image-20210427133954940.png)

## 线索二叉树

![image-20210427135443237](markdownImg/DataStructure&Algorithm/image-20210427135443237.png)

+ 增加一个头结点

![image-20210427135312036](markdownImg/DataStructure&Algorithm/image-20210427135312036.png)

### 先序线索二叉树

![image-20210427135012385](markdownImg/DataStructure&Algorithm/image-20210427135012385.png)

## 树的存储结构

### 双亲表示法

![image-20210427140520548](markdownImg/DataStructure&Algorithm/image-20210427140520548.png)

### 孩子链表

+ 找孩子容易，找双亲难

![image-20210427141210013](markdownImg/DataStructure&Algorithm/image-20210427141210013.png)

![image-20210427141332592](markdownImg/DataStructure&Algorithm/image-20210427141332592.png)

### 带双亲孩子链表

![image-20210427141551424](markdownImg/DataStructure&Algorithm/image-20210427141551424.png)

### 孩子兄弟表示法（二叉树表示法，二叉链表表示法）

![image-20210427142017989](markdownImg/DataStructure&Algorithm/image-20210427142017989.png)

## 树与二叉树的转换

### 1. 树转为二叉树

+ 通过孩子兄弟方法转换

![image-20210427142931202](markdownImg/DataStructure&Algorithm/image-20210427142931202.png)

![image-20210427142949153](markdownImg/DataStructure&Algorithm/image-20210427142949153.png)

![image-20210427143109023](markdownImg/DataStructure&Algorithm/image-20210427143109023.png)

### 2. 二叉树转为树

![image-20210427143301613](markdownImg/DataStructure&Algorithm/image-20210427143301613.png)

![image-20210427143422924](markdownImg/DataStructure&Algorithm/image-20210427143422924.png)

## 森林和二叉树转换

### 1. 森林转换成二叉树

![image-20210427143904629](markdownImg/DataStructure&Algorithm/image-20210427143904629.png)

![image-20210427143949980](markdownImg/DataStructure&Algorithm/image-20210427143949980.png)

### 2. 二叉树转换为森林

![image-20210427144312896](markdownImg/DataStructure&Algorithm/image-20210427144312896.png)

![image-20210427144445728](markdownImg/DataStructure&Algorithm/image-20210427144445728.png)

## 树与森林的遍历

### 树的遍历

![image-20210427145155788](markdownImg/DataStructure&Algorithm/image-20210427145155788.png)

### 森林的遍历

#### 1. 先序遍历

![image-20210427145612445](markdownImg/DataStructure&Algorithm/image-20210427145612445.png)

#### 2. 中序遍历

![image-20210427145645124](markdownImg/DataStructure&Algorithm/image-20210427145645124.png)

# 哈弗曼树

## 哈弗曼树定义

![image-20210427153606092](markdownImg/DataStructure&Algorithm/image-20210427153606092.png)

## 树的路径长度（TL）

![image-20210427152802896](markdownImg/DataStructure&Algorithm/image-20210427152802896.png)

## 权、带权路径长度

![image-20210427153406436](markdownImg/DataStructure&Algorithm/image-20210427153406436.png)

## 哈夫曼算法

### 口诀

![image-20210427154139274](markdownImg/DataStructure&Algorithm/image-20210427154139274.png)

### 构造哈弗曼树

![image-20210427154852424](markdownImg/DataStructure&Algorithm/image-20210427154852424.png)

### 构造哈弗曼树算法实现

![image-20210427155744693](markdownImg/DataStructure&Algorithm/image-20210427155744693.png)

+

![image-20210427155957761](markdownImg/DataStructure&Algorithm/image-20210427155957761.png)

## 哈夫曼编码（HC）

前缀编码

最优前缀码

![image-20210427161005906](markdownImg/DataStructure&Algorithm/image-20210427161005906.png)

### 哈夫曼编码算法

![image-20210427163413351](markdownImg/DataStructure&Algorithm/image-20210427163413351.png)

![image-20210427162612052](markdownImg/DataStructure&Algorithm/image-20210427162612052.png)

![image-20210427162536293](markdownImg/DataStructure&Algorithm/image-20210427162536293.png)

## 哈夫曼解码

![image-20210427163310446](markdownImg/DataStructure&Algorithm/image-20210427163310446.png)

![image-20210427163257616](markdownImg/DataStructure&Algorithm/image-20210427163257616.png)

# 图

## 图的定义及术语

![image-20210427163943542](markdownImg/DataStructure&Algorithm/image-20210427163943542.png)

#### 完全图

![image-20210427164032909](markdownImg/DataStructure&Algorithm/image-20210427164032909.png)

#### 稀疏图、稠密图、网、邻接、关联

![image-20210427164314781](markdownImg/DataStructure&Algorithm/image-20210427164314781.png)

#### 顶点的度、入度、出度

![image-20210427164423451](markdownImg/DataStructure&Algorithm/image-20210427164423451.png)

#### 有向树

![image-20210427165826507](markdownImg/DataStructure&Algorithm/image-20210427165826507.png)

#### 路径、路径长度、回路、简单路径、简单回路（简单环）

![image-20210427164802488](markdownImg/DataStructure&Algorithm/image-20210427164802488.png)

#### 连通图（强连通图）

![image-20210427165028396](markdownImg/DataStructure&Algorithm/image-20210427165028396.png)

#### 权和网

![image-20210427165138369](markdownImg/DataStructure&Algorithm/image-20210427165138369.png)

#### 子图

![image-20210427165740453](markdownImg/DataStructure&Algorithm/image-20210427165740453.png)

#### 联通分量（强联通分量）

![image-20210427165357475](markdownImg/DataStructure&Algorithm/image-20210427165357475.png)

![image-20210427165548483](markdownImg/DataStructure&Algorithm/image-20210427165548483.png)

#### 极小联通子图、生成树、生成森林

![image-20210427165709724](markdownImg/DataStructure&Algorithm/image-20210427165709724.png)

## 邻接矩阵（表示稠密图）

### 邻接矩阵定义存储结构

![image-20210427194759249](markdownImg/DataStructure&Algorithm/image-20210427194759249.png)

### 算法（图的存储）

#### 邻接矩阵表示创建无向网

![image-20210427195229864](markdownImg/DataStructure&Algorithm/image-20210427195229864.png)

![image-20210427195240288](markdownImg/DataStructure&Algorithm/image-20210427195240288.png)

#### 查找顶点

+ 查找图中相同顶点的下标

![image-20210427195509129](markdownImg/DataStructure&Algorithm/image-20210427195509129.png)

## 邻接表（表示稀疏图）

![image-20210427201332225](markdownImg/DataStructure&Algorithm/image-20210427201332225.png)

### 无向图邻接表

![image-20210427201846016](markdownImg/DataStructure&Algorithm/image-20210427201846016.png)

### 有向图邻接表

![image-20210427204833155](markdownImg/DataStructure&Algorithm/image-20210427204833155.png)

### 邻接表缺点

![image-20210427211648628](markdownImg/DataStructure&Algorithm/image-20210427211648628.png)

### 算法：图的邻接表存储

#### 顶点的结点结构

![image-20210427205241931](markdownImg/DataStructure&Algorithm/image-20210427205241931.png)

#### 弧(边)的结点结构

![image-20210427205429467](markdownImg/DataStructure&Algorithm/image-20210427205429467.png)

#### 图的结构定义

![image-20210427205559649](markdownImg/DataStructure&Algorithm/image-20210427205559649.png)

#### 算法：邻接表创建无向网

![image-20210427210125936](markdownImg/DataStructure&Algorithm/image-20210427210125936.png)

![image-20210427210241355](markdownImg/DataStructure&Algorithm/image-20210427210241355.png)

 ![image-20210427210517812](markdownImg/DataStructure&Algorithm/image-20210427210517812.png)

## 十字链表

![image-20210427212520955](markdownImg/DataStructure&Algorithm/image-20210427212520955.png)

## 邻接多重表

 ![image-20210427213529214](markdownImg/DataStructure&Algorithm/image-20210427213529214.png)

## 图的遍历

### 深度优先搜索(Depth_First Search-DFS)

一条道走到黑

![image-20210427214316290](markdownImg/DataStructure&Algorithm/image-20210427214316290.png)

![image-20210427214449348](markdownImg/DataStructure&Algorithm/image-20210427214449348.png)

#### 算法实现：深度优先搜索

![image-20210427214944601](markdownImg/DataStructure&Algorithm/image-20210427214944601.png)

### 广度优先搜索（Breadth_First Search-BFS）

![image-20210427215610848](markdownImg/DataStructure&Algorithm/image-20210427215610848.png)

#### 算法实现：广度优先搜索

![image-20210427220029136](markdownImg/DataStructure&Algorithm/image-20210427220029136.png)

## 生成树

### 生成树定义

![image-20210429081724018](markdownImg/DataStructure&Algorithm/image-20210429081724018.png)

### 无向图生成树

![image-20210429082110408](markdownImg/DataStructure&Algorithm/image-20210429082110408.png)

### 最小生成树的定义

![image-20210429082253732](markdownImg/DataStructure&Algorithm/image-20210429082253732.png)

### MST

![image-20210429083929699](markdownImg/DataStructure&Algorithm/image-20210429083929699.png)

### 构造最小生成树算法

#### 普里姆算法

通过MST进行

![image-20210429083801318](markdownImg/DataStructure&Algorithm/image-20210429083801318.png)

#### 克鲁斯卡尔算法

最小生成树可能不唯一

![image-20210429084343393](markdownImg/DataStructure&Algorithm/image-20210429084343393.png)

#### 算法比较

![image-20210429084554482](markdownImg/DataStructure&Algorithm/image-20210429084554482.png)

## 最短路径

### 算法

#### 单源最短路径-Dijkstra算法

![image-20210429085754460](markdownImg/DataStructure&Algorithm/image-20210429085754460.png)

![image-20210429095343266](markdownImg/DataStructure&Algorithm/image-20210429095343266.png)

#### 所有顶点间的最短路径-Floyd算法

![image-20210429100134496](markdownImg/DataStructure&Algorithm/image-20210429100134496.png)

## 拓扑排序

+ AOV（vertex）

+ 如果图中存在换，则不能输出全部顶点

![image-20210429104600330](markdownImg/DataStructure&Algorithm/image-20210429104600330.png)

## 关键路径

+ AOE（edge）

![image-20210429125010088](markdownImg/DataStructure&Algorithm/image-20210429125010088.png)

![image-20210429131253714](markdownImg/DataStructure&Algorithm/image-20210429131253714.png)

### 求关键路径

![image-20210429132234339](markdownImg/DataStructure&Algorithm/image-20210429132234339.png)

# 查找

## 查找基本概念

### 平均查找长度

![image-20210429133207366](markdownImg/DataStructure&Algorithm/image-20210429133207366.png)

## 1. 线性表的查找

![image-20210429133851425](markdownImg/DataStructure&Algorithm/image-20210429133851425.png)

### 顺序查找

![image-20210429134150983](markdownImg/DataStructure&Algorithm/image-20210429134150983.png)

![image-20210429134650387](markdownImg/DataStructure&Algorithm/image-20210429134650387.png)

### 折半查找

+ 只用于有序表，且限于顺序存储结构
+ 比顺序查找效率高

![image-20210429140031423](markdownImg/DataStructure&Algorithm/image-20210429140031423.png)

![image-20210429140327279](markdownImg/DataStructure&Algorithm/image-20210429140327279.png)

![image-20210429144719394](markdownImg/DataStructure&Algorithm/image-20210429144719394.png)

### 分块查找

![image-20210429150046646](markdownImg/DataStructure&Algorithm/image-20210429150046646.png)

### 线性表查找方法比较

![image-20210429150218921](markdownImg/DataStructure&Algorithm/image-20210429150218921.png)

## 2. 树表的查找

### 二叉排序树

#### 定义

![image-20210429150516221](markdownImg/DataStructure&Algorithm/image-20210429150516221.png)

#### 二叉排序树的存储结构

![image-20210429151247764](markdownImg/DataStructure&Algorithm/image-20210429151247764.png)

+ 递归算法

![image-20210429151517814](markdownImg/DataStructure&Algorithm/image-20210429151517814.png)

+ 时间复杂度

![image-20210504085450205](markdownImg/DataStructure&Algorithm/image-20210504085450205.png)

### 平衡二叉树(AVL)

![image-20210504085743340](markdownImg/DataStructure&Algorithm/image-20210504085743340.png)

![image-20210504085808218](markdownImg/DataStructure&Algorithm/image-20210504085808218.png)

#### 变换

![image-20210504090717092](markdownImg/DataStructure&Algorithm/image-20210504090717092.png)

## 3. 散列表的查找（哈希表）

![image-20210504094035370](markdownImg/DataStructure&Algorithm/image-20210504094035370.png)

### 线性探测法



### 二次探测法（开放定址法）

![image-20210504100444805](markdownImg/DataStructure&Algorithm/image-20210504100444805.png)

### 链地址法

![image-20210504100821922](markdownImg/DataStructure&Algorithm/image-20210504100821922.png)

+ 优点

![image-20210504100949587](markdownImg/DataStructure&Algorithm/image-20210504100949587.png)

### 散列表的查找

# 排序

+ 存储结构，记录序列以顺序表存储

![image-20210504103018126](markdownImg/DataStructure&Algorithm/image-20210504103018126.png)

## 插入排序

![image-20210504103226298](markdownImg/DataStructure&Algorithm/image-20210504103226298.png)

![image-20210504103326294](markdownImg/DataStructure&Algorithm/image-20210504103326294.png)

### 直接插入排序

![image-20210504103940284](markdownImg/DataStructure&Algorithm/image-20210504103940284.png)

![image-20210504104021201](markdownImg/DataStructure&Algorithm/image-20210504104021201.png)

### 二分插入排序（折半）

![image-20210504104713717](markdownImg/DataStructure&Algorithm/image-20210504104713717.png)

### 希尔排序

![image-20210504105235329](markdownImg/DataStructure&Algorithm/image-20210504105235329.png)

![image-20210504105538838](markdownImg/DataStructure&Algorithm/image-20210504105538838.png)

## 交换排序

### 冒泡排序

![image-20210504110451492](markdownImg/DataStructure&Algorithm/image-20210504110451492.png)

### 快速排序

![image-20210504111156928](markdownImg/DataStructure&Algorithm/image-20210504111156928.png)

![image-20210504111301503](markdownImg/DataStructure&Algorithm/image-20210504111301503.png)

![image-20210504111407012](markdownImg/DataStructure&Algorithm/image-20210504111407012.png)

![image-20210504111502693](markdownImg/DataStructure&Algorithm/image-20210504111502693.png)

## 选择排序

### 简单选择排序

![image-20210504111957748](markdownImg/DataStructure&Algorithm/image-20210504111957748.png)

![image-20210504112128460](markdownImg/DataStructure&Algorithm/image-20210504112128460.png)

### 堆排序

![image-20210504112846152](markdownImg/DataStructure&Algorithm/image-20210504112846152.png)

![image-20210504113326327](markdownImg/DataStructure&Algorithm/image-20210504113326327.png)

![image-20210504114016031](markdownImg/DataStructure&Algorithm/image-20210504114016031.png)

## 归并排序

![image-20210504114324852](markdownImg/DataStructure&Algorithm/image-20210504114324852.png)



## 基数排序

分配+收集

![image-20210504115042246](markdownImg/DataStructure&Algorithm/image-20210504115042246.png)

![image-20210504115157904](markdownImg/DataStructure&Algorithm/image-20210504115157904.png)

## 外部排序

略

## 各种排序比较

![image-20210504115359332](markdownImg/DataStructure&Algorithm/image-20210504115359332.png)

# 堆

## 定义

![image-20210504112535724](markdownImg/DataStructure&Algorithm/image-20210504112535724.png)

## 例子

![image-20210504112702891](markdownImg/DataStructure&Algorithm/image-20210504112702891.png)



# ==存储结构==

有效的组织计算机存储



# ==算法==

有效的实现对象之间的"运算"关系

## 算法设计要求

+  正确性
+ 可行性
+ 鲁棒性、健壮性
+ 高效性

## 算法时间复杂度

求嵌套层数最多的语句，比如 n^2^或n^3^...

## 平均查找长度（ASL)

![image-20210425132702193](markdownImg/DataStructure&Algorithm/image-20210425132702193.png)

