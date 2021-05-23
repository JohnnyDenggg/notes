# 教程

https://www.bilibili.com/video/BV16t411N7RD

回顾：P21，22

https://www.bilibili.com/video/BV1eV411t7fn

P25未



C语言、模电/数电、单片机、Linux、自控原理、 RTOS，RISC-V，异构

# 软件

Altium Designer 20

立创EDA

# 插件

## 铺铜插件

下载：

1. https://www.pcbbar.com/，右上角搜索“脚本”
2. 选择“[AD Skill/ad插件/ad**脚本**/ad敷铜**脚本** AD18/19快速敷铜**脚本**](https://www.pcbbar.com/forum.php?mod=viewthread&tid=10342&highlight=%BD%C5%B1%BE)”

使用：

1. AD-文件-运行脚本-浏览-选择脚本位置
2. 点击“FY_main.pas”，确定
3. 工具栏-布线辅助-铜皮分配网络属性

# 快捷键

| 功能                                 | 操作                                                         |
| ------------------------------------ | ------------------------------------------------------------ |
| 移动                                 | 右击                                                         |
| 放大缩小                             | Ctrl + 滚轮(Ctrl+右键，上下移动鼠标)                         |
| 旋转                                 | 空格                                                         |
| 复制                                 | Shift+左键                                                   |
| 对齐                                 | A                                                            |
| 修改快捷键                           | Ctrl+左击命令（没效果则可能冲突，再工具栏-customizing中查找冲突的快捷键） |
| 修改快捷键                           | 右击工具栏-Customizing-                                      |
| 镜像                                 | Y                                                            |
| 改属性                               | tab                                                          |
| 画水平垂直线(自动校准)               | Shift+Space                                                  |
| 视窗切换（3D等）                     | Ctrl+D                                                       |
| 3D旋转                               | Shift+右键                                                   |
| 移动                                 | M（MS,移动所选）                                             |
| 测量距离                             | Ctrl+M                                                       |
| 去除测量标注                         | Shift+C                                                      |
| 将图放到中心位置                     | 工具栏-编辑-设置参考-中心（EFC）                             |
| 画线（PcbLib）                       | PL                                                           |
| 镜像（复制，点击镜像点，黏贴，x或y） | x或y                                                         |
| 镜像                                 | 选中-MS-点击镜像点-按X或Y-点击镜像点                         |
| 特殊粘贴                             | 选中被复制体，Ctrl+C,点击中心，EA，阵列黏贴，属性设置好确定，再点击被复制体中心 |
| 割断（裁剪导线）                     | EK                                                           |
| 适用屏幕（原件）                     | VF（PCB库文件下）                                            |
| 复位错误标志                         | TM                                                           |
| 器件排列                             | 选中需要排列的-TO（L/R)                                      |
| 标记尺寸                             | PD                                                           |
| 层叠管理器                           | DK                                                           |
| 单层显示                             | Shift+S(一直按一直切换)变灰?                                 |
| 分屏                                 | 右击上部文件标题，垂直分割                                   |
| 联合、合并                           | 选中要联合的器件-右击-联合-从选中的器件联合                  |
| 高亮                                 | [                                                            |
| 显示线路                             | N-显示连接                                                   |
| 查看Class                            | DC                                                           |
| 规则                                 | DR                                                           |
| 选择网络                             | SN                                                           |
| 显示连线                             | N                                                            |
| 显示某层                             | L                                                            |
| DRC                                  | TD                                                           |

#### 建议快捷键（较常用P24）

![1](markdownImg/Altium Designer/1.png)



# 新建项目

1. 新建工程项目（选择目录，项目名）
2. 新建-库-原理图库（放在项目下，项目名.SchLib）
3. 新建-原理图（放在项目下，项目名.SchDoc）
4. 新建-库-PCB元件库（放在项目下，项目名.PcbLib）
5. 新建-PCB（放在项目下，项目名.PcbDoc）

# PCB设计注意点

1. 边框线与元件引脚焊盘最短距离不能小于2MM,(一般取5MM较合理)

2. PCB设计中,如果电路系统同时存在数字电路和模拟电路.pcblayout培训以及大电流电路,则必须分开布局,使各系统之间藕合达到最小在同一类型电路中,按信号流向及功能,分块,分区放置元件.

3. 输入信号处理单元,输出信号驱动元件应靠近pcb设计培训电路板边,使输入输出信号线尽可能短,以减小输入输出的干扰.

4. 元件放置方向: 元件只能沿水平和垂直两个方向排列.否则不得于插件. 当元件间电位差较大时,元件间距应足够大,防止出现放电现象

5. 元件间距.对于中等密度板,小元件,如小功率电阻,电容,二极管,等分立元件彼此的间距与插件,焊接工艺有关,波峰焊接时,元件间距可以取50-100MIL(1.27–2.54MM)手工可以大些,如取100MIL,集成电路芯片,元件间距一般为100–150MIL在而已进IC去藕电容要靠近芯片的电源秋地线引脚.不然滤波效果会变差.在数字电路中,为保证数字电路系统可靠工作。

   在每一数字集成电路芯片的电源和地之间均放置IC去藕电容.去藕电容一般采用瓷片电容,容量为0.01~0.1UF去藕电容容量的选择一般按系统工作频率F的倒数选择.此外,在电路电源的入口处的电源线和地线之间也需加接一个10UF的电容,以及一个0.01UF的瓷片电容.

   时钟电路元件尽量靠近单片机芯片的时钟信号引脚,以减小时钟电路的连线长度.且下面最好不要走线.刚印刷导线电阻大,线上的电压降也就大,影响电路的性能, 线宽太宽,则布线密度不高,板面积增加,除了增加成本外,也不利于小型化.

   如果电流负荷以20A/平方毫米计算,当覆铜箔厚度为0.5MM时,(一般为这么多,)则1MM(约40MIL)线宽的电流负荷为1A,因此,线宽取1–2.54MM(40–100MIL)能满足一般的应用要求,大功率设备板上的地线和电源,根据功率大小,可适当增加线宽,而在小功率的数字电路上,为了提高布线密度,最小线宽取0.254–1.27MM(10–15MIL)就能满足.

# 公式

| 电压U = IR                  |
| --------------------------- |
| 功率P = UI = I^2^R = U^2^/R |
|                             |
|                             |

#### 功率

1. 串联和并联功率都相加

#### 电阻

1. 串联电阻增大，并联电阻减小

# 电烙铁

1. 温度一般300-350

# 楞次定律

来拒去留、增反减同、增缩减扩

# 信号频率

1. 1秒内有多少个周期
2. 单位为Hz(赫兹)

![image-20210125123332789](markdownImg/Altium Designer/image-20210125123332789.png)

## 占空比

1. 一个周期高电平所占时间的比例
2. 占空比越大，功率输出越大

![image-20210125123804055](markdownImg/Altium Designer/image-20210125123804055.png)

# 器件代表符号

| 原件                 | 英文                                           | 单位                        |
| -------------------- | ---------------------------------------------- | --------------------------- |
| 电压                 | （voltage）                                    | V                           |
| 电流                 | （current）                                    | A                           |
| 伏特                 | Volt                                           |                             |
| 安培                 | Ampere                                         |                             |
| 瓦特                 | Watt                                           |                             |
| 电路                 | circuit                                        |                             |
| 电路元件             | circuit element                                |                             |
| 电阻                 | RES（resistance）                              | Ω（欧姆）                   |
| 电阻器               | resistor                                       |                             |
| 电感（电能存为磁能） | L (inductance)                                 |                             |
| 电感器               | inductor                                       |                             |
| 电容                 | CAP（capacitance）                             | F（法拉）<br />1uF = 1000nF |
| 电容器               | capacitor                                      |                             |
| 欧姆定律             | Ohm’s law                                      |                             |
| 基尔霍夫定律         | Kirchhoff’s law                                |                             |
| 基尔霍夫电压定律     | Kirchhoff’s voltage law(KVL)                   |                             |
| 基尔霍夫电流定律     | Kirchhoff’s current law(KCL)                   |                             |
| 回路                 | loop                                           |                             |
| 无源二端网络         | passive two-terminal network                   |                             |
| 有源二端网络         | active two-terminal network                    |                             |
| 三极管               | Q                                              |                             |
| 二极管               | D                                              |                             |
| 保险丝               | F                                              |                             |
| 晶振                 | X、Y                                           | MHz（兆赫兹）               |
| 蜂鸣器               | “H”或“HA”（旧标准用“FM”、“ZZG”、“LB”、“JD”等） |                             |

# 器件

## 变压器

1. 只能用于改变交流电

电压：U1/U2 = n1/n2（线圈数）

功率：P1 = P2

电流：I1/I2 = n2/n1  (根据P = UI)



![image-20210126130149953](markdownImg/Altium Designer/image-20210126130149953.png)

## 电容

1. 阻直流，通交流

![image-20210126105642875](markdownImg/Altium Designer/image-20210126105642875.png)

![image-20210125090143905](markdownImg/Altium Designer/image-20210125090143905.png)

## 继电器（开关）

![image-20210125164225159](markdownImg/Altium Designer/image-20210125164225159.png)

![image-20210125164157567](markdownImg/Altium Designer/image-20210125164157567.png)

## 光敏电阻

1. 光越强，电阻越小

## 场效应管（MOS管）

1. 栅极电压控制漏记和源极的开闭
2. 触发电压大约3.5-20V

![image-20210125105441739](markdownImg/Altium Designer/image-20210125105441739.png)

![image-20210125105249597](markdownImg/Altium Designer/image-20210125105249597.png)

## 三端稳压管

1. 将高电压转为低电压
2. 输入电压至少要大于额定输出电压2V左右时，才能保持输出电压稳定。
3. 输入电压大于三端稳压管最大输入电压时，输出电压不稳定。

![image-20210125105838199](markdownImg/Altium Designer/image-20210125105838199.png)

![image-20210125110356332](markdownImg/Altium Designer/image-20210125110356332.png)

## 可控硅、晶闸管

单项可控硅与MOS管相比

	1. 可大电流大耐压、可实现很大得功率。
	2. 能开不能关，必须通过关闭电源进行关闭（可通过适当电路弥补）

![image-20210125154116622](markdownImg/Altium Designer/image-20210125154116622.png)

双向可控硅（TRIAC/BCR）

1. 可控制交流电

![image-20210125155326079](markdownImg/Altium Designer/image-20210125155326079.png)

## 干簧管

1. 有常开和常闭两种
2. 常开：有磁铁靠近，两片靠近，通。

![image-20210125110636102](markdownImg/Altium Designer/image-20210125110636102.png)

![image-20210125110716306](markdownImg/Altium Designer/image-20210125110716306.png)

## 电感器

1. 减小电流增大和减小的速度（相当于阻碍和惯性）

![image-20210125111310819](markdownImg/Altium Designer/image-20210125111310819.png)

## 发光二极管

1. 长脚正极，短脚负极
2. 工作电流一般不超过20mA

![image-20210125120647881](markdownImg/Altium Designer/image-20210125120647881.png)

![image-20210125120820823](markdownImg/Altium Designer/image-20210125120820823.png)

## 稳压二极管

![image-20210125121626741](markdownImg/Altium Designer/image-20210125121626741.png)

## 双向出发二极管

![image-20210126093401796](markdownImg/Altium Designer/image-20210126093401796.png)

## 晶体三极管

![image-20210125112052420](markdownImg/Altium Designer/image-20210125112052420.png)

![image-20210125112319346](markdownImg/Altium Designer/image-20210125112319346.png)

![image-20210125112605380](markdownImg/Altium Designer/image-20210125112605380.png)

## 水银开关

![image-20210125122030091](markdownImg/Altium Designer/image-20210125122030091.png)

![image-20210125122008201](markdownImg/Altium Designer/image-20210125122008201.png)

## 温度开关

1. 达到温度，形成闭路

![image-20210125122251251](markdownImg/Altium Designer/image-20210125122251251.png)

## 震动开关（震动传感器）

1. 有常闭型和常开型

## 光耦

1. 内部左侧发光二极管，右侧光敏电阻

![image-20210125125940535](markdownImg/Altium Designer/image-20210125125940535.png)

![image-20210125130617401](markdownImg/Altium Designer/image-20210125130617401.png)

## 上拉电阻

![image-20210125164433671](markdownImg/Altium Designer/image-20210125164433671.png)

## 下拉电阻

![image-20210125164458143](markdownImg/Altium Designer/image-20210125164458143.png)

## 霍尔元件

型号举例：AH3503

应用：马达测转速

1. 磁铁的N级越靠近，输出电压越高。S级越靠近，输出电压越低。

## IGBT

型号举例：H25R1202

优点：高电压、高输入阻抗、热稳定性号、电压驱动型、大电流等

应用场景：高压、千瓦功率以上用IGBT。低压、中小功率用场效应管

![image-20210126103312906](markdownImg/Altium Designer/image-20210126103312906.png)

## 运算放大器（运放）回顾1、2、3、实验

1. 两个输入端一个级微小得电压差，输出电压就会放大100000-10000000倍，达到饱和

![image-20210125164705457](markdownImg/Altium Designer/image-20210125164705457.png)

![image-20210125164814846](markdownImg/Altium Designer/image-20210125164814846.png)

![image-20210125165010780](markdownImg/Altium Designer/image-20210125165010780.png)

#### 反相比例放大器

1. 作用：让输出电压为输入电压的倍数（而非运放的输出电压一下饱和）
2. 倍数：Auf = - Rf / R1 (10K/1K=10, 输出电压就是出入电压的10倍)

![image-20210126084402667](markdownImg/Altium Designer/image-20210126084402667.png)

## 锂电池

1. 最小2.7V,最大4.2V。过大或过小可能会损坏电池(可用PMOS管控制)

## 晶振

![image-20210206105047314](markdownImg/Altium Designer/image-20210206105047314.png)

![image-20210206105127714](markdownImg/Altium Designer/image-20210206105127714.png)

## 热敏电阻

1. 正温度系数热敏电阻器(PTC)在温度越高时电阻值越大
2. 负温度系数热敏电阻器(NTC)在温度越高时电阻值越低

![IMG_256](markdownImg/Altium Designer/clip_image002.jpg)

![img](markdownImg/Altium Designer/clip_image002-1612590188004.jpg)

# 注意点

#### 修改所有标号

选中一个标号-右键-查找相似对象-查找-取消-在右侧修改高即可

#### 线宽

1. VCC: 30mil

#### 层

```
toplayer ——顶层布线层,bottomlayer ——底层布线层,具有电气特性的走线。就是线路板上连接bai各个元器件引脚的连线。

mechanical ——机械层是定义整个PCB板的外观的，其实我们在说机械层的时候就是指整个PCB板的外形结构。

keepoutlayer ——禁止布线层，禁止布线层是定义我们在布电气特性的铜时的边界，也就是说我们先定义了禁止布线层后，我们在以后的布线过程中，所布的具有电气特性的线是不可能超出禁止布线层的边界。

topoverlay ——顶层丝印层，bottomoverlay ——底层丝印层，定义顶层和底层的丝印字符，就是一般我们在PCB板上看到的元件编号和一些字符。

toppaste ——顶层焊盘层，bottompaste ——底层焊盘层，顶层和底层焊盘层，它就是指我们可以看到的贴片元件的焊盘。

topsolder ——顶层阻焊层，bottomsolder ——底层阻焊层，由于PCB板是要默认上绿油的，用这两个层画线的地方就会开个“天窗"，不上绿油。在一些需要大电流流通的地方可以使用，以便另外加焊锡。

multilaye这个层实际上就和机械层差不多了，顾名思义，这个层就是指PCB板的所有层。
```

#### 分屏同时选中

```\
1.分屏模式下
2.勾选工具-交叉选择模式
```

#### 查找对应器件

```
1. PcbDoc中选择器件
2. 快捷键TC（即可在SchDoc中看到对应器件）
```

#### 将所有器件名放到器件中心

```
1. 选中所有器件
1. A-定位器件文本-标识符，点到中心-确定
```



#### 添加外部库

```
右击项目*.PrjPcb-添加已有文档到工程
```

#### 上划线

```
上划线（字母前后面都加\）
```

#### 生成原理图库

```
点击.SchLib文件-工具栏-设计-生成原理图库
复制到自己的原理图库中
```

#### 生成PCB库(DP)

```
点击.PcbDoc文件-工具栏-设计-生成PCB库
复制到自己的PCB库（PcbLib）
注意：一定要在左侧name栏黏贴
```

#### 将原理图库显示在右侧

```
1.点击右下角Panels，选择Components
2.选择 .SchLib文件
3.左键拖动电阻等到原理图中
```

![image-20210120215118605](markdownImg/Altium Designer/image-20210120215118605.png)

# 更新器件位号（Value值）

1. 工具-标注-原理图标注

![image-20210120204241268](markdownImg/Altium Designer/image-20210120204241268.png)

![image-20210120204256048](markdownImg/Altium Designer/image-20210120204256048.png)

# 封装（统一管理）

1. 工具-封装管理器

![image-20210120205050930](markdownImg/Altium Designer/image-20210120205050930.png)

# 规则

## 间距规则

1. 丝印与丝印间距>=2miil
   1. 字宽/字高（4/25mil, 5/30mil, 6/45mil)
   2. 推荐字母在左、下
2. 1

# 错误

1. 右击左侧栏的工程“*.PrjPcb”-工程选项（工具栏-工程-工程选项）

![image-20210120210145559](markdownImg/Altium Designer/image-20210120210145559.png)

2. 编译原理图

![image-20210120210254283](markdownImg/Altium Designer/image-20210120210254283.png)

3. 查看错误

![image-20210120210409577](markdownImg/Altium Designer/image-20210120210409577.png)

# 错误类型

1. 

![image-20210120210823466](markdownImg/Altium Designer/image-20210120210823466.png)

![image-20210120211336402](markdownImg/Altium Designer/image-20210120211336402.png)

2. 

![image-20210120210904234](markdownImg/Altium Designer/image-20210120210904234.png)

![image-20210120211315564](markdownImg/Altium Designer/image-20210120211315564.png)

3. 

![image-20210120211253722](markdownImg/Altium Designer/image-20210120211253722.png)

![image-20210120211918668](markdownImg/Altium Designer/image-20210120211918668.png)

![image-20210120211639154](markdownImg/Altium Designer/image-20210120211639154.png)

![image-20210120211710387](markdownImg/Altium Designer/image-20210120211710387.png)

# DRC检查

1. 工具-设计规则检查-运行DRC

# 导入logo

1. 脚本-PCB联盟网-搜索“脚本”-点击“Altium PCB Logo 导入脚本”
2. AD-文件-运行脚本-选择脚本解压目录-点击“RunConverterScript”
3. 将logo用画图打开，保存为“单色位图”
4. 点击脚本上的“load”，找到刚刚保存的单色位图，选择
5. 点击脚本上“Board Layer”,选择层，一般选择“Top Overlay”
6. 脚本上“Scaling Factor”为缩小比例
7. 点击“Convert”
8. 框选中logo,右击“联合”，从选中的器件生成联合
9. 框选中logo,右击“联合”，调整联合大小
10. Ctrl+C，Ctrl+V复制到板子中

