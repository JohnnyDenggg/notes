# 教程

https://www.bilibili.com/video/BV154411n79k

+ 回顾
  + P88多线程，信号连接

https://www.bilibili.com/video/BV1e64y1T7PD

# ==PYQT5案例！！！==

https://gitee.com/PyQt5/PyQt?_from=gitee_search

# ==布局！！！==

1. 主窗口继承QMainWindow

2. 主窗口设置主部件QWidget

3. 主部件设置布局QGridLayout

4. 设置左侧部件QWidget和名字setObjectName

5. 左侧部件设置布局QGridLayout

6. 设置右侧部件QWidget和名字setObjectName

7. 右侧部件设置布局QGridLayout

8. 主布局中添加左右部件addWidget(self.left_widget,0,0,12,2)# 左侧部件在第0行第0列，占12行2列

   addWidget(self.right_widget,0,2,12,10) # 右侧部件在第0行第3列，占12行10列

> 如果有放大窗口的需求

主窗体可以加一个水平布局，左侧QWidget设置一个固定宽度setFixedWidth

# 注意点

## 文字带参数

+ 第一种

```
print('delrow =%s' % str(delrow))
```

+ 第二种

```
sql = "UPDATE Book SET NumStorage=NumStorage+%d,NumCanBorrow=NumCanBorrow+%d WHERE BookId='%s'" % (addBookNum, addBookNum, bookId)

sql = "INSERT INTO book VALUES ('%s','%s','%s','%s','%s','%s',%d,%d,0)" % (bookName, bookId, authName, bookCategory, publisher, publishTime, addBookNum, addBookNum)
```



# 布局

## 水平、垂直布局比例

```
self.verticalLayout.setStretch(0, 1)	# 第一个占比1
self.verticalLayout.setStretch(1, 1)	# 第二个占比1
self.verticalLayout.setStretch(2, 3)	# 第三个占比3
```

+ 当布局添加了QFrame时

```
vlayout_left.setStretchFactor(frame_logo,1)
vlayout_left.setStretchFactor(frame_button,1)
vlayout_left.setStretchFactor(self.tree,4)
```

## 固定大小

+ 比如：在水平布局左边添加QFrame，设置固定宽度setStretch为0。窗口变形大小不变

```
frame_left = QFrame()
# frame_left.setFrameShape(QFrame.StyledPanel)  #加这个有边框
frame_left.setMaximumWidth(140)

hlayout_window = QHBoxLayout()
hlayout_window.addWidget(frame_left)
hlayout_window.addLayout(vlayout_right)
hlayout_window.setStretch(0,0)
hlayout_window.setStretch(1,3)
```



# 功能

## 最小化、最大化、关闭、全屏

```
Qt.WindowMinimizeButtonHint
Qt.WindowMaximizeButtonHint
Qt.WindowCloseButtonHint
```

#### 全屏

```
class MyWindow(QWidget):
    def __init__(self, parent=None):
        super(MyWindow, self).__init__(parent)
        self.resize(600, 600)

        self.button1 = QPushButton('我是按钮', self)
        self.button1.clicked.connect(self.test)


    def test(self):
        desktop = QApplication.desktop()
        rect = desktop.availableGeometry()
        self.setGeometry(rect)
```

#### 关闭

```
self.button1.clicked.connect(self.close)
```

#### 最大化

```
self.button1.clicked.connect(self.maxOrNormal)

def maxOrNormal(self):
	if self.isMaximized():
		self.showNormal()
	else:
		self.showMaximized()
```

#### 最小化

```
self.button1.clicked.connect(self.showMinimized)
```

## 窗口在最上层

```
self.setWindowFlags(Qt.WindowStaysOnTopHint)
```

## 窗口最大组件

```
self.setCentralWidget(self.tree)
```

## 分屏、控件边界

#### 主窗口添加分屏Layout

```
# 总窗口
hlayout_window = QHBoxLayout()

hlayout_window.addLayout(vlayout_left)
hlayout_window.addLayout(vlayout_right)
hlayout_window.setStretch(0,0)   # 表示第一个布局，在窗口大小变动时不变大小
hlayout_window.setStretch(1,4)   # 表示第二个布局，分4份

self.setLayout(hlayout_window)
```

#### 主窗口添加分屏QSplitter

```
# 水平线分割
self.mainSplitter.setOrientation(Qt.Horizontal)

self.mainSplitter.addWidget(leftSplitter)
self.mainSplitter.addWidget(rightSplitter)
# 分割比例
self.mainSplitter.setStretchFactor(0, 1)  #第0个控件分1+2里的1份
self.mainSplitter.setStretchFactor(1, 2)

self.mainSplitter.show()
self.setWindowTitle("Splitter")
```



#### 案例QSplitter

```
from PyQt5.QtWidgets import *
from PyQt5.QtCore import *
from PyQt5.QtGui import *
import sys


class MyWindow(QWidget):
    def __init__(self, parent=None):
        super(MyWindow, self).__init__(parent)
        self.resize(600, 600)

        topleft = QFrame()
        topleft.setFrameShape(QFrame.StyledPanel)

        bottom = QFrame()
        bottom.setFrameShape(QFrame.StyledPanel)

        splitter1 = QSplitter(Qt.Horizontal)
        testedit = QTextEdit()
        splitter1.addWidget(topleft)
        splitter1.addWidget(testedit)

        splitter2 = QSplitter(Qt.Vertical)
        splitter2.addWidget(splitter1)
        splitter2.addWidget(bottom)

        hbox = QHBoxLayout()
        hbox.addWidget(splitter2)
        self.setLayout(hbox)

if __name__ == "__main__":
    app = QApplication(sys.argv)
    window = MyWindow()
    window.show()
    sys.exit(app.exec_())
```

## 颜色

```
Qt.white
```

```
tree.setStyleSheet("QTreeWidget{background-color:#c0c0c0}")
```

```
tree.setStyleSheet("QTreeWidget{background-color:rgb(192,192,192)}")
```



### 设置组件大小

```
self.button2.setGeometry(20,20,260,30) # 左距，上距，宽，高
```

## 按钮操作

```
self.themeButton.clicked.connect(self.show_theme)
```

## 隐藏tab widget的头

```
self.tabWidget.tabBar().setVisible(False)
```

## 按钮绑定tab widget的分页

```
def handle_buttons(self):
	self.bookButton.clicked.connect(self.open_book_tab)
	self.settingButton.clicked.connect(self.open_setting_tab)
	
def open_book_tab(self):
	self.tabWidget.setCurrentIndex(0)
	
def open_setting_tab(self):
    self.tabWidget.setCurrentIndex(1)
```

## 状态栏

```
class MyWindow(QMainWindow):
    def __init__(self):
        super(MyWindow,self).__init__()
        self.initUI()

        bar = self.menuBar()
        file = bar.addMenu('文件')
        file.addAction('新建')

        save = QAction('保存',self)  # self表示放在窗口上
        save.setShortcut('Ctrl + S')

        file.addAction(save)
        file.triggered.connect(self.actions)

    def actions(self,a):
        self.statusBar().showMessage(a.text()+'被点击了！', 5000)  # 显示5秒
```

## 提示信息（鼠标放上去）

```
        QToolTip.setFont(QFont('微软雅黑',12))
        self.button1 = QPushButton('我是按钮')
        self.button1.setToolTip("我真的是按钮")
```

## 弹出消息对话框

#### 1. 关于对话框

```
    def showDialog(self):
        QMessageBox.about(self,'关于','这是一个对话框的信息')
```

#### 2. 消息对话框(确认、取消)

```
        reply = QMessageBox.information(self,'消息','这是消息对话框',QMessageBox.Yes|QMessageBox.No,QMessageBox.Yes)
        print(reply)
        print(reply==QMessageBox.Yes)  # 返回True/False
```

确认对话框(只有确认按钮)

```
QMessageBox.information(self,'消息','这是确认对话框',QMessageBox.Ok)
```

#### 3. 警告对话框(确认、取消)

```
        reply = QMessageBox.warning(self,'警告','这是警告对话框',QMessageBox.Yes|QMessageBox.No,QMessageBox.Yes)
        print(reply)
        print(reply==QMessageBox.Yes)
```

#### 4. 错误对话框(确认、取消)

```
        reply = QMessageBox.critical(self,'错误','这是错误对话框',QMessageBox.Yes|QMessageBox.No,QMessageBox.Yes)
        print(reply)
        print(reply==QMessageBox.Yes)
```

#### 5. 提问对话框(确认、取消)

```
        reply = QMessageBox.question(self,'提问','这是提问对话框',QMessageBox.Yes|QMessageBox.No,QMessageBox.Yes)
        print(reply)
        print(reply==QMessageBox.Yes)
```

## 输入对话框

#### 1. 选择列表对话框

```
        items =('c','c++','python','java')
        item, ok = QInputDialog.getItem(self,'对话框标题','列表标题',items)
        print(item,ok)
```

#### 2. 文本输入对话框

```
        item, ok = QInputDialog.getText(self,'对话框标题','文本框标题')
        print(item,ok)
```

#### 3. 数字输入对话框

```
        item, ok = QInputDialog.getInt(self,'对话框标题','数字输入框标题')
        print(item,ok)
```

## 打开文本文件

```
    
    def showDialog(self):

        items =('c','c++','python','java')
        dialog = QFileDialog()
        dialog.setFileMode(QFileDialog.AnyFile)
        dialog.setFilter(QDir.Files)
        # print(item,ok)
        if dialog.exec():
            filenames = dialog.selectedFiles()
            f = open(filenames[0],encoding='utf-8',mode='r')
            with f:
                data = f.read()
                self.contents.setText(data)   #contents是QTextEdit()
```

