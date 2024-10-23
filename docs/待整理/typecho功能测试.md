# 内嵌 B 站视频

- 参考：

1. [该怎么把 b 站的视频嵌入到自己的博客中？ - Typecho Forum](https://forum.typecho.org/viewtopic.php?t=24681)
2. [网站中嵌入 B 站视频，禁止 iframe 代码中的视频自动播放 - 前端 - 大象笔记]
   (https://www.sunzhongwei.com/video-websites-embed-bilibili-iframe-code-video-disable-play-automatically)

在 bilibili 里点击分享，选择代码；
![https://ty.goca.top/usr/uploads/2024/09/2024048335.png][1]
然后再 typecho 文章中输入三个英文感叹号，如下示例：

```
！！！
<iframe src="//player.bilibili.com/player.html?isOutside=true&aid=511521164&bvid=BV1Au41167Dk&cid=719543608&p=1" scrolling="no" border="0" frameborder="no" framespacing="0" allowfullscreen="true" autoplay=0></iframe>
！！！
```

效果如下：

<iframe src="//player.bilibili.com/player.html?isOutside=true&aid=511521164&bvid=BV1Au41167Dk&cid=719543608&p=1" scrolling="no" border="0" frameborder="no" framespacing="0" allowfullscreen="true" autoplay=0></iframe>

# 内嵌 ip.skk.moe

代码如下：

```html
<iframe
  src="https://ip.skk.moe/simple"
  style="height: 221px; width: 350px; border: 1;"
></iframe>
```

效果如下

<iframe src="https://ip.skk.moe/simple" style="height: 221px; width: 350px; border: 1;" ></iframe>

[1]: https://ty.goca.top/usr/uploads/2024/09/2024048335.png

# 其他

1. [Typecho 博客使用 Cloudflare CDN 的相关问题及解决方法 - 波波的博客](https://bobqu.cyou/2020/11/04/42.html)
2. [自己写了个 Typecho 博客自动清理 CloudFlare 缓存插件 - 明月的运维学习笔记 Blog](https://www.imydl.tech/ty/1107.html)
