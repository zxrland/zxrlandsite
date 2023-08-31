## 欢迎来到评论区使用教程！
## 1、注册
打开[评论系统后台注册区](https://comment.zxrn.info/ui/register)填写昵称、邮箱等有关信息。（没有邮箱的可以在这里用手机号注册：[链接](https://signup.live.com/signup?cobrandid=ab0455a0-8d03-46b9-b18b-df2f57b9e44c&id=292841&contextid=EADF4752E5130137&opid=51DE6DACED52546D&bk=1693478453&sru=https://login.live.com/login.srf%3fcobrandid%3dab0455a0-8d03-46b9-b18b-df2f57b9e44c%26id%3d292841%26cobrandid%3dab0455a0-8d03-46b9-b18b-df2f57b9e44c%26id%3d292841%26contextid%3dEADF4752E5130137%26opid%3d51DE6DACED52546D%26mkt%3dEN-US%26lc%3d1033%26bk%3d1693478453%26uaid%3d33d71254805245179f9b8d3aaf178198&uiflavor=web&lic=1&mkt=EN-US&lc=1033&uaid=33d71254805245179f9b8d3aaf178198)(在主页点击登录后再在里面点注册)）
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
