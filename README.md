模版文件说明

/2014
/css
  /css/all.min.css
/fonts
  /fonts/RuiHeiXiTi.otf
/img
  /img/***.jpg
  /img/***.gif
/js
  /js/all.min.js
  /js/audio.min.js
  /js/brav1toolbox.js
  /js/flowtime.js
  /js/love.min.js
  /js/love.src.js
/music
  /music/saveme.mp3
  /music/lovebgm.mp3
index.php
love.php
loveNote.txt
loveTpl.html

/2014 用于存放生成的静态页面，若更改，请同时修改love.php里的路径
/js/love.min.js 字段获取js压缩文件 /js/love.src.js 是未压缩的
love.php 核心处理文件，love.min.js传参给此文件处理并生成相应静态页面
loveNote.txt 数据记录
loveTpl.html 页面模版文件 love.php生成的页面以此文件为模版

程序运行原理

给页面文字添加span标签，设置id="text-xx"唯一属性，使用contenteditable="true"，开启该元素的编辑模式，用jQuery属性.click()判断点击，用.text()返回此元素的文本内容，并用正则进行判断内容是否合法，然后通过AJAX POST给php处理，php对传入的参数进行过滤，然后读取模版文件，替换模版文件对应内容，保存为新文件并记录操作，最后返回数据给前端，前端处理数据并更新页面。