# 拼板

1. 工具栏-放置-拼版阵列
2. tab-选择pcb，填入行数、列数
3. 填写板子距离

# 添加过孔

1. 工具-缝合孔/屏蔽-给网络添加缝合孔

P37

# Gerber文件输出

1. 文件-制造输出-Gerber Files

# 立创EDA

| 功能               | 操作                                                      |
| ------------------ | --------------------------------------------------------- |
| 自动选择对应元器件 | 工具-布局传递                                             |
| 修改所有标号       | 选中一个标号-右键-查找相似对象-查找-取消-在右侧修改高即可 |
|                    |                                                           |

# 稚晖君的软件

```
【手动挡钢铁侠之软件篇】
创意收集整理：
1、XMind ZEN(思维导图，zen版本更为简洁)
2、Typora(写markdown的编辑器)
3、有道云笔记(推荐)、印象笔记、为知笔记、OneNote

关于markdown：
github：readme.md(md=markdown)
建议从事技术的同行都掌握的一种文本语言
可以在多平台自由遨游，到处分享而无须担心格式

【电路】
1、AltiumDesigner(AD)：用于绘制电路板
2、eagle(开源硬件界电路设计，偏简单)：转化文件格式
3、fritzing(面包板电路示意图绘制等，文章配图)   
4、allegro、pads(大公司会用的软件(显卡、主板))

个人补充：绘制简单电路示意图图也可以可以选择网页版TinkerCAD，画电路板这几年有风向kiCAD，也可以试试。

【结构设计】
1、Rhinocores(俗称 犀牛)
2、Fusion360(良心软件，联系学习)
3、Cinema4D
4、solidworks(机械相关专业必备)
5、UG
6、proE
渲染：KeyShot
矢量图编辑：inkScape
雕刻机刀路artCAM
3D打印机软件(具体与自己的机器有关)推荐一个Cura

【软件开发】
1、宇宙第一IDE ：VisualStudio(C++、openCV)
2、ardroidStudio：开发安卓APP
3、jetbrain全家桶：JAVA开发
4、PyCharm：人生苦短  我用python
5、rider：c#开发
6、clion：C、C++

【硬件开发】
1、keil、cubeMX(51单片机、STM32等)
2、arduino IDE(开源硬件扛把子) 
3、KendrytelIDE(开发K210)

软件交互，一个画画的编程语言：processing
数学仿真：Matlab

【小工具类】
linux服务器：XShell、XFtp
串口、网络调试助手
cmake：跨平台安装编译工具
GitGUI：代码版本控制
coolformat：代码批量格式化工具
ida：反编译
WireShark：网络协议分析
SerialChart：串口绘图
Netron：图形化查看神经网络
beyonCompare：代码修改对比
```

