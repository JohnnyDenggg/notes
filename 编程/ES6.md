# 教程

ES6: https://www.bilibili.com/video/BV1Kt411w7MP  P35

ES6+: https://www.bilibili.com/video/BV1uK411H7on    P53未

# 注意点

1. 定时器的this永远指向window
2. 双击禁止选中文字

```
window.getSelection?window.getSelection().removeAllRanges():document.selection.empty();
```

```
#判断前者是否属于后者
console.log(f instanceof Object);
```



# ES6

## 创建类

![image-20201022130913939](markdownImg/ES6/image-20201022130913939.png)

## 类添加方法

![image-20201022131044615](markdownImg/ES6/image-20201022131044615.png)

## 继承

![image-20201022131638616](markdownImg/ES6/image-20201022131638616.png)

### super

![image-20201022132538168](markdownImg/ES6/image-20201022132538168.png)

![image-20201022134050313](markdownImg/ES6/image-20201022134050313.png)

## 类get、set

![image-20201028105754690](markdownImg/ES6/image-20201028105754690.png)

## 类的注意点

![image-20201022140018564](markdownImg/ES6/image-20201022140018564.png)

###### 案例：tab栏切换

## 构造函数

![image-20201027131235617](markdownImg/ES6/image-20201027131235617.png)

![image-20201027131301126](markdownImg/ES6/image-20201027131301126.png)

### 静态成员

![image-20201028111005247](markdownImg/ES6/image-20201028111005247.png)

### prototype

![image-20201027132124327](markdownImg/ES6/image-20201027132124327.png)

![image-20201027132231594](markdownImg/ES6/image-20201027132231594.png)

## 对象原型__proto__

![image-20201027134302594](markdownImg/ES6/image-20201027134302594.png)

### constructor

指向原构造函数

### 构造函数、实例、原型对象关系

![image-20201027135249977](markdownImg/ES6/image-20201027135249977.png)

### 原型链

![image-20201027135512922](markdownImg/ES6/image-20201027135512922.png)

### 构造函数this指向

1. 指向对象实例

2. 构造函数里的原型对象也指向实例对象

## call()

1. 括号里面填谁，this就指向谁

![image-20201027141108068](markdownImg/ES6/image-20201027141108068.png)

### 继承父构造函数的属性

![image-20201028130920105](markdownImg/ES6/image-20201028130920105.png)

## 类的本质

1. 函数，是构造函数更简单的写法
2. 有prototype,constructor
3. 也可以通过原型对象添加方法 Star.prototype.sing= function(){console.log('冰雨');}

## 数组方法

##### forEach()

![image-20201027092638075](markdownImg/ES6/image-20201027092638075.png)

![image-20201027092952284](markdownImg/ES6/image-20201027092952284.png)

##### filter()

![image-20201027093407518](markdownImg/ES6/image-20201027093407518.png)

![image-20201027093555412](markdownImg/ES6/image-20201027093555412.png)

### some()

![image-20201028134805955](markdownImg/ES6/image-20201028134805955.png)

## trim()

![image-20201028152053438](markdownImg/ES6/image-20201028152053438.png)

![image-20201028152147421](markdownImg/ES6/image-20201028152147421.png)

## Object.defineProperty方法

![image-20201028155908715](markdownImg/ES6/image-20201028155908715.png)

![image-20201028160002510](markdownImg/ES6/image-20201028160002510.png)



![image-20201028160335019](markdownImg/ES6/image-20201028160335019.png)

![image-20201028161724390](markdownImg/ES6/image-20201028161724390.png)

## 函数的定义和调用

![image-20201028162735372](markdownImg/ES6/image-20201028162735372.png)

![image-20201028162406198](markdownImg/ES6/image-20201028162406198.png)

## this指向

![image-20201028163255183](markdownImg/ES6/image-20201028163255183.png)

## apply()

![image-20201028164223042](markdownImg/ES6/image-20201028164223042.png)

![image-20201028164721245](markdownImg/ES6/image-20201028164721245.png)

## bind()

![image-20201027094146709](markdownImg/ES6/image-20201027094146709.png)

## 严格模式

![image-20201028210439268](D:\OneDrive\笔记\编程\markdownImg/ES6\image-20201028210439268.png)

![image-20201028210707251](D:\OneDrive\笔记\编程\markdownImg/ES6\image-20201028210707251.png)

###  为整个脚本开启严格模式

![image-20201028204952833](D:\OneDrive\笔记\编程\markdownImg/ES6\image-20201028204952833.png)

### 为函数开启严格模式

![image-20201028205024604](D:\OneDrive\笔记\编程\markdownImg/ES6\image-20201028205024604.png)

## 高阶函数

![image-20201028211059964](D:\OneDrive\笔记\编程\markdownImg/ES6\image-20201028211059964.png)

## 闭包

![image-20201028212918924](D:\OneDrive\笔记\编程\markdownImg/ES6\image-20201028212918924.png)

