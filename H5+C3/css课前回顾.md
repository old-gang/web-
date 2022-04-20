## day06

```css
css三大特性：
    优先级：
        样式表的优先级：
            内部样式表优先级别最高
            外部和外部样式表的优先级跟位置有关，就近原则；
        选择器优先级：
            选择器自带权重，权重大的优先级高；
            权重相等，就近原则
        属性的优先级：
            选择器权重相等时，根据就近原则，后面的会把前面的覆
盖
            选择器不相等时，根据权重大小显示；
    
	层叠性：
        层叠是覆盖的意思
        当发生冲突时，优先级高的会把优先级低的层叠掉
        当没有发生，就不会发生层叠，样式都会被显示；
    继承性：
        给父元素添加的属性，后代元素也会应用；
        有的属性可以继承，有的不能继承；
注释语句：
    /*注释内容*/
    作用：
        隐藏代码
        提示信息

选择器：
    基础选择器：
        类型选择器(元素选择器)
            语法：元素名称{属性：属性值；}
            使用场景：统一一类标签的样式时使用；设置全局样式
        class选择器(类选择器)
            语法：.class名{属性：属性值；}
            说明：要配合html里面的class属性一起使用；
            class属性特点：一个元素可有多个class属性值(class名)，也可以和其他元素有相同的名字；
        id选择器
            语法：#id名{属性：属性值；}
            说明：要配合html里面的id属性一起使用；
            id属性特点：唯一性；一个元素只能有一个唯一的id属性值(id名字)；
					  一般配合js使用，或者实现某些功能时使用
        通配符选择器
            语法：*{属性：属性值；}
            说明：*代表页面中的所有标签；
            使用场景：设置全局样式时使用
    复合选择器：
        交集选择器
            语法：选择器1选择器2...属性值n{属性：属性值；}
            说明：选择器1和选择器2...选择器n之间没有空格，是挨着写的；
                  选择器1和选择器2是针对同一个标签的
                  交集选择器的指向更加具体和精确，有更加强调的作用；
            
        并集选择器(群组选择器)：
            语法：选择器，选择器2，...，选择器n{属性，属性值；}
            说明：提取同分类项；
                 当选择器具有相同的属性及属性值时，可以把这个选择器用逗号隔开的形式提取出来，组成一组，				 共同添加相同的属性及属性值；

        后代选择器(包含选择器)：
            语法：选择器1 选择器2 ... 选择器n{属性：属性值；}
            说明：通过父元素找子元素(所有后代元素)；
```



## day07

```css
选择器：
    1、动态伪类选择器：
        :link{}     初始状态
        :visited{}  访问后状态
        :hover{}    鼠标滑过状态
        :active{}   激活状态
        如果想设置超链接的四个状态相同，可以怎样写代
            -> 用群组选择器
            -> 直接给a设置，因为给a设置，是包含了这
            -> 先设置a的样式，然后在设置伪类，
        说明：
            1、在组合使用时，注意顺序：L V H A 
            2、:hover{} 和 :active{}可以给任意元素设
    设置表单元素聚焦状态：
        :focus{} 
    2、子选择器：
        语法：
            选择器1>选择器2{}
            说明：选择器1 必须是选择器2 的直接父元素
    3、相邻兄弟选择器：
        语法：
            选择器1+选择器2{}
            说明：选择器2是选择器1后面的第一个兄弟元
    4、通用选择器
        语法：
            选择器1~选择器2{}
            说明：选择器2 是选择器1后面的所有兄弟元
选择器权重
    基础选择器：
        类型选择器      0,0,0,1
        id选择器        0,1,0,0
        class选择器     0,0,1,0
        通配符选择器    0,0,0,0
        伪类选择器      0,0,1,0 
    复合选择器
        后代选择器      权重相加
        子选择器        
        并集选择器      选择器自身权重大小
        交集选择器
        相邻兄弟选择器
        通用选择器
        伪类选择器
    其他权重：
        继承属性：      0,0,0,0
        行内样式表；    1,0,0,0
        !improtant     无穷大
css属性-文本属性：
    1、字号大小         font-size:;
    2、文本颜色         color:;
    3、文本加粗        
         font-weight:;
         属性值：
            lighter 极细的
            normal  常规显示
            bold    加粗显示
    4、文本倾斜
        font-style:;
            属性值：
                normal  常规显示
                italic  斜体字
                oblique 倾斜的文字
    5、小型的大写字母
        font-variant:;
            属性值：
                normal      常规显示
                small-caps  小型的大写字母
```



