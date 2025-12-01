---
slug: Lighthouse
title: Lighthouse
authors: [singi]
tags: [Lighthouse, Web性能优化]
---

## 使用`Lighthouse`进行性能优化

在某个页面打开调试工具，切换到`Lighthouse`，然后选择模式，设备类型，最后点击右上角的分析页面负载。等的生成测试报告，针对性的优化即可。

## 优化常用方法

- 启用`HTTP2`,甚至`HTTP3`
- 开启网络传输压缩：`gzip`等
- UI图片尽量使用`webp`，且压缩到合适的大小
- `css`,`js`等文件需要压缩后，再投入生产环境使用
- `css`,`js`等静态文件，如果可以，尽量主动设置请求头缓存。（但需要考虑副作用，设置后，必须改变文件名才能获取到最新的文件，对构建性应用友好，因为每次都会生成新的文件名，浏览器环境谨慎使用。）
- 不影响页面渲染的`css`可以延迟加载`<link href="xxx.css" rel="preload" as="style" onload="this.rel='stylesheet'">`
- 屏幕外的图片使用延迟加载，需要设置固定占位宽高。`<img loading="lazy" class="size-[40px]" ... />`

<!-- truncate -->