## 菜单栏

```
class MyWindow(QMainWindow):
    def __init__(self):
        super(MyWindow,self).__init__()
        self.test()

        bar = self.menuBar()
        file = bar.addMenu('文件')
        file.addAction('新建')

        save = QAction('保存',self)  # self表示放在窗口上
        save.setShortcut('Ctrl + S')
        save.triggered.connect(self.actions)
        file.addAction(save)


    def actions(self,a):
        print(self.sender().text(),a)
```

## 工具栏

```
    def initUI(self):
        self.setWindowTitle('测试测试')
        self.resize(400,400)
        # 创建工具栏
        tb = self.addToolBar('File')
        # 添加按钮
        a1 = QAction(QIcon('D.ico'),'new',self) # new是鼠标提示
        tb.addAction(a1)
		
		#默认只显示图标
		
        
```

```
# 显示图标和文字
tb.setToolButtonStyle(Qt.ToolButtonTextBesideIcon)

# 图标下方显示文字
tb.setToolButtonStyle(Qt.ToolButtonTextUnderIcon)

# 只显示文字
tb.setToolButtonStyle(Qt.ToolButtonTextOnly)
```

## 打印机

打印界面

```
from PyQt5.QtWidgets import *
from PyQt5.QtCore import *
from PyQt5.QtGui import *
from PyQt5.QtMultimedia import *
from PyQt5.uic import loadUiType
from PyQt5.QtPrintSupport import *
import sys

class MyWindow(QMainWindow):
    def __init__(self):
        super(MyWindow,self).__init__()
        self.printer = QPrinter()
        self.initUI()

    def initUI(self):
        self.setGeometry(300,300,500,400)
        self.setWindowTitle('测试测试')

        self.editor = QTextEdit('默认文本',self)
        self.editor.setGeometry(20,20,300,270)

        self.openButton = QPushButton('打开文件',self)
        self.openButton.move(350,20)
        self.openButton.clicked.connect(self.openFile)

        self.settingButton = QPushButton('打印设置',self)
        self.settingButton.move(350, 50)
        self.settingButton.clicked.connect(self.showSettingDialog)

        self.printButton = QPushButton('打印文档',self)
        self.printButton.move(350, 80)
        self.printButton.clicked.connect(self.showPrintDialog)

    def openFile(self):
        fname = QFileDialog.getOpenFileName(self,'打开文本文件','./')
        if fname[0]:
            with open(fname[0],'r',encoding='utf-8',errors='ignore') as f:
                self.editor.setText(f.read())


    def showSettingDialog(self):
        printDialog = QPageSetupDialog(self.printer,self)
        printDialog.exec()

    def showPrintDialog(self):
        printdialog = QPrintDialog(self.printer,self)
        if QDialog.Accepted == printdialog.exec():
            self.editor.print(self.printer)


    def print(self):
        printer = QPrinter()
        painter = QPainter()
        # 将绘制的目标重印像到打印机
        painter.begin(printer)
        screen = self.editor.grab()
        painter.drawPixmap(10,10,screen)
        painter.end()

if __name__ == '__main__':
    app = QApplication(sys.argv)
    main = MyWindow()
    main.show()
    sys.exit(app.exec_())
```

另一个

```
from PyQt5.QtPrintSupport import *

class MyWindow(QMainWindow):
    def __init__(self):
        super(MyWindow,self).__init__()
        self.button2 = QPushButton('我是按钮2',self)
        self.button2.setGeometry(20,20,260,30)

        self.editor = QTextEdit('默认文本',self)
        self.editor.setGeometry(20,60,260,200)
        self.button2.clicked.connect(self.print)


    def print(self):
        printer = QPrinter()
        painter = QPainter()
        # 将绘制的目标重印像到打印机
        painter.begin(printer)
        screen = self.editor.grab()
        painter.drawPixmap(10,10,screen)
        painter.end()
```

## 右击菜单

P77

```
# 右键菜单
        self.todoTableWidget.setContextMenuPolicy(Qt.CustomContextMenu)
        self.todoTableWidget.customContextMenuRequested.connect(self.generateMenu)

# 右键菜单槽
    def generateMenu(self,pos):
        print(pos)
        for i in self.todoTableWidget.selectionModel().selection().indexes():
            rowNum = i.row()
        print(rowNum)
        # 如果行索引小于2，弹出菜单。也就是前两行才弹出菜单

        menu = QMenu()
        item1 = menu.addAction('添加任务')
        item2 = menu.addAction('删除任务')
        screenPos = self.todoTableWidget.mapToGlobal(pos)
        # 被阻塞
        action = menu.exec(screenPos)
        # print('action',action)
        if action ==item1:
            print('添加任务')
        elif action ==item2:
            print('删除任务')
            self.todoTableWidget.removeRow(self.todoTableWidget.currentIndex().row())
            # print('选择了添加行2',self.todoTableWidget.item(rowNum,0).text())
        else:
            return
```



#### 托盘图标的右击菜单

```
    def createMenu(self):
        self.menu = QtWidgets.QMenu()
        self.showAction1 = QtWidgets.QAction("启动", self, triggered=self.show_window)
        self.showAction2 = QtWidgets.QAction("显示通知", self, triggered=self.showMsg)
        self.quitAction = QtWidgets.QAction("退出", self, triggered=self.quit)

        self.menu.addAction(self.showAction1)
        self.menu.addAction(self.showAction2)
        self.menu.addAction(self.quitAction)
        self.setContextMenu(self.menu)

        # 设置图标
        self.setIcon(QtGui.QIcon("D.ico"))
        self.icon = self.MessageIcon()

        # 把鼠标点击图标的信号和槽连接
        self.activated.connect(self.onIconClicked)

    def onIconClicked(self, reason):
        if reason == 2 or reason == 3:
            # self.showMessage("Message", "skr at here", self.icon)
            if self.ui.isMinimized() or not self.ui.isVisible():
                # 若是最小化，则先正常显示窗口，再变为活动窗口（暂时显示在最前面）
                self.ui.showNormal()
                self.ui.activateWindow()
                self.ui.setWindowFlags(QtCore.Qt.Window)
                self.ui.show()
            else:
                # 若不是最小化，则最小化
                self.ui.showMinimized()
                self.ui.setWindowFlags(QtCore.Qt.SplashScreen)
                self.ui.show()
                # self.ui.show()
```



## 树控件(P77)

```
class MyWindow(QMainWindow):
    def __init__(self,parent=None):
        super(MyWindow,self).__init__(parent)
        self.setWindowTitle('测试测试')
        self.resize(400, 400)


        self.tree = QTreeWidget()
        self.tree.setColumnCount(2)
        self.tree.setHeaderLabels(['key','value'])
        tree.setHeaderHidden(True)

        root = QTreeWidgetItem(self.tree)
        root.setText(0,'根节点')
        root.setIcon(0,QIcon('D.ico'))
        root.setText(1,'0')
        self.tree.setColumnWidth(0,120)

        child1 = QTreeWidgetItem(root)
        child1.setText(0,'子节点1')
        child2 = QTreeWidgetItem(root)
        child2.setText(0,'子节点2')

        self.setCentralWidget(self.tree)
```

#### 绑定事件

```
self.tree.clicked.connect(self.onTreeClick)

    def onTreeClick(self,index):
        item = self.tree.currentItem().text(0)
        print(item)
        print(index.row())
```



## 传递信号

```
from PyQt5.QtCore import *
import sys

class MySignal(QObject):
    # 定义一个信号
    sendmsg = pyqtSignal(object)  # sendmsg相当于click信号
    sendmsg1 = pyqtSignal(str,int,int)

    def run(self):
        self.sendmsg.emit('Hello')

    def run1(self):
        self.sendmsg1.emit('Hello',3,5)

class MySlot(QObject):
    def get(self,msg):
        print('信息'+ msg)

    def get1(self,msg,a,b):
        print('信息'+ msg)
        print(a + b)

if __name__ == '__main__':
    send = MySignal()
    slot = MySlot()
    send.sendmsg.connect(slot.get)
    send.run()

    send.sendmsg1.connect(slot.get1)
    send.run1()
```

## 多窗口交互

### 1. 使用信号与槽（推荐）

+ 弹出窗口文件

```
from PyQt5.QtWidgets import *
from PyQt5.QtCore import *
from PyQt5.QtGui import *
import sys


class NewDateDialog(QDialog):
    Signal_OneParameter = pyqtSignal(str)
    # 定义构造方法
    def __init__(self,parent=None):
        super(NewDateDialog,self).__init__(parent)
        self.setWindowTitle('子窗口：发射信号')
        layout = QVBoxLayout(self)

        self.label = QLabel(self)
        self.label.setText('前者发射内置信号\n后者发射自定义信号')

        self.datetime_inner = QDateTimeEdit(self)
        self.datetime_inner.setCalendarPopup(True)
        self.datetime_inner.setDateTime(QDateTime.currentDateTime())

        self.datetime_emit = QDateTimeEdit(self)
        self.datetime_emit.setCalendarPopup(True)
        self.datetime_emit.setDateTime(QDateTime.currentDateTime())

        layout.addWidget(self.label)
        layout.addWidget(self.datetime_inner)
        layout.addWidget(self.datetime_emit)

        buttons = QDialogButtonBox(QDialogButtonBox.Ok | QDialogButtonBox.Cancel,Qt.Horizontal,self)
        buttons.accepted.connect(self.accept)
        buttons.rejected.connect(self.reject)
        layout.addWidget(buttons)

        self.datetime_emit.dateTimeChanged.connect(self.emit_signal)

    def emit_signal(self):
        date_str = self.datetime_emit.dateTime().toString()
        self.Signal_OneParameter.emit(date_str)
```