## day08

```css
字体族：
    font-family:字体1，字体1，……；
字体的复合式属性:
    包含了：
        font-weight:;
        font-style:;
        font-size:;
        font-family:;
        font-variant:;
        line-height:;
    使用复合式属性的条件：
        ->同时具有size和family
        ->size和family要写在最后的位置
        ->line-height要写在size后 用 / 隔开 size/line-height
对齐：
    水平对齐：
        text-align:;
            left    左对齐
            right   右对齐
            center  居中对齐
            justify 两端对齐(对最后一行文本不去左右)
            text-align-last:;   最后一行
    垂直对齐：
        vertical-align:
            middle  居中
            top     顶对齐
            bottom  底对齐(可以取消有文字是插入图片下端有间隙的
            baseline基线对齐(默认值) 
            super   上标
            sub     下表
            text-top 跟文本顶端对齐
            text-bottom 跟文本底端对齐
行高：
    ling-height:value;
        默认时，文本有自带行高，文本的1.3倍左右
文本修饰：
    text-decoration:underline red dashed;
        text-decoration-line:;
            none            取消修饰(默认值)
            underline       下划线
            overline        上划线
            line-through    删除线
        text-decoration-color:;
        默认和文本颜色统一
        text-decoration-style:;
            solid   实线(默认值)
            dashed  虚线
            dotted  点线
            double  双线
首行缩进：
    text-indent:value;
        ->只针对第一行起作用
        ->支持负值
字间距：
    letter-spacing:value(数值);
        ->支持负值
        ->设置汉字和汉字以及字母和字母之间
词间距：
    word-spacing:value;
        ->支持负值
        ->主要设置单词和单词之间的间距
空余空间：
    white-space:;
        ->normal    (默认值，浏览器会忽略空格和换行)
        ->nowrap    强制文本在一行显示
单行文本溢出显示省略号：
    width:;
    overflow:hidden;
    white-space:nowrap;
    text-ovreflow:ellipsis;
文本溢出：
    overflow:;
        visible 溢出显示(默认值)
        hidden  溢出隐藏
        scroll  溢出显示滚动条
        auto    如果溢出则显示滚动条
    overflow-x:;
    overflow-y:;
```



## day09

```css
透明度 opacity:number;  number的取值范围 0  -  1;

ps的切图:
    单张图
    多张图
    
网页常用的图片格式
    jpg  不支持透明图，适用于色彩比较丰富的图片
    png  支持透明图，适用于色彩数量比较少的图片
    gif  支持透明图，支持动图，适用于色彩数量比较少的图片

隐藏元素属性
    visibility:;
        visible  显示（默认值）
        hidden   隐藏，不显示 元素隐藏，但是位置保留
    visibility:hidden; 和opacity:0的效果一样
    overflow:hidden;  溢出隐藏，当内容溢出元素以外的时候，移出去的那部分会被隐藏；             
具有继承性的属性
    设置文本类的属性大部分都可以继承
    设置结构的属性大部分都不能继承

    text-indent和text-align是块元素能继承；

表格属性:
    单元格之间间距：border-spacing:value;   
    合并相邻单元格边框： border-collapse:collapse; 相当于让单元格之间合体，共用一个边框；
    设置单元格固定宽：
        table-layout:;
            auto    自由显示宽度（默认值）
            fixed   宽度固定，平均分配
    隐藏无内容单元格：
        empty-cells:;
            show 显示（默认值）
            hide 隐藏 ，不显示
            注：什么内容以及标签都没有，包括空格符也没有；
    表格标题位置：
        caption-side:;
            top   显示在表格的上方 （默认值）
            bottom 显示在表格的下方

背景属性
    复合式写法:background:;
        背景色： background-color:;
        背景图： background-image:url();
        背景图平铺属性：
            background-repeat:;
                repeat  平铺（默认值）
                repeat-x   横向平铺
                repeat-y   纵向平铺
                no-repeat  不平铺
        背景图位置属性：
            复合式属性：
             background-position:x y;
                默认值都是 0； 
                如果只写一个值，那么这个值表示的水平位置（x）的距离，垂直方向会以center显示；
                    background-position:center;
                background-position-x:;
                background-position-y:;
                注：支持负值；
        背景图固定属性：
            background-attachment:;
                scroll  滚动（默认值）
                fixed   固定，不跟随滚动条滚动
                当设置了背景图固定了，那么他的显示位置会发生变化；会相对浏览器的可视窗口显示图片的位置；

换行属性
    word-break:;
        normal  默认值，跟距浏览器默认效果折行
        break-all  折行显示，允许在单词内部折行
        keep-all 在半角以及连接符（-）和空格的地方折行

列表属性
    list-style:none;取消列表符号

鼠标指针
    cursor:pointer; 手型
```



