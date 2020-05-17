# Markdown简明教程[1]基本介绍

## 什么是Markdown

![image-20200516092510930](https://cdn.jsdelivr.net/gh/wangrusheng/k/img/202005/image-20200516092510930.png)

Markdown 是一种轻量级标记语言，它允许人们使用易读易写的纯文本格式编写文档，用户可以使用这些标记符号以最小的输入代价生成极富表现力的文档。 

Markdown 语言在 2004 由约翰·格鲁伯（英语：John Gruber）创建。  

Markdown 编写的文档可以导出 HTML 、Word、图像、PDF、Epub 等多种格式的文档。 

Markdown 编写的文档后缀为 **.md**, **.markdown**。

## Markdown 应用

Markdown 能被使用来：

> 整理知识、学习笔记。
>
> 撰写电子书，如：Gitbook。
>
> 撰写发布技术文稿（代码支持）
>
> 撰写发布学术论文（LaTeX 公式支持）

## Markdown编辑器

### Typora

支持 MacOS 、Windows、Linux 平台，`Simple, yet Powerful`。  
官网:https://typora.io/

<video autoplay="" muted="muted" preload="preload" loop="loop" style="border-radius: 8px;box-shadow: 0px 0px 8px 3px #ccc;"  src="https://cdn.jsdelivr.net/gh/wangrusheng/images/img/beta.mp4" width="400" height="300"></video>

### Cmd Markdown

支持 MacOS 、Windows、Linux 平台，优秀的Mardown语法教程，编辑模式和阅读模式分栏显示可以帮助我们对照学习Markdown语法。  
官网:https://www.zybuluo.com/

![image-20200516120057269](https://cdn.jsdelivr.net/gh/wangrusheng/k/img/202005/image-20200516120057269.png)

# Markdown简明教程[2]基础语法

## 1. 分级标题

使用 **#** 号可表示 1-6 级标题，一级标题对应一个 **#** 号，二级标题对应两个 **#** 号，以此类推。

```
# 一级标题
## 二级标题
### 三级标题
#### 四级标题
##### 五级标题
###### 六级标题
```
显示效果:

![image-20200516130017041](https://cdn.jsdelivr.net/gh/wangrusheng/k/img/202005/image-20200516130017041.png)

## 2. 斜体和粗体

使用 * 和 ** 表示斜体和粗体。

```
这是 *斜体*，这是 **粗体**。
```

显示效果:

这是 *斜体*，这是 **粗体**。

## 3. 删除线

使用 ~~ 表示删除线。

```
~~这是一段错误的文本。~~
```

显示效果：

~~这是一段错误的文本。~~

## 4.分隔线

你可以在一行中用三个以上的星号、减号、底线来建立一个分隔线。

```
***
```

显示效果：

***

## 5.脚注

脚注是对文本的补充说明。

```
创建脚注格式类似这样 [^RUNOOB]。

[^RUNOOB]: 菜鸟教程 -- 学的不仅是技术，更是梦想！！！
```

显示效果：

![md5](https://cdn.jsdelivr.net/gh/wangrusheng/k/img/202005/md5.gif)

## 6.外链接

使用 \[描述](链接地址) 为文字增加外链接。

```
这是去往 [弦歌飞鸿](https://www.cnblogs.com/xgfh/) 的链接。
```

显示效果：

这是去往 [弦歌飞鸿](https://www.cnblogs.com/xgfh/) 的链接。

## 7.无序列表

使用 *，+，- 表示无序列表。

```
* 无序列表项 一
* 无序列表项 二
* 无序列表项 三
```
显示效果

* 无序列表项 一
* 无序列表项 二
* 无序列表项 三

## 8.有序列表

使用数字和点表示有序列表。

```
1. 有序列表项 一
2. 有序列表项 二
3. 有序列表项 三
```
显示效果

1. 有序列表项 一

2. 有序列表项 二
3. 有序列表项 三

## 9.文字引用

使用 > 表示文字引用。

```
人生到处知何似，应似飞鸿踏雪泥。
```

显示效果：
> 人生到处知何似，应似飞鸿踏雪泥。

## 10.代码片段

使用 \`代码` 表示代码片段。

```
`markdown`是一种轻量级标记语言
```

显示效果

`markdown`是一种轻量级标记语言。

## 11.代码块

使用 **```** 包裹一段代码，并指定一种语言（也可以不指定）：

```markdown
​```javascript
$(document).ready(function () {
    alert('RUNOOB');
});
​```
```

显示效果：

```javascript
$(document).ready(function () {
    alert('RUNOOB');
});
```

## 12.图像

使用 \!\[描述](图片链接地址) 插入图像。

```markdown
![image-20200516092510930](https://cdn.jsdelivr.net/gh/wangrusheng/k/img/202005/image-20200516092510930.png)
```

显示效果

![image-20200516092510930](https://cdn.jsdelivr.net/gh/wangrusheng/k/img/202005/image-20200516092510930.png)

## 13.表格
Markdown 制作表格使用 **|** 来分隔不同的单元格，使用 **-** 来分隔表头和其他行，使用**:**表示对齐方向。

```markdown
| 项目   |   价格 | 数量 |
| ------ | -----: | :--: |
| 计算机 | ￥1600 |  5   |
| 手机   |   ￥12 |  12  |
| 管线   |    ￥1 | 234  |
```

显示效果：

| 项目   |   价格 | 数量 |
| ------ | -----: | :--: |
| 计算机 | ￥1600 |  5   |
| 手机   |   ￥12 |  12  |
| 管线   |    ￥1 | 234  |

# Markdown简明教程[3]进阶语法

## 1.特殊符号

反斜杠来帮助插入特殊符号

```
\\   反斜线
\`   反引号
\*   星号
\#   井字号
```

显示效果

\\   反斜线
\`   反引号
\*   星号
\#   井字号

## 2.段落

Markdown 段落没有特殊的格式，直接编写文字就好，段落换行有多种方式

两个空格+shift+enter换行

显示效果：

行一  
行二

直接回车空行换行

显示效果

行一

行二

```
html<br>换行
```

html<br>换行

## 3.目录

在段落中填写 `[TOC]` 以显示全文内容的目录结构。

```
[TOC]

# 一级标题
## 二级标题
### 三级标题
#### 四级标题
##### 五级标题
###### 六级标题
```

显示效果：

![image-20200516145226986](https://cdn.jsdelivr.net/gh/wangrusheng/k/img/202005/image-20200516145226986.png)

### 4.待办事宜

使用带有 [ ] 或 [x] （未完成或已完成）项的列表语法撰写一个待办事宜列表，并且支持子列表嵌套以及混用Markdown语法。

```
- [ ] **Markdown 文档**
    - [ ] 基本介绍
    - [ ] 基础语法
    - [x] 进阶语法
        - [x] 修复 LaTex 公式
        - [x] 流程图
```

显示效果：

![image-20200516191244122](https://cdn.jsdelivr.net/gh/wangrusheng/k/img/202005/image-20200516191244122.png)

## 4.LaTeX 公式[^LaTeX]

`$` 表示行内公式，`$$` 表示整行公式

```
质能守恒方程可以用一个很简洁的方程式 $E=mc^2$ 来表达。
```

质能守恒方程可以用一个很简洁的方程式 $E=mc^2$ 来表达。

```
$$\sum_{i=1}^n a_i=0$$
```

$$\sum_{i=1}^n a_i=0$$

```
$$f(x_1,x_x,\ldots,x_n) = x_1^2 + x_2^2 + \cdots + x_n^2 $$
```

$$f(x_1,x_x,\ldots,x_n) = x_1^2 + x_2^2 + \cdots + x_n^2 $$

```
$$\sum^{j-1}_{k=0}{\widehat{\gamma}_{kj} z_k}$$
```

$$\sum^{j-1}_{k=0}{\widehat{\gamma}_{kj} z_k}$$

## 5.绘图

### 5.1 flow流程图[^flowchart]

```markdown
​```flow
st=>start: 开始框
op=>operation: 处理框
cond=>condition: 判断框(是或否?)
sub1=>subroutine: 子流程
io=>inputoutput: 输入输出框
e=>end: 结束框
st->op->cond
cond(yes)->io->e
cond(no)->sub1(right)->op
​```
```

![image-20200516210940069](https://cdn.jsdelivr.net/gh/wangrusheng/k/img/202005/image-20200516210940069.png)

### 5.2 sequence时序图[^js-sequence]

```
​```sequence
Title: 标题：复杂使用
对象A->对象B: 对象B你好吗?（请求）
Note right of 对象B: 对象B的描述
Note left of 对象A: 对象A的描述(提示)
对象B-->对象A: 我很好(响应)
对象B->对象C: 你好吗
对象C-->>对象A: 对象B找我了
对象A->对象B: 你真的好吗？
Note over 对象C,对象B: 我们是朋友
participant 对象D
Note right of 对象D: 没人陪我玩
​```
```
![image-20200516211054089](https://cdn.jsdelivr.net/gh/wangrusheng/k/img/202005/image-20200516211054089.png)

### 5.2mermaid 流程图[^mermaid]

```
​```mermaid
graph TD
A[方形] --> B(圆角)
    B --> C{条件a}
    C --> |a=1| D[结果1]
    C --> |a=2| E[结果2]
​```
```

![image-20200516211114754](https://cdn.jsdelivr.net/gh/wangrusheng/k/img/202005/image-20200516211114754.png)

### 5.4mermaid 时序图

```
​```mermaid
  sequenceDiagram
    participant 张三
    participant 李四
    张三->王五: 王五你好吗？
    loop 健康检查
        王五->王五: 与疾病战斗
    end
    Note right of 王五: 合理 食物 <br/>看医生...
    李四-->>张三: 很好!
    王五->李四: 你怎么样?
    李四-->王五: 很好!
​```
```

![image-20200516211140609](https://cdn.jsdelivr.net/gh/wangrusheng/k/img/202005/image-20200516211140609.png)

### 5.6mermaid类图

```
​```mermaid
classDiagram
      Animal <|-- Duck
      Animal <|-- Fish
      Animal <|-- Zebra
      Animal : +int age
      Animal : +String gender
      Animal: +isMammal()
      Animal: +mate()
      class Duck{
          +String beakColor
          +swim()
          +quack()
      }
      class Fish{
          -int sizeInFeet
          -canEat()
      }
      class Zebra{
          +bool is_wild
          +run()
      }
​```
```

![image-20200516211421185](https://cdn.jsdelivr.net/gh/wangrusheng/k/img/202005/image-20200516211421185.png)

### 5.7mermaid状态图

```
​```mermaid
stateDiagram
    [*] --> Still
    Still --> [*]
    Still --> Moving
    Moving --> Still
    Moving --> Crash
    Crash --> [*]
​```
```

![image-20200516211255022](https://cdn.jsdelivr.net/gh/wangrusheng/k/img/202005/image-20200516211255022.png)

### 5.8mermaid饼图

```
​```mermaid
pie title Pets adopted by volunteers
    "Dogs" : 386
    "Cats" : 85
    "Rats" : 15 
​```
```

![image-20200516211514437](https://cdn.jsdelivr.net/gh/wangrusheng/k/img/202005/image-20200516211514437.png)

### 5.9mermaid甘特图

```
​```mermaid
        gantt
        dateFormat  YYYY-MM-DD
        title 软件开发甘特图
        section 设计
        需求                      :done,    des1, 2014-01-06,2014-01-08
        原型                      :active,  des2, 2014-01-09, 3d
        UI设计                    :         des3, after des2, 5d
        未来任务                   :         des4, after des3, 5d
        section 开发
        学习准备理解需求            :crit, done, 2014-01-06,24h
        设计框架                   :crit, done, after des2, 2d
        开发                      :crit, active, 3d
        未来任务                   :crit, 5d
        修复bug                   :2d
        section 测试
        功能测试                   :active, a1, after des3, 3d
        压力测试                   :after a1  , 20h
        测试报告                   :48h
​```
```

![image-20200516211603718](https://cdn.jsdelivr.net/gh/wangrusheng/k/img/202005/image-20200516211603718.png)



[^LaTeX]: *LaTeX*（LTEX，音译“拉泰赫”）是一种基于ΤΕΧ的排版系统, 访问 [MathJax](http://meta.math.stackexchange.com/questions/5020/mathjax-basic-tutorial-and-quick-reference) ，[Cmd Markdown 公式指导手册](https://www.zybuluo.com/codeep/note/163962)参考更多使用方法。
[^flowchart]:Draws simple SVG flow chart diagrams from textual ，访问 [flowchart](http://flowchart.js.org/) 参考更多使用方法。
[^js-sequence]:Turns text into UML sequence diagrams,访问 [js-sequence](https://bramp.github.io/js-sequence-diagrams/) 参考更多使用方法。

[^mermaid]:Mermaid(英[ˈmɜːmeɪd],美人鱼),Generation of diagrams and flowcharts from text in a similar manner as markdown.访问[mermaid](https://mermaid-js.github.io/mermaid/#/)参考更多使用方法。



