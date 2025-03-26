---
title: wangeditor编辑区域 hoverbar 定位异常
date: 2024-10-25 14:55:38
tags: html
categories: 记录类
author: konoXIN
cover: https://i-blog.csdnimg.cn/direct/ddf1fb3d1d084196ae7593ae0119eac8.png
---
<meta name="referrer" content="no-referrer"/>

这几天在做公司的项目，要求用到富文本编辑器，于是就是用了最为稳定的wangeditor，但由于我用的地方比较多，所以出现这个警告时候，一长串非常烦人：
![在这里插入图片描述](https://i-blog.csdnimg.cn/direct/ddf1fb3d1d084196ae7593ae0119eac8.png)
网上有很多方法，比如

## 1.在组件中引入

```html
<style src="@wangeditor/editor/dist/css/style.css"></style>
```
或者

```javascript
import '@wangeditor/editor/dist/css/style.css'
```

## 2.在组件中设置高度

```css
::v-deep .w-e-text-container {
  height: 420px !important;
}
```
最后解决我问题的是

## 3.在组件中设置高度的同时，其次还需注意组件中style标签不能有scope

```html
<style>
::v-deep .w-e-text-container {
  height: 420px !important;
}
.w-e-text-container .w-e-scroll {
  height: 500px !important;
  -webkit-overflow-scrolling: touch;
}

</style>
```
![在这里插入图片描述](https://i-blog.csdnimg.cn/direct/45ec6fca1bd0488ba8cc2856d4feca10.png)