## day10

```css
 一、盒子模型：设置元素和元素之间的位置关系；
盒模型的组成：content（内容区）、padding（填充区）、border（边框区）、margin（外边距）
content（内容区）：表示显示内容的区域；
    主要作用：显示内容的地方；
padding（填充区）：显示在内容区和边框区之间的空白区；
    主要作用：设置父元素和子元素之间的间距；
    说明：
        -> 在标准盒模型里，padding值会撑大元素的宽高，如果想保证元素原本的大小不变，需要在宽高上减掉相应的padding值；
        -> 在没有给元素添加宽度的时候，所添加的padding的左右和margin的左右的值就不用减；
        -> padding对背景不起作用，padding区是会显示背景的；
    使用方法：
        复合式：padding:10px 20px 30px 40px;
        单一设置：
            padding-top:;
            padding-right:;
            padding-bottom:;
            padding-left:;
border（边框区） ：显示在盒子边缘的区域；
    主要作用：设置网页上一些修饰性的线条；
    说明：边框也会把元素原本的宽高撑大，如果想保持原本大小不变，需在原有宽高上减掉相应的border值；
    使用方法：
        复合式：
            border:width color style;
                border-right:width color style;
                border-top:width color style;
                border-bottom:width color style;
                border-left:width color style;
        单一设置：
            border-width:;
                border-top-width:;
                border-right-width:;
                border-bottom-width:;
                border-left-width:;
            border-color:;
                border-top-color:;
                border-right-color:;
                border-bottom-color:;
                border-left-color:;
            border-style:;
                border-top-style:;
                border-right-style:;
                border-bottom-style:;
                border-left-style:;
margin（外边距） ：显示在边框以外的空白区；
    主要作用：同辈元素之间的间距；
    说明：不会把元素原本的宽高撑大，但是也会占位置；
    使用方法：
        复合式：
            margin:10px 20px 30px 40px;
        单一设置：
            margin-top:;
            margin-right:;
            margin-bottom:;
            margin-left:;
    注：margin可以设置负值；
        margin的属性值还有auto；auto 表示自由显示（自动分配）；
        margin：0 auto; 设置块元素水平居中
    margin的bug：
        1、两个元素上下之间的margin值会重叠，根据做大的值显示；
        2、元素内，第一个子元素的margin-top会向上传递给父元素；（overflow：hidden可以解决此问题）
标准盒模型实际占有大小的计算：
    标准盒模型的实际占有大小 =  content + padding + border + margin 
怪异盒模型实际占有大小的计算：
    怪异盒模型的实际占有大小 = width/height(content + padding +border) + margin
                
设置元素所遵循的盒模型规则属性：
    box-sizing:;
        content-box  遵循标准盒模型的显示规则
        border-box   遵循怪异盒模型的显示规则
 二、元素类型：
块状元素：
    1、可以直接定义宽高
    2、独占一行，自上而下排列
    3、可以作为容器使用（p和h1 - h6除外，他们是不可以容纳其他块元素的；）
    4、严格遵循盒模型的显示规则
    5、常见的块元素：div table caption hr ul li ol dt dd dl form...
行内元素：
    1、默认不能定义宽高
    2、像文本一样，自左向右排列；
    3、遵循盒模型的显示规则，但是不能直接定义padding-top/bottom,margin-top/bottom,border-top/bottom，他们的显示时不正确的；
    4、常见的行内元素：a b strong i em sub sup ins del span img...
行内块元素：
    1、可以直接定义宽高
    2、像文本一样，自左向右排列；
    3、严格遵循盒模型的显示规则
    4、常见的行内块元素：button ，input ，textarea ，select ，td , th...
    （了解即可）
     img 、input... 属于置换元素；默认具有宽高比;所显示的内容是通过属性添加的；
转换元素原本的元素类型的属性：
    display:;
        none   不显示元素类型，隐藏元素
        block  显示为块状元素
        inline 显示为行内元素
        inline-block 显示为行内块元素；
        了解即可：
            list-item  显示为列表的元素类型
            table      显示为表格的元素类型
            table-cell 显示为td或者th的元素类型
```