+ 主窗口文件

```
from PyQt5.QtWidgets import *
from PyQt5.QtCore import *
from PyQt5.QtGui import *
from NewDateDialog import NewDateDialog
import sys


class MainApp(QWidget):
    # 定义构造方法
    def __init__(self,parent=None):
        super(MainApp,self).__init__(parent)
        self.setWindowTitle('多窗口交互，使用信号槽')
        self.resize(400,140)

        self.lineEdit_inner = QLineEdit(self)
        self.lineEdit_inner.setText('接收子窗口_内置_信号的时间')
        self.lineEdit_emit = QLineEdit(self)
        self.lineEdit_emit.setText('接收子窗口_自定义_信号的时间')
        self.open_btn = QPushButton('弹出对话框1')
        self.open_btn.clicked.connect(self.openDialog)

        gridLayout = QGridLayout()
        gridLayout.addWidget(self.lineEdit_inner)
        gridLayout.addWidget(self.lineEdit_emit)
        gridLayout.addWidget(self.open_btn)

        self.setLayout(gridLayout)

    def openDialog(self):
        dialog = NewDateDialog(self)
        # 链接子窗口的内置信号与主窗口的槽函数
        dialog.datetime_inner.dateTimeChanged.connect(self.deal_inner_slot)
        # 链接子窗口的自定义信号与主窗口的槽函数
        dialog.Signal_OneParameter.connect(self.deal_emit_slot)
        dialog.show()

    def deal_inner_slot(self,date):
        self.lineEdit_inner.setText(date.toString())

    def deal_emit_slot(self,dateStr):
        self.lineEdit_emit.setText(dateStr)



if __name__ == '__main__':
    app = QApplication(sys.argv)
    window = MainApp()
    window.show()
    sys.exit(app.exec_())
```

### 2. 不使用信号与槽

+ 弹出窗口文件

```
from PyQt5.QtWidgets import *
from PyQt5.QtCore import *
from PyQt5.QtGui import *
import sys


class DateDialog(QDialog):
    # 定义构造方法
    def __init__(self,parent=None):
        super(DateDialog,self).__init__(parent)
        self.setWindowTitle('DateDialog')
        layout = QVBoxLayout(self)
        self.datetime = QDateTimeEdit(self)
        self.datetime.setCalendarPopup(True)
        self.datetime.setDateTime(QDateTime.currentDateTime())
        # self.button = QPushButton('我是按钮',self)
        layout.addWidget(self.datetime)

        buttons = QDialogButtonBox(QDialogButtonBox.Ok | QDialogButtonBox.Cancel,Qt.Horizontal,self)
        buttons.accepted.connect(self.accept)
        buttons.rejected.connect(self.reject)
        layout.addWidget(buttons)

    def dateTime(self):
        return self.datetime.dateTime()

    @staticmethod
    def getDateTime(parent=None):
        dialog = DateDialog()
        result = dialog.exec()
        date = dialog.dateTime()
        return (date.date(),date.time(),result==QDialog.Accepted)
```

+ 主窗口文件

```
from PyQt5.QtWidgets import *
from PyQt5.QtCore import *
from PyQt5.QtGui import *
from DateDialog import DateDialog
import sys


class MainApp(QWidget):
    # 定义构造方法
    def __init__(self,parent=None):
        super(MainApp,self).__init__(parent)
        self.setWindowTitle('多窗口交互，不使用信号槽')

        self.lineEdit = QLineEdit(self)
        self.button1 = QPushButton('弹出对话框1')
        self.button1.clicked.connect(self.onButton1Click)
        self.button2 = QPushButton('弹出对话框2')
        self.button2.clicked.connect(self.onButton2Click)

        gridLayout = QGridLayout()
        gridLayout.addWidget(self.lineEdit)
        gridLayout.addWidget(self.button1)
        gridLayout.addWidget(self.button2)

        self.setLayout(gridLayout)

    def onButton1Click(self):
        dialog = DateDialog(self)
        result = dialog.exec()
        date = dialog.datetime()
        self.lineEdit.setText(date.date().toString())
        dialog.destroy()

    def onButton2Click(self):
        date,time,result = DateDialog.getDateTime()
        self.lineEdit.setText(date.toString())
        if result == QDialog.Accepted:
            print('点击确定按钮')
        else:
            print('点击取消按钮')



if __name__ == '__main__':
    app = QApplication(sys.argv)
    window = MainApp()
    window.show()
    sys.exit(app.exec_())

```

## 绘图

```
from PyQt5.QtWidgets import *
from PyQt5.QtCore import *
from PyQt5.QtGui import *
from NewDateDialog import NewDateDialog
import sys

class MainApp(QWidget):
    # 定义构造方法
    def __init__(self,parent=None):
        super(MainApp,self).__init__(parent)
        self.pix = QPixmap()
        self.lastPoint = QPoint()
        self.endPoint = QPoint()
        self.initUI()


    def initUI(self):
        self.setWindowTitle('这是一个测试窗口')
        self.resize(600, 600)
        # 画布大小位400*400，背景位白色
        self.pix = QPixmap(600,600)
        self.pix.fill(Qt.white)

    def paintEvent(self,event):
        pp = QPainter(self.pix)
        # 根据鼠标指针前后两个位置绘制直线
        pp.drawLine(self.lastPoint,self.endPoint)
        # 让前一个坐标值等于后一个坐标值
        self.lastPoint = self.endPoint
        painter = QPainter(self)
        painter.drawPixmap(0,0,self.pix)

    def mousePressEvent(self, event):
        if event.button() == Qt.LeftButton:
            self.lastPoint = event.pos()

    def mouseMoveEvent(self, event):
        if event.buttons() and Qt.LeftButton:
            self.endPoint = event.pos()
            self.update()

    def mouseReleaseEvent(self, event):
        # 鼠标左键释放
        if event.button() == Qt.LeftButton:
            self.endPoint = event.pos()
            # 重新绘制
            self.update()
            
if __name__ == '__main__':
    app = QApplication(sys.argv)
    window = MainApp()
    window.show()
    sys.exit(app.exec_())
```

## 透明度

```
self.setWindowOpacity(0.5)  #设置窗口透明度，越小越透明
```

```
self.setAttribute(Qt.WA_TranslucentBackground) # 设置窗口背景透明
```

## 隐藏、显示窗口

```
# 隐藏窗口
MainWindow.setWindowFlags(QtCore.Qt.SplashScreen | QtCore.Qt.FramelessWindowHint)
MainWindow.showMinimized()

# 显示窗口
self.ui.showNormal()
self.ui.activateWindow()
```

## 窗口填充颜色

```
pe = QPalette()
MyWindow.setAutoFillBackground(True)
pe.setColor(QPalette.Window,Qt.lightGray)  #设置背景色
MyWindow.setPalette(pe)
```



## 滑动隐藏窗口

```
import sys,random
from PyQt5.QtGui import QPalette,QColor
from PyQt5.QtWidgets import QWidget,QVBoxLayout,QPushButton,\
    QDesktopWidget,QApplication
from PyQt5.QtCore import Qt,QRect,QEvent,QPoint
from PyQt5.Qt import QCursor,QPropertyAnimation

SCREEN_WEIGHT = 1920
SCREEN_HEIGHT = 1080
WINDOW_WEIGHT = 300
WINDOW_HEIGHT = 600
class Ui_Form(QWidget):
    def __init__(self):
        self.moved = False
        super(Ui_Form,self).__init__()
        self.setupUi()
        self.resize(WINDOW_WEIGHT, WINDOW_HEIGHT)
        self.show()
    def setupUi(self):
        self.setWindowFlags(Qt.FramelessWindowHint
                            | Qt.WindowStaysOnTopHint
                            | Qt.Tool) # 去掉标题栏
        self.widget = QWidget()
        self.Layout = QVBoxLayout(self.widget)
        self.Layout.setContentsMargins(0,0,0,0)
        self.setLayout(self.Layout)
        self.setWindowFlag(Qt.Tool)
        self.main_widget = QWidget()
        self.Layout.addWidget(self.main_widget)
        self.paint = QPushButton(self.main_widget)
        self.paint.setText("改变颜色")
        self.paint.move(QPoint(120,200))
        self.paint.clicked.connect(self.Painting)
        self.exit = QPushButton(self.main_widget)
        self.exit.setText("  退出  ")
        self.exit.move(QPoint(120,400))
        self.exit.clicked.connect(lambda:exit(0))
        self.setStyleSheet('''
                QPushButton {
                color: rgb(137, 221, 255);
                background-color: rgb(37, 121, 255);
                border-style:none;
                border:1px solid #3f3f3f;
                padding:5px;
                min-height:20px;
                border-radius:15px;
            }
            ''')
    def Painting(self):
        color = random.choice(["CCFFFF","CC6699","CC99FF","99CCFF"])
        palette1 = QPalette()
        palette1.setColor(self.backgroundRole(),
                          QColor("#{}".format(color))) # 改变窗体颜色
        self.setPalette(palette1)
    def enterEvent(self, event):
        self.hide_or_show('show', event)
    def leaveEvent(self, event):
        self.hide_or_show('hide', event)
    def mousePressEvent(self, event):
        if event.button() == Qt.LeftButton:
            self.dragPosition = event.globalPos() - self.frameGeometry(
            ).topLeft()
            QApplication.postEvent(self, QEvent(174))
            event.accept()
    def mouseMoveEvent(self, event):
        if event.buttons() == Qt.LeftButton:
            try:
                self.move(event.globalPos() - self.dragPosition)
                event.accept()
            except:pass
    #def mouseReleaseEvent(self, event):
        #self.moved = True
        #self.hide_or_show('show', event)
    def hide_or_show(self, mode, event):
        pos = self.frameGeometry().topLeft()
        if mode == 'show' and self.moved:
            if pos.x() + WINDOW_WEIGHT >= SCREEN_WEIGHT:  # 右侧显示
                self.startAnimation(SCREEN_WEIGHT - WINDOW_WEIGHT + 2, pos.y())
                event.accept()
                self.moved = False
            elif pos.x() <= 0:  # 左侧显示
                self.startAnimation(0,pos.y())
                event.accept()
                self.moved = False
            elif pos.y() <= 0: # 顶层显示
                self.startAnimation(pos.x(),0)
                event.accept()
                self.moved = False
        elif mode == 'hide':
            if pos.x() + WINDOW_WEIGHT >= SCREEN_WEIGHT:  # 右侧隐藏
                self.startAnimation(SCREEN_WEIGHT - 2,pos.y())
                event.accept()
                self.moved = True
            elif pos.x() <= 2:  # 左侧隐藏
                self.startAnimation(2 - WINDOW_WEIGHT,pos.y())
                event.accept()
                self.moved = True
            elif pos.y() <= 2: # 顶层隐藏
                self.startAnimation(pos.x(),2 - WINDOW_HEIGHT)
                event.accept()
                self.moved = True
    def startAnimation(self,width,height):
        animation = QPropertyAnimation(self,b"geometry",self)
        startpos = self.geometry()
        animation.setDuration(200)
        newpos = QRect(width,height,startpos.width(),startpos.height())
        animation.setEndValue(newpos)
        animation.start()
if __name__ == "__main__":
    app = QApplication(sys.argv)
    ui = Ui_Form()
    sys.exit(app.exec_())

```

