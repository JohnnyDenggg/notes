# 其他操作

### 去除空格

```
a.strip()
```

### 以符号分割字符、文件名

```
filename.rsplit('.', 1)[0]  #0去.前面的字符
```

### 判断文件类型是否符合

```
ALLOWED_EXTENSIONS = set(['png', 'jpg', 'JPG', 'PNG', 'bmp'])

file = '123.ico'

def allowed_file(filename):
    return '.' in filename and filename.rsplit('.', 1)[1] in ALLOWED_EXTENSIONS
```



# 文件夹路径

### 判断文件夹路径是否存在，创建文件夹

```
import os
receive_dirpath = './resources/received_img'
if not os.path.isdir(receive_dirpath):
	os.makedirs(receive_dirpath)
```

### 拼接路径

```
img_file_path = os.path.join(receive_dirpath,img_path)
```

### 路径分割

```
os.path.split(imagePath)[1]   #分为路径和文件名，0为路径，1为文件名
```

### 当前路径获取

```
basepath = os.path.dirname(__file__) #获取当前文件路径
```



# 图片数据处理

### 将图片转为数组、变形、增加维度

```
img = Image.open(img_path)
x = img.resize((224, 224))	
x = np.expand_dims(x, axis=0)  	# (1, 224, 224, 3)
```

```
inputs = img_ndarray[np.newaxis,...] 			#数组增加维度
```

### 图片转为灰度，去掉最后一维

```
img = Image.open(img_path)
img = np.array(img.convert('L'))
print(img.shape)
```



# onehot转为分类名

```
def predict_image(model, inputs):
    predict_Y = model.predict(inputs)[0]
    predict_y = np.argmax(predict_Y)
    predict_classId = predict_y
    predict_className = classId_to_className(predict_classId)
    return predict_className

def classId_to_className(classId):
    category_list = ['plane', 'car', 'bird', 'cat', 'deer', 'dog', 'frog', 'horse', 'ship', 'truck']
    className = category_list[classId]
    return className
```

+ 分类名转为json，用flask在网页中显示

```
from flask import Flask, render_template, request, jsonify

@app.route("/predict_image", methods=['POST'])
def anyname_you_like():
        predict_className = predict_image(model, imageFilePath)
        return jsonify(predict_className=predict_className)
```

# 读取json

### 方法1

```python
    def search_info(self):
        input = self.right_bar_widget_search_input.text()
        response  = requests.get('https://autumnfish.cn/search?keywords={}'.format(input))
        # print(response .text)
        content = response.content
        result = json.loads(content)
        # print(content)
        # print(result)
        song_list = []
        songs = result["result"]["songs"]
        print(songs)
        # print(len(songs))
        for i in range (len(songs)):
            song = {}
            song['name']=songs[i]['name']
            song['id'] = songs[i]['id']
            song_list.append(song)
        print(song_list)
```

### 方法二

```python
rep = requests.get('http://www.weather.com.cn/data/sk/101020100.html')
        rep.encoding = 'utf-8'
        print(rep.json())

        msg1 = '城市: %s' % rep.json()['weatherinfo']['city'] + '\n'
        msg2 = '风向: %s' % rep.json()['weatherinfo']['WD'] + '\n'
        msg3 = '温度: %s' % rep.json()['weatherinfo']['temp'] + ' 度' + '\n'
        msg4 = '风力: %s' % rep.json()['weatherinfo']['WS'] + '\n'
        msg5 = '湿度: %s' % rep.json()['weatherinfo']['SD'] + '\n'
```