## day11

```css
01_使用display：inline-block实现并列显示布局的问题
    默认情况下：元素之间会有缝隙；
    默认情况下：是基线对齐，不能实现顶端对齐；
02_浮动的作用
    实现元素并列显示的作用；
    环绕布局
03_浮动的属性
    float:;
        left   左浮动 ：自左向右排列
        right  右浮动 ：自右向左排列，顺序会颠倒
        none   不浮动（默认值）
04_浮动对块元素本身的影响
    块元素添加浮动之后，宽高就和内容一样大了，但是依然可以定义宽高；
05_浮动对行内元素的影响
    行内元素添加浮动之后，就可以定义宽高的，就想是加了浮动的块元素的效果；
06_浮动和margin:auto的优先级
    浮动的优先级高于margin:auto;              
07_浮动怎样引发的高度塌陷
    当父元素没有设置高度，然后子元素浮动了，父元素就会高度塌陷（没有高度）；
08_解决高度塌陷的方法
    -> 给父元素定义高度；(看情况适用)
        优点：简单
        缺点：高度固定了，显示不灵活；
    -> 开启父元素的bfc;
        + overflow:hidden;(推荐使用)
            优点：简单；
            缺点：当有子元素溢出父元素的范围时，会被隐藏；
        + float:left;
        + display:inline-block;
        + position:absolute/fixed;
            以上三种不推荐使用，会带来新的布局问题；
        ...
    -> 在浮动元素的后面添加空的div,并且给div添加css属性clear:both;
        缺点：会增加页面结构标签；（不建议使用）
    -> 万能清除法;(最推荐使用的)
        语法：
            父元素::after{
                content:'';
                display:block;
                clear:both;
            }
            
            父元素::after{
                content:'';
                display:table;
                clear:both;
            }
09_浮动实现环绕布局
    文本会围绕浮动元素显示，从而实现环绕布局
            
```



## day12

> bfc：独立的渲染区域，块级格式化上下文；
>
> bfc的布局原则：
>     1、bfc区域里的块元素会自上而下一个接一个的排列；
>
> ​    2、bfc区域里盒子的距离由margin决定，俩盒子相邻的上下margin会重叠；以最大值显示
>
> ；
>     3、每个元素的margin-left,和包含块的左边边缘相接触；
>
> ​    4、计算bfc的高度时，会把浮动元素计算在内；
>
> ​    5、bfc是一个独立的容器，bfc里面的内容不会影响他外面的元素；
>
> ​    6、bfc区域不会被浮动元素所覆盖；
>
> 开启bfc的条件：
>     1、html是一个大bfc区域；
>
> ​    2、float不为none；
>
> ​    3、overflow不为visible；
>
> ​    4、position为absolute和fixed时；
>
> ​    5、display为inline-block, table-cell, table-caption, flex, inline-flex;
>
> 通过bfc解决高度塌陷的问题以及自适应两栏布局等问题；



## day13

