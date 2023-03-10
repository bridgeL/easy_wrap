# easy_wrap

基于[pillow](https://python-pillow.org/)的简单文本转图片渲染工具，帮助实现自动换行

## 安装

```pip install easy_wrap```

**需要Python3.8及以上环境**


## 示例代码

```py
from easy_wrap import Drawer

text = "... the text you want to render ....测试自动换行"

font_path = "msyh.ttc"
font_size = 30
drawer = Drawer(font_path, font_size)

image_width = 180
canvas = drawer.draw_text(text, image_width)

# save the image
canvas.save(open("test.png", "wb")) 
```

![图片](./test.png)

## 特性

- 快速，800字平均渲染时长为0.04s（i7 cpu 2.7GHz）
- 遵循如下换行规则（与css word-break: normal 稍有差异）
  - 纯中文：自动换行，一个汉字看做一个单词；
  - 纯英文：看做一个单词，不换行；
  - 遇到英文空格或者换行符：会换行；

## 更新日志

### 0.1.0

- 第一个可用版本

### 0.1.1

- 修复BUG：修复3.10以下python环境调用easy_wrap发生`TypeError: 'type' object is not subscriptable`的问题

### 0.1.2

- 优化代码结构，完善注释
