## 一、CSS的显示模式

### 1、什么是元素的显示模式

#### 1.1、定义

元素显示模式就是元素（标签）以什么方式进行显示，比如自己占一行，比如一行可以放多个`<span>`。

#### 1.2、作用

网页的标签非常多，在不同地方会用到不同类型的标签，了解他们的特点可以更好的布局我们的网页。

### 2、元素显示模式的分类

#### 2.1、块元素

+ **常见的块元素**：

  ```css
  div、h1-h6、 ul、 ol、 li、 dl、 dt、 dd、 hr、 p、 form
  ```

  `<div>` 标签是最典型的块元素。

+ **块级元素的特点**：

  - 比较霸道，自己独占一行。
  - 高度，宽度、外边距以及内边距都可以控制。
  - 宽度默认自动填满父级的宽度，也可以人为设置宽度，并且这个宽度可以大于或小于父级宽度。
  - 是一个容器及盒子，里面可以放行内或者块级元素。

+ **注意：**

  文字类的元素内不能放块级元素

  ```css
  <p> 标签主要用于存放文字，因此 <p> 里面不能放块级元素，特别是不能放<div> 
  同理， <h1>~<h6>等都是文字类块级标签，里面也不能放其他块级元素
  ```

#### 2.2、行内元素

+ **常见的行内元素：**

  ```css
  <a>、<strong>、<b>、<em>、<i>、(删除线)<del>、<s>、(下划线)<ins>、<u>、<span>
  ```

  `<span>` 标签是最典型的行内元素。有的地方也将行内元素称为内联元素。

+ **行内元素的特点：**

  - 相邻行内元素在一行上，一行可以显示多个，直到一行排列不下，才会换行。
  - 高、宽直接设置是无效的。
  - 默认宽度就是它本身内容的宽度。
  - 行内元素只能容纳文本或其他行内元素。

+ **注意：**

  链接里面不能再放链接 特殊情况链接 `<a>`里面可以放块级元素，但是给 `<a>`转换一下块级模式最安全

#### 2.3、行内块元素

+ **常见的行内块标签**：

  ```css
  <img />、<input />、<td>
  ```

   它们同时具有块元素和行内元素的特点。有些资料称它们为行内块元素。

+ **行内块元素的特点**：

  - 和相邻行内元素（行内块）在一行上，但是他们之间会**有空白缝隙**。
  - 一行可以显示多个（行内元素特点）。
  - 默认宽度就是它本身内容的宽度（行内元素特点）。
  - 高度，行高、外边距以及内边距都可以控制（块级元素特点）。

#### 2.4、元素显示模式总结

| 元素模式   | 元素排列               | 设置样式               | 默认高度       | 包含                     |
| ---------- | ---------------------- | ---------------------- | -------------- | ------------------------ |
| 块级元素   | 一行只能放一个块级元素 | 可以设置宽度高度       | 容器的100%     | 容器级可以包含任何标签   |
| 行内元素   | 一行可以放多个行内元素 | 不可以直接设置宽度高度 | 本身内容的宽度 | 容纳文本或者其他行内元素 |
| 行内块元素 | 一行放多个行内块元素   | 可以设置宽度高度       | 本身内容的宽度 |                          |

学习元素显示模式的主要目的就是分清它们各自的特点，当我们网页布局的时候，在合适的地方用合适的标签元素。

### 3、元素显示模式的转换

#### 3.1、概念

一个模式的元素需要另外一种模式的特性 比如想要增加链接 `<a>` 的触发范围。

#### 3.2、转换方式

- 转换为块元素：    display:block;
- 转换为行内元素：display:inline;
- 转换为行内块：    display: inline-block;
- 隐藏元素：            display：none;

## 四、盒子模型

### 1、盒子模型是什么

> 盒模型是css布局的基石，是用来设置元素之间的**位置关系**；

网页布局的核心本质： 就是利用 CSS 摆盒子

网页布局过程：

1. 先准备好相关的网页元素，网页元素基本都是盒子 Box 。
2. 利用 CSS 设置好盒子样式，然后摆放到相应位置。
3. 往盒子里面装内容

### 2、盒子模型的组成

**盒子模型**：是css布局的基石，它规定了网页元素如何显示以及元素间相互关系。css定义所有的元素都可以拥有像盒子一样的外形和平面空间。即都包含内容区、补白（填充）、边框、边界(外边距)这就是盒模型。