## 隐藏窗口边框

```
MyWindow.setWindowFlag(QtCore.Qt.FramelessWindowHint) # 隐藏边框
```

## 获取窗口大小(高度、宽度)

```
# 不含窗口边框的高度、宽度
a = self.width()
b = self.height()

# 含窗口边框的高度、宽度
a = self.frameGeometry().width()
b = self.frameGeometry().height()
```

## 坐标

```
# 含窗口边框的窗口坐标
self.x()
self.y()

# 不含窗口边框的窗口坐标
self.geometry().x()
self.geometry().y()
```

## 获取屏幕大小

```
app = QApplication(sys.argv)
desktop1 = app.desktop()
a = desktop1.width()
b = desktop1.height()
print(a, b)
```

## 对齐方式

```
hlayout.addWidget(QPushButton('按钮1'),1,Qt.AlignLeft | Qt.AlignTop)  
hlayout.addWidget(QPushButton('按钮1'),4,Qt.AlignLeft | Qt.AlignTop)  #水平布局中占 1+4 中的4份
```

## 伸缩量

```
hlayout.addStretch(0)  # 0 永远在左侧，或者上侧
hlayout.addStretch(1)  # 填几就在布局中占总量的比例
```

## 布局中控件的间距

```
hlayout.setSpacing(40)  
```

## 绝对布局

```
self.button1.move(30,30)
```

## 网页页面加载

```
pip install PyQtWebEngine -i https://pypi.douban.com/simple/
```

```
from PyQt5.QtWidgets import *
from PyQt5.QtCore import *
from PyQt5.QtWebEngineWidgets import *
import sys


class MyWindow(QMainWindow):
    def __init__(self, parent=None):
        super(MyWindow, self).__init__(parent)
        # self.resize(600, 600)
        self.browser = QWebEngineView()
        self.browser.load(QUrl('https://www.jd.com'))
        self.setCentralWidget(self.browser)



if __name__ == "__main__":
    app = QApplication(sys.argv)
    window = MyWindow()
    window.show()
    sys.exit(app.exec_())
```



## 创建快捷方式

```
```

## 开机自动启动

```
```

## 最小化到托盘

+ 定义一个右击菜单类

```
from PyQt5.QtWidgets import *
from PyQt5.QtCore import *
from PyQt5.QtGui import *
from PyQt5.QtMultimedia import *
from PyQt5.uic import loadUiType
from PyQt5 import QtPrintSupport
import sys
import os


class MyWindow(QMainWindow):
    def __init__(self, parent=None):
        super(MyWindow, self).__init__(parent)
        self.resize(600, 600)

        self.pushbutton_mini = QPushButton('我是按钮', self)
        pushbutton_mini.clicked.connect(self.clickmini)

    def clickmini(self):
        self.setWindowFlags(Qt.SplashScreen | Qt.FramelessWindowHint)
        self.showMinimized()

# 右击菜单（右下角）
class TrayIcon(QSystemTrayIcon):
    def __init__(self, MainWindow, parent=None):
        super(TrayIcon, self).__init__(parent)
        self.ui = MainWindow
        self.createMenu()

    def createMenu(self):
        self.menu = QMenu()
        self.showAction1 = QAction("启动", self, triggered=self.show_window)
        self.showAction2 = QAction("显示通知", self, triggered=self.showMsg)
        self.quitAction = QAction("退出", self, triggered=self.quit)

        self.menu.addAction(self.showAction1)
        self.menu.addAction(self.showAction2)
        self.menu.addAction(self.quitAction)
        self.setContextMenu(self.menu)

        # 设置图标
        self.setIcon(QIcon("icons/D.ico"))
        self.icon = self.MessageIcon()

        # 把鼠标点击图标的信号和槽连接
        self.activated.connect(self.onIconClicked)

    def showMsg(self):
        self.showMessage("Message", "skr at here", self.icon)

    def show_window(self):
        # 若是最小化，则先正常显示窗口，再变为活动窗口（暂时显示在最前面）
        self.ui.showNormal()
        self.ui.activateWindow()

    def quit(self):
        qApp.quit()

    # 鼠标点击icon传递的信号会带有一个整形的值，1是表示单击右键，2是双击，3是单击左键，4是用鼠标中键点击
    def onIconClicked(self, reason):
        if reason == 2 or reason == 3:
            # self.showMessage("Message", "skr at here", self.icon)
            if self.ui.isMinimized() or not self.ui.isVisible():
                # 若是最小化，则先正常显示窗口，再变为活动窗口（暂时显示在最前面）
                self.ui.showNormal()
                self.ui.activateWindow()
                self.ui.setWindowFlags(Qt.Window)
                self.ui.show()
            else:
                # 若不是最小化，则最小化
                self.ui.showMinimized()
                self.ui.setWindowFlags(Qt.SplashScreen)
                self.ui.show()
                # self.ui.show()

if __name__ == "__main__":
    app = QApplication(sys.argv)
    window = MyWindow()
    window.show()

    ti = TrayIcon(window)
    ti.show()

    sys.exit(app.exec_())
```

## 定时

#### 开始、停止时间案例

```
from PyQt5.QtWidgets import *
from PyQt5.QtCore import *
import sys


class MyWindow(QWidget):
    def __init__(self, parent=None):
        super(MyWindow, self).__init__(parent)
        # self.resize(600, 600)

        self.label1 = QLabel('我是一个label')
        self.button1 = QPushButton('我是按钮1')
        self.button2 = QPushButton('我是按钮2')
        self.button1.clicked.connect(self.startTimer)
        self.button2.clicked.connect(self.endTimer)


        layout = QGridLayout()
        layout.addWidget(self.label1,0,0,1,2)
        layout.addWidget(self.button1,1,0)
        layout.addWidget(self.button2,1,1)

        self.setLayout(layout)

        self.timer = QTimer()
        self.timer.timeout.connect(self.showTime)

    def showTime(self):
        time = QDateTime.currentDateTime()
        timeDisplay = time.toString('yyyy-MM-dd hh:mm:ss dddd')
        self.label1.setText(timeDisplay)

    def startTimer(self):
        self.timer.start(1000)
        self.button1.setEnabled(False)
        self.button2.setEnabled(True)

    def endTimer(self):
        self.timer.stop()
        self.button1.setEnabled(True)
        self.button2.setEnabled(False)


if __name__ == "__main__":
    app = QApplication(sys.argv)
    window = MyWindow()
    window.show()
    sys.exit(app.exec_())
```

#### 5秒窗口自动关闭

```
QTimer.singleShot(5000,app.quit)  
```

## 网格布局

```
self.label1 = QLabel('我是一个label')
self.button1 = QPushButton('我是按钮1')
self.button2 = QPushButton('我是按钮2')
self.button1.clicked.connect(self.startTimer)
self.button2.clicked.connect(self.endTimer)


layout = QGridLayout()
layout.addWidget(self.label1,0,0,1,2)
layout.addWidget(self.button1,1,0)
layout.addWidget(self.button2,1,1)

self.setLayout(layout)
```

## tab选项卡

```
class MyWindow(QMainWindow):
    def __init__(self, parent=None):
        super(MyWindow, self).__init__(parent)
        self.resize(600, 600)
        
        self.tab1 = QWidget()
        self.tab2 = QWidget()
        self.tab3 = QWidget()
        self.tab = QTabWidget(self)
        self.tab.resize(200,200)
        # self.tab.tabBar().setVisible(False)  # 隐藏选项卡标题
        self.tab.addTab(self.tab1,'选项卡1')
        self.tab.addTab(self.tab2,'选项卡2')
        self.tab.addTab(self.tab3,'选项卡3')
        self.button1 = QPushButton('我是按钮',self)
        self.button1.move(10,200)
        self.button1.clicked.connect(self.test)


    def test(self):
        self.tab.setCurrentIndex(1)  # 打开第二个选项卡

```

## 显示图片

```
pix = QPixmap('icons/D.ico')
lb_img = QLabel(self)
lb_img.setGeometry(0, 0, 300, 200)
lb_img.setStyleSheet("border: 2px solid red")
lb_img.setPixmap(pix)
```