![image-20201028213531757](D:\OneDrive\笔记\编程\markdownImg/ES6\image-20201028213531757.png)

###### 案例：计算打车价格

![image-20201028214314520](D:\OneDrive\笔记\编程\markdownImg/ES6\image-20201028214314520.png)

## 递归函数（自己调用自己）

![image-20201028215632761](D:\OneDrive\笔记\编程\markdownImg/ES6\image-20201028215632761.png)

![image-20201028215658333](D:\OneDrive\笔记\编程\markdownImg/ES6\image-20201028215658333.png)

![image-20201028220305644](D:\OneDrive\笔记\编程\markdownImg/ES6\image-20201028220305644.png)

###### 案例：

![image-20201028221324295](D:\OneDrive\笔记\编程\markdownImg/ES6\image-20201028221324295.png)

![image-20201028221244592](D:\OneDrive\笔记\编程\markdownImg/ES6\image-20201028221244592.png)

## 浅拷贝

其中拷贝的方法只是拷贝方法地址，如果原对象

```
Object.assign(o,obj)    #将obj拷贝给o
```

## 深拷贝

方法也拷贝一份，产生新的内存空间地址

封装函数

![image-20201028223549564](D:\OneDrive\笔记\编程\markdownImg/ES6\image-20201028223549564.png)

![image-20201028223630974](D:\OneDrive\笔记\编程\markdownImg/ES6\image-20201028223630974.png)



## 正则表达式

### 语法

![image-20201027101548863](markdownImg/ES6/image-20201027101548863.png)

### 测试

![image-20201027101722377](markdownImg/ES6/image-20201027101722377.png)

![image-20201027101747421](markdownImg/ES6/image-20201027101747421.png)

![image-20201027102213244](markdownImg/ES6/image-20201027102213244.png)

### 字符

#### 边界符

![image-20201027102027206](markdownImg/ES6/image-20201027102027206.png)

![image-20201027102319946](markdownImg/ES6/image-20201027102319946.png)

### []

![image-20201027102643014](markdownImg/ES6/image-20201027102643014.png)

![image-20201027102819441](markdownImg/ES6/image-20201027102819441.png)

### -

![image-20201027103205985](markdownImg/ES6/image-20201027103205985.png)

### 取反

![image-20201027104120402](markdownImg/ES6/image-20201027104120402.png)

### 括号总结

![image-20201028225136906](D:\OneDrive\笔记\编程\markdownImg/ES6\image-20201028225136906.png)

### 预定义类

![image-20201028225317455](D:\OneDrive\笔记\编程\markdownImg/ES6\image-20201028225317455.png)

![image-20201028230349991](D:\OneDrive\笔记\编程\markdownImg/ES6\image-20201028230349991.png)

### 常用正则表达式

![image-20201027103814003](markdownImg/ES6/image-20201027103814003.png)

###### 案例：表单验证

### 正则替换

![image-20201027104429554](markdownImg/ES6/image-20201027104429554.png)

### 全局匹配g，忽略大小写i

![image-20201027105445581](markdownImg/ES6/image-20201027105445581.png)



###### 案例：敏感词替换

![image-20201027104613851](markdownImg/ES6/image-20201027104613851.png)

![image-20201027105546739](markdownImg/ES6/image-20201027105546739.png)

# ES6+

## let声明变量

不可重复声明，var可以重复声明

块级作用域

不存在变量提升

不影响作用域链

## const声明常量

一定要赋初始值

一般常量使用大写

常量的值不能修改

块儿级作用域

对于数组和对象的元素修改，不算对常量的修改，不会报错

## 解构赋值

![image-20201027123407035](markdownImg/ES6/image-20201027123407035.png)

![image-20201027123739043](markdownImg/ES6/image-20201027123739043.png)

![image-20201027123831496](markdownImg/ES6/image-20201027123831496.png)

## 模板字符串

符号包起来    ``

内容中可以出现换行符

变量拼接

![image-20201027125203293](markdownImg/ES6/image-20201027125203293.png)

## 对象简化写法

![image-20201027125434194](markdownImg/ES6/image-20201027125434194.png)

## 箭头函数

1. this是静态的，this始终指向函数声明时所在作用域下的this值

2. 不能作为构造实例化对象

3. 不能使用aruments变量

4. 箭头函数简写
   1. 省略小括号，当形参有且只有一个
   2. 省略花括号，当代码体只有一条语句，此时return必须省略
5. 适合与this无关的回调，定时器，数组方法回调
6. 不适合于this有关的回调，事件回调，对象的方法

![image-20201027125648953](markdownImg/ES6/image-20201027125648953.png)

## 函数参数的默认值

1. 具有默认值的参数，一般位置要靠后

![image-20201027143506078](markdownImg/ES6/image-20201027143506078.png)

![image-20201027144130199](markdownImg/ES6/image-20201027144130199.png)

## 剩余参数

1. ​    ...args（相当于ES5中arguments）
2. 必须要放到参数最后