CSS 盒子模型本质上是一个盒子，封装周围的 HTML 元素，它包括：**宽度**、**高度**、**边框**、**外边距**、**内边距**、和 **实际内容**



![04](.\img\盒模型.jpg)

一个盒子模型有以下四部分组成：

- **Margin(外边距)** 清除边框外的区域，外边距是透明的。
- **Border(边框)** 围绕在内边距和内容外的边框。
- **Padding(内边距)** 清除内容周围的区域，内边距是透明的。
- **Content(内容)** 盒子的内容，显示文本和图像。

**注意：**

> 一个盒子实际的大小 = 内容的大小 + padding + border宽度。

外边距不计入盒子的大小。



### 3、盒子模型的内容

#### 3.1、设置内容区域的宽高

内容区（content）是盒子模型的中心，它呈现了盒子的主要信息内容。

| CSS 属性名    | 功能          | 属性值  |
| ---------- | ----------- | ---- |
| width      | 设置内容区域宽度    | 长度   |
| max-width  | 设置内容区域的最大宽度 | 长度   |
| min-width  | 设置内容区域的最小宽度 | 长度   |
| height     | 设置内容区域的高度   | 长度   |
| max-height | 设置内容区域的最大高度 | 长度   |
| min-height | 设置内容区域的最小高度 | 长度   |

> **注意：**
>
> max-width / min-width 一般不与 width 一起使用。
>
> max-height / min-height 一般不与 height 一起使用。 



#### 3.2、块级元素默认内容宽度

> 块级元素的默认**总宽度** = 父元素内容区域的宽度 - 该块级元素的左右外边距 
>
> 块级元素**内容区域**的默认宽度 =  父元素内容区域的宽度 - 该块级元素的左右外边距 - 该块级元素的左右边框宽度 - 该块级元素的左右内边距。



### 4、盒子模型的内边距

#### 4.1、基本使用

+ 概念:内边距 padding 也叫补白或填充，是**边框和内容之间**的空间

> 填充区 (padding) :显示在内容区和边框区之间的空白
>     1、作用：设置**父子元素之间**的位置关系；
>
> ​    2、说明：
> ​        -> 是显示在盒子内部，在边框和内容区之间的空白
>
> ​        -> padding对**背景的位置不产生影响**(背景图的位置要靠背景的位置属性来设置)
>
> ​        -> padding区会显示背景色和背景图
>
> ​        -> padding区的大小会把元素原本的宽高撑大
>
> ​        -> 如果想保证盒子的原本显示的位置大小不变，需要在原本的宽高上减去相应的padding值



+ 语法：

  + 复合写法(**顺时针的顺序**)

  | 值的个数                          | 描述                                       |
  | ----------------------------- | ---------------------------------------- |
  | padding: 10px;                | 1个值，表示四个方向内边距都是 10 px。                   |
  | padding: 10px 20px;           | 2个值，表示上下内边距是10px，左右内边距是20px;             |
  | padding: 10px 20px 30px;      | 3个值，表示上内边距10px，左右内边距20px，下内边距30px        |
  | padding: 10px 20px 30px 40px; | 4个值，表示上内边距10px，右内边距是20px，下内边距30px，左内边距40px。上 右 下 左 |

  + 分写写法

  | CSS 属性名        | 功能   |
  | -------------- | ---- |
  | padding-top    | 上内边距 |
  | padding-right  | 右内边距 |
  | padding-bottom | 下内边距 |
  | padding-left   | 左内边距 |

> **padding 值的规则：**
>
> padding 的值不能是负数，也不能是 `auto`



#### 4.2、行内元素设置内边距

> 行内元素可以完美地设置左右内边距，上下内边距不能完美设置。
>
> 块级元素和行内块元素四个方向内边距都可以完美设置。
>
> 注：行内元素设置上下内边距==不能==改变元素上下的位置，只能撑大元素的大小，
>
> ​		设置左右内边距可以改变元素左右的距离



### 5、盒子模型的边框

#### 5.1、基本使用

+ 概念：border可以设置元素的边框。边框有三部分组成：边框宽度(粗细)、边框样式、边框颜色；
+ **作用：**可以用做网页上的一些装饰性的线条，还有分割线

> **说明**：
>
> 1.border会把元素原本的宽高**撑大**，如果想保留原本的大小不变，需要减去相应的border值
>
> 2.边框默认三像素宽，颜色默认黑色，线性默认none.所以写边框时一定要写线型！