## 设置字体

```
QToolTip.setFont(QFont('微软雅黑',12))
```

```
QFont('Times',40,QFont.Black)
```

## label字体样式

```
self.label  = QLabel('<font color=red size=140><b>Hello World,窗口在5秒后关闭！</b></font>')
```

## 按住拖动窗口

```
    def mousePressEvent(self, event):
        if event.button()==Qt.LeftButton:
            self.m_flag=True
            self.m_Position=event.globalPos()-self.pos() #获取鼠标相对窗口的位置
            event.accept()
            self.setCursor(QCursor(Qt.OpenHandCursor))  #更改鼠标图标
            
    def mouseMoveEvent(self, QMouseEvent):
        if Qt.LeftButton and self.m_flag:  
            self.move(QMouseEvent.globalPos()-self.m_Position)#更改窗口位置
            QMouseEvent.accept()
            
    def mouseReleaseEvent(self, QMouseEvent):
        self.m_flag=False
        self.setCursor(QCursor(Qt.ArrowCursor))
```

## 图标

#### 窗口图标

```
MainWindow.setWindowIcon(QIcon("./logo.ico"))
```

#### 单元格图标

```
newItem = QTableWidgetItem(QIcon('D.ico'),'背包')   #此单元格前面是ico，后面是文字‘背包’
self.tableWidget.setItem(0,3,newItem)
```



## 表格、单元格设置

#### 单元格高度设置

```

tableWidget.setRowHeight(0,80)  #将第一行高度设置为80
```

#### 单元格宽度设置

```

tableWidget.setColumnWidth(2,80)  #将第三列宽度设置为80
```

#### 单元格放控件

```
combox =QComboBox()
combox.addItem('男')
combox.setStyleSheet('QComboBox{margin:3px}')  #控件距离单元格边框3个像素
tableWidget.setCellWidget(0,1,combox)  # 1行2列放置控件
```

#### 表第一行标题的设置

```
```



#### 表格的行、列设置

```
tableWidget.setRowCount(4)
tableWidget.setColumnCount(3)
```



## 距离

#### 鼠标点击到屏幕的距离

```
screenPos = view.mapToGlobal(pos)  #pos是鼠标点击到控件左上角的距离
print('screenPos')
```

## 显示通知（右下角）

```
    def showMsg(self):
        self.showMessage("Message", "skr at here", self.icon)
```

## 时间、日历

#### 日历

```
        self.cal = QCalendarWidget(self)
        self.cal.setMinimumDate(QDate(1988,1,1))
        self.cal.setMaximumDate(QDate(2080,1,1))
        self.cal.setGridVisible(True)
        self.cal.move(20,20)
        date = self.cal.selectedDate()
        self.cal.clicked.connect(self.showDate)
    def showDate(self):
        self.label.setText((self.cal.selectedDate().toString('yyyy-MM-dd dddd')))
```

#### 时间格式

```
dateEdit1 = QDateTimeEdit()
dateEdit2 = QDateTimeEdit(QDateTime.currentDateTime())
dateEdit = QDateTimeEdit(QDate.currentDate())
timeEdit = QDateTimeEdit(QTime.currentTime())

dateEdit1.setDisplayFormat('yyyy-MM-dd HH:mm:ss')
dateEdit2.setDisplayFormat('yyyy/MM/dd HH-mm-ss')
dateEdit.setDisplayFormat('yyyy.MM.dd')
timeEdit.setDisplayFormat('HH:mm：ss')
```

#### 时间操作

+ 设置最大最小时间

```
dateEdit1.setMinimumDate(QDate.currentDate().addDays(-365))  
```

+ 时间变化

```
        dateEdit1 = QDateTimeEdit()
        dateEdit1.setDisplayFormat('yyyy-MM-dd HH:mm:ss')
        dateEdit1.dateChanged.connect(self.onDateChanged)
        dateEdit1.timeChanged.connect(self.onTimeChanged)
        dateEdit1.dateTimeChanged.connect(self.OnDatetimeChanged)

    def onDateChanged(self,date):
        print(date)
    
    def onTimeChanged(self,time):
        print(time)
    
    def OnDatetimeChanged(self,datatime):
        print(datatime)
```

## 字体

```
font.setPixelSize(16)
self.addBookButton.setFont(font)
```

## 禁止其他界面响应

```
非模态：正常模式
self.setWindowModality(Qt.NonModal )

半模态：窗口级模态对话框，阻塞父窗口、父窗口的父窗口及兄弟窗口。
self.setWindowModality(Qt.WindowModal )

模态：应用程序级模态对话框，阻塞整个应用程序的所有窗口。
self.setWindowModality(Qt.ApplicationModal )
```

# 事件

### 点击关闭按钮

```
    def closeEvent(self, event):
        print('111')
```

### 鼠标进入事件

```
def enterEvent(self, event):
        self.hide_or_show('show', event)
```

### 鼠标离开事件

```
def enterEvent(self, event):
        self.hide_or_show('show', event)
```

### 鼠标点击事件

```
def mousePressEvent(self, event):
        if event.button() == Qt.LeftButton:
            self.dragPosition = event.globalPos() - self.frameGeometry(
            ).topLeft()
            QApplication.postEvent(self, QEvent(174))
            event.accept()
```

### 捕捉鼠标移动事件

```
def mouseMoveEvent(self, event):
        if event.buttons() == Qt.LeftButton:
            try:
                self.move(event.globalPos() - self.dragPosition)
                event.accept()
            except:pass
```

## 回车事件

```
self.search_lineEdit.returnPressed.connect(self.search_slot)
```



# QSS设置样式

## 1. 编写*.qss文件,连接

1. 创建一个style.qss文件，编写样式代码

```
 QMainWindow{
    border-image:url(./images/python.jpg);
}
QPushButton {
    background-color:red
}
```

2. 创建一个"CommonHelper.py"文件，编写下面代码

```
class CommonHelper:
    @staticmethod
    def readQSS(style):
        with open(style,'r') as f:
            return f.read()
```

3. 在主文件中导入CommonHelper.py文件

```
from CommonHelper import CommonHelper
```

## 2. 在主文件中添加qss

#### 1. 通用样式

+ 

```
if __name__ == '__main__':
    app = QApplication(sys.argv)
    window = MainApp()
    qssStyle = '''
        QPushButton {
            background-color:red
        }
    '''
    window.setStyleSheet(qssStyle)
    window.show()
    sys.exit(app.exec_())
```

+ 

```
        self.pushButton_2.setStyleSheet("QPushButton{color:black}"
                                        "QPushButton:hover{color:white}"
                                        "QPushButton{background-color:red}"
                                        "QPushButton{border:2px}"
                                        "QPushButton{border-radius:10px}"
                                        "QPushButton{padding:2px 4px}")
```



#### 2. 选择器样式

```
		self.button1 = QPushButton('我是按钮',self)
		self.button2.setProperty('name','btn1')
        self.button2 = QPushButton('我是按钮', self)
        self.button2.setProperty('name','btn2')

if __name__ == '__main__':
    app = QApplication(sys.argv)
    window = MainApp()
    qssStyle = '''
        QPushButton[name='btn2'] {
            background-color:red;
            color:yellow;
        }
        QPushButton[name='btn1'] {
            background-color:yellow;
            color:red;
        }
    '''
    window.setStyleSheet(qssStyle)
    window.show()
    sys.exit(app.exec_())
```

#### 3. 子控件选择器

+ 修改下拉框的按钮

```
class MainApp(QWidget):
    def __init__(self,parent=None):
        super(MainApp,self).__init__(parent)
        combo = QComboBox(self)
        combo.setObjectName('myComboBox')
        combo.addItem('11111')
        combo.addItem('22222')
        combo.addItem('33333')
        combo.move(50, 50)
        self.setGeometry(250, 200, 320, 150)

if __name__ == '__main__':
    app = QApplication(sys.argv)
    window = MainApp()
    qssStyle = '''
        QComboBox#myComboBox::drop-down {
            image:url(D.ico)
        }
    '''
    window.setStyleSheet(qssStyle)
    window.show()
    sys.exit(app.exec_())
```

## 3. 连接外部qss文件

```
app.setStyleSheet(open("./UnFrameStyle.qss").read())
```



# icons.qrc文件

（索引：添加图标）

比如创建一个文件夹"icons"的资源

1. 右击项目文件夹-New-File-"icons.qrc"

2. 将对应的文件写进去

   ```
   <!DOCTYPE RCC><RCC version="1.0">
       <qresource>
           <file>icons/D.ico</file>
       </qresource>
   </RCC>
   ```

3. 用"Pyrcc"工具将icons.qrc转换为icons.py文件

4. 在QT designer软件中，比如点击一个按钮，在属性中找到"icon"，点击"选择资源"

5. 弹窗中点击"小铅笔图标(编辑资源)"

6. 弹窗中点击"打开资源文件图标"，找到"icons.qrc"文件，打开，确定

7. 回到属性中icon下，调整图标大小

# 美化

## qtawesome

+ 按钮

```python
self.left_button_1 = QtWidgets.QPushButton(qtawesome.icon('fa.music', color='white'), "华语流行")
```



## qdarkstyle

```
import qdarkstyle

if __name__ == "__main__":
    app = QApplication(sys.argv)
    app.setWindowIcon(QIcon("./images/MainWindow_1.png"))
    app.setStyleSheet(qdarkstyle.load_stylesheet_pyqt5())
    mainMindow = UserManage()
    mainMindow.show()
    sys.exit(app.exec_())
```

## 按钮

