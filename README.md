#mobilePit

Pit the front of mobile development

这个项目记录移动端HTML/CSS/JS开发所碰到的问题及小技巧

##非首屏JS绑定的事件无法触发（**android下微信**）

对有需要触发JS事件的元素其CSS属性里增加 **-webkit-transform: translate3d(0,0,0)** 方可解决

##audio元素音频文件无法预加载导致播放延迟

audio的autoplay属性无法生效，系统为用户手机节省流量默认行为。 如果需要预加载则从代码逻辑上先播放后迅速暂停播放从而实现触发播放行为而实现预加载，实际意义上则不会出现声音播放。

如：
<pre>
var music = {
        obj:null,
        create:function(){
            music.obj =  new Audio();
            music.obj.preload= 'auto';
            music.obj.type = 'audio/mpeg';
            var source = document.createElement('source');
            source.src = 'http://mobilegame.tencent.com/act/a20140723invite/crack.mp3';
            music.obj.appendChild(source);
        },
        play:function(){
            music.obj.play();
        },
        stop:function(){
            music.obj.pause();
        }
    };
music.create();
music.play();   //播放
music.stop();   //暂停

-------

然后在适当的地方   music.play();  播放。
</pre>
