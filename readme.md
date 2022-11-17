# echarts-renderjs

## 问题描述

我在uni-app中使用render.js渲染了echarts，在PC端点击事件是正常的，**在移动端点击事件就失效了**。

查看 components目录下的 echarts 文件，初始化图表以后为图表绑定了点击事件，但在移动端点击后并没有执行点击的回调函数。