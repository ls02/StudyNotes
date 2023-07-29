[TOC]

# CSS是什么？

CSS能够对网页中的元素颜色样式等等进行精准控制和修改，能够做到页面的样式和结构分离。

## 基本语法规则



**语法：** 选择器 {属性};

**使用案列：**

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>我的标题</title>
    <style>
        p {
            color: red;
        }
    </style>
</head>
<body>
    <p>我是红色</p>
</body>
</html>
```

![image-20220630224426912](https://cdn.jsdelivr.net/gh/ls02/Image/img/image-20220630224426912.png)

## 引入方式

### 内部样式表

内部样式就是嵌入到html内部。

**优点：** 这样能够让样式和页面结构分离。

**缺点：** 分离的还不够彻底，尤其是CSS内容多的时候

**使用案列：**

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>我的标题</title>
    <style>
        p {
            color: red;
        }
    </style>
</head>
<body>
    <p>我是红色</p>
</body>
</html>
```

### 行内样式表

通过表标签的style的属性来设置样式，不需要写选择器了，只针对当前行有效。
最大的问题在于不饿能写太复杂的样式，行内样式的优先级比内部样式更高。
如果两边同时尝试设置不同的属性值，行内样式覆盖内部样式。

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
    <!-- 行内样式表，如果需要多个属性可以空格隔开 -->
    <p style="color:red">我是红色</p>
</body>
</html>
```

![image-20220630224739828](https://cdn.jsdelivr.net/gh/ls02/Image/img/image-20220630224739828.png)

### 外部样式表

1. 创建一个CSS文件
2. 使用`link`标签引入CSS

```html
<link rel="stylesheet" href="CSS文件路径">
```

创建demo.html

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>我的标题</title>
    <link href="./Demo1.css" rel="stylesheet">
</head>
<body>
    <div>我是一个红色</div>
    <div>我是一个红色</div>
    <div>我是一个红色</div>
</html>
```

创建Test.css

```css
div {
    color: red;
}
```