+ 语法：

  + 复合写法

    ```css
            宽度  样式   颜色
    border: 1px  solid   red;
    ```

  + 分写写法

  ```css
  border : border-width || border-style || border-color;
  ```

  | 属性           | 描述            |
  | ------------ | ------------- |
  | border-width | 定义边框的粗细，单位是px |
  | border-style | 边框的样式         |
  | border-color | 边框的颜色         |

  > 外边距border-width的取值，谷歌浏览器默认为3px

   + 边框样式border-style可以设置如下值：
     + none：    边框没有样式，此时看不到边框（默认值）
     + solid：     边框为单实线(最为常用的)
     + dashed：边框为虚线
     + dotted： 边框为点线
     + double： 双实线

  > 边框颜色border-color：默认的是元素本身的文本的颜色。没有文本时，默认黑色


#### 5.2、分写的多种组合

+ border-width
  + border-top-width：       10px；
  + border-right-width：     10px；
  + border-bottom-width：10px；
  + border-left-width：        10px；
  + border-width:top/right/bottom/left;设置一个值
  + border-width:top/bottom left/right;设置两个值
  + border-width:top right/left bottom;设置三个值
  + border-width:top right bottom left;设置四个值
+ border-style
  + border-top-style：         solid；
  + border-right-style：       solid；
  + border-bottom-style：  solid；
  + border-left-style：          solid；
  + border-style:top/right/bottom/left;设置一个值
  + border-style:top/bottom left/right;设置两个值
  + border-style:top right/left bottom;设置三个值
  + border-style:top right bottom left;设置四个值
+ border-color
  + border-top-color：         red；
  + border-right-color：       red；
  + border-bottom-color：  red；
  + border-left-color：          red；
  + border-color:top/right/bottom/left;设置一个值
  + border-color:top/bottom left/right;设置两个值
  + border-color:top right/left bottom;设置三个值
  + border-color:top right bottom left;设置四个值

#### 5.3、 边框写三角形

```css
.box {
    width: 0;
    height: 0;
    border: 20px solid  transparent;
    border-top-color: red;
    border-left-color: red;
    margin: 0 auto;
}
```

<img src="img/三角形.png" alt="盒子模型" style="zoom:60%;" />

<img src="img/梯形.png" alt="梯形" style="zoom:60%;" />

**写法说明：**

> 1. 写个盒子，宽高设置为0     (设置了宽度变成梯形！)
> 2. 四个边框设置宽度和颜色
> 3. 看情况，需要留哪个



### 6、盒子模型的外边距

margin 属性用于设置外边距，即控制同辈元素之间的距离。

> **说明：**margin不会把元素的原本大小撑大，但是会增加元素的显示位置；
>
> **作用：**设置==同辈==元素的位置关系；(padding设置==父子==元素的位置)



#### 6.1、基本使用

| 属性                           | 描述                |
| ---------------------------- | ----------------- |
| margin-left                  | 左外边距              |
| margin-right                 | 右外边距              |
| margin-top                   | 上外边距              |
| margin-bottom                | 下外边距              |
| margin:10px;                 | 一个值  上下左右         |
| margin:10px 20px;            | 两个值   上下   左右     |
| margin:10px 20px 30px;       | 三个值  上  左右  下     |
| margin: 10px 20px 30px 40px; | 四个值 上  右    下   左 |

**margin 属性值的规则：**

1. 复合属性可以设置 1 ~ 4 个值，规则同 padding 相同
2. 外边距的值**可以是负值**。
3. 外边距的值也**可以设置为 auto**。如果left和right设置为auto，则**块元素**居中。

> **使用外边距让块级水平居中**
>
> **条件**
>
> + ==**盒子必须指定了宽度**==（width）
> + 盒子左右的外边距都设置为 auto 

**写法**

```css
margin-left: auto;   margin-right: auto;
margin: auto;
margin: 0 auto;
```

> **注意：**以上方法是让块级元素水平居中，行内元素或者行内块元素水平居中给其父元素添加 text-align:center 即可。



+ 父子关系

  元素设置外边距，如果与父元素，距离的是父元素内容的边界。

  
  
+ 兄弟关系

  元素设置外边距，如果与兄弟元素， 上和左外边距影响自己的位置，下和右外边距影响后面兄弟元素的位置。

  + 纵向关系

    
    
  + 横向关系
  
    
  
+ 行内元素设置外边距

  对于块级元素和行内块元素，可以完美地设置四个方向的外边距； **对于行内元素，左右外边距可以完美设置，上下外边距设置无效**。**! ! !**

  
  


