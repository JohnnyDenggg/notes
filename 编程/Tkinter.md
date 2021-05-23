# 教程

https://www.bilibili.com/video/BV1jW411Y7dL

# 点

## 导入

```
import tkinter as tk
```

## 创建窗口

```
window = tk.Tk()
window.title('my window')
window.geometry('200x200')
```

## 按钮(Button)

```
b1=tk.Button(window,text='insert point',width=15,height=2,command=insert_point)
b1.pack()
```

## 输入框(Entry)

```
e=tk.Entry(window,show=None)  # show='*'密码形式
```

## 文本框(Text)

```
t = tk.Text(window,height=2)
```

## 列表(Listbox)

```
lb = tk.Listbox(window,listvariable=var2)
```

## 刻度(Scale)

```
s = tk.Scale(window,label = 'try me',from_=5,to=11,orient = tk.HORIZONTAL,length=200,showvalue=0,tickinterval=3,resolution=0.01,command=print_selection)
# showvalue=0 显示目前标尺的值，0不显示，1显示
#tickinterval 间隔标尺
#resolution 保留小数几位，1为整数
# orient = tk.HORIZONTAL 横向的
```

## 画布(Canvas)

```
canvas = tk.Canvas(window, bg='blue', height=100, width=200)

#画布中元素移动（画布中元素，x移动像素，y移动像素）
def moveit():
    canvas.move(rect,0,2)
```

![image-20201023131415741](markdownImg/Tkinter/image-20201023131415741.png)

## 图片(image)

```
canvas = tk.Canvas(window, bg='blue', height=400, width=1000)
image_file = tk.PhotoImage(file='111.gif')
image = canvas.create_image(0,0,anchor='nw',image=image_file)
canvas.pack()
#  0,0为画布的点
#  anchor 为图片的锚点
```

## 菜单(Menu)

```
menubar = tk.Menu(window)
filemenu = tk.Menu(menubar, tearoff=1)    #tearoff能否将菜单移出，0为不行，1为可以
menubar.add_cascade(label='File', menu=filemenu)
filemenu.add_command(label='New', command=do_job)
filemenu.add_command(label='Open', command=do_job)
filemenu.add_command(label='Save', command=do_job)
filemenu.add_separator()  #添加分界线
filemenu.add_command(label='Exit', command=window.quit)
```

## 框架(Frame)

```
frm = tk.Frame(window)
frm.pack()
```

## 弹窗(messagebox)

```
def hit_me():
    #弹出信息			    
    tk.messagebox.showinfo(title='Hi',message='hahaha')
    #弹出警告信息
    tk.messagebox.showwarning(title='Hi', message='Noooooo')
    #弹出错误信息
    tk.messagebox.showerror(title='Hi', message='No!! Never!')
    #弹出询问窗口,返回yes 或者 no
    tk.messagebox.askquestion(title='Hi', message='hahaha')
    #if return == 'yes'  继续编辑后续
    # 弹出询问窗口，返回true或false
    tk.messagebox.askyesno(title='Hi', message='hahaha')
    # 弹出询问窗口，返回true或false
    tk.messagebox.askretrycancel(title='Hi', message='hahaha')
    # 弹出询问窗口，返回true或false
    tk.messagebox.askokcancel(title='Hi', message='hahaha')
```

## 位置

```
#上下左右 #pack
tk.Label(window,text='top').pack(side='top')
tk.Label(window,text='buottom').pack(side='bottom')
tk.Label(window,text='left').pack(side='left')
tk.Label(window,text='right').pack(side='right')

#4行3列输出内容1,行内容间隔15单位，列内容间隔10单位,内部xy扩展5 #grid
for i in range(4):
    for j in range(3):
        tk.Label(window, text=1).grid(row=i,column=j,padx=15,pady=10,ipadx=5,ipady=5)

#指定点x,y位置,anchor为图片的锚点位置 #place
tk.Label(window,text=1).place(x=10,y=10,anchor='nw')
        
```



## 画图形

```
x0,y0,x1,y1 = 50,50,80,80
#直线
line = canvas.create_line(x0,y0,x1,y1)
#圆，fill填充
oval = canvas.create_oval(x0,y0,x1,y1, fill='red')
#扇形， start，extent从开始到结束
arc = canvas.create_arc(x0+30,y0+30,x1+30,y1+30, start=0, extent=180)
#方形
rect = canvas.create_rectangle(100,30,100+20,30+20)
```



## 插入(insert)

```
def insert_point():
    var = e.get()
    t.insert('insert',var)
# (从哪里插入，插入什么)
# insert插在光标处
# end插在末尾处
# 1.1插在第一行第一位后面
```

## 删除delete

```
lb.delete(2)    #删除第二位
```



## 函数(def)

```
#定义
def insert_point():
    var = e.get()
    t.insert('insert',var)
#引用
b1=tk.Button(window,command=insert_point)
```

## 定义值

```
var = tk.StringVar()  #字符串
var = tk.IntVar()     #整数
#获取值
var.get()
```

## 修改标签属性config

```
l = tk.Label(window,bg='yellow',width=4,text='empty')
#修改
l.config(text='you have selected' + var.get())
```

# 连接数据库

### 连接Excel

+ 安装包

```
pip install pypyodbc
```

```
pip install openpyxl
```

### 连接mysql

+ 安装包

  ```
  pip install pymysql
  ```

+ 连接

  ```
  con = pymysql.connect(host="localhost", user="root", password="root", database="sch")
  ```

  

# 打包exe

### 安装包

```
pip install PyInstaller
```

1. 进入anaconda的环境

2. ```
   #进入到*.py文件和*.ico的目录
   cd /d D:\Projects\Python Projects\DemoTkinter
   ```

3. ```
   #运行打包命令
   #去除DOS黑框 --noconsole
   pyinstaller -F -i *.ico *.py --noconsole
   ```

4. 

# 将exe打包成安装程序

# 案例

### 学生管理系统

1. mysql:host="localhost", user="root", password="root", database="sch"
2. 数据库login表中把主键都去除