```
self.button1.setStyleSheet(''' 
                     QPushButton
                     {text-align : center;
                     background-color : white;
                     font: bold;
                     border-color: gray;
                     border-width: 2px;
                     border-radius: 10px;
                     padding: 6px;
                     height : 14px;
                     border-style: outset;
                     font : 14px;}
                     QPushButton:pressed
                     {text-align : center;
                     background-color : light gray;
                     font: bold;
                     border-color: gray;
                     border-width: 2px;
                     border-radius: 10px;
                     padding: 6px;
                     height : 14px;
                     border-style: outset;
                     font : 14px;}
                     ''')
```



# ==初始模板==

```
from PyQt5.QtWidgets import *
from PyQt5.QtCore import *
from PyQt5.QtGui import *
from PyQt5.QtMultimedia import *
from PyQt5.uic import loadUiType
from PyQt5 import QtPrintSupport
from PyQt5.QtWebEngine import *
from PyQt5.QtWebEngineWidgets import *
import sys
import os


class MyWindow(QMainWindow):
    def __init__(self, parent=None):
        super(MyWindow, self).__init__(parent)
        self.resize(600, 600)

        self.button1 = QPushButton('我是按钮', self)
        self.button1.clicked.connect(self.test)


    def test(self):
        pass


if __name__ == "__main__":
    app = QApplication(sys.argv)
    window = MyWindow()
    window.show()
    sys.exit(app.exec_())
```



# MySQL操作

### 写一个dbutil.py工具

```
# 数据库的工具类
import mysql.connector as mysql_conn

# 获取连接
def get_conn():
    try:
        conn = mysql_conn.connect(host='localhost',database='library',
                                  user = 'root',password='root')
        return conn
    except mysql_conn.Error:
        print('数据库连接异常')

# 关闭连接
def close_conn(conn,cursor):
    try:
        if cursor:
            cursor.close()
        if conn:
            conn.close()
    except mysql_conn.Error:
        print('数据库关闭异常')
    finally:
        cursor.close()
        conn.close()

print(get_conn())
```

### 添加操作

```
	def handle_buttons(self):
        self.add_category_Button.clicked.connect(self.add_category)

    # 数据库处理
    # 1. 添加类别
    def add_category(self):
        # 数据库操作流程
        # 1. 获取连接
        conn = get_conn()
        # 2. 获取cursor
        cur = conn.cursor()
        # 3. sql语句
        sql = 'insert into category(category_name) values(%s)'
        category_name = self.add_category_name.text()
        # 4. 执行语句
        cur.execute(sql,(category_name,))
        # 5. insert、update、delete必须显示提交
        conn.commit()
        # 6. 关闭资源
        close_conn(conn,cur)
        # 7. 消息提示
        self.statusBar().showMessage('类别添加成功！')
        # 8. 添加后，将文本框设置为空
        self.add_category_name.setText('')
```

### 读取、显示操作

```
    # 显示已有类别，并且添加完直接看到
    def show_category(self):
        conn = get_conn()
        cur = conn.cursor()
        sql = "select category_name from category"
        cur.execute(sql)
        data = cur.fetchall()
        print(data)
        if data:
            self.category_table.setRowCount(0)
            self.category_table.insertRow(0)
            for row,form in enumerate(data):
                for column,item in enumerate(form):
                    self.category_table.setItem(row,column,QTableWidgetItem(str(item)))
                    column += 1
                row_position = self.category_table.rowCount()
                self.category_table.insertRow(row_position)
```

# SQLite数据库操作

```
from PyQt5.QtWidgets import *
from PyQt5.QtCore import *
import sys
from PyQt5.QtSql import *

def initializeModel(model):
    # 创建表
    model.setTable('people')
    # 修改
    model.setEditStrategy(QSqlTableModel.OnFieldChange)
    model.select()
    model.setHeaderData(0,Qt.Horizontal,'ID')
    model.setHeaderData(1,Qt.Horizontal,'姓名')
    model.setHeaderData(2,Qt.Horizontal,'地址')

def createView(title,model):
    view = QTableView()
    view.setModel(model)
    view.setWindowTitle(title)
    return view

def findrow(i):
    delrow = i.row()
    print('del row =%s' % str(delrow))

def addrow():
    ret = model.insertRows(model.rowCount(),1)
    print('insertRow=%s' % str(ret))

if __name__ == '__main__':
    app = QApplication(sys.argv)
	
	# 如果数据库不存在，则创建数据库。必须先创建db文件夹
    db = QSqlDatabase.addDatabase('QSQLITE')
    db.setDatabaseName('./db/database.db')
    if not db.open():
        print('无法建立与数据库的链接')
        return False
    model = QSqlTableModel()
    delrow = -1
    initializeModel(model)
    view = createView('显示数据',model)
    view.clicked.connect(findrow)

    dlg = QDialog()
    layout = QVBoxLayout()
    layout.addWidget(view)

    # 添加数据
    addBtn = QPushButton('添加一行')
    addBtn.clicked.connect(addrow)

    # 删除数据
    delBtn = QPushButton('删除一行')
    delBtn.clicked.connect(lambda :model.removeRow(view.currentIndex().row()))

    layout.addWidget(addBtn)
    layout.addWidget(delBtn)
    dlg.setLayout(layout)

    dlg.setWindowTitle('Database Demo')
    dlg.resize(500,400)
    dlg.show()
    sys.exit(app.exec())

```

## 创建数据库、表

```
def createDB():
    # 创建数据库
    db = QSqlDatabase.addDatabase('QSQLITE')
    db.setDatabaseName('./db/database.db')
    if not db.open():
        print('无法建立与数据库的链接')
        return False

    # 添加数据
    query = QSqlQuery()
    query.exec('create table people(id int primary key,name varchar(10),address 	varchar(50))')
    query.exec('insert into people values(1,"李宁","上海")')
    db.close()
    return True
```

## 1. 连接数据库

```
from PyQt5 import QtSql
from PyQt5.QtSql import QSqlQuery

database = QtSql.QSqlDatabase.addDatabase('QSQLITE')
database.setDatabaseName('test.db')
database.open()
```

## 2. 新建表

```
q = QSqlQuery()
sql_code = 'create table tbname (id int primary key, name varchar(30), age int)'
if q.exec_(sql_code):
    print('create a table')
```

## 3. 插入数据

````
q = QSqlQuery()
sql_code = 'insert into tbname values(1, "name", 15)'
if q.exec_(sql_code):
    print('succeed insert data')
````

## 4. 查询

```
q = QSqlQuery()
sql_code = 'select id,name,age from tbname'
if q.exec(sql_code):
    id_index = q.record().indexOf('id')
    name_index = q.record().indexOf('name')
    age_index = q.record().indexOf('age')
    while q.next():
        id = q.value(id_index)
        name = q.value(name_index)
        age = q.value(age_index)
        print(id, name, age)
```

```
q = QSqlQuery()
sql_code = 'select id ,name,age from tbname'
if q.exec(sql_code):
    while q.next():
        id = q.value(0)
        name = q.value(1)
        age = q.value(2)
        print(id, name, age)
```

```
q = QSqlQuery()
sql_code = 'select id,name,age from tbname'
q.prepare(sql_code)
q.addBindValue([6,7,8])
q.addBindValue(['test5','test6','test7'])
q.addBindValue([1,1,1])
if q.execBatch():
    print("inserted ")
```

```
q = QSqlQuery()
sql_code = 'select id ,name,age from tbname'
if query.exec(sql_code):
    while query.next():
        id = query.value(0)
        name = query.value(1)
        age = query.value(2)
        print(id, name, age)
print(query.executedQuery())
```



## 5. 获取SQLite数据库中的表信息

+ **查询所有表名信息**

```
select * from sqlite_master
select * from sqlite_sequence

# SQLite数据库中的信息存在于一个内置表sqlite_master中，在查询器中可以用:select * from sqlite_master来查看，如果只要列出所有表名的话，则只要一个语句
SELECT name FROM sqlite_master WHERE type='table' order by name
```

+ **返回tables数据表的数量**

```
select count(*) from sqlite_sequence
select count(*) from sqlite_master
```

+ **返回指定表的字段信息**

```
pragma table_info(table_name)
```

## 6. 插入字段

```
ALTER TABLE tablename ADD columm type
```

## 7. 示例代码

+ ***SQLite_tools.py***

