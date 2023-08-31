## 欢迎来到评论区使用教程！
## 1、注册
打开[评论系统后台注册区](https://comment.zxrn.info/ui/register)填写昵称、邮箱等有关信息。（没有邮箱的可以在这里用手机号注册：[链接](https://outlook.live.com)(在主页点击登录后再在里面点注册)）
## 2、使用
注册完成后，系统将自动跳转登录界面，在此处输入你的用户名和密码登录。进入个人主页后，回到本页，点击下方评论区的“登录”按钮，就可以愉快地评论啦！
## 评论区
<head>
  <!-- ... -->
  <link
    rel="stylesheet"
    href="https://unpkg.com/@waline/client@v2/dist/waline.css"
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
      serverURL: 'https://comment.zxrn.info',
    });
  </script>
</body>
