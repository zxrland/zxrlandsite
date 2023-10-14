## 原始赛车场代码列表
### [index.js](https://www.zxrn.info/codes/yscar/index-js/)
### [manager.js](https://www.zxrn.info/codes/yscar/manager-js/)
### [time-sun-gui.js](https://www.zxrn.info/codes/yscar/time-sun-gui-js/)
### [second-manager.js](https://www.zxrn.info/codes/yscar/second-manager-js/)
### [racer.js](https://www.zxrn.info/codes/yscar/racer-js/)
### [other.js](https://www.zxrn.info/codes/yscar/other-js/)
### [car.js](https://www.zxrn.info/codes/yscar/car-js/)
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