> 

#### 6.2、margin的bug

##### 6.2.1 上边距塌陷

定义：在一个元素里，第一个子元素的 margin-top 会塌陷给父级；最后一个子元素的 margin-bottom 会塌陷给父级。(父元素和子元素之间)

**解决margin塌陷**

- 方案一： 给父元素设置不为 0 的内边距。
- 方案二： 给父元素设置宽度不为 0 的边框。
- 方案三：给父元素设置 css 样式 `overflow:hidden`。(推荐)
- 方案四：给父元素或者子元素添加float:left;



##### 6.2.2、margin合并

当上下相邻的两个块元素（兄弟关系）相遇时，如果上面的元素有下外边距 margin-bottom，下面的元素有上外边距 margin-top ，则他们之间的垂直间距不是 margin-bottom 与 margin-top 之和。取两个值中的较大者这种现象被称为相邻块元素垂直外边距的合并。

![05](.\img\05.jpg)



> **解决方案：** 
>
> -> 尽量只给一个盒子添加 margin 值。
>
> -> 给后面的元素添加浮动；（不推荐）
>
> -> 一般不需要解决

### 7、盒子模型相关

#### 7.1、水平方向布局

默认情况下块级元素各组成部分的横向尺寸始终等于容纳块（离的最近的祖辈块状元素）的宽度。容纳块的宽度=子margin-left + 子border-left + 子padding-left + 子width + 子元素的padding-right + 子元素的border-right + 子元素的margin-right

七个属性中，只有子元素的width、子元素的margin-left和子元素的margin-right可以设置为auto。其他的属性的值只能设置为具体的值或默认值（默认值为0）。

- 情况一：width、margin-left、margin-right其中两个设置为具体指，一个为auto的时候。

  在这种情况下设置的auto的值必须满足上面的容纳块的公式，你可以理解为auto为补全总和所缺少的尺寸。

  ```html
  <!DOCTYPE html>
  <html>
      <head>
          <style>
              html,body{
                  margin:0;
              }
              #f{
                  width:300px;
                  height:300px;
                  border:1px solid green;
              }
              #z{
                  width:auto;
                  height:100px;
                  margin-left:10px;
                  margin-right:20px;
                  border:1px solid blue;
              }
          </style>
      </head>

      <body>
         <div id="f">
             <div id="z"></div>
         </div>

      </body>

  </html>
  ```

- 情况二：width、margin-left、margin-right其中两个设置为auto的情况

  - 如果是margin-left和margin-right设置为auto，那么剩下的空间将会被他们两个平分造成了元素居中的结果。

    ```html
    <!DOCTYPE html>
    <html>

        <head>
            <style>
                html,body{
                    margin:0;
                }
                #f{
                    width:300px;
                    height:300px;
                    border:1px solid green;
                }
                #z{
                    width:200px;
                    height:100px;
                    margin-left:auto;
                    margin-right:auto;
                    border:1px solid blue;
                }
            </style>
        </head>

        <body>
           <div id="f">
               <div id="z"></div>
           </div>

        </body>

    </html>
    ```

  - 宽度和左、右任意一边设置为auto时，这个时候设置为auto那边运算结果为0，width被设置为填满容纳块所需要的值。

    ```html
    <!DOCTYPE html>
    <html>
        <head>
            <style>
                html,body{
                    margin:0;
                }
                #f{
                    width:300px;
                    height:300px;
                    border:1px solid green;
                }
                #z{
                    width:auto;
                    height:100px;
                    margin-left:10px;
                    margin-right:auto;
                    border:1px solid blue;
                }
            </style>
        </head>

        <body>
            <div id="f">
            <div id="z"></div>
            </div>
        </body>

    </html>
    ```

- 情况三：width、marign-left、margin-right三个设置为auto时

  这个时候margin-left和margin-right将会设置为0，width将会要多宽有多宽。

  ```html
  <!DOCTYPE html>
  <html>

  <head>
      <style>
          html,body{
              margin:0;
          }
          #f{
              width:300px;
              height:300px;
              border:1px solid green;
          }
          #z{
              width:auto;
              height:100px;
              margin-left:auto;
              margin-right:auto;
              border:1px solid blue;
          }
      </style>
  </head>

  <body>
     <div id="f">
         <div id="z"></div>
     </div>

  </body>

  </html>
  ```

- 情况四：width、margin-left、margin-right都设置具体的值。这种情况叫过度约束。

#### 7.2、内容溢出

