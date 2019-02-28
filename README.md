# html2canvas
把我遇到一件特别坑的事先讲在前面<br />
##### 我的项目是vue-cli的 原先html2canvas是npm 引入的 后来要压缩vendor的大小要把npm引入的几个资源包改成cdn引入的，后来发现html2canvas只能生产可视化区域的图片，查了半天原因查到是版本问题，所以大家除了用npm下载之外不要用其他cdn上的版本，自测都不好使，我用过bootcdn的跟staticfile的都是0.5的版本，建议大家之间下载，如果是普通web页面 不用npm下载的话就用 http://47.98.201.115/file/js/html2canvas.js 这个 你可以打开下载到你本地
---
当当当 ！ 该清醒了，是不是看上面的字有点犯困，其实我码字也不容易动动小手先点个star吧！！！

### 进入主题
1. 安装
```
npm 安装
npm install --save html2canvas
yarn 安装
yarn add html2canvas
cdn 引入 或者 下载html2canvas.js
http://47.98.201.115/file/js/html2canvas.js
```
2. 基本语法
```
html2canvas(element, options);
html2canvas(document.body, {
  onrendered: function(canvas) {
    var url = canvas.toDataURL();//图片地址
    document.body.appendChild(canvas);
  },
  width: 300,
  height: 300
});
```
或者使用ES6的promise
```
//两个参数：所需要截图的元素id，截图后要执行的函数， canvas为截图后返回的最后一个canvas
html2canvas(document.getElementById('id')).then(function(canvas) {document.body.appendChild(canvas);});
```
3. 参数

参数名称|类型|默认值|描述
--|:--:|--:|--:
allowTaint|boolean|false|允许污染
background|string|#fff|canvas的背景颜色，如果没有设定默认透明
height|number|null|canvas高度设定
letterRendering|boolean|false|在设置了字间距的时候有用
logging|boolean|false|console.log 输出日志
proxy|string|undefined|代理地址
taintTest|boolean|true|是否在渲染前测试图片
timeout|number|0|图片加载延迟，默认延迟为0，单位毫秒
width|number|null|canvas宽度
useCORS|boolean|false|允许跨域

码字不易，记得点star哦！！！