![image-20201027145614940](markdownImg/ES6/image-20201027145614940.png)

![image-20201027145652965](markdownImg/ES6/image-20201027145652965.png)

## spread扩展运算符...

![image-20201027150157282](markdownImg/ES6/image-20201027150157282.png)

##### 扩展运算符-合并

![image-20201027150411566](markdownImg/ES6/image-20201027150411566.png)

![image-20201027150456736](markdownImg/ES6/image-20201027150456736.png)

![image-20201029111222110](markdownImg/ES6/image-20201029111222110.png)

##### 扩展运算符-克隆

![image-20201027150649650](markdownImg/ES6/image-20201027150649650.png)

##### 扩展运算符-将伪数组转为真正的数组

![image-20201027150913610](markdownImg/ES6/image-20201027150913610.png)

## Array扩展方法

### Array.from()

![image-20201029111902844](markdownImg/ES6/image-20201029111902844.png)

![image-20201029112018626](markdownImg/ES6/image-20201029112018626.png)

### array.find()

![image-20201029112151140](markdownImg/ES6/image-20201029112151140.png)

### array.findindex()

![image-20201029112627137](markdownImg/ES6/image-20201029112627137.png)

### array.includes()

![image-20201029112753526](markdownImg/ES6/image-20201029112753526.png)

## String的扩展方法

### 模板字符串``

![image-20201029112949370](markdownImg/ES6/image-20201029112949370.png)

![image-20201029122933260](markdownImg/ES6/image-20201029122933260.png)

![image-20201029123037007](markdownImg/ES6/image-20201029123037007.png)

![image-20201029123140793](markdownImg/ES6/image-20201029123140793.png)

### startsWith()和endsWith()

![image-20201029123347809](markdownImg/ES6/image-20201029123347809.png)

### repeat()

![image-20201029123632366](markdownImg/ES6/image-20201029123632366.png)

## Symbol

![image-20201027151545182](markdownImg/ES6/image-20201027151545182.png)

 ![image-20201027151415954](markdownImg/ES6/image-20201027151415954.png)

##### 对象添加Symbol类型的属性

![image-20201027151914786](markdownImg/ES6/image-20201027151914786.png)

![image-20201027152044452](markdownImg/ES6/image-20201027152044452.png)

##### Symbol内置值

![image-20201027152155374](markdownImg/ES6/image-20201027152155374.png)

![image-20201027152233660](markdownImg/ES6/image-20201027152233660.png)

## 迭代器

完全按自己意愿实现Symbol迭代

## 生成器

1. 是一个特殊的函数
2. 异步编程 纯回调函数

![image-20201027161234222](markdownImg/ES6/image-20201027161234222.png)

## 生成器函数实例

1. 解决回调地狱

2. 用户数据=>订单数据=>商品数据，有调用顺序

![image-20201027164636230](markdownImg/ES6/image-20201027164636230.png)

![image-20201027164645153](markdownImg/ES6/image-20201027164645153.png)

## Promise

![image-20201028085357883](markdownImg/ES6/image-20201028085357883.png)

### Promise用nodejs读取文件

![image-20201028090638430](markdownImg/ES6/image-20201028090638430.png)

### Promise封装AJAX请求

![image-20201028091244254](markdownImg/ES6/image-20201028091244254.png)

## set()

![image-20201029123818635](markdownImg/ES6/image-20201029123818635.png)

![image-20201029124038188](markdownImg/ES6/image-20201029124038188.png)	

![image-20201028100119505](markdownImg/ES6/image-20201028100119505.png)

### 去重、交集、并集、差集

![image-20201028103048902](markdownImg/ES6/image-20201028103048902.png)

## map()

![image-20201028103359447](markdownImg/ES6/image-20201028103359447.png)

## 数值扩展

![image-20201029125610450](markdownImg/ES6/image-20201029125610450.png)

![image-20201029125819849](markdownImg/ES6/image-20201029125819849.png)

## 对象方法的扩展

![image-20201029130147214](markdownImg/ES6/image-20201029130147214.png)

![image-20201029130354211](markdownImg/ES6/image-20201029130354211.png)

## 模块化

### 暴露模块

![image-20201029130518038](markdownImg/ES6/image-20201029130518038.png)

![image-20201029130810862](markdownImg/ES6/image-20201029130810862.png)

![image-20201029131207219](markdownImg/ES6/image-20201029131207219.png)

![image-20201029131318688](markdownImg/ES6/image-20201029131318688.png)

![image-20201029131434613](markdownImg/ES6/image-20201029131434613.png)

### 引入模块

![image-20201029132044465](markdownImg/ES6/image-20201029132044465.png)s

## async函数

![image-20201029135626274](markdownImg/ES6/image-20201029135626274.png)

![image-20201029135956893](markdownImg/ES6/image-20201029135956893.png)

## await表达式

![image-20201029140119835](markdownImg/ES6/image-20201029140119835.png)

![image-20201029141325208](markdownImg/ES6/image-20201029141325208.png)