| CSS 属性名    | 功能             | 属性值                                      |
| ---------- | -------------- | ---------------------------------------- |
| overflow   | 溢出内容的处理方式      | visible：显示，默认值<br>hidden：隐藏<br>scroll：显示滚动条，不论内容是否溢出<br>auto：自动显示滚动条，内容不溢出不显示 |
| overflow-x | 水平方向溢出内容的处理方式  | 同 overflow                               |
| overflow-y | 垂直方向溢出内容给的处理方式 | 同 overflow                               |

> **注意：**
>
> 1. 如果通过 overflow-x 或者 overflow-y 只设置一个方向上内容溢出处理方式，另一个会调整为 auto （不论是否设置），不好使也不常用。
> 2. overflow 常用的值是 hidden 和 auto，处了能够处理溢出内容的显示方式，还可以解决很多疑难杂症。

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Document</title>
    <style>
        .box {
            border: 2px solid red;
            padding: 20px;
            width: 400px;
            height: 300px;

            /* 设置内容溢出的处理方式 */
            /* overflow: visible; */
            /* 隐藏 */
            /* overflow: hidden; */
            /* 显示滚动条 不论内容是否溢出 */
            /* overflow: scroll; */
            /* 自动显示滚动条 */
            /* overflow: auto; */


            overflow-x: visible;
            overflow-y: hidden;
        }
        .box p {
            width: 2000px;
            background-color: green;
        }
    </style>
</head>
<body>
    <div class="box">
        Lorem ipsum dolor, sit amet consectetur adipisicing elit. Autem praesentium sed nam in non, eius fuga consequuntur iure et dolores minus. Accusantium dicta, illo quibusdam aspernatur magnam explicabo rem est!
        Lorem ipsum dolor, sit amet consectetur adipisicing elit. Autem praesentium sed nam in non, eius fuga consequuntur iure et dolores minus. Accusantium dicta, illo quibusdam aspernatur magnam explicabo rem est!
        
        <p>Lorem ipsum dolor sit amet consectetur, adipisicing elit. A dolorem assumenda nulla incidunt quibusdam sit? Voluptates aliquam, cum doloribus delectus impedit aspernatur odio fugiat dicta, architecto quas similique neque ea.</p>
        Lorem ipsum dolor, sit amet consectetur adipisicing elit. Autem praesentium sed nam in non, eius fuga consequuntur iure et dolores minus. Accusantium dicta, illo quibusdam aspernatur magnam explicabo rem est!
        Lorem ipsum dolor, sit amet consectetur adipisicing elit. Autem praesentium sed nam in non, eius fuga consequuntur iure et dolores minus. Accusantium dicta, illo quibusdam aspernatur magnam explicabo rem est!
        Lorem ipsum dolor, sit amet consectetur adipisicing elit. Autem praesentium sed nam in non, eius fuga consequuntur iure et dolores minus. Accusantium dicta, illo quibusdam aspernatur magnam explicabo rem est!
    </div>
    <hr>
</body>
</html>
```

#### 7.3、垂直方向布局

块级元素的内容决定元素的默认高度：

- 如果块级元素设定具体的高度并且指定的高度大于显示内容所需要的高度，多出来的高度看起来像是内边距。
- 如果块级元素设定具体的高度并且指定的高度小于显示内容所需要的高度，具体的行为将取决于overflow属性的值。

`容纳快的高度=子margin-top+子border-top+子padding-top+子height+子padding-bottom+子border-bottom+子margin-bottom`

高度、上、下外边距可以设置为auto。其他的必须为具体的值。

- margin-top和margin-bottom设置为auto，这个时候自动计算为0。
- margin-top、margin-bottom设置为具体的值，height的值为auto时高度不会被自动拉开（会为0）。
- 某一边和height设置为auto，外边距为auto的那个会被设置为0。
- 上、下和height都设置为具体的值，设置的多少就是多少。
- 都设置为auto时都会设置为0。

#### 7.4、隐藏元素

① 方案一： visibility 属性

visibility 属性默认值是 `show`，如果设置为 `hidden`，元素会隐藏。

元素看不见了，还占有原来的位置（元素的大小依然保持）。

② 方案二： display 属性

设置 `display:none`，就可以让元素隐藏。

彻底地隐藏，不但看不见也不占用任何位置，没有大小宽高。

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Document</title>
    <style>
        .box {
            width: 400px;
            height:300px;
            border: 2px solid red;
            background-color:#ccc;
        }

        .box1 {
            /* 隐藏 */
            /* visibility: hidden; */

            /* 隐藏 */
            display: none;
        }
    </style>
</head>
<body>
    <div class="box box1">box1</div>
    <div class="box box2">box2</div>
</body>
</html>
```

