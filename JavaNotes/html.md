[TOC]

# HTML

## DOM目录树



## 标签

标签在HTML中是一个对象，同时也是构成网页的基本元素。

### html标签

html标签是整个DOM目录树的根节点。

### head标签

用于展示html标签的属性

### title标签

用于表示网页的标题

### body标签

body标签用于展示html的内容

### 注释标签

html中的注释和其它语言不太一样，它会在网页的源代码中显示用户可以看得到所以注释不能乱写。

```html
<!--注释内容-->
```

![image-20220628160559840](https://cdn.jsdelivr.net/gh/ls02/Image/img/image-20220628160559840.png)

### h标签

h标签是表示内容主题标题标签，h标签一共有六个级别分别从1-6，数字越小显示的字体越大，数字越大显示的字体越小。

在`html`中，代表的换行或空格一般对于页面时没有效果的，一个元素对应一个属性，换行是一个独立的元素。

**语法：** hN(N表示数字)

**使用案列：**

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>我的标题</title>
</head>
<body>
    <h1>一级标题</h1>
    <h2>二级标题</h2>
    <h3>三级标题</h3>
    <h4>四级标题</h4>
    <h5>五级标题</h5>
    <h6>六级标题</h6>
</body>
</html>
```

![image-20220628161314082](https://cdn.jsdelivr.net/gh/ls02/Image/img/image-20220628161314082.png)

### p标签

p标签是段落标签，用于作为文字内容的形式展现，段落和段落之间存在间距来区分不同的段落。

开头不能通过空格来达到缩进的效果得依靠`CSS`来完成。

**语法：** p 内容

**使用案列：**

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>我的标题</title>
</head>
<body>
    <!-- lorem随机生成一句话 -->
    <!-- <p>lorem</p> -->
    <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Veniam nulla id dolorem quis sit fugit, rem cupiditate tenetur maxime expedita vitae hic laborum obcaecati velit inventore libero? Temporibus, eum deleniti.</p>
    <p>第一个段落</p>
    <p>第二个段落</p>
    <p>第三个段落</p>
</body>
</html>
```

![image-20220628162116022](https://cdn.jsdelivr.net/gh/ls02/Image/img/image-20220628162116022.png)

### br标签

br标签是一个换行标签，我们如果想在段落里换行得通过br来完成，直接换行页面效果不会有反应。

**语法：** br

**使用案列：**

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>我的标题</title>
</head>
<body>
    <!-- 不严格的写法,可能部分浏览器会有问题，但是目前主流的几个都没问题 -->
    <p>第一个<br>段落</p>
    <!-- 严格的写法 -->
    <p>第二个<br/>段落</p>
</body>
</html>
```

![image-20220628162857683](https://cdn.jsdelivr.net/gh/ls02/Image/img/image-20220628162857683.png)

### 格式化标签

格式化标签可以影响到样式，同时格式化标签不会独占一行。

#### strong和b标签

这两个标签都是用来加粗字体的。

**语法：** b(strong) 内容

**使用案列：**

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>我的标题</title>
</head>
<body>
    <strong>加粗效果</strong>
    <b>加粗效果</b>
</body>
</html>
```

![image-20220628163858567](https://cdn.jsdelivr.net/gh/ls02/Image/img/image-20220628163858567.png)

#### em和i标签

em和i标签都是用于把字体斜体展示。

**语法：** em（i）内容

**使用案列：**

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>我的标题</title>
</head>
<body>
    <em>斜线标签</em>
    <i>斜线标签</i>
</body>
</html>
```

![image-20220628164104690](https://cdn.jsdelivr.net/gh/ls02/Image/img/image-20220628164104690.png)

#### del和s标签

del和s标签都是用来把字体以删除线的形式展示。

**语法：** del(s) 内容

**使用案列：**

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>我的标题</title>
</head>
<body>
    <del>删除线</del>
    <s>删除线</s>
</body>
</html>
```

![image-20220628164248331](https://cdn.jsdelivr.net/gh/ls02/Image/img/image-20220628164248331.png)

#### ins和u标签

ins和u标签是用于把字体以下划线的形式展示。

**语法：** ins(u) 内容

**使用案列：**

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>我的标题</title>
</head>
<body>
    <ins>下划线</ins>
    <u>下划线</u>
</body>
</html>
```

![image-20220628164426426](https://cdn.jsdelivr.net/gh/ls02/Image/img/image-20220628164426426.png)



### img标签

用于表示图片的标签，如果我们想展示某个图片到网页上那么我就可以用img标签来完成。

+ 属性

  1. src

     用于表示图片的路径，可以是网络路径也可以是本地路径

  2. alt

     如果图片加载失败想表示这本来有图片的效果，那么就使用这个标签

  3. title

     表示图片的信息，鼠标移动到图片上会显示，如果没写这个属性不会显示

  4. width

     表示图片的宽度

  5. height

     表示图片的高度

  6. border

     表示图片的边框大小

  **使用案列：**

  ```html
  <!DOCTYPE html>
  <html lang="en">
  <head>
      <meta charset="UTF-8">
      <meta http-equiv="X-UA-Compatible" content="IE=edge">
      <meta name="viewport" content="width=device-width, initial-scale=1.0">
      <title>我的标题</title>
  </head>
  <body>
      <img src="./img/1.jpg"
      alt="加载失败"
      title="涩图"
      width="500px"
      height="700px"
      border="3px">
  </body>
  </html>
  ```

  

### a标签

a标签是一个超链接标签用来完成网页跳转的功能。

#### 属性

+ href

  要跳转的本地路径或网络路径

+ target

  表示跳转的过程是否要替换，默认不写就是替换当前页面到跳转路径，如果想新建跳转那么使用`target="_blank"`来实现。

**使用案列：**

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>我的标题</title>
</head>
<body>
    <!-- 如果没加target属性那么就会把当前页面替换到跳转页面 -->
    <a href="http://www.baidu.com" target="_blank">这是百度的超链接</a>
</body>
</html>
```

![image-20220629145643300](https://cdn.jsdelivr.net/gh/ls02/Image/img/image-20220629145643300.png)





### 表格标签

#### table标签

table标签表示的是整个表格。

#### 属性

+ width

  表示表格的宽度

+ height

  表示表格的高度

+ border

  表示表格的边框

+ cellspacing

  表示表格之间的间距

+ align

  控制整个表格在网页中的位置

####  tr标签

表示表格中的一行



#### td标签

表示表格中一行的一个单元格

#### th标签

表示表格表头的单元格

#### thead标签

表格的头部区域

#### tbody标签

表示表格的主题区域



**使用案列：**

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>我的标题</title>
</head>
<body>
    <!-- 整个表格 heigh高度 width宽度 border边框 cellspacing表示表格之间边框的间隙 align表示表格的对齐方式-->
    <table heigh="500px"
    width="600px"
    border="1px"
    cellspacing="0px"
    align="center">
        <!-- 第一行 -->
        <tr>
            <!-- 表头 -->
            <th>姓名</th>
            <th>年龄</th>
            <th>性别</th>
        </tr>
        <!-- 第二行 -->
        <tr>
            <!-- 一行中的一个单元格 -->
            <td>张三</td>
            <td>22</td>
            <td>男</td>
        </tr>
        <!-- 第三行 -->
        <tr>
            <!-- 一行中的一个单元格 -->
            <td>李四</td>
            <td>20</td>
            <td>女</td>
        </tr>
    </table>
</body>
</html>
```

![image-20220629151655377](https://cdn.jsdelivr.net/gh/ls02/Image/img/image-20220629151655377.png)

### 列表标签

#### 无需列表

+ ul

  表示整个无序列表

+ li

  列表项一个例表中包含多个列表项

**使用案列：**

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>我的标题</title>
</head>
<body>
    <ul>
        <li>吃饭</li>
        <li>睡觉</li>
    </ul>
</body>
</html>
```

![image-20220629151950601](https://cdn.jsdelivr.net/gh/ls02/Image/img/image-20220629151950601.png)

#### 有序列表

+ ol

  表示整个有序列表

+ li

  列表项一个例表中包含多个列表项

**使用案列：**

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>我的标题</title>
</head>
<body>
    <ol>
        <li>吃饭</li>
        <li>睡觉</li>
    </ol>
</body>
</html>
```

![image-20220629152103473](https://cdn.jsdelivr.net/gh/ls02/Image/img/image-20220629152103473.png)

#### 自定义列表标签

+ dl

  表示整个列表

+ dt

  小标题

+ dd

  标题下面的内容

**使用案列：**

```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>我的标题</title>
</head>
<body>
    <dl>
        <dt>行为</dt>
        <dd>吃饭</dd>
        <dd>睡觉</dd>
    </dl>
</body>
</html>
```

![image-20220629152345608](https://cdn.jsdelivr.net/gh/ls02/Image/img/image-20220629152345608.png)

### 表单标签

#### form标签

`form`标签是用于表示整个表单

**属性**

+ action

  表示用户输入的数据要交给谁，写一个具体的url地址。

  

##### input标签

`input`标签是一个控件标签，具体表示什么控件需要看给的值。

**type属性的相关值**

+ text值

  表示最基本的文本框，单行文本框只能保存一行的内容不能换行。

+ password值

  表示密码文本框，和text一样唯一的区别是输入的内容会被替换

+ radio值

  表示单选框，可以使用name属性来关联多个单选框就能实现N选一的效果，如果需要默认选中可以使用checked来完成。

+ checkbox值

  表示复选框

+ button值

  表示按钮，加上`value`属性可以给按钮里面加上文字，`onclick`表示弹窗。

+ submit值

  表示提交按钮，清空文本框的内容

+ file值

  表示想要选择的文件，可以完成上传文件的效果。

  

  ##### textarea标签

  `textarea`标签是表示一个多文本框

  ##### label标签

  `label`标签用来配合单选框和复选框来使用的，`lavel`存在的意义是让用户更容易的选中，`for`属性表示你要与那个`input`标签关联起来，这时我们还需要一个id。

  

  **使用案列：**

  ```html
  <!DOCTYPE html>
  <html lang="en">
  <head>
      <meta charset="UTF-8">
      <meta http-equiv="X-UA-Compatible" content="IE=edge">
      <meta name="viewport" content="width=device-width, initial-scale=1.0">
      <title>我的标题</title>
  </head>
  <body>
      <!-- form标签表示整个表单 action属性表示数据要交给谁处理，如果没有后端我们可以不写-->
      <form action="">
          <!-- text值表示单行文本框 -->
          <span>用户名：</span><input type="text"><br>
          <span>密码：</span><input type="password"><br>
          <!-- radio表示单选框 name表示关联 checked表示默认选中 label表示点击文字也能进行选中提升用户体验 -->
          <label><input type="radio" name="sex">男</label>
          <label><input type="radio" name="sex" checked="checked">女</label><br>
          <span><b>备注：</b></span>
          <!-- textarea表示多文本框 rows表示宽度 clos表示高度 -->
          <textarea rows="10" clos="30"></textarea><br>
          <!-- file值表示选择要上传的文件 -->
          <input type="file"><br>
          <!-- button值表示按钮 value表示里面的文职 onclick表示弹窗 alert表示一个函数 -->
          <input type="button" value="提交" onclick="alert('提交成功')">
          <!-- submit值表示清除按钮 value表示里面的文字 -->
          <input type="submit" value="清除"><br>
  
      </form>
  </body>
  </html>
  ```

  ![image-20220629161154134](https://cdn.jsdelivr.net/gh/ls02/Image/img/image-20220629161154134.png)

  

### 下拉框

#### select标签

select是标识下拉框本身，里面的选项是一个一个的option标签。

#### option标签

用于搭配select使用，selected="selected"控制默认选项。

**使用案列：**

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>我的标题</title>
</head>
<body>
    <select>
        <option>2000</option>
        <option>2001</option>
        <option>2002</option>
        <option>2003</option>
        <option>2004</option>
        <option>2005</option>
        <option>2006</option>
        <option>2007</option>
        <option>2008</option>
        <option>2009</option>
        <!-- selected表示默认选择 -->
        <option selected="selected">-- 请选择日期 --</option>
    </select>
</body>
</html>
```

![image-20220629161810819](https://cdn.jsdelivr.net/gh/ls02/Image/img/image-20220629161810819.png)

### 无语义标签

#### div标签

div是一个大盒子独占一行

#### span标签

span是小盒子不独占一行



**使用案列：**

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>我的标题</title>
</head>
<body>
    <div>睡觉</div>
    <div>睡觉</div>
    <span>吃饭</span>
    <span>吃饭</span>
</body>
</html>
```

![image-20220629162030590](https://cdn.jsdelivr.net/gh/ls02/Image/img/image-20220629162030590.png)

## HTML特殊字符

有些特殊的字符在html文件中是不能直接表示的，例如：

**空格：** `&nbsp;`

**小于号：** `&lt;`

**大于号：**`&gt;`

**按位与：** `&amp;`