![image-20220630231231011](https://cdn.jsdelivr.net/gh/ls02/Image/img/image-20220630231231011.png)

## 选择器种类

### 基础选择器

1. 标签选择器

   用于选中一类标签，例如选中p标签就会让当前页面所有的p标签都被选中。

   ```html
   <!DOCTYPE html>
   <html lang="en">
   <head>
       <meta charset="UTF-8">
       <meta http-equiv="X-UA-Compatible" content="IE=edge">
       <meta name="viewport" content="width=device-width, initial-scale=1.0">
       <title>我的标题</title>
       <style>
           p {
               color: red;
           }
       </style>
   </head>
   <body>
       <p>我是红色</p>
   </body>
   </html>
   ```

2. 类选择器

   有i时候我们只需要修改一个元素，其它的元素不修改，那么我们可以在CSS中创建“类”通过这个类来手动指定那些元素要遵守修改样式。

   类名不能乱起，包含数字字母，不能是数字开头也不能是中文或标签。

   **使用案列：**

   ```html
   <!DOCTYPE html>
   <html lang="en">
   <head>
       <meta charset="UTF-8">
       <meta http-equiv="X-UA-Compatible" content="IE=edge">
       <meta name="viewport" content="width=device-width, initial-scale=1.0">
       <title>我的标题</title>
       <!-- 类选择器开头必须跟. -->
       <style>
           .grep {
               color:red;
           }
   
           .size{
               font-size: 30px;
           }
       </style>
   </head>
   <body>
       <!-- 类选择器如果想要多个用空格隔开表示 -->
       <div class="grep size">我是一个红色</div>
       <div class="grep">我是一个红色</div>
       <div>我是一个红色</div>
   </html>
   ```

   ![image-20220701001345983](C:/Users/86176/AppData/Roaming/Typora/typora-user-images/image-20220701001345983.png)

3. id选择器

   id选择器在创建的时候要#开头，引用的时候id属性中不需要#。

   ```html
   <!DOCTYPE html>
   <html lang="en">
   <head>
       <meta charset="UTF-8">
       <meta http-equiv="X-UA-Compatible" content="IE=edge">
       <meta name="viewport" content="width=device-width, initial-scale=1.0">
       <title>我的标题</title>
       <!-- id选择器必须#开头 -->
       <style>
           #grep {
               color:red;
           }
   
           #size{
               font-size: 30px;
           }
       </style>
   </head>
   <body>
       <!-- id选择器只能有一个选择器 -->
       <div id="grep">我是红色</div>
       <div id="size">我是红色</div>
       <div>我是一个红色</div>
   </html>
   ```

   ![image-20220701001758671](C:/Users/86176/AppData/Roaming/Typora/typora-user-images/image-20220701001758671.png)

4. 通配符选择器

   选中页面所有元素，使用的很少，存在的意义往往是消除浏览器的默认样式。

   ```html
   <!DOCTYPE html>
   <html lang="en">
   <head>
       <meta charset="UTF-8">
       <meta http-equiv="X-UA-Compatible" content="IE=edge">
       <meta name="viewport" content="width=device-width, initial-scale=1.0">
       <title>我的标题</title>
       <!-- id选择器必须#开头 -->
       <style>
           /* 所有字体默认颜色都变成红色 */
           * {
               color:red;
           }
       </style>
   </head>
   <body>
       <!-- 如果有其它选择器会优先使用，默认都是红色 -->
       <div style="color:yellow">我是一个红色</div>
       <div>我是一个红色</div>
       <div>我是一个红色</div>
       <div>我是一个红色</div>
   </html>
   ```

   ![image-20220701002056480](https://cdn.jsdelivr.net/gh/ls02/Image/img/202211222238813.png)

### 复合选择器

#### 后代选择器

用于对某个元素的子标签进行CSS属性设置。

**使用案列：**

```html
<html lan="en">
    <head>
        <meta charset="UTF-8">
        <meta http-equiv="X-UA-Compatible" content="IE=edge">
        <meta name="viewport" content="width=device-width, initial-scale=1.0">
        <title>我的标题</title>
        <style>
            ul li{
                color:rgb(15, 113, 198);
            }
        </style>
    </head>
    <body>
        <ul>
            <li>你好</li>
            <li>你好</li>
            <li>你好</li>
            <li>你好</li>
        </ul>
        <ol>
            <li>你好</li>
        </ol>
    </body>
</html>
```

![image-20220714223636683](https://cdn.jsdelivr.net/gh/ls02/Image/img/image-20220714223636683.png)

#### 子类选择器

子类选择器是只能对子类的标签生效孙子标签无法生效。

**使用案列：**

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>

    <style>
        .list li{
            color:brown;
        }
    </style>
</head>
<body>
    <ul class="list">
        <li>你好</li>
        <li>你好</li>
        <li>你好</li>
    </ul>
</body>
</html>
```

![image-20220714224750674](https://cdn.jsdelivr.net/gh/ls02/Image/img/image-20220714224750674.png)

#### 并集选择器

在有些时候我们需要对多组标签进行同样的样式调整的时候，不想敲一个一个的重复代码想复用那么我们可以使用并集选择器。

**使用案列：**

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>

    <style>
        .list li,
        div,
        span{
            color:brown;
            font-size: 50px;
        }
    </style>
</head>
<body>
    <ul class="list">
        <li>你好</li>
        <li>你好</li>
        <li>你好</li>
    </ul>

    <div class="a">睡觉</div>
    <span>吃饭</span>
</body>
</html>
```

![image-20220714225216884](https://cdn.jsdelivr.net/gh/ls02/Image/img/image-20220714225216884.png)

#### 伪类选择器

链接伪类选择器和a标签搭配使用，可以根据a标签的状态来选择。

a标签一般有几种状态分别是：

1. 未被访问过

   `:link`

2. 已经被修改过

   `:visited`

3. 鼠标悬停

   `:hover`

4. 活动链接（点下去之后没松手）

   `:active`

**注意：**带`:`的就是伪类选择器。

**使用案列：**

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>

    <style>
        .T:link{
            color:red;
        }

        .T:visited{
            color:aqua;
        }

        .T:hover{
            color:bisque;
        }

        .T:active{
            color:rgb(37, 205, 15);
        }
    </style>
</head>
<body>
    <a href="https://baidu.com" class="T">我是一个百度链接</a>
</body>
</html>
```

### 属性

#### 字体属性

+ 字体类型

  

  ```html
  <style>
      .list {
          /*部分编译器是支持中文的。*/
          font-family: `微软雅黑`;
      }
  </style>
  ```

  

+ 字体大小

  ```html
  <style>
      .list {
          font-size: 50px;
      }
  </style>
  ```

+ 字体粗细

  ```html
  <style>
      .list {
          font-weight: 500px;
      }
  </style>
  ```

+ 字体样式

  ```html
  <style>
      .list {
          /*设置字体倾斜，一般很少把正常的字给斜了，都是把斜的给弄正常。*/
  		font-style: italic;/*设置倾斜*/
  		font-style: normal;/*取消倾斜*/
      }
  </style>
  ```

+ 字体颜色

  ```html
  <style>
      .list {
  		color: rgb(0,0,.255);
      }
  </style>
  ```

+ 字体对齐

  ```html
  <style>
      .list {
          text-align: left;
          text-align: right;/*dada*/
          text-align: center;
          text-align: none;/*正常*/
          text-align: underline;/*下划线*/
          text-align: overline;/*上划线*/
          text-align: line-through;/*删除线*/
          text-indent: 2em;/*缩进 em是一个单位是以当前字体为基准的。*/
      }
  </style>
  ```

  
