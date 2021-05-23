# 安装

进入anaconda相应环境

```
pip install Flask==1.1.1

# python对象操作数据库，不用sql语句
pip install flask-sqlalchemy

# 连接mysql                                     
pip install flask-mysql

#

```

# HTML

| 功能         | 代码 |
| ------------ | ---- |
| 横线、分割线 | <hr> |
|              |      |
|              |      |



# 使用

+ 不需要指定静态目录'static'文件夹
+ 不需要指定模板目录'templates'文件夹

```
from flask import Flask

# Flask类接受一个参数__name__
app = Flask(__name__)

# 装饰器的作用是将路由映射到试图函数index
@app.route('/')
def index():
    return 'Hello World'

# Flask应用程序是咧的run方法启动web服务器
if __name__ == '__main__':
    app.run()
```

# ==修改HTML,立即生效==

```
app.jinja_env.auto_reload=True
app.config['TEMPLATES_AUTO_RELOAD']=True
```



# 例子

## 例1

+ 将index.html文件放入templates文件夹中

```
from flask import Flask,render_template

# Flask类接受一个参数__name__
app = Flask(__name__)

# 装饰器的作用是将路由映射到试图函数index
@app.route('/', methods=['GET'])
def index():
    # Main page
    return render_template('index.html')

# Flask应用程序是咧的run方法启动web服务器
if __name__ == '__main__':
    app.run()
```



# 参数

+ import_name

  ```
  app = Flask(__name__)  # __name__就是
  ```

+ static_url_path

  ```
  # 将static目录文件夹缩写成s
  
  app = Flask(__name__,static_url_path='/s')
  
  # 访问static文件时，输入http://127.0.0.1:5000/s/...
  ```

+ static_folder

  + 指定static文件夹

  + ```
    app = Flask(__name__,static_folder='static_files')
    ```

+ template_folder

  + 指定templates文件夹

# 编码

```
import sys
reload(sys)
sys.setdefaultencoding("utf-8")
```



# 配置

app.config.

# 请求方式

```
@app.route('/', methods=['GET','POST'])
```

# 路由参数

```
@app.route('/order/<order_id>')
def getorderid(order_id):
    return 'oderid是%s' % order_id
```

+ 字符类型限定

```
@app.route('/order/<int:order_id>')
def getorderid(order_id):
    return 'oderid是%s' % order_id
    
@app.route('/order/<float:order_id>')
def getorderid(order_id):
    return 'oderid是%s' % order_id
```

# 后台传值到页面

#### 传值

py文件

```
@app.route('/')
def hello_word():
    ustr = 'www.baidu.com'
    return render_template('index.html',ustr=ustr)
```

index.html

```
<body>
    <h1>hello world</h1>
    {{ustr}}
</body>
```

#### 传列表

```
@app.route('/')
def hello_word():
    list = [1,3,5]
    return render_template('index.html',ustr=ustr)
```

```
<body>
    <h1>hello world</h1>
    {{list.2}}
    {{list[2]}}
</body>
```

#### 传字典

```
@app.route('/')
def hello_word():
    dict = {'a':'b','c':'d'}
    return render_template('index.html',ustr=ustr)
```

```
<body>
    <h1>hello world</h1>
    {{dict.a}}
    {{dict['c']}}
</body>
```

# 控制代码

```
{% for i in list%}
    {%if i >3%}
    {{i}}
    {%endif%}
{%endfor%}
```

# 过滤器

```
{{ustr | upper | reverse}}  #将传过来的字符变大写再反转
```

# 表单提交

```
@app.route('/',methods=['GET','POST'])
def index():
    if request.method == 'POST':
        username = request.form.get('username')
        print(username)
        return 'success'
    return render_template('index.html')
```

```
    <form method="post">
        <input type="text" name="username"><br>
        <input type="submit" value="提交">
    </form>
```

# 闪现消息

需要加密secret_key

```
from flask import Flask,render_template,request,flash

app = Flask(__name__)
app.secret_key ='woshisecretkey'

@app.route('/',methods=['GET','POST'])
def index():
    if request.method == 'POST':
        username = request.form.get('username')
        if not username:
            flash(u'未填写用户名')
        else:
            print(username)
            return 'success'
    return render_template('index.html')

if __name__ == '__main__':
    app.run(debug=True)
```

```
    <form method="post">
        <input type="text" name="username"><br>
        <input type="submit" value="提交">
        {% for message in get_flashed_messages() %}
            {{ message }}
        {% endfor %}
    </form>
```

# 获取选择的图片名

```
@app.route('/',methods=['GET','POST'])
def index():
    if request.method == 'POST':
        received_file = request.form.get('img_file')
        print(received_file)
        return received_file
    return render_template('index.html')
```



# 数据库连接mysql