```
def create_SQL(sqlname):
    '''
    创建数据库
    :param sqlname: 数据库目录名称
    '''
    database = QtSql.QSqlDatabase.addDatabase('QSQLITE')
    database.setDatabaseName(sqlname)
    database.open()

def create_SQLtable(tbname):
    '''
    创建通用数据表，默认第一列为主键，名称:ID，类型:INTEGER, 自增
    :param tbname: 数据表名称
    '''
    # CREATE TABLE if not exists 表名 (ID INTEGER PRIMARY KEY AUTOINCREMENT);
    q = QSqlQuery()
    command = u"CREATE TABLE if not exists {} (ID INTEGER PRIMARY KEY AUTOINCREMENT);".format(tbname)
    q.exec_(command)

def add_SQLtable_cloumn(tbname, column_name, genre):
    '''
    指定数据表添加列
    :param tbname: 表名
    :param column_name: 列名
    :param genre: 添加列类型
    '''
    # ALTER TABLE 表名 ADD 列名 列类型;
    q = QSqlQuery()
    command = u"ALTER TABLE {} ADD {} {};".format(tbname, column_name, genre)
    q.exec_(command)

def add_SQLtable_row(tbname, row_num):
    '''
    指定数据表添加行
    :param tbname: 表格名称
    :param row_num: 行数
    '''
    # INSERT INTO 表名 (ID) VALUES (行);
    q = QSqlQuery()
    for row in range(1, row_num + 1):
        command = "INSERT INTO {} (ID) VALUES ({});".format(tbname, str(row))
        q.exec_(command)

def set_SQLtable_value(tbname, column, row, value):
    '''
    更新数据表指定位置的值
    :param tbname: 数据表名称
    :param row: 行数
    :param column: 列数
    :param value: 值
    '''
    # UPDATE 表名 SET 列名=值 WHERE ID=行;
    q = QSqlQuery()
    command = u"UPDATE {} SET {}='{}' WHERE ID={};".format(tbname, column, value, str(row))
    q.exec_(command)

def get_SQLtable_value(tbname, column, row):
    '''
    读取指定数据表的指定列行数据
    :param tbname: 数据表名称
    :param row: 数据表行
    :param column: 数据表列
    :return 返回查询到的值
    '''
    # SELECT 列名 FROM 表名 WHERE ID = 行号;
    q = QSqlQuery()
    command = "SELECT {} FROM {} WHERE ID={};".format(column, tbname, str(row))
    q.exec_(command)
    if q.next():
        result = q.value(0)
        return result

def get_SQLtable_column(tbname, column):
    '''
    读取数据表指定列的所有数据
    :param tbname: 数据表名称
    :param column: 列名称
    :return 返回查询到的值列表
    '''
    # SELECT 列名 FROM 表名;
    q = QSqlQuery()
    command = "SELECT {} FROM {};".format(column, tbname)
    value_list = []
    if q.exec_(command):
        column_index = q.record().indexOf(column)  # 获取列索引值
        while q.next():
            value = q.value(column_index)
            value_list.append(value)
    return value_list

def get_SQLtable_column_name(tbname):
    '''
    获取数据表字段名字
    :param tbname: 数据表名称
    :return: 返回字段(列)名称列表
    '''
    q = QSqlQuery()
    command = "pragma table_info({})".format(tbname)
    name_list = []
    if q.exec_(command):
        while q.next():
            column_name = q.value(1)
            name_list.append(column_name)
    return name_list

def get_SQLtable_row(tbname, row):
    '''
    读取数据表指定行的所有数据
    :param tbname: 数据表名称
    :param column: 行名称
    :return 返回查询到的值列表
    '''
    # SELECT * FROM 表名 WHERE ID = 行号;
    name_list = get_SQLtable_column_name(tbname)
    num = len(name_list) - 1
    q = QSqlQuery()
    command = "SELECT * FROM {} WHERE ID={};".format(tbname, str(row))
    value_list = []
    if q.exec_(command):
        while q.next():
            for i in range(1, num):
                value = q.value(i)
                value_list.append(value)
    return value_list

def delete_SQLtable_value(tbname):
    '''
    清空指定数据表
    :param tbname: 表名
    '''
    # DELETE FROM table_name WHERE[condition];
    q = QSqlQuery()
    command = "DELETE FROM " + tbname + ";"
    q.exec_(command)


```

+ ***PyQt5_SQLite.py***

```
# coding:utf-8

from PyQt5 import QtSql
from PyQt5.QtSql import QSqlQuery

from SQLite_tools import *


db_name = './PtQt5_SQLite.db'
create_SQL(db_name)
tablename = "year"
create_SQLtable(tablename)

#添加12列
for i in range(1, 13):
    month = "month" + str(i)
    add_SQLtable_cloumn(tablename, month, "text")

# 添加31行
add_SQLtable_row(tablename, 31)

# 设置每行每列的值
for i in range(1, 13):
    month = "month" + str(i)
    for j in range(32):
        day = str(j)
        set_SQLtable_value(tablename, month, day, "0")

# 修改 month3 列 13行 的值
set_SQLtable_value(tablename, "month3", "13", "0 1 2 3 4 5 6 7 8 9")

#读取指定位置的值
s1 = get_SQLtable_value(tablename, "month3", "13")
print('s1', s1)

#读取数据表整列的值
s2 = get_SQLtable_column(tablename, "month3")
print('s2', s2)

#读取数据表整行的值
s3 = get_SQLtable_row (tablename, '13')
print('s3', s3)

```

# QTableView

#### 原始和Sqlite交互

```
from PyQt5.QtWidgets import *
from PyQt5.QtCore import *
import sys
from PyQt5.QtSql import *
import os


def initializeModel(model):
    # 创建表
    model.setTable('todo')
    # 修改
    model.setEditStrategy(QSqlTableModel.OnFieldChange)
    model.select()
    model.setHeaderData(0,Qt.Horizontal,'ID')
    model.setHeaderData(1,Qt.Horizontal,'姓名')
    model.setHeaderData(2,Qt.Horizontal,'地址')

def createView(title,model):
    view = QTableView()
    view.setModel(model)
    view.setWindowTitle(title)
    return view

def findrow(i):
    delrow = i.row()
    print('del row =%s' % str(delrow))

def addrow():
    ret = model.insertRows(model.rowCount(),1)
    print('insertRow=%s' % str(ret))



if __name__ == '__main__':
    app = QApplication(sys.argv)

    # if not os.path.exists('./db/database.db'):


    db = QSqlDatabase.addDatabase('QSQLITE')
    db.setDatabaseName('./db/database.db')
    model = QSqlTableModel()
    delrow = -1
    initializeModel(model)
    view = createView('显示数据',model)
    view.clicked.connect(findrow)

    dlg = QDialog()
    layout = QVBoxLayout()
    layout.addWidget(view)

    # 添加数据
    addBtn = QPushButton('添加一行')
    addBtn.clicked.connect(addrow)

    # 删除数据
    delBtn = QPushButton('删除一行')
    delBtn.clicked.connect(lambda :model.removeRow(view.currentIndex().row()))

    layout.addWidget(addBtn)
    layout.addWidget(delBtn)
    dlg.setLayout(layout)

    dlg.setWindowTitle('Database Demo')
    dlg.resize(500,400)
    dlg.show()
    sys.exit(app.exec())

```



#### 不和Sqlite交互，教程

```
import sys
from PyQt5.QtCore import *
from PyQt5.QtWidgets import *
from PyQt5.QtGui import *
from PyQt5.QtSql import *

class Table(QWidget):
    def __init__(self,parent=None):
        super(Table, self).__init__(parent)
        #设置标题与初始大小
        self.setWindowTitle('QTableView表格视图的例子')
        self.resize(500,300)

        #设置数据层次结构，4行4列
        self.model=QStandardItemModel()
        #设置水平方向四个头标签文本内容
        self.model.setHorizontalHeaderLabels(['标题1','标题2'])

        # 创建数据库
        db = QSqlDatabase.addDatabase('QSQLITE')
        db.setDatabaseName('./db/database.db')
        if not db.open():
            print('无法建立与数据库的链接')
            return False

        # 检查表是否存在，不存在则创建表
        query = QSqlQuery()
        # 如果没有此表，则创建表
        query.exec('create table todo(taskname varchar(10),status varchar(50))')
        # query.exec('insert into todo values("这是要做的事","未完成")')
        # db.close()
        q = QSqlQuery()
        sql = 'select taskname,status from todo'
        q.exec(sql)
        data = []
        while q.next():
            taskname = q.value(0)
            status = q.value(1)
            data.append({'taskname': taskname, 'status': status})
            # data.append({'status': status})
        print(data)
        for row, i in enumerate(data):
            # print(row)
            # print(i["taskname"],i["status"])
            tasknamedata = QStandardItem(i["taskname"])
            taskstatusdata = QStandardItem(i["status"])
            # print(tasknamedata,taskstatusdata)
            self.model.setItem(row, 0, tasknamedata)
            self.model.setItem(row, 1, taskstatusdata)

        # #Todo 优化2 添加数据
        # self.model.appendRow([
        #     QStandardItem('row %s,column %s' % (11,11)),
        #     QStandardItem('row %s,column %s' % (11,11)),
        #     QStandardItem('row %s,column %s' % (11,11)),
        #     QStandardItem('row %s,column %s' % (11,11)),
        # ])

        # for row in range(4):
        #     for column in range(4):
        #         item=QStandardItem('row %s,column %s'%(row,column))
        #         #设置每个位置的文本值
        #         self.model.setItem(row,column,item)

        #实例化表格视图，设置模型为自定义的模型
        self.tableView=QTableView()
        self.tableView.setModel(self.model)



        # #todo 优化1 表格填满窗口
        # #水平方向标签拓展剩下的窗口部分，填满表格
        # self.tableView.horizontalHeader().setStretchLastSection(True)
        # #水平方向，表格大小拓展到适当的尺寸
        # self.tableView.horizontalHeader().setSectionResizeMode(QHeaderView.Stretch)
        #
        # #TODO 优化3 删除当前选中的数据
        # indexs=self.tableView.selectionModel().selection().indexes()
        # print(indexs)
        # if len(indexs)>0:
        #     index=indexs[0]
        #     self.model.removeRows(index.row(),1)


        #设置布局
        layout=QVBoxLayout()
        layout.addWidget(self.tableView)
        self.setLayout(layout)
if __name__ == '__main__':
    app=QApplication(sys.argv)
    table=Table()
    table.show()
    sys.exit(app.exec_())
```



# QTableWidget

#### 单元格控件居中

```
widget = QWidget()
celllayout = QHBoxLayout()
checkBox = QCheckBox()
celllayout.addWidget(checkBox)
celllayout.setAlignment(checkBox,Qt.AlignCenter)
checkBox.setChecked(i["status"])
widget.setLayout(celllayout)
self.todoTableWidget.setCellWidget(row, 1, widget)
```

#### 当前行索引index

```
self.todoTableWidget.clicked.connect(self.findrow)

    def findrow(self,i):
        delrow = i.row()
        print('delrow =%s' % str(delrow))
```

