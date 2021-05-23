# 教程

https://www.bilibili.com/video/BV1Kt4y1y7LP

P2未

教程3未

# 软件

1. 设置中文（打开Processing>文件>偏好设定>编辑器和控制字体-宋体）

# 注意点

```
//拖动颜色、位置等参数调整
速写本-调试
```



```
void setup(){}
void draw(){}
```



```
//满屏画布
fullScreen();
//画布大小
size(400,400);
width
height
//背景
background(0,0,200,5);
background(#FFFFFF);
//填充颜色透明度
fill(255,0,0，100);
noFill();
//线 (10,20起点 30，40终点)
line(10,20,30,40)
//圆，1,2中心点，3左右半径4上下半径
ellipse(100,100,100,100); 
//长方形
rect(100,100,100,100); 
//边框粗细，往内外各延伸一半
strokeWeight(20);
//边框颜色
stroke(0,0,0,100)
//去掉边框
noStroke();
//随机数(从100到200)
random(100,200)
//循环运行速度，每秒运行的次数
frameRate(20);
//类型
int
float
boolean
//鼠标坐标
rect(mouseX,mouseY,100,100)
//按住鼠标
mousePressed
//map
map(被映射的值，a,b,A,B)  //a,b原来区间，A,B被映射到的区间
//noise 连续的随机值
noise(x)   // 为介于0~1间的值（随着x的增长或减小时）
noise(x,y);
noise(x,y,z);
//导入图片 （将图片放入与.pde文件同级的data文件夹中）
PImage _kenan; //变量名智能以_或字母开头
void setup(){
	size(600,600);
	background(255);
	_kenan = loadImage("test1.png");
	_kenan.resize(100,100); //宽度，高度（必须是整数）
	background(_kenan);  //图片做背景（图片大小必须和窗口大小一致，图片.resize(width,height)）
}
void draw(){
  image(_kenan,200,200); //200,200为图片左上角点
}
//向量
PVector location;
```

```
// 环境光
  lights();
  
//将当前变换矩阵推送到矩阵堆栈
  pushMatrix();
  translate(width/2, height/2, 200 * sin(timer));

// 鼠标左键拖动旋转
  if (mouseButton == LEFT) {
    rotateX(mouseY * 0.05);
    rotateY(mouseX * 0.05);
    // 通过调整球体网格的顶点数量来控制用于渲染球体的细节。默认分辨率为30
    sphereDetail(mouseX / 4);
  }
  
// y 轴旋转
  rotateY(timer);
  
// x 轴旋转30
  rotateX(PI/6);
  
//球密度
  sphere(300);
  
// 球体中部文字
  textMode(CENTER);
  fill(255, 0, 0);
  text("Hello world,My name is liShengFu!", -300, 0, 0);
  popMatrix();
  
  timer = (timer+0.01)%TWO_PI;
  text(year() + "年"  + month()+ "月" + day()+ "日" +hour()+ "时" + 
    minute()+ "分" +second()+ "秒", 50, height-50, 0);

// 鼠标右键保存图片
  if (mouseButton == RIGHT) {          
    String picName = "PDE_" + year()+ "_" + month()+"_" + day()+"_" +   
      hour()+"_" + minute()+"_" + second();  
    save(picName + ".png");  
    println(" ----> Picture saved.");
  }
```



```
//数组 （索引从0开始）
int colors[] = {#aaaaaa,#bbbbbbb,#cccccc,#dddddd};

int mingzu[] = new int[56];
mingzu[0] = hanzu;

//数组大小
colors.length

//二维数组
int colors[2][4] = {
	{#aaaaaa,#bbbbbbb,#cccccc,#dddddd},
	{#aaaaaa,#bbbbbbb,#cccccc,#dddddd}						
};
```

```
//类class
void setup(){
	NPY1 = new NPY;
};
class NPY{
	int nianling;
	float shengao,tizhong;
	NPY(int nl, float sg, float tizhogn){
		nianling = nl;
		shengao = sg;
		this.tizhong = tizhong;  //this代表class
	}
	void update(){};  //用来更新变量
	void display(){};	//用来画画

}

NPY[] NPYS = new NPY[5];    //类名[] 对象数组名 = new 类名[数组大小]
```

```
//dist 距离函数
dist(x1,y1,x2,y2);  //计算从x1,y1到x2，y2的距离
```



```
//强制转换
colors[（int）random(0,4)];  //转换为整数
```

```
//console窗口显示
print(c);
```

```
//查看目前的坐标
yuan1.x
yuan1.y
```



```
int c =5;
ellipse(c,c,c,c)
```

```
//for循环
for(int i=0;i<a.length;i++){};
```

```
if () {

} else {

}
//语句只有一句时，可以省略{}
```

```
while(){

}
```

```
x += 1；
x -= 1；
x *= 1；
x /= 1；
```

# 安装库

1. 安装库文件夹
   1. 打开Processing>文件>偏好设定>速写本位置
   2. 将库文件夹解压到“速写本位置”下的libraries文件夹下
   3. 重启软件
2. 安装自带库
   1. 打开Processing>速写本>引用库文件>添加库文件>libraries
   2. 搜索库文件名>install



# 案例

```
//流星甩尾

void setup(){
  size(600,600);
}
void draw(){
  //窗口
  fill(255,0,0,20);
  rect(0,0,width,height);
  //圆
  noStroke();
  fill(0);
  ellipse(mouseX,mouseY,30,30);
}
```



