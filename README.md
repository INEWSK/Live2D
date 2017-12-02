原文出自一个大佬的博客，猫与向日葵。[阅读原文](https://imjad.cn/archives/lab/add-dynamic-poster-girl-with-live2d-to-your-blog-02 "阅读原文")  
本文对于原文有删改。  

嘛，不少人对这个 Live2D 看板娘很感兴趣呢！  
纷纷让我写文章，而学长也是懒癌晚期，一直拖到现在 ~  

好了，还是准备开始我们的教程吧！
俗话说：“授人以鱼不如授人以渔”，但是说这个“渔”比较难教，还是给条“鱼”你完事了。

### 准备工作
首先到我的 Github 去下载整理后的 Live2D 代码，毕竟整理后的话好下手 ~

下载后解压代码到你的博客网站根目录去。（目录位置可以自定义）

然后把解压出来的文件夹改名为：live2d 。

### 正式开工
在你博客程序头部文件（header）引入界面样式，在 head 标签内插入如下代码：
```html
<link rel="stylesheet" href="/live2d/css/live2d.css" />
```

在你博客程序页脚文件（footer）引入脚本，在 body 标签结束前插入如下代码：
```html
<script type="text/javascript">
    var message_Path = '/live2d/'
    var home_Path = 'https://haremu.com'  //此处修改为你的域名
</script>
<script type="text/javascript" src="/live2d/js/live2d.js"></script>
<script type="text/javascript" src="/live2d/js/message.js"></script>
<script type="text/javascript">
    loadlive2d("live2d", "/live2d/model/tia/model.json");
</script>
```

在合适的页面位置插入 Live2D 看板娘的元素，可以放在底部：
```html
<div id="landlord">
    <div class="message" style="opacity:0"></div>
    <canvas id="live2d" width="280" height="250" class="live2d"></canvas>
</div>
```

鼠标放在页面某个元素上时，需要 Live2D 看板娘提示的请修改 message.json 文件。

**示例：**
```json
{
    "mouseover": [
        {
            "selector": ".title a",  //此处修改为你页面元素的标签名
            "text": ["要看看 {text} 么？"]  //此处修改为你需要提示的文字
        },
        {
            "selector": "#searchbox",
            "text": ["在找什么东西呢，需要帮忙吗？"]
        }
    ],
    "click": [  //此处是 Live2D 看板娘的触摸事件提示
        {
            "selector": "#landlord #live2d",
            "text": ["不要动手动脚的！快把手拿开~~", "真…真的是不知羞耻！","Hentai！", "再摸的话我可要报警了！⌇●﹏●⌇", "110吗，这里有个变态一直在摸我(ó﹏ò｡)"]
        }
    ]
}
```

然后，刷新你的博客页面，看看效果吧！

注意路径别弄错了噢 ~
使用主题函数获取路径其实是很好的。

问：“为什么这个 Live2D 没有换装功能哎？”
答：“自己研究去。”

### 看板娘欣赏
![image](https://haremu.com/wp-content/uploads/2017/12/QQ%E6%88%AA%E5%9B%BE20171202210923.png)
![image](https://haremu.com/wp-content/uploads/2017/12/QQ%E6%88%AA%E5%9B%BE20171202210951.png)
