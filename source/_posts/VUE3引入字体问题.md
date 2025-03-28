---
title: VUE3引入字体问题
date: 2025-03-28 13:28:14
categories: 记录类
cover: /images/VUE3引入字体问题/image3.png
---

今天做项目时候，遇到了一个问题，就是在VUE3中引入字体文件，发现字体文件没有生效，经过一番排查，还是没有解决。
查阅大量资料后，在博客：

[亲身踩坑 多种方法帮你解决 Failed to decode downloaded font VUE 引入字体没有效果-CSDN博客](https://blog.csdn.net/Youweretrouble/article/details/129451853)

找到了解决方法，特别感谢。

# 问题描述
出现如下的警告
![spFrou](/images/VUE3引入字体问题/image2.png)

这个时候是因为ttf格式解析失败导致的，需要用根据转为woff和woff2

使用网站把ttf转为woff和woff2：

 [Online @font-face generator — Transfonter](https://transfonter.org/) 

![spFrou](/images/VUE3引入字体问题/image.png)

之后在你的assets/fonts/fonts.scss下

```scss
  @font-face {
    font-family: 'Alibaba-PuHuiTi-Heavy';
    src: url('./Alibaba-PuHuiTi-H.woff') format('woff'),
         url('./Alibaba-PuHuiTi-H.woff2') format('woff2');
    font-weight: normal;
    font-style: normal;
}
```

在main.js注册一下

```js
import '@/assets/fonts/fonts.scss'
```

然后在组件内使用

```css
  div:nth-child(1) {
    font-family: 'Alibaba-PuHuiTi-Heavy';
  }

```