```css
定位（position）：
    无特殊定位 :   
    相对定位
    绝对定位
    固定定位
    粘性定位
   
position:;
    static    无特殊定位（默认值）
        说明：  
            1、没有定位效果，可以用作取消定位使用
            2、即使给无特殊定位的元素设置了偏移量，也不起作用；
    relative  相对定位
        说明：
            1、设置了相对定位之后，效果和无特殊定位一样，但是会发生层级变化；
            2、当设置了偏移量之后，元素的位置会相应的发生位移；
            3、相对定位不脱离文档流，移动之后，原来的位置保留，不会对布局产生影响；
            4、相对定位的参照物，就是元素原本所在的位置；
            5、一般用相对定位设置包含块
    absolute  绝对定位
        说明：
            1、绝对定位元素会脱离文档流，不占据文档流的位置，后面的元素会把位置补上去；
            2、绝对定位元素，对margin的auto，和浮动失效；
            3、默认情况下所有绝对定位元素的参照物（包含块），都是可视窗口的第一屏；
            4、绝对定位元素会相对离他最近的并且具有定位属性的祖先级元素定位；
            5、当绝对定位元素，没有设置偏移量的时候，是在当前位置不动，但是会脱离文档流；
            6、绝对定位对元素本身的影响：
                -> 当块元素设置了绝对定位之后，宽高就和内容一样大，但是依然可以设置宽高；
                -> 当行内元素设置了绝对定位之后，就可以设置宽高；
            7、绝对定位元素的包含块可以修改，但是想作为绝对定位元素的包含块，需要满足两个条件：
                -> 必须是绝对定位元素的祖先级元素；（建议给最近的父元素定义包含块，主要看情况而定；）
                -> 这个祖先级元素需要设置定位属性，并且属性值为：relative、absolute、fixed；（建议使用relative；）
            
    fixed     固定定位
    sticky    粘性定位
定位元素的层级关系：
    根据html里的书写顺序有关，后写的层级高；
    改变定位元素层级关系的属性：
        z-index:;
            auto   默认值，自由显示，遵循html的属性书写顺序显示；相当于数值为0；
            number 是一个数值，不加单位，可以为负值，值越大层级越高；如果所设置的值相同，则会遵循html的属性书写顺序显示；
            注：z-index单独使用无效，要配合定位属性一起使用；
偏移量的设置：
    top      距上边的距离
    left     距左边的距离
    right    距右边的距离
    bottom   距下边的距离
    注：
        1、不能单独使用，要配合定位属性使用；
        2、属性值可以设置为：px  %;支持负值；
        3、当top和bottom同时使用时，会优先识别top;当left和right同时使用时，会优先识别left；
    相对定位和绝对定位的区别：
        1、是否脱离文档流：
            -> 绝对定位会脱离文档流
            -> 相对定位不会脱离文档流
        2、参照物：
            -> 绝对定位元素的参照物是包含块；
            -> 相对定位的参照物是元素原本所在的位置；
```

## day14

```css
固定定位：
    position:fixed;
    说明：
        1、固定定位元素对margin的auto和浮动属性失效；
        2、会脱离文档流，不占据文档流的位置；
        3、不会跟随滚动条滚动；
        4、参照物始终是可视窗口；
        5、没有设置偏移量的时候，固定定位元素在当前位置不动；但脱离文档流；
        6、固定定位对元素本身的影响：
            -> 块元素加了固定定位后，宽高和内容一样大，但依然可以定义宽高；
            -> 行内元素加了固定定位后，就可以定义宽高了；

固定定位和绝对定位的区别：
        1、是否跟随滚动条滚动：
                -> 固定定位不跟随滚动条滚动
                -> 绝对定位跟随滚动条滚动
                
        2、参照物不同：
          -> 固定定位的参照物 始终是可视窗口；
          -> 绝对定位的参照物 是包含块
            + 默认情况下，可视窗口的第一屏是一个大的包含块；绝对定位元素都会相对它去定位；
            + 绝对定位的包含块是可以修改的，但是要满足两个条件：
                    a 、 必须是绝对定位元素的祖先级元素
                    b 、 必须具有定位属性，并且属性值为relative、absolute、fixed；
        
                
绝对定位和相对定位的区别：
        1、是否脱离文档流
          -> 绝对定位元素 会脱离文档流
          -> 相对定位元素 不会脱离文档流 
        2、参照的不同
          -> 绝对定位的参照物 是包含块
            + 默认情况下，可视窗口的第一屏是一个大的包含块；绝对定位元素都会相对它去定位；
            + 绝对定位的包含块是可以修改的，但是要满足两个条件：
                a 、 必须是绝对定位元素的祖先级元素
                b 、 必须具有定位属性，并且属性值为relative、absolute、fixed；
          -> 相对定位的参照物 是自身原本所在的位置；
粘性定位：
    position:sticky;
        说明：
            1、具有吸附效果
            2、是static 和fixed的结合
            3、一般通过偏移量设置吸顶效果，当你那定定位元素在窗口范围内的时候，就跟没有定位的效果一样，一旦这个元素将要超出窗口范围内的时候，就会以所设置的偏移量实现固定定位；

图片整合
1、什么是图片整合？
    将很多小的背景图片整合到一张大的图片上；
2、通过谁实现背景图片定位的技术？
    利用background-position实现背景图定位技术；
3、为什么使用图片整合技术？
    图片整的的优点：减少对服务器的请求次数，减小图片的大小，增加页面的加载速度；
    图片整的的缺点：使用繁琐，修改不灵活
```