#### 删除当前行

```
self.button = QPushButton('删除')
self.button.clicked.connect(self.removerow)
self.layout.addWidget(self.button)

    def removerow(self):
        self.todoTableWidget.removeRow(self.todoTableWidget.currentIndex().row())
```

#### 添加行

```
```

#### 返回当前行的值

```
self.todoTableWidget.clicked.connect(self.findrow)

self.todoTableWidget.setCellWidget(row, 1, checkBox)
self.todoTableWidget.setItem(row, 2, QTableWidgetItem(i["details"]))

def findrow(self,i):
        delrow = i.row()
        print('delrow =%s' % str(delrow))
        print(self.todoTableWidget.item(delrow, 0).text(),
              self.todoTableWidget.cellWidget(delrow,1).isChecked(),  #复选框不居中，要放在QWidget的layout里
              self.todoTableWidget.item(delrow, 2).text())
```

#### 监听内容改变

```

```

```
import sys
from PyQt5.QtWidgets import *
from getData import *

class Table(QWidget):
    def __init__(self):
        super(Table, self).__init__()
        self.initUI()
    def initUI(self):
        self.setWindowTitle("QTableWidget例子")
        self.resize(400,300)
        layout=QHBoxLayout()

        #实现的效果是一样的，四行三列，所以要灵活运用函数，这里只是示范一下如何单独设置行列
        self.tableWidget=QTableWidget()
        # 设置水平方向的表头标签与垂直方向上的表头标签，注意必须在初始化行列之后进行，否则，没有效果
        data,num = getTodoData()
        self.tableWidget.setRowCount(num)
        self.tableWidget.setColumnCount(3)
        self.tableWidget.setHorizontalHeaderLabels(['任务名', '状态','任务内容'])
        for row, i in enumerate(data):
            self.tableWidget.setItem(row, 0, QTableWidgetItem(i["taskname"]))
            checkBox = QCheckBox()
            checkBox.setChecked(i["status"])
            self.tableWidget.setCellWidget(row, 1,checkBox)
            self.tableWidget.setItem(row, 2, QTableWidgetItem(i["details"]))
            # self.model.s(row, 2, QCheckBox())

        # TableWidget = QTableWidget()

        #TOdo 优化7 在单元格内放置控件
        # comBox=QComboBox()
        # comBox.addItems(['男','女'])
        # comBox.addItem('未知')
        # comBox.setStyleSheet('QComboBox{margin:3px}')
        # TableWidget.setCellWidget(0,1,comBox)
        #
        # searchBtn=QPushButton('修改')
        # searchBtn.setDown(True)
        # searchBtn.setStyleSheet('QPushButton{margin:3px}')
        # TableWidget.setCellWidget(0,2,searchBtn)


        #添加数据
        # newItem=QTableWidgetItem('张三')
        # self.tableWidget.setItem(0,0,newItem)
        #
        # newItem=QTableWidgetItem('男')
        # self.tableWidget.setItem(0,1,newItem)
        #
        # newItem=QTableWidgetItem('160')
        # self.tableWidget.setItem(0,2,newItem)

        layout.addWidget(self.tableWidget)

        self.setLayout(layout)
if __name__ == '__main__':
    app=QApplication(sys.argv)
    win=Table()
    win.show()
    sys.exit(app.exec_())

```



#### 使用教程

```
import sys
from PyQt5.QtWidgets import *

class Table(QWidget):
    def __init__(self):
        super(Table, self).__init__()
        self.initUI()
    def initUI(self):
        self.setWindowTitle("QTableWidget例子")
        self.resize(400,300)
        layout=QHBoxLayout()

        #实现的效果是一样的，四行三列，所以要灵活运用函数，这里只是示范一下如何单独设置行列
        TableWidget=QTableWidget(4,3)

        # TableWidget = QTableWidget()
        # TableWidget.setRowCount(4)
        # TableWidget.setColumnCount(3)



        #设置水平方向的表头标签与垂直方向上的表头标签，注意必须在初始化行列之后进行，否则，没有效果
        TableWidget.setHorizontalHeaderLabels(['姓名','性别','体重（kg）'])
        #Todo 优化1 设置垂直方向的表头标签
        #TableWidget.setVerticalHeaderLabels(['行1', '行2', '行3', '行4'])
		
		# #水平方向标签拓展剩下的窗口部分，填满表格,并内容自动换行
        # TableWidget.horizontalHeader().setStretchLastSection(True)
        #TODO 优化 2 设置水平方向表格为自适应的伸缩模式
        ##TableWidget.horizontalHeader().setSectionResizeMode(QHeaderView.Stretch)

        #TODO 优化3 将表格变为禁止编辑
        #TableWidget.setEditTriggers(QAbstractItemView.NoEditTriggers)

        #TODO 优化 4 设置表格整行选中
        #TableWidget.setSelectionBehavior(QAbstractItemView.SelectRows)

        #TODO 优化 5 将行与列的高度设置为所显示的内容的宽度高度匹配
        #QTableWidget.resizeColumnsToContents(TableWidget)
        #QTableWidget.resizeRowsToContents(TableWidget)

        #TODO 优化 6 表格头的显示与隐藏
        #TableWidget.verticalHeader().setVisible(False)
        #TableWidget.horizontalHeader().setVisible(False)

        #TOdo 优化7 在单元格内放置控件
        # comBox=QComboBox()
        # comBox.addItems(['男','女'])
        # comBox.addItem('未知')
        # comBox.setStyleSheet('QComboBox{margin:3px}')
        # TableWidget.setCellWidget(0,1,comBox)
        #
        # searchBtn=QPushButton('修改')
        # searchBtn.setDown(True)
        # searchBtn.setStyleSheet('QPushButton{margin:3px}')
        # TableWidget.setCellWidget(0,2,searchBtn)


        #添加数据
        newItem=QTableWidgetItem('张三')
        TableWidget.setItem(0,0,newItem)

        newItem=QTableWidgetItem('男')
        TableWidget.setItem(0,1,newItem)

        newItem=QTableWidgetItem('160')
        TableWidget.setItem(0,2,newItem)

        layout.addWidget(TableWidget)

        self.setLayout(layout)
if __name__ == '__main__':
    app=QApplication(sys.argv)
    win=Table()
    win.show()
    sys.exit(app.exec_())
```



# ==UI界面（不需将.ui转换为.py）==

1. 将icon、image等文件夹各配置一个.qrc文件，放在项目根目录

2. 通过工具“Pyrcc”将.qrc文件转换为_rc.py

3. 用QT designer编辑好软件界面保存为.ui文件

4. 在项目跟文件夹下创建index.py文件，写入下面代码，运行

   ```
   from PyQt5.QtWidgets import *
   from PyQt5.QtCore import *
   from PyQt5.QtGui import *
   from PyQt5.uic import loadUiType
   import sys
   
   # ui--logic分离
   ui, _=loadUiType('main.ui')
   
   class MainApp(QMainWindow,ui):
       # 定义构造方法
       def __init__(self):
           QMainWindow.__init__(self)
           self.setupUi(self)
   
   def main():
       app = QApplication([])
       window = MainApp()
       window.show()
       app.exec_()
   
   if __name__ == '__main__':
       main()
   
   ```

# ==UI界面(直接调用UI.py文件)==

```
from PyQt5.QtWidgets import *
from PyQt5.QtCore import *
from PyQt5.QtGui import *
from PyQt5.QtMultimedia import *
from PyQt5.uic import loadUiType
import sys
import os
from ui_test import Ui_MainWindow

class MainWindow(QMainWindow,Ui_MainWindow):
    def __init__(self,parent=None):
        super(MainWindow, self).__init__(parent)
        self.setupUi(self)
        # 设置信号和槽
        self.CreateSignalSlot()

    # 设置信号与槽
    def CreateSignalSlot(self):
        self.pushButton.clicked.connect(self.test)

    def test(self):
        pass

if __name__ == '__main__':
    app = QApplication(sys.argv)
    window = MainWindow()
    window.show()
    sys.exit(app.exec_())
```

+ ui.py文件

```
from PyQt5 import QtCore, QtGui, QtWidgets

class Ui_MainWindow(object):
    def setupUi(self, MainWindow):
        MainWindow.setObjectName("MainWindow")
        MainWindow.resize(413, 341)
        self.centralwidget = QtWidgets.QWidget(MainWindow)
        self.centralwidget.setObjectName("centralwidget")
        
        self.centralwidget.setLayout(self.hlayout_window)
```



# 打包pyinstaller

+ -w：不显示终端（DOS框）
+ -F：将所有的库打包成一个单独的文件

```
pyinstaller -Fw demo.py
```

# 读取Json数据

```
{'weatherinfo': {'city': '上海', 'cityid': '101020100', 'temp': '23.5', 'WD': '东北风', 'WS': '小于3级', 'SD': '80%', 'AP': '1006.4hPa', 'njd': '2903', 'WSE': '<3', 'time': '17:00', 'sm': '1.1', 'isRadar': '1', 'Radar': 'JC_RADAR_AZ9210_JB'}}

import requests

rep = requests.get('http://www.weather.com.cn/data/sk/101020100.html')
rep.encoding = 'utf-8'
print(rep.json())

msg1 = '城市: %s' % rep.json()['weatherinfo']['city'] + '\n'
msg2 = '风向: %s' % rep.json()['weatherinfo']['WD'] + '\n'
msg3 = '温度: %s' % rep.json()['weatherinfo']['temp'] + ' 度' + '\n'
msg4 = '风力: %s' % rep.json()['weatherinfo']['WS'] + '\n'
msg5 = '湿度: %s' % rep.json()['weatherinfo']['SD'] + '\n'
```

