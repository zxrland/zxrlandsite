## FAQ
### Q:这个网站是做什么的？
### A:这个是网站未来将会开放一些网站作者的代码（作者Box3账号：zxr6247）
### Q:未来会有其他语言的版本吗？
### A:可能有繁体中文的版本，取决于作者是否有时间（狗头）
### Q:什么时候会有代码在网站上公布？
### A:等到作者的地图完成的时候就会有代码了。
### 注:这些内容更新于2023/3/15，作者是个Markdown新手，如果界面很丑陋请不要在意，如果对网站有什么意见，欢迎在👇下方评论区评论
## 代码
### 敬请期待
## 评论
<head>
  <!-- ... -->
  <link
    rel="stylesheet"
    href="https://cdn.bootcdn.net/@waline/client@v2/dist/waline.css"
  />
  <!-- ... -->
</head>
<body>
  <!-- ... -->
  <div id="waline"></div>
  <script type="module">
    import { init } from 'https://unpkg.com/@waline/client@v2/dist/waline.mjs';

    init({
      el: '#waline',
      serverURL: 'https://comment.zxrn.cf',
    });
  </script>
</body>
