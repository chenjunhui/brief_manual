# Markdown 简明手册

## 标题

### 子标题

#### 子子标题

##### 子子子标题

## 段落

正常文本

## 列表

无序列表‌：使用星号

* 项目 1
  * 子项目 1
  * 子项目 2
* 项目 2
  * 子项目 1
  * 子项目 2

有序列表：使用数字加句点加空格，如 1. 项目 或 2. 项目

1. 项目 1
2. 项目 2

## 任务列表

* [ ] 未完成任务 1
* [ ] 未完成任务 2
* [x] 已完成任务 1
* [x] 已完成任务 2

## 文本样式

**加粗**
*斜体*
~~删除线~~

## 图片

图片：![图片描述](https://i-blog.csdnimg.cn/blog_migrate/8f1b213356ed81d5a706d52c6ab7cb6d.png)

## 代码块

三反引号（```）是最常用的代码块语法，支持语法高亮和多行代码展示。

```text
文本块，没有语法高亮。
```

```javascript
$(document).ready(function () {
    alert('RUNOOB');
});
```

```python
def hello_world():
    print("Hello, World!")
```

```html
<!DOCTYPE html>
<html>
<head>
<title>Page Title</title>
</head>
<body>
Hello, World!
</body>
</html>
```

```css
body {
    background-color: lightblue;
}
```

## 引用

Markdown 区块引用是在段落开头使用 > 符号 ，然后后面紧跟一个空格符号：
> 区块引用
> 菜鸟教程
> 学的不仅是技术更是梦想

多级嵌套引用
另外区块是可以嵌套的，一个 > 符号是最外层，两个 > 符号是第一层嵌套，以此类推：
> 最外层
> > 第一层嵌套
> > > 第二层嵌套

## 公式

公式：$E=mc^2$

## 表格

| 表头 1 | 表头 2 |
| ------ | ------ |
| 单元格 | 单元格 |
| 单元格 | 单元格 |

| Column 1 | Column 2 | Column 2 |
|:--|:--:| --:|
|  文本居左 |  文本居中 |  文本居右 |

## 分割线

---

## 链接

[菜鸟 Markdown 教程](https://www.runoob.com/markdown/md-tutorial.html)