#### 7.5、样式继承

有些样式会继承，一个元素如果本身设置了某个样式就使用本身设置的样式；但是如果本身没有设置某个样式，会从父元素开始一级一级继承（优先继承离得近的祖先元素）。

① 会继承 css 属性

```
字体属性、文本属性（除了vertical-align）、文字颜色、鼠标样式
```

② 不会继承的 css 属性

```
边框、背景、内边距、外边距、宽高、溢出方式 等
```

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Document</title>
    <style>
         html {
            font-size: 20px;
            font-weight: 700;
            color: blue;
            background-color: #ccc;
            cursor: pointer;
        }
        .wrapper {
            width: 600px;
            height: 400px;
            padding: 20px;
            border: 2px solid red;
            color: red;
        }
        .box {
            margin-top: 100px;
            border: 2px solid green;
            padding: 20px;
            height: 200px;
        }
        p {
            border: 2px solid orange;
            /* padding: 20px; */
            font-size: 40px;
            
        }
    </style>
</head>
<body>
    <div class="wrapper">
        <div class="box">
            <p>
                Lorem ipsum dolor sit amet consectetur adipisicing elit. Maiores dolores natus accusamus minus fuga illum dolore illo quo placeat sit autem, officiis provident nisi aut laborum veniam quas nesciunt id.
            </p>
        </div>
    </div>
</body>
</html>
```

#### 7.6、默认样式

有些元素有默认的样式：

```
超链接默认: 下划线、字体颜色、鼠标小手
标题 h1~h6： 加粗 字体大小、上下外边距
段落 p：上下外边距
ul、ol：左内边距
body： 8px外边距（4个方向）
```

**元素的默认样式优先级大于继承的样式**， 如果要重置元素的默认样式，选择器一定要直接选择器到元素。

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Document</title>
    <style>
        .box {
            width: 600px;
            height: 200px;
            padding: 20px;
            border: 2px solid red;

            color: red;
            font-weight: bold;
            text-decoration: none;

        }

        a {
            text-decoration: none;
            color: #333;
            border: 1px solid #ccc;
        }

        .box a {
            display: inline;
        }

    </style>
</head>
<body>
    
    <div class="box">
        <a href="#" style="overflow:hidden">我是超链接</a>
        <span>我是普通文字</span>

        <h1>朦朦你好啊</h1>
    </div>

</body>
</html>
```

#### 7.7、行内元素或行内块布局

+ 文本属性作用于行内元素和行内块元素

  行内元素和行内块元素可以被父元素当做文本处理，给父元素设置文本属性，会被里面的行内或行内块元素起作用

##### 让行内块元素或行内元素水平居中（在父元素中）

  ```css
  给它的父元素设置 text-align: center;
  ```



  ##### 让行内元素或行内块元素垂直居中（在父元素中）

  ```css
  给它的父元素设置 line-height 跟父元素高度一致。
  行内块元素本身还要再设置一 vertical-align: middle。
  ```



  ##### 行内元素或行内块元素之间的空白问题

  行内块元素以及行内元素会被当做文本去处理，由于换行或者沿文字基线对齐会产生一些空白。

==之间的空白==

  **产生的原因：**

  敲代码的时候，为了代码具有良好的可读性，写一个标签就换个行。 行内块元素或行内元素之间的换行会被浏览器解析为一个空白字符。

> **解决方案：**
>
> 方案一： 去掉行内或行内块元素之间的换行和空格。（不推荐）
>
> 方案二： 在父元素中设置 `font-size:0`；如果行内块或行内元素内有文字再单独给元素设置字体大小。（推荐）

 ==底部的空白==（图片的幽灵空白）

  **产生原因：**

  行内块元素或行内元素与文本的基线对齐，**幽灵空白**就是基线与底线之间的距离。

>   **解决方案：**
>
> **方案一：** 给行内元素或行内块元素设置`vertical` 的值不为 `baseline` 即可，设置为 `middel`、`bottom`、`top` 都可以。
>
> **方案二：** 给父元素设置 `font-size: 0`。如果该行内元素或行内块元素内部还有文本内容需单独设置`font-size`。
>
> **方案三：** 主要针对图片，设置图片为 `display:block`。



  

