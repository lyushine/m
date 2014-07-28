#mobilePit

Pit the front of mobile development

这个项目记录移动端HTML/CSS/JS开发所碰到的问题及小技巧

##除第一页外JS事件不能触发（**android下微信**）

对有需要触发JS事件的元素其CSS属性里增加 **-webkit-transform: translate3d(0,0,0)** 方可解决