```
import tkinter
import tkinter.messagebox
import re
import pymysql
from tkinter import scrolledtext
import os
from tkinter import *


def window_info(main):
    w = main.winfo_screenwidth()
    h = main.winfo_screenheight()
    x = (w / 2) - 200
    y = (h / 2) - 200
    return (x, y)


def conn():
    con = pymysql.connect(host="localhost", user="root", password="root", database="sch")
    return con


def cur(connection):
    cur = connection.cursor()
    return cur


def exitsys():
    root.destroy()


def teacherlogin():
    # ===============================================================================
    def managerindex():
        def addstudent():
            def addone():
                connection = conn()
                cursor = cur(connection)
                try:
                    cursor.execute('insert into student values(%s,%s,%s,%s,%s)',
                                   (addnameentry.get(), addageentry.get(),
                                    addnoentry.get(), addclassentry.get(), '未注册'))
                    connection.commit()
                except:
                    if addsuccessentry.get() != '':
                        addsuccessentry.delete('0', 'end')
                        addsuccessentry.insert('0', '添加失败!')
                    else:
                        addsuccessentry.insert('0', '添加失败!')
                    connection.rollback()
                    connection.close()
                    cursor.close
                if addsuccessentry.get() != '':
                    addsuccessentry.delete('0', 'end')
                    addsuccessentry.insert('0', '添加成功!')
                else:
                    addsuccessentry.insert('0', '添加成功!')

            def addcancel():
                addnameentry.delete('0', 'end')
                addageentry.delete('0', 'end')
                addnoentry.delete('0', 'end')
                addclassentry.delete('0', 'end')
                addsuccessentry.delete('0', 'end')

            def exit():
                add.destroy()

            add = Toplevel()
            add.title('添加学生信息')
            x, y = window_info(add)
            add.geometry("415x295+%d+%d" % (x, y))
            add['bg'] = 'dodgerblue'

            labelname = tkinter.Label(add, text='添加学生', width=80, bg='dodgerblue')
            labelname.place(x=140, y=50, width=150, height=20)

            labelname = tkinter.Label(add, text='学生名:', width=80)
            labelname.place(x=140, y=80, width=60, height=20)
            addnameentry = tkinter.Entry(add, width=200)
            addnameentry.place(x=195, y=80, width=80, height=20)

            labelage = tkinter.Label(add, text='年  龄:', width=80)
            labelage.place(x=140, y=110, width=60, height=20)
            addageentry = tkinter.Entry(add, width=200)
            addageentry.place(x=195, y=110, width=80, height=20)

            labelno = tkinter.Label(add, text='学 号:', width=80)
            labelno.place(x=140, y=140, width=60, height=20)
            addnoentry = tkinter.Entry(add, width=200)
            addnoentry.place(x=195, y=140, width=80, height=20)

            labelclass = tkinter.Label(add, text='班  级:', width=80)
            labelclass.place(x=140, y=170, width=60, height=20)
            addclassentry = tkinter.Entry(add, width=200)
            addclassentry.place(x=195, y=170, width=80, height=20)

            addsuccessentry = tkinter.Entry(add, width=200, state='normal')
            addsuccessentry.place(x=140, y=200, width=135, height=20)

            buttonadd = tkinter.Button(add, text="添加", command=addone)
            buttonadd.place(x=140, y=230, width=50, height=20)

            buttoncancel = tkinter.Button(add, text="重置", command=addcancel)
            buttoncancel.place(x=220, y=230, width=50, height=20)

            add.mainloop()
            return add
            # ===================================================================================

        def findonestudent():
            def search():
                if textsearch.get('1.0', 'end') != '':
                    textsearch.delete('1.0', 'end')
                else:
                    connection = conn()
                    cursor = cur(connection)
                    try:
                        cursor.execute('select * from student where sno=%s', (entrysearchone.get()))
                        data = list(cursor.fetchone())
                        textsearch.insert('insert', "学生姓名:" + data[0]
                                          + "\n" + "年龄:" + data[1]
                                          + "\n" + "学号" + data[2]
                                          + "\n" + "班级:" + data[3] + "\n\n")
                        connection.commit()
                    except:
                        connection.rollback()
                        connection.close()
                        cursor.close
                connection = conn()
                cursor = cur(connection)
                try:
                    cursor.execute('select * from student where sno=%s', (entrysearchone.get()))
                    data = list(cursor.fetchone())
                    textsearch.insert('insert', "学生姓名:" + data[0]
                                      + "\n" + "年龄:" + data[1]
                                      + "\n" + "学号" + data[2]
                                      + "\n" + "班级:" + data[3] + "\n\n")
                    connection.commit()
                except:
                    connection.rollback()
                    connection.close()
                    cursor.close

            def searchonecancel():
                textsearch.delete('1.0', 'end')

            def searchnocancel():
                entrysearchone.delete('0', 'end')

            def exit():
                findone.destroy()

            findone = Toplevel()
            findone.title('查询学生信息')
            x, y = window_info(findone)
            findone.geometry("415x295+%d+%d" % (x, y))
            findone['bg'] = 'dodgerblue'

            labelname = tkinter.Label(findone, text='请输入要查询学生的学号:', width=80, bg='dodgerblue')
            labelname.place(x=140, y=50, width=140, height=20)

            entrysearchone = tkinter.Entry(findone, width=200)
            entrysearchone.place(x=140, y=80, width=150, height=20)

            buttonsearch = tkinter.Button(findone, text="查找", command=search)
            buttonsearch.place(x=140, y=110, width=50, height=20)

            buttonsearch = tkinter.Button(findone, text="重置", command=searchnocancel)
            buttonsearch.place(x=240, y=110, width=50, height=20)

            textsearch = tkinter.scrolledtext.ScrolledText(findone, width=18, height=6)
            textsearch.place(x=140, y=140)

            buttoncancel = tkinter.Button(findone, text="清空", command=searchonecancel)
            buttoncancel.place(x=190, y=230, width=50, height=20)

            findone.mainloop()

        # ==================================================================================
        def deletestudent():
            def deleteone():
                if deleteoneentry.get() == '':
                    tkinter.messagebox.showerror('error', message="请输入学号!")
                else:
                    if textdelete.get('1.0', 'end') != '':
                        textdelete.delete('1.0', 'end')
                    else:
                        connection = conn()
                        cursor = cur(connection)
                        try:
                            cursor.execute('delete from student where sno=%s', (deleteoneentry.get()))
                            connection.commit()
                            cursor.execute('select * from student')
                            data = list(cursor.fetchall())
                            textdelete.insert('insert', "姓名:\t\t年龄:\t\t学号:\t\t班级:")
                            textdelete.insert('insert', "\n")
                            for i in data:
                                print(i)
                                textdelete.insert('insert', '\t\t'.join(i))
                                textdelete.insert('insert', "\n")
                        except:
                            connection.rollback()
                            connection.close()
                            cursor.close
                    connection = conn()
                    cursor = cur(connection)
                    try:
                        cursor.execute('delete from student where sno=%s', (deleteoneentry.get()))
                        connection.commit()
                        cursor.execute('select * from student')
                        data = list(cursor.fetchall())
                        textdelete.insert('insert', "姓名:\t\t年龄:\t\t学号:\t\t班级:")
                        textdelete.insert('insert', "\n")
                        for i in data:
                            print(i)
                            textdelete.insert('insert', '\t\t'.join(i))
                            textdelete.insert('insert', "\n")
                    except:
                        connection.rollback()
                        connection.close()
                        cursor.close

            def exit():
                deleteone.destroy()

            def deleteonecancel():
                deleteoneentry.delete('0', 'end')

            delete = Toplevel()
            delete.title('删除学生信息')
            x, y = window_info(delete)
            delete.geometry("415x295+%d+%d" % (x, y))
            delete['bg'] = 'dodgerblue'

            labelname = tkinter.Label(delete, text='请输入要删除学生的学号:', bg='dodgerblue')
            labelname.place(x=5, y=20, width=140, height=20)

            deleteoneentry = tkinter.Entry(delete, width=200)
            deleteoneentry.place(x=5, y=50, width=150, height=20)

            buttondelete = tkinter.Button(delete, text="删除", command=deleteone)
            buttondelete.place(x=5, y=80, width=50, height=20)

            buttondelete = tkinter.Button(delete, text="重置", command=deleteonecancel)
            buttondelete.place(x=105, y=80, width=50, height=20)

            textdelete = tkinter.scrolledtext.ScrolledText(delete, width=54, height=9)
            textdelete.place(x=5, y=110)

            delete.mainloop()

        # =======================================================================================
        def findallstudent():
            def show():
                if textshow.get('1.0', 'end') != '':
                    textshow.delete('1.0', 'end')
                else:
                    connection = conn()
                    cursor = cur(connection)
                    try:
                        cursor.execute('select * from student')
                        data = list(cursor.fetchall())
                        textshow.insert('insert', "姓名:\t\t年龄:\t\t学号:\t\t班级:\t\t登录密码:")
                        textshow.insert('insert', "\n")
                        for i in data:
                            print(i)
                            textshow.insert('insert', '\t\t'.join(i))
                            textshow.insert('insert', "\n")
                    except:
                        connection.rollback()
                        connection.close()
                        cursor.close
                connection = conn()
                cursor = cur(connection)
                try:
                    cursor.execute('select * from student')
                    data = list(cursor.fetchall())
                    textshow.insert('insert', "姓名:\t\t年龄:\t\t学号:\t\t班级:\t\t登录密码:")
                    textshow.insert('insert', "\n")
                    for i in data:
                        print(i)
                        textshow.insert('insert', '\t\t'.join(i))
                        textshow.insert('insert', "\n")
                except:
                    connection.rollback()
                    connection.close()
                    cursor.close

            def searchallcancel():
                textshow.delete('1.0', 'end')

            def exit():
                findall.destroy()

            findall = Toplevel()
            findall.title('查询所有学生信息')
            x, y = window_info(findall)
            findall.geometry("520x295+%d+%d" % (x, y))
            findall['bg'] = 'dodgerblue'
            labelname = tkinter.Label(findall, text='查询所有学生信息?', bg='dodgerblue')
            labelname.place(x=5, y=20, width=100, height=20)

            buttonshow = tkinter.Button(findall, text="确定", command=show)
            buttonshow.place(x=5, y=50, width=50, height=20)

            textshow = tkinter.scrolledtext.ScrolledText(findall, width=75, height=9)
            textshow.place(x=5, y=80)

            buttoncancel = tkinter.Button(findall, text="清空", command=searchallcancel)
            buttoncancel.place(x=5, y=210, width=50, height=20)

            findall.mainloop()

        # =======================================================================================
        def modifystudent():
            def modifyfindone():
                connection = conn()
                cursor = cur(connection)
                try:
                    cursor.execute('select * from student where sno=%s', (modifyoneentry.get()))
                    connection.commit()
                except:
                    connection.rollback()
                    connection.close()
                    cursor.close
                data = list(cursor.fetchall())
                if data == []:
                    tkinter.messagebox.showerror(message="没有查询到该学生的信息!")
                else:
                    modifynameentry.insert('0', data[0][0])
                    modifyageentry.insert('0', data[0][1])
                    modifynoentry.insert('0', data[0][2])
                    modifyclassentry.insert('0', data[0][3])

            def submit():
                print(modifynameentry.get())
                print(modifyoneentry.get())
                connection = conn()
                cursor = cur(connection)
                sqlname = "update student set sname = %s where sno = %s"
                cursor.execute(sqlname, (modifynameentry.get(), modifyoneentry.get()))
                sqlage = "update student set sage = %s where sno = %s"
                cursor.execute(sqlage, (modifyageentry.get(), modifyoneentry.get()))
                sqlno = "update student set sno = %s where sno = %s"
                cursor.execute(sqlno, (modifynoentry.get(), modifyoneentry.get()))
                sqlclass = "update student set sclass = %s where sno = %s"
                cursor.execute(sqlclass, (modifyclassentry.get(), modifyoneentry.get()))
                connection.commit()
                if modifysuccessentry.get() != '':
                    modifysuccessentry.delete('0', 'end')
                    modifysuccessentry.insert('0', '修改成功!')
                else:
                    modifysuccessentry.insert('0', '修改成功!')

            modify = Toplevel()
            modify.title('修改学生信息')
            x, y = window_info(modify)
            modify.geometry("415x295+%d+%d" % (x, y))
            modify['bg'] = 'dodgerblue'
            labelname = tkinter.Label(modify, text='请输入要修改学生的学号:', bg='dodgerblue')
            labelname.place(x=5, y=20, width=140, height=20)

            buttonshow = tkinter.Button(modify, text="确定", command=modifyfindone)
            buttonshow.place(x=155, y=50, width=50, height=20)

            modifyoneentry = tkinter.Entry(modify, width=200)
            modifyoneentry.place(x=5, y=50, width=150, height=20)

            labelname = tkinter.Label(modify, text='该学生信息如下', bg='dodgerblue')
            labelname.place(x=5, y=70, width=85, height=20)

            labelname = tkinter.Label(modify, text='姓名:', bg='dodgerblue')
            labelname.place(x=5, y=100, width=30, height=20)
            modifynameentry = tkinter.Entry(modify, width=200)
            modifynameentry.place(x=5, y=120, width=150, height=20)

            labelname = tkinter.Label(modify, text='年龄:', bg='dodgerblue')
            labelname.place(x=200, y=100, width=30, height=20)
            modifyageentry = tkinter.Entry(modify, width=200)
            modifyageentry.place(x=200, y=120, width=150, height=20)

            labelname = tkinter.Label(modify, text='学号:', bg='dodgerblue')
            labelname.place(x=5, y=150, width=30, height=20)
            modifynoentry = tkinter.Entry(modify, width=200)
            modifynoentry.place(x=5, y=170, width=150, height=20)

            labelname = tkinter.Label(modify, text='班级:', bg='dodgerblue')
            labelname.place(x=200, y=150, width=30, height=20)
            modifyclassentry = tkinter.Entry(modify, width=200)
            modifyclassentry.place(x=200, y=170, width=150, height=20)

            modifysuccessentry = tkinter.Entry(modify, width=200)
            modifysuccessentry.place(x=5, y=200, width=150, height=20)

            buttonshow = tkinter.Button(modify, text="提  交", command=submit)
            buttonshow.place(x=5, y=230, width=50, height=20)
            modify.mainloop()

        # ==================================================================================
        def findselectcourseinfor():
            def show():
                print('swj')
                if textshow.get('1.0', 'end') != '':
                    textshow.delete('1.0', 'end')
                else:
                    connection = conn()
                    cursor = cur(connection)
                    try:
                        cursor.execute(
                            'select sno,sname,sclass,cno,cname from student,course where student.sno=sc.sno and course.cno=sc.cno')
                        data = list(cursor.fetchall())
                        textshow.insert('insert', "学号:\t\t姓名:\t\t班级:\t\t课程编号:\t\t课程名:")
                        textshow.insert('insert', "\n")
                        for i in data:
                            print(i)
                            textshow.insert('insert', '\t\t'.join(i))
                            textshow.insert('insert', "\n")
                    except:
                        connection.rollback()
                        connection.close()
                        cursor.close
                connection = conn()
                cursor = cur(connection)
                try:
                    cursor.execute(
                        'select sc.sno,sname,sclass,sc.cno,course.cname from student,course,sc where student.sno=sc.sno and course.cno=sc.cno')
                    data = list(cursor.fetchall())
                    textshow.insert('insert', "学号:\t\t姓名:\t\t班级:\t\t课程编号:\t\t课程名:")
                    textshow.insert('insert', "\n")
                    for i in data:
                        print(i)
                        textshow.insert('insert', '\t\t'.join(i))
                        textshow.insert('insert', "\n")
                except:
                    connection.rollback()
                    connection.close()
                    cursor.close

            def searchallcancel():
                textshow.delete('1.0', 'end')

            findall = Toplevel()
            findall.title('查询学生选课信息')
            x, y = window_info(findall)
            findall.geometry("520x295+%d+%d" % (x, y))
            findall['bg'] = 'dodgerblue'
            labelname = tkinter.Label(findall, text='查询学生选课信息?', bg='dodgerblue')
            labelname.place(x=5, y=20, width=100, height=20)

            buttonshow = tkinter.Button(findall, text="确定", command=show)
            buttonshow.place(x=5, y=50, width=50, height=20)

            textshow = tkinter.scrolledtext.ScrolledText(findall, width=105, height=9)
            textshow.place(x=5, y=80)

            buttoncancel = tkinter.Button(findall, text="清空", command=searchallcancel)
            buttoncancel.place(x=5, y=210, width=50, height=20)

            findall.mainloop()

        # ===================================================================================
        def addcourse():
            def addonecourse():

                print(addcnoentry.get())
                connection = conn()
                cursor = cur(connection)
                try:
                    cursor.execute('insert into course values(%s,%s,%s)',
                                   (addcnoentry.get(), addcnameentry.get(),
                                    addtnoentry.get()))
                    connection.commit()
                except:
                    if addsuccessentry.get() != '':
                        addsuccessentry.delete('0', 'end')
                        addsuccessentry.insert('0', '添加失败!')
                    else:
                        addsuccessentry.insert('0', '添加失败!')
                    connection.rollback()
                    connection.close()
                    cursor.close
                if addsuccessentry.get() != '':
                    addsuccessentry.delete('0', 'end')
                    addsuccessentry.insert('0', '添加成功!')
                else:
                    addsuccessentry.insert('0', '添加成功!')

            def addcancel():
                addcnoentry.delete('0', 'end')
                addcnameentry.delete('0', 'end')
                addtnoentry.delete('0', 'end')

                addsuccessentry.delete('0', 'end')

            addcourse = Toplevel()
            addcourse.title('添加学生信息')
            x, y = window_info(addcourse)
            addcourse.geometry("415x295+%d+%d" % (x, y))
            addcourse['bg'] = 'dodgerblue'

            labelname = tkinter.Label(addcourse, text='添加学生', width=80, bg='dodgerblue')
            labelname.place(x=140, y=50, width=150, height=20)

            labelname = tkinter.Label(addcourse, text='课程号:', width=80)
            labelname.place(x=140, y=80, width=60, height=20)
            addcnoentry = tkinter.Entry(addcourse, width=200)
            addcnoentry.place(x=195, y=80, width=80, height=20)

            labelage = tkinter.Label(addcourse, text='课程名:', width=80)
            labelage.place(x=140, y=110, width=60, height=20)
            addcnameentry = tkinter.Entry(addcourse, width=200)
            addcnameentry.place(x=195, y=110, width=80, height=20)

            labelno = tkinter.Label(addcourse, text='教师编号:', width=80)
            labelno.place(x=140, y=140, width=60, height=20)
            addtnoentry = tkinter.Entry(addcourse, width=200)
            addtnoentry.place(x=195, y=140, width=80, height=20)

            addsuccessentry = tkinter.Entry(addcourse, width=200, state='normal')
            addsuccessentry.place(x=140, y=170, width=135, height=20)

            buttonadd = tkinter.Button(addcourse, text="添加", command=addonecourse)
            buttonadd.place(x=140, y=200, width=50, height=20)

            buttoncancel = tkinter.Button(addcourse, text="重置", command=addcancel)
            buttoncancel.place(x=220, y=200, width=50, height=20)

            addcourse.mainloop()

        def exitsys():
            root.destroy()

        studentindex = Toplevel()
        studentindex.title('学生信息管理系统')
        x, y = window_info(studentindex)
        studentindex.geometry("430x505+%d+%d" % (x, y))
        studentindex['bg'] = 'dodgerblue'

        labelname = tkinter.Label(studentindex, text='欢迎使用学生信息管理系统', bg='dodgerblue', font=("楷体", 20))
        labelname.place(x=60, y=30, width=350, height=40)

        buttonadd = tkinter.Button(studentindex, text="添    加", command=addstudent)
        buttonadd.place(x=150, y=90, width=100, height=40)

        buttonadd = tkinter.Button(studentindex, text="查    询", command=findonestudent)
        buttonadd.place(x=150, y=140, width=100, height=40)

        buttonadd = tkinter.Button(studentindex, text="删    除", command=deletestudent)
        buttonadd.place(x=150, y=190, width=100, height=40)

        buttonadd = tkinter.Button(studentindex, text="查询所有", command=findallstudent)
        buttonadd.place(x=150, y=240, width=100, height=40)

        buttonadd = tkinter.Button(studentindex, text="修    改", command=modifystudent)
        buttonadd.place(x=150, y=290, width=100, height=40)

        buttonadd = tkinter.Button(studentindex, text="添加课程", command=addcourse)
        buttonadd.place(x=150, y=340, width=100, height=40)

        buttonadd = tkinter.Button(studentindex, text="学生选课信息", command=findselectcourseinfor)
        buttonadd.place(x=150, y=390, width=100, height=40)

        buttonadd = tkinter.Button(studentindex, text="退出系统", command=exitsys)
        buttonadd.place(x=150, y=440, width=100, height=40)
        studentindex.mainloop()

    # ===============================================================================
    def login():
        name = entryName.get()
        pwd = entryPwd.get()
        connection = conn()
        cursor = cur(connection)
        cursor.execute('select * from login')
        data = list(cursor.fetchall())
        print(data)
        if data == []:
            tkinter.messagebox.showerror(message="账号或密码错误!")
            return 0
        for i in data:
            print(i[0])
            print(i[1])
            if i[0] == name and i[1] == pwd:
                managerindex()

    def forregister():
        def loginregister():
            if pwdentry.get() == '' or confirmpwdentry.get == '':
                tkinter.messagebox.showerror(message="请输入账号密码!")

            elif pwdentry.get() == confirmpwdentry.get():
                connection = conn()
                cursor = cur(connection)
                try:
                    cursor.execute('insert into login(user,password)values(%s,%s)',
                                   (userentry.get(), pwdentry.get()))
                    connection.commit()
                    if registersuccessentry.get() != '':
                        registersuccessentry.delete('0', 'end')
                        registersuccessentry.insert('0', '注册成功!')
                    else:
                        registersuccessentry.insert('0', '注册成功!')
                    bottonOk = tkinter.Button(studentregister, text="立即登录", command=registerlogin, bg='dodgerblue')
                    bottonOk.place(x=125, y=230, width=70, height=30)
                    # return userentry.get(), pwdentry.get()
                except:
                    connection.rollback()
                    if registersuccessentry.get() != '':
                        registersuccessentry.delete('0', 'end')
                        registersuccessentry.insert('0', '注册失败!')
                    else:
                        registersuccessentry.insert('0', '注册失败!')

            else:
                tkinter.messagebox.showerror(message="两次输入的密码不相同!")

        def registerlogin():

            managerindex()

        studentregister = Toplevel()
        x, y = window_info(studentregister)
        studentregister.title('学生信息管理系统')
        studentregister.geometry("415x295+%d+%d" % (x, y))
        studentregister['bg'] = 'dodgerblue'

        labelname = tkinter.Label(studentregister, text='注册学生信息管理系统', bg='dodgerblue', font=("楷体", 20))
        labelname.place(x=60, y=30, width=300, height=40)

        labelName = tkinter.Label(studentregister, text="账      号：", bg='dodgerblue', width=80)
        labelName.place(x=115, y=110, width=80, height=20)

        userentry = tkinter.Entry(studentregister, width=80)
        userentry.place(x=210, y=110, width=80, height=20)

        labelPwd = tkinter.Label(studentregister, text="密      码：", bg='dodgerblue', width=80)
        labelPwd.place(x=115, y=135, width=80, height=20)

        pwdentry = tkinter.Entry(studentregister, width=80)
        pwdentry.place(x=210, y=135, width=80, height=20)

        labelPwd = tkinter.Label(studentregister, text="确认密码：", bg='dodgerblue', width=80)
        labelPwd.place(x=115, y=160, width=80, height=20)

        confirmpwdentry = tkinter.Entry(studentregister, width=80)
        confirmpwdentry.place(x=210, y=160, width=80, height=20)

        registersuccessentry = tkinter.Entry(studentregister, width=80)
        registersuccessentry.place(x=125, y=190, width=165, height=20)

        bottonCancel = tkinter.Button(studentregister, text='注册', command=loginregister, bg='dodgerblue')
        bottonCancel.place(x=225, y=230, width=70, height=30)
        studentregister.mainloop()

    manager = Toplevel()
    manager.title(' 管理员端')
    x, y = window_info(manager)
    manager.geometry("415x295+%d+%d" % (x, y))
    manager['bg'] = 'dodgerblue'

    varLoginName = tkinter.StringVar()
    varLoginPwd = tkinter.StringVar()

    labelname = tkinter.Label(manager, text='欢迎使用学生信息管理系统', bg='dodgerblue', font=("楷体", 18))
    labelname.place(x=60, y=30, width=300, height=40)

    labelName = tkinter.Label(manager, text="账    号：", justify=tkinter.RIGHT, bg='dodgerblue', width=80)
    labelName.place(x=110, y=110, width=80, height=20)
    labelPwd = tkinter.Label(manager, text="密    码：", justify=tkinter.RIGHT, bg='dodgerblue', width=80)
    labelPwd.place(x=110, y=135, width=80, height=20)

    entryName = tkinter.Entry(manager, width=80, textvariable=varLoginName)
    entryName.place(x=210, y=110, width=80, height=20)
    entryPwd = tkinter.Entry(manager, show='*', width=80, textvariable=varLoginPwd)
    entryPwd.place(x=210, y=135, width=80, height=20)

    bottonOk = tkinter.Button(manager, text="登录", command=login, bg='dodgerblue')
    bottonOk.place(x=125, y=170, width=70, height=30)
    bottonCancel = tkinter.Button(manager, text='注册', command=forregister, bg='dodgerblue')
    bottonCancel.place(x=225, y=170, width=70, height=30)

    manager.mainloop()


def studentlogin():
    def forstudentregister():

        def loginregister():
            if pwdentry.get() == '' or confirmpwdentry.get == '':
                tkinter.messagebox.showerror(message="请输入账号密码!")

            elif pwdentry.get() == confirmpwdentry.get():
                connection = conn()
                cursor = cur(connection)
                try:
                    sqlpwd = "update student set loginpwd = %s where sno = %s"
                    cursor.execute(sqlpwd, (pwdentry.get(), userentry.get()))
                    connection.commit()
                    if registersuccessentry.get() != '':
                        registersuccessentry.delete('0', 'end')
                        registersuccessentry.insert('0', '注册成功!')
                    else:
                        registersuccessentry.insert('0', '注册成功!')
                    bottonOk = tkinter.Button(studentregister, text="立即登录", command=registerlogin, bg='dodgerblue')
                    bottonOk.place(x=125, y=230, width=70, height=30)
                except:
                    connection.rollback()
                    if registersuccessentry.get() != '':
                        registersuccessentry.delete('0', 'end')
                        registersuccessentry.insert('0', '注册失败!')
                    else:
                        registersuccessentry.insert('0', '注册失败!')

            else:
                tkinter.messagebox.showerror(message="两次输入的密码不相同!")

            return userentry.get()

        def registerlogin():
            studentindex(userentry.get())

        studentregister = Toplevel()
        x, y = window_info(studentregister)
        studentregister.title('学生信息管理系统-注册')
        studentregister.geometry("415x295+%d+%d" % (x, y))
        studentregister['bg'] = 'dodgerblue'

        labelname = tkinter.Label(studentregister, text='注册学生信息管理系统', bg='dodgerblue', font=("楷体", 20))
        labelname.place(x=60, y=30, width=300, height=40)

        labelName = tkinter.Label(studentregister, text="学      号：", bg='dodgerblue', width=80)
        labelName.place(x=115, y=110, width=80, height=20)

        userentry = tkinter.Entry(studentregister, width=80)
        userentry.place(x=210, y=110, width=80, height=20)

        labelPwd = tkinter.Label(studentregister, text="密      码：", bg='dodgerblue', width=80)
        labelPwd.place(x=115, y=135, width=80, height=20)

        pwdentry = tkinter.Entry(studentregister, width=80)
        pwdentry.place(x=210, y=135, width=80, height=20)

        labelPwd = tkinter.Label(studentregister, text="确认密码：", bg='dodgerblue', width=80)
        labelPwd.place(x=115, y=160, width=80, height=20)

        confirmpwdentry = tkinter.Entry(studentregister, width=80)
        confirmpwdentry.place(x=210, y=160, width=80, height=20)

        registersuccessentry = tkinter.Entry(studentregister, width=80)
        registersuccessentry.place(x=125, y=190, width=165, height=20)

        bottonCancel = tkinter.Button(studentregister, text='注册', command=loginregister, bg='dodgerblue')
        bottonCancel.place(x=225, y=230, width=70, height=30)

        studentregister.mainloop()

    def studentindex(name):
        loginingno = name
        print('sdfsdffds')

        def showinfor():
            def show():
                if textshowinformation.get('1.0', 'end') != '':
                    textshowinformation.delete('1.0', 'end')
                else:

                    print(loginingno)
                    print('swj')
                    connection = conn()
                    cursor = cur(connection)
                    try:
                        cursor.execute('select * from student where sno=%s', (loginingno))
                        data = list(cursor.fetchone())
                        textshowinformation.insert('insert', "学生姓名:" + data[0]
                                                   + "\n" + "年龄:" + data[1]
                                                   + "\n" + "学号" + data[2]
                                                   + "\n" + "班级:" + data[3] + "\n\n")
                        connection.commit()
                    except:
                        connection.rollback()
                        connection.close()
                        cursor.close
                connection = conn()
                cursor = cur(connection)
                try:
                    cursor.execute('select * from student where sno=%s', (loginingno))
                    data = list(cursor.fetchone())
                    textshowinformation.insert('insert', "学生姓名:" + data[0]
                                               + "\n" + "年龄:" + data[1]
                                               + "\n" + "学号" + data[2]
                                               + "\n" + "班级:" + data[3] + "\n\n")
                    connection.commit()
                except:
                    connection.rollback()
                    connection.close()
                    cursor.close

            def showinforcancel():
                textshowinformation.delete('1.0', 'end')

            showinformation = Toplevel()
            showinformation.title('查询学籍信息')
            x, y = window_info(showinformation)
            showinformation.geometry("415x295+%d+%d" % (x, y))
            showinformation['bg'] = 'dodgerblue'
            labelname = tkinter.Label(showinformation, text='查询学籍信息?', bg='dodgerblue')
            labelname.place(x=5, y=20, width=100, height=20)

            buttonshow = tkinter.Button(showinformation, text="确定", command=show)
            buttonshow.place(x=5, y=50, width=50, height=20)

            textshowinformation = tkinter.scrolledtext.ScrolledText(showinformation, width=60, height=9)
            textshowinformation.place(x=5, y=80)

            buttoncancel = tkinter.Button(showinformation, text="清空", command=showinforcancel)
            buttoncancel.place(x=5, y=210, width=50, height=20)

            showinformation.mainloop()

        def findcourseinfor():
            def show():
                if textshow.get('1.0', 'end') != '':
                    textshow.delete('1.0', 'end')
                else:
                    connection = conn()
                    cursor = cur(connection)
                    try:
                        cursor.execute('select * from course')
                        data = list(cursor.fetchall())
                        textshow.insert('insert', "课程号:\t\t\t课程名:\t\t\t教师编号:")
                        textshow.insert('insert', "\n")
                        for i in data:
                            print(i)
                            textshow.insert('insert', '\t\t'.join(i))
                            textshow.insert('insert', "\n")
                    except:
                        connection.rollback()
                        connection.close()
                        cursor.close
                connection = conn()
                cursor = cur(connection)
                try:
                    cursor.execute('select * from course')
                    data = list(cursor.fetchall())
                    textshow.insert('insert', "课程号:\t\t\t课程名:\t\t\t教师编号:")
                    textshow.insert('insert', "\n")
                    for i in data:
                        print(i)
                        textshow.insert('insert', '\t\t\t'.join(i))
                        textshow.insert('insert', "\n")
                except:
                    connection.rollback()
                    connection.close()
                    cursor.close

            def searchallcancel():
                textshow.delete('1.0', 'end')

            findall = Toplevel()
            findall.title('查询课程信息')
            x, y = window_info(findall)
            findall.geometry("520x295+%d+%d" % (x, y))
            findall['bg'] = 'dodgerblue'
            labelname = tkinter.Label(findall, text='查询所有课程信息?', bg='dodgerblue')
            labelname.place(x=5, y=20, width=100, height=20)

            buttonshow = tkinter.Button(findall, text="确定", command=show)
            buttonshow.place(x=5, y=50, width=50, height=20)

            textshow = tkinter.scrolledtext.ScrolledText(findall, width=75, height=9)
            textshow.place(x=5, y=80)

            buttoncancel = tkinter.Button(findall, text="清空", command=searchallcancel)
            buttoncancel.place(x=5, y=210, width=50, height=20)

            findall.mainloop()

        def selectcourse():
            def show():
                if textshow.get('1.0', 'end') != '':
                    textshow.delete('1.0', 'end')
                else:
                    connection = conn()
                    cursor = cur(connection)
                    try:
                        cursor.execute('select * from course')
                        data = list(cursor.fetchall())
                        textshow.insert('insert', "课程号:\t\t\t课程名:\t\t\t教师编号:")
                        textshow.insert('insert', "\n")
                        for i in data:
                            print(i)
                            textshow.insert('insert', '\t\t'.join(i))
                            textshow.insert('insert', "\n")
                    except:
                        connection.rollback()
                        connection.close()
                        cursor.close
                connection = conn()
                cursor = cur(connection)
                try:
                    cursor.execute('select * from course')
                    data = list(cursor.fetchall())
                    textshow.insert('insert', "课程号:\t\t\t课程名:\t\t\t教师编号:")
                    textshow.insert('insert', "\n")
                    for i in data:
                        print(i)
                        textshow.insert('insert', '\t\t\t'.join(i))
                        textshow.insert('insert', "\n")
                except:
                    connection.rollback()
                    connection.close()
                    cursor.close

            def searchallcancel():
                textshow.delete('1.0', 'end')

            def select():
                connection = conn()
                cursor = cur(connection)
                try:
                    cursor.execute('insert into sc values(%s,%s)',
                                   (loginingno, entrysearchone.get()))
                    connection.commit()
                except:
                    if addsuccessentry.get() != '':
                        addsuccessentry.delete('0', 'end')
                        addsuccessentry.insert('0', '选课失败!')
                    else:
                        addsuccessentry.insert('0', '选课失败!')
                    connection.rollback()
                    connection.close()
                    cursor.close
                if addsuccessentry.get() != '':
                    addsuccessentry.delete('0', 'end')
                    addsuccessentry.insert('0', '选课成功!')
                else:
                    addsuccessentry.insert('0', '选课成功!')

            def addcancel():
                entrysearchone.delete('0', 'end')
                addsuccessentry.delete('0', 'end')

            findall = Toplevel()
            findall.title('学生选课')
            x, y = window_info(findall)
            findall.geometry("520x325+%d+%d" % (x, y))
            findall['bg'] = 'dodgerblue'
            labelname = tkinter.Label(findall, text='查询所有课程信息?', bg='dodgerblue')
            labelname.place(x=5, y=20, width=100, height=20)

            buttonshow = tkinter.Button(findall, text="确定", command=show)
            buttonshow.place(x=5, y=50, width=50, height=20)

            textshow = tkinter.scrolledtext.ScrolledText(findall, width=75, height=9)
            textshow.place(x=5, y=80)

            labelname = tkinter.Label(findall, text='请输入课程编号:', bg='dodgerblue')
            labelname.place(x=5, y=210, width=100, height=20)

            entrysearchone = tkinter.Entry(findall, width=200)
            entrysearchone.place(x=5, y=240, width=150, height=20)

            addsuccessentry = tkinter.Entry(findall, width=200)
            addsuccessentry.place(x=5, y=270, width=75, height=20)

            buttoncancel = tkinter.Button(findall, text="选择", command=select)
            buttoncancel.place(x=5, y=300, width=50, height=20)

            buttoncancel = tkinter.Button(findall, text="重置", command=addcancel)
            buttoncancel.place(x=105, y=300, width=50, height=20)

            findall.mainloop()

        def findselectcourseinfor():
            def show():
                print('swj')
                if textshow.get('1.0', 'end') != '':
                    textshow.delete('1.0', 'end')
                else:
                    connection = conn()
                    cursor = cur(connection)
                    try:
                        cursor.execute(
                            'select sno,sname,sclass,cno,cname from student,course where student.sno=sc.sno and course.cno=sc.cno and sno=%s',
                            (loginingno))
                        data = list(cursor.fetchall())
                        textshow.insert('insert', "学号:\t\t姓名:\t\t班级:\t\t课程编号:\t\t课程名:")
                        textshow.insert('insert', "\n")
                        for i in data:
                            print(i)
                            textshow.insert('insert', '\t\t'.join(i))
                            textshow.insert('insert', "\n")
                    except:
                        connection.rollback()
                        connection.close()
                        cursor.close
                connection = conn()
                cursor = cur(connection)
                try:
                    cursor.execute(
                        'select sc.sno,sname,sclass,sc.cno,course.cname from student,course,sc where student.sno=sc.sno and course.cno=sc.cno and sc.sno=%s',
                        (loginingno))
                    data = list(cursor.fetchall())
                    textshow.insert('insert', "学号:\t\t姓名:\t\t班级:\t\t课程编号:\t\t课程名:")
                    textshow.insert('insert', "\n")
                    for i in data:
                        print(i)
                        textshow.insert('insert', '\t\t'.join(i))
                        textshow.insert('insert', "\n")
                except:
                    connection.rollback()
                    connection.close()
                    cursor.close

            def searchallcancel():
                textshow.delete('1.0', 'end')

            findall = Toplevel()
            findall.title('查询选课信息')
            x, y = window_info(findall)
            findall.geometry("520x295+%d+%d" % (x, y))
            findall['bg'] = 'dodgerblue'
            labelname = tkinter.Label(findall, text='查询选课信息?', bg='dodgerblue')
            labelname.place(x=5, y=20, width=100, height=20)

            buttonshow = tkinter.Button(findall, text="确定", command=show)
            buttonshow.place(x=5, y=50, width=50, height=20)

            textshow = tkinter.scrolledtext.ScrolledText(findall, width=105, height=9)
            textshow.place(x=5, y=80)

            buttoncancel = tkinter.Button(findall, text="清空", command=searchallcancel)
            buttoncancel.place(x=5, y=210, width=50, height=20)

            findall.mainloop()

        print(3)
        indexofstudent = Toplevel()
        indexofstudent.title('学生信息管理系统-学生')
        x, y = window_info(indexofstudent)
        indexofstudent.geometry("430x425+%d+%d" % (x, y))
        indexofstudent['bg'] = 'dodgerblue'

        labelname = tkinter.Label(indexofstudent, text='欢迎使用学生信息管理系统', bg='dodgerblue', font=("楷体", 20))
        labelname.place(x=60, y=30, width=350, height=40)

        buttonadd = tkinter.Button(indexofstudent, text="查询学籍信息", command=showinfor)
        buttonadd.place(x=150, y=90, width=100, height=40)

        buttonadd = tkinter.Button(indexofstudent, text="查询课程信息", command=findcourseinfor)
        buttonadd.place(x=150, y=140, width=100, height=40)

        buttonadd = tkinter.Button(indexofstudent, text="选    课", command=selectcourse)
        buttonadd.place(x=150, y=190, width=100, height=40)

        buttonadd = tkinter.Button(indexofstudent, text="查询选课信息", command=findselectcourseinfor)
        buttonadd.place(x=150, y=240, width=100, height=40)

        buttonadd = tkinter.Button(indexofstudent, text="退出系统", command=exitsys)
        buttonadd.place(x=150, y=290, width=100, height=40)

        indexofstudent.mainloop()

    def login():
        name = entryName.get()
        pwd = entryPwd.get()
        connection = conn()
        cursor = cur(connection)
        cursor.execute('select * from student')
        data = list(cursor.fetchall())
        print(data)
        if data == []:
            tkinter.messagebox.showerror(message="账号或密码错误!")
            return 0
        for i in data:
            print(i[2])
            print(i[4])
            if i[2] == name and i[4] == pwd:
                studentindex(name)

    student = Toplevel()
    student.title(' 登录-学生端')
    x, y = window_info(student)
    student.geometry("415x295+%d+%d" % (x, y))
    student['bg'] = 'dodgerblue'

    labelname = tkinter.Label(student, text='欢迎使用学生信息管理系统', bg='dodgerblue', font=("楷体", 18))
    labelname.place(x=60, y=30, width=300, height=40)

    labelName = tkinter.Label(student, text="学    号：", bg='dodgerblue', width=80)
    labelName.place(x=110, y=110, width=80, height=20)
    labelPwd = tkinter.Label(student, text="密    码：", bg='dodgerblue', width=80)
    labelPwd.place(x=110, y=135, width=80, height=20)

    entryName = tkinter.Entry(student, width=80, textvariable=varLoginName)
    entryName.place(x=210, y=110, width=80, height=20)
    entryPwd = tkinter.Entry(student, show='*', width=80, textvariable=varLoginPwd)
    entryPwd.place(x=210, y=135, width=80, height=20)

    bottonOk = tkinter.Button(student, text="登录", command=login, bg='dodgerblue')
    bottonOk.place(x=125, y=170, width=70, height=30)
    bottonCancel = tkinter.Button(student, text='注册', command=forstudentregister, bg='dodgerblue')
    bottonCancel.place(x=225, y=170, width=70, height=30)

    student.mainloop()


root = tkinter.Tk(className=' 学生信息管理系统')
x, y = window_info(root)
root.geometry("415x295+%d+%d" % (x, y))
root['bg'] = 'dodgerblue'

varLoginName = tkinter.StringVar()
varLoginPwd = tkinter.StringVar()

labelname = tkinter.Label(root, text='欢迎使用学生信息管理系统', bg='dodgerblue', font=("楷体", 18))
labelname.place(x=60, y=30, width=300, height=40)

bottonOk = tkinter.Button(root, text="学生登录", command=studentlogin, bg='dodgerblue')
bottonOk.place(x=150, y=140, width=100, height=40)
bottonCancel = tkinter.Button(root, text='管理员登录', command=teacherlogin, bg='dodgerblue')
bottonCancel.place(x=150, y=200, width=100, height=40)


def createdatabase():
    conn = pymysql.connect(host="localhost", user="root", password="root")
    cur = conn.cursor()
    cur.execute('create database if not exists sch')


def createtable():
    connection = conn()
    cursor = cur(connection)
    sqlstudent = """create table if not exists student(
                    sname char(45) not null,
                    sage char(45),
                    sno char(45) primary key,
                    sclass char(45),
                    loginpwd char(45)
                    )engine=innodb"""
    cursor.execute(sqlstudent)

    sqllogin = """create table if not exists login(
                    user char(45)primary key,
                    password char(45) not null
                    )engine=innodb"""
    cursor.execute(sqllogin)
    connection.commit()
    cursor.execute("""insert into login(user,password) values('user','pwd')""")
    connection.commit()

    sqlteacher = """create table if not exists teacher(
                    tno char(45) primary key,
                    tname char(45) 
                    )engine=innodb"""
    cursor.execute(sqlteacher)
    connection.commit()

    sqlcourse = """create table if not exists course(
                        cno char(45) ,
                        cname char(45),
                        tno char(45),
                        constraint pk_course primary key (cno,tno)
                        )engine=innodb"""
    cursor.execute(sqlcourse)
    connection.commit()

    sqlsc = """create table if not exists sc(
                        sno char(45),
                        cno char(45),
                        constraint pk_sc primary key (sno,cno)
                        )engine=innodb"""
    cursor.execute(sqlsc)
    connection.commit()


createdatabase()
createtable()

root.mainloop()

```