```
from flask import Flask,render_template,request,flash
from flask_sqlalchemy import SQLAlchemy

app = Flask(__name__)
# 连接数据库
app.config['SQLALCHEMY_DATABASE_URI'] = 'mysql://root:root@127.0.0.1:3306/flask_sql_demo'
# 动态追踪修改设置，如未设置会提示警告，不建议开启
app.config['SQLALCHEMY_TRACK_MODIFICATIONS'] = False
# 查询时显示所有原始sql语句
app.config['SQLALCHEMY_ECHO'] = True
db = SQLAlchemy(app)


class Role(db.Model):
    #定义表名
    __tablename__ = 'roles'
    # 定义字段
    id = db.Column(db.Integer,primary_key=True)
    name = db.Column(db.String(16),unique=True)
    # User给自己Role用，role_id给User用
    users = db.relationship('User',backref='role')

class User(db.Model):
    # 定义表名
    __tablename__ = 'users'
    # 定义字段
    id = db.Column(db.Integer, primary_key=True)
    name = db.Column(db.String(16), unique=True)
    password = db.Column(db.String(20))
    role_id = db.Column(db.Integer,db.ForeignKey('roles.id'))


@app.route('/')
def index():
    roles = Role.query.all()
    return render_template('index.html',roles=roles)

if __name__ == '__main__':
    # 删除表
    db.drop_all()
    # 创建表
    db.create_all()

    ro1 = Role(name='admin')
    ro2 = Role(name='localuser')
    db.session.add_all([ro1,ro2])
    db.session.commit()

    us1 = User(name='zhang',password='123',role_id=ro1.id)
    us2 = User(name='wang',password='456',role_id=ro1.id)
    us3 = User(name='li',password='789',role_id=ro2.id)
    db.session.add_all([us1,us2,us3])
    db.session.commit()

    app.run(debug=True)
```

```
    <ul>
        {% for role in roles %}
            <li>{{role.name}}</li>
            <ul>
                {% for user in role.users %}
                <li>{{user.name}}</li>
                {% endfor %}
            </ul>
        {% endfor %}
    </ul>
```

# ==获取页面传入图片的数组==

```
@app.route('/', methods=['POST', 'GET'])  # 添加路由
def upload():
    if request.method == 'POST':
        f = request.files['file']
        img = f.read()
        img_array = cv2.imdecode(np.frombuffer(img, np.uint8), cv2.IMREAD_COLOR)
        print('img',img_array.shape)
        return '1'

    return render_template('index.html')
```

# ==保存页面传入图片==

### 更更简单？？？

```
@app.route('/', methods=['POST', 'GET'])  # 添加路由
def upload():
    if request.method == 'POST':
        f = request.files['file']
        if not f:
        abort(400)
        resultdata = make_predict(f.read())
        data = resultdata.read()
        resultdata.close()

        return data

    return render_template('index.html')
```



### 最简单

```
@app.route('/', methods=['POST', 'GET'])  # 添加路由
def upload():
    if request.method == 'POST':
        f = request.files['file']
        img = Image.open(f)
        img = img.resize((28, 28), Image.ANTIALIAS)
        img_arr = np.array(img.convert('L'))
        print(img_arr)
        for i in range(28):
            for j in range(28):
                if img_arr[i][j] < 200:
                    img_arr[i][j] = 255
                else:
                    img_arr[i][j] = 0

        img_arr = img_arr / 255.0
        x_predict = img_arr[tf.newaxis, ...]
        result = model.predict(x_predict)
        pred = tf.argmax(result, axis=1)
        pred = pred.numpy()
        pred = str(pred[0])

        return pred

    return render_template('index.html')
```

### 可能比上面多此一举

````
import io

@app.route('/', methods=['POST', 'GET'])  # 添加路由
def upload():
    if request.method == 'POST':
        f = request.files['file']
        img = f.read()
        byte_stream = io.BytesIO(img)
        img = Image.open(byte_stream)
        img = img.resize((28, 28), Image.ANTIALIAS)
        img_arr = np.array(img.convert('L'))
        print(img_arr)
        for i in range(28):
            for j in range(28):
                if img_arr[i][j] < 200:
                    img_arr[i][j] = 255
                else:
                    img_arr[i][j] = 0

        img_arr = img_arr / 255.0
        x_predict = img_arr[tf.newaxis, ...]
        result = model.predict(x_predict)
        pred = tf.argmax(result, axis=1)
        pred = pred.numpy()
        pred = str(pred[0])

        return pred
````

### 将图片保存到本地，再读取

```
@app.route('/', methods=['POST', 'GET'])  # 添加路由
def upload():
    if request.method == 'POST':
        f = request.files['file']

        basepath = os.path.dirname(__file__)  # 当前文件所在路径

        upload_path = os.path.join(basepath, 'static/images',secure_filename(f.filename))  #注意：没有的文件夹一定要先创建，不然会提示没有该路径
        f.save(upload_path)
        img_path = 'images/test.jpg'
        return '1'

    return render_template('index.html')
```

