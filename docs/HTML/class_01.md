# HTML 笔记

## HTML 简介

### 什么是 HTML

HTML 是用来描述网页的一种语言

- **H**yper **T**ext **M**arkup **L**anguage，超文本标记语言
- 不是编程语言，是一种标记语言

### HTML 标签

HTML 通过标记标签来描述网页

- 标签是由尖括号包围的关键词，比如`<html>`
- 标签通常是成双成对出现的，比如`<a>`和`</a>`
- 标签对中的第一个标签是**开始标签**，第二个是**结束标签**
- 开始和结束标签也被称为**开放标签**和**闭合标签**

## HTML 文档

- HTML 文档也被称为网页
- HTML 文档包含 HTML 标签和纯文本

Web 浏览器的作用是读取 HTML 文档，并以网页的形式显示出它们。浏览器不会显示 HTML 标签，而是使用标签来解释页面的内容：

**HTML 文档基本结构**

```html
<!-- 声明文档类型 -->
<!DOCTYPE html>
<!-- 根标签 -->
<html lang="en">
  <!-- 网页头部 -->
  <head>
    <!-- 指定字符编码 -->
    <meta charset="UTF-8" />
    <!-- 网页标题 -->
    <title>Document</title>
  </head>
  <!-- 网页的主题，可视区域 -->
  <body>
    <h1>这是一个网页</h1>
  </body>
</html>
```

---

### HTML 注释

语法格式如下：

> `<!--  这是html中的注释 -->`

### HTML 元素

**HTML 文档是由 HTML 元素定义的**

#### HTML 元素语法

HTML 元素指的是从开始标签（start tag）到结束标签（end tag）的所有代码。

| **开始标签** | **元素内容**   | **结束标签** |
| ------------ | -------------- | ------------ |
| `<h1>`       | 我的第一个标题 | `</h1>`      |
| `<p>`        | 我的第一个标题 | `</p>`       |
| `<br />`     |                |              |

- HTML 元素以开始标签起始，以结束标签终止
- 元素的内容是开始标签和结束标签之间的内容
- 某些元素具有空内容，空元素直接在开始标签进行关闭

#### 嵌套的 HTML 元素

大多数 HTML 元素可以嵌套（可以包含其他 HTML 元素）。<br>
HTML 文档由嵌套的 HTML 元素构成。

#### HTML 属性

属性为 HTML 元素提供附加的信息。<br>
属性总是以**键值对**的形式出现，比如`name="value"`。<br>
属性总是卸载 HTML 元素的开始标签中。<br>
例如：<br>
HTML 链接由`<a>`标签定义，链接的地址在`href`属性中指定：

```html
<a href="http://www.baidu.com">百度一下</a>
```

## 文本标签

### 标题标签

> 标题通过 `<h1>-<h6>` 进行定义。
> 标题标签从大到小依次为：`h1-h6`

```html
<!-- 示例代码 -->
<h1>一级标题</h1>
<h2>二级标题</h2>
<h3>三级标题</h3>
<h4>四级标题</h4>
<h5>五级标题</h5>
<h6>六级标题</h6>
```

> 效果如下：

<div
      style="
        border: 1px solid #ccc;
        width: auto;
        height: auto;
      "
    >
<h1>一级标题</h1>
<h2>二级标题</h2>
<h3>三级标题</h3>
<h4>四级标题</h4>
<h5>五级标题</h5>
<h6>六级标题</h6>
</div>

---

### 段落标签

> 段落是通过`<p>`标签定义的</br>
> 作用：大段的文字可使用段落标签</br>
> 特性：浏览器会自动在段落的前后加空行。`<p>`是块级元素。

```html
<!-- 示例代码 -->
<p>这里是大段文字</p>
```

> 效果如下：

<div style='border: 1px solid #ccc;'>
    <p>这里是大段文字</p>
</div>

---

### 超链接标签

> `<a>`标签在 HTML 中创建链接</br>
> 作用：用于链接到其他网页，或用作在文章内跳转</br>
> 备注：超链接默认在单行显示，如有多个超链接，可用`<p>`包裹`<a>`以达到换行，或在`<a>`后加上`<br>`标签

```html
<!-- 示例代码 -->
<a href="https://stays1993.github.io/">在当前标签页跳转到其他网页</a>
<a href="https://stays1993.github.io/" target="_blank"
  >在新标签页跳转到其他网页</a
>
<a href="#">回到顶部</a>
<a href="#lable">跳转到锚点</a>
<a id="lable">我是锚点</a>
```

> 效果如下：

<div style='border: 1px solid #ccc;'>
    <a href="https://stays1993.github.io/">在当前标签页跳转到其他网页</a><br>
    <a href="https://stays1993.github.io/" target="_blank">在新标签页跳转到其他网页</a><br>
    <a href="#">回到顶部</a><br>
    <a href="#lable">跳转到锚点</a><br>
    <a id="lable">我是锚点</a><br>
</div>

---

## 图像标签 `<img src=url>`

> 作用：显示图片<br>
> src 属性：图片的链接，本地链接或网络链接<br>
> alt 属性：如果图片链接不存在，会有提示信息<br>

```html
<!-- 示例代码 -->
<!-- 引用网络图片 -->
<img
  src="https://alist.goca.top/d/local_storage/img/%E5%A4%B4%E5%83%8F.jpeg"
  alt=""
  style="height: 128px; width: 128px"
/>

<!-- 引用本地图片 -->
<img src="./123.png" style="height: 128px; width: 128px" alt="头像" />

<!-- 如果图片不存在 -->
<img src="./1213.png" alt="头像" />
```

> 效果如下：

<img
  src="https://alist.goca.top/d/local_storage/img/%E5%A4%B4%E5%83%8F.jpeg?sign=BKMirKxVSUdSxJjSL_QAhsZCS5Tp9Ad7YmkJxxAshIo=:0"
  alt=""
  style="height: 128px; width: 128px"
/>

<p>引用网络图片</p>

<!-- 引用本地图片 -->
<img src="./123.jpeg" style="height: 128px; width: 128px" alt="头像" />
<p>引用本地图片</p>

<!-- 如果图片不存在 -->
<img src="./1213.png" alt="头像" />
<p>如果图片不存在</p>

---

## 列表标签

### 无序列表

> 作用：无序列表<br>
> ul：<br>
> li：内容<br>

```html
<!-- 示例代码 -->
<ul>
  <li>你好</li>
  <li>我好</li>
  <li>它好</li>
</ul>
```

> 效果如下：

<p>无序列表</p>
<ul>
  <li>你好</li>
  <li>我好</li>
  <li>它好</li>
</ul>

---

### 有序列表

> 作用：有序列表<br>
> ol：<br>
> li：内容<br>

```html
<!-- 示例代码 -->
<ol>
  <li>你好</li>
  <li>我好</li>
  <li>它好</li>
</ol>
```

> 效果如下：

<p>有序列表</p>
<ol>
  <li>你好</li>
  <li>我好</li>
  <li>它好</li>
</ol>

---

### 自定义列表

> 作用：自定义列表，可以自己定义序号是什么<br>
> dl：<br>
> dt：序号<br>
> dd：内容<br>

```html
<!-- 示例代码 -->
<dl>
  <dt>One</dt>
  <dd>你好</dd>
  <dt>Two</dt>
  <dd>我好</dd>
  <dt>Three</dt>
  <dd>它好</dd>
</dl>
```

> 效果如下：

<p>自定义列表</p>
<dl>
  <dt>One</dt>
  <dd>你好</dd>
  <dt>Two</dt>
  <dd>我好</dd>
  <dt>Three</dt>
  <dd>它好</dd>
</dl>

---

## 表格

> 作用：表格<br>
> table：表格<br>
> thead：定义表头<br>
> tbody：定义表内容体<br>
> tr：定义行<br>
> td：定义单元格<br>

```html
<!-- 示例代码 -->
<table>
  <thead>
    <tr>
      <td>表头1</td>
      <td>表头2</td>
      <td>表头3</td>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>1</td>
      <td>2</td>
      <td>3</td>
    </tr>
    <tr>
      <td>1</td>
      <td>2</td>
      <td>3</td>
    </tr>
    <tr>
      <td>1</td>
      <td>2</td>
      <td>3</td>
    </tr>
  </tbody>
</table>
```

> 效果如下：

<table>
  <thead>
    <tr>
      <td>表头1</td>
      <td>表头2</td>
      <td>表头3</td>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>1</td>
      <td>2</td>
      <td>3</td>
    </tr>
    <tr>
      <td>1</td>
      <td>2</td>
      <td>3</td>
    </tr>
    <tr>
      <td>1</td>
      <td>2</td>
      <td>3</td>
    </tr>
  </tbody>
</table>

## 表单 `<from>`

> 作用：用于收集用户的输入信息
> from：
> input：
> button：

```html
<!-- 示例代码 -->
<form action="">
  <p>
    用户名：<input type="text" name="username" placeholder="请输入用户名" />
  </p>
  <p>密码：<input type="password" name="password" /></p>
  <p>年龄：<input type="number" name="number" /></p>
  <p>邮箱：<input type="email" name="email" /></p>
  <p>
    性别： 男<input type="radio" name="sex" value="1" /> 女<input
      type="radio"
      name="sex"
      value="0"
    />
  </p>
  <p>
    爱好：骑马<input type="checkbox" name="hobby" value="1" />射箭<input
      type="checkbox"
      name="hobby"
      value="2"
    />
  </p>
  <p>
    国籍：<select name="country">
      <option value="1" selected>中国</option>
      <option value="2">美国</option>
      <option value="3">英国</option>
    </select>
  </p>
  <p>
    <textarea
      name="introduction"
      rows="10"
      cols="30"
      placeholder="个人简介"
    ></textarea>
  </p>

  <input type="submit" value="提交" />
  <button type="reset">重置</button>
  <button type="submit">另一个提交按钮</button>
</form>
```

> 效果如下：

<form action="">
  <p>
    用户名：<input type="text" name="username" placeholder="请输入用户名" />
  </p>
  <p>密码：<input type="password" name="password" /></p>
  <p>年龄：<input type="number" name="number" /></p>
  <p>邮箱：<input type="email" name="email" /></p>
  <p>
    性别： 男<input type="radio" name="sex" value="1" /> 女<input
      type="radio"
      name="sex"
      value="0"
    />
  </p>
  <p>
    爱好：骑马<input type="checkbox" name="hobby" value="1" />射箭<input
      type="checkbox"
      name="hobby"
      value="2"
    />
  </p>
  <p>
    国籍：<select name="country">
      <option value="1" selected>中国</option>
      <option value="2">美国</option>
      <option value="3">英国</option>
    </select>
  </p>
  <p>
    <textarea
      name="introduction"
      rows="10"
      cols="30"
      placeholder="个人简介"
    ></textarea>
  </p>

  <input type="submit" value="提交" />
  <button type="reset">重置</button>
  <button type="submit">另一个提交按钮</button>
</form>

---

## div 块 `<div> </div>`

> 作用：div 是一个块级元素，本身没有特殊含义，是容器，主要用来包含其他元素，用来设计网页布局

```html
<!-- 示例代码 -->
<div style="background-color: green; height: 200px; width: auto;">
  <p>我是一个div容器</p>
  <p>背景是绿色</p>
  <p>高度是200px</p>
  <p>宽度是自动</p>
</div>
```

> 效果如下：

<div style="background-color: green; height: 200px; width: auto;">
  <p>我是一个div容器</p>
  <p>背景是绿色</p>
  <p>高度是200px</p>
  <p>宽度是自动</p>
</div>

---

### span 标签 `<span> </span>`

> 作用：span 标签是内联元素，本身没有特殊含义，主要作为文本容器和 css 配合给部分文本设置样式

```html
<!-- 示例代码 -->
<p>
  span标签是内联元素，本身没有特殊含义，<span
    style="color: red; font-size: 20px"
    >作为文本容器</span
  >
  和css配合给部分文本设置样式
</p>
```

> 效果如下：

<p>
  span标签是内联元素，本身没有特殊含义，<span
    style="color: red; font-size: 20px"
    >作为文本容器</span>
  和css配合给部分文本设置样式
</p>

---

## 特殊标签

### 水平线标签

> `<hr />` 标签在 HTML 页面中创建水平线<br>
> 作用：用于分割内容

```html
<hr />
```

> 效果如下：

<div style='border: 1px solid #ccc;'>
    <hr />
</div>
