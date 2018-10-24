javascript

考点——知识——题目

js中的变量类型

值类型和引用类型

- 值类型
  undefined
  string
  number
  boolean
- 引用类型
  object:
  	{}
  	[]
  	null
  	function
- 强制类型转换
  字符串拼接
  ==运算符
  if语句
  逻辑运算符
  	判断是否是true还是false： console.log(!!a);
  
  
  

===与== 强制类型转换

JS中的内置函数

JS变量按照存储方式分为哪些类型

理解json

window.onload和DOMContentloaded  浏览器渲染

作用域

JS模块化

JS的基础算法

作用域和闭包

	执行上下文		

		自动会将函数声明 和函数表达式提前

	this

		在执行时，才能确认值

		

	作用域

	作用域链

	闭包

变量提升

	函数和声明会提前

this的几种场景

	作为构造函数

	作为对象属性

	作为普通函数

	call  直接用

	apply  要用[] 数组方式

	bind    （.bind({y:100})）

创建10个a 分别点击 分别弹出序号

作用域

闭包



异步和单线程

同步和异步

	

setTimeout

前端使用异步的场景

- 	在可能等待的情况需要异步
  - 不能像alert阻塞程序运行
  - 所以 等待的情况下 都需要异步
    定时任务：setTimeout  setInterval
    网络请求：ajax请求，动态IMG的加载
    	

    			var xhr=new XMLHttpRequest()
    
    			xhr.open("get",url)
    			
    			xhr.onreadystatechange=function(){
    	
    				if(xhr.readystatechange==4&&xhr.status==200)
                        {
                            document.getElementById("myDiv").innerHTML=xhr.responseText;
                        }
    			}
    			
    			xhr.send()
    

	事件绑定

日期

    function foematDate(dt){
        if(!dt){
        dt=new Date()
    }
        var year = dt.getFullYear()
        var month = dt.getMonth()+1
        var date = dt.getDate()
        if(month<10){
            month='0'+month
    }
        if(date<10){
            date='0'+date
    }
        return year+ '-' +month+'-'date //日期格式
    }
    var dt=new Date()
    var formatDate = formatDate(dt)
    console.log(formatDate)

Math

获取0-1之间的随机数Math.random()

    var random=Math.random()
    var random=random+'0000000000'
    var random=random.slice(0,10)
    console.log(random)



数组API

forEach:遍历所有元素

    var arr = ['a','b','c','d']
    arr.forEach(function(item,index){
        console.log(index,item)
    })



    function forEach(obj,fn)
    {
        var kry
        if(obj instanceof Array)
        {
            obj.forEach(function(item,index)
            {
                fn(index,item)
            })
        }
        else
        {
            for(key in obj)
            {
                if (obj.hasOwnProperty(key))
                {
                    fn(key,obj[key])
                }
            }
        }
    }
    var arr = [1,2,3,4]
    forEach(arr,function(index,item)
    {
        console.log(index,item)
    })
    var obj={x:100,y:200,z:300}
    forEach(obj,function(key,val)
    {
        console.log(key,val)
    })



every：判断所有元素是否符合条件

    var arr = [1,2,3,4]
    var result=arr.every(function(item,index){
       if(item<5){
           return true
       }
    })
    console.log(result)

some判断至少一个元素符合条件

    var arr = [1,2,3,4]
    var result=arr.some(function(item,index){
       if(item<3){
           return true
       }
    })
    console.log(result)

sort

})：排序

    var arr = [1,6,2,7,3,5,4]
    var arr2=arr.sort(function(a,b){
           return a-b //从小到大排序 反之 大到小
    })
    console.log(arr2)

map：对元素重新组装

    var arr = [1,2,3,4]
    var arr2=arr.map(function(item,index){
           return '<b>+item+</b>'
    })
    console.log(arr2)

filter：过滤符合条件的元素

    var arr = [1,2,3,4]
    var arr2=arr.filter(function(item,index){
    	   if(item>2){
               return true
    	   }
    })
    console.log(arr2) 

for in

    var obj = {
    	x:100,
    	y:200,
    	z:300
    }
    var key
    for (key in obj)
    	if(obj.hasOwnProperty(key))
    	{
            console.log(key,obj[key])
    	}

web-api

DOM（documen object model）

- dom树。
- 节点操作
  - 获取dom接点
        document.getElementById('id')//元素id
        document.getElementByTagName('div')//集合
        document.getElementByClassName('.bannerName')//集合
        document.querySelectorAll('p')//集合
        ......
  - attr属性（针对HTML标签）
        var pList=document.querySelectorAll('p')
        var p = pList[0]
        p.getAttribute('dataname')
        p.setAttribute('dataname','othername')
        p.getAttribute('style','othername')
        p.setAttribute('style')
  - DOM结构操作
    	新增节点
    		appendChild()
    	获取父元素
    		parentElement()
    	获取子元素
    		childNodes()
    	删除节点
    		removeChild()
  - property属性(对JS对象的属性的修改)
        var pList=document.querySelectorAll('p')
        var p = pList[0]
        console.log(p.style.width)//获取样式
        p.style.width='999px'//修改
        console.log(p.className)//获取类名
        p.className='otheName'//修改
        //获取nodeName和NodeType
        console.log(p.nodeName)
        console.log(p.nodeType)
    

BOM操作 （browser boject model）

浏览器类型

URL

- navigator
      var ua = navigator.userAgent
      var isChrome=ua.indexOf('Chrome')
      console.log(isChrome)
- screen
      console.log(screen.width)
      console.log(screen.height)
- location
      console.log(location.href)
      console.log(location.protocol)//http
      console.log(location.pathname)/demo/demo
      console.log(location.search)
      console.log(location.hash)
  
- history
      history.back()
      history.forward()	
  事件
  - 事件监听函数
        var btn = document.getElementById('btn1')
        btn.addEventListener('click',function(event)
        {
            var target
            if(selector){
            	target=e.target
            		if(target.matches(selector))
            		{
                        fn.call(target,e)
            		}
            	}
            	else{
                    fn{e}
            	}
        })
        
        function bindEvent(elem,type,selector,fn)
        {
            if(fn==null){
                fn=selector
                selector=null
            }
        }
        var a = document.getElementById('link1')
        bindEvent(a,'click',function(e){
            e.preventDefault()
            alert('clicked')
        })
    
  - 事件冒泡
    - 触发子事件，父事件也会触发
          var p1=document.getElementById('p1')
          var body = document.body
          bindEvent(p1,'click',function(e){
              e.stopPropagation()//阻止冒泡事件
              alert('激活')
          })
          bindEvent(body,'click',function(e){
              alert('取消')
          })
  - 代理
    - 代码简洁
    - 减少浏览器内存使用
        <div id='div1'>
        	<a href="#">a1</a>
        	<a href="#">a2</a>
        	<a href="#">a3</a>
        	<a href="#">a4</a>
        </div>
        var div1=document.getElementById('div1')
        div1.addEventListener('click',function(e){
            var target=e.target
            if(target.nodeName==='A')
            {
                alert(target.innerHTML)
            }
        })
    e.preventDefault()//阻止默认行为



Ajax

手写ajax

    var xhr=new XMLHttpRequest()
    xhr.open("GET","/url/demo",false)//false 为异步 不填默认同步
    xhr.onreadystatechange = function()
    {
        if(xhr.readyState==4&&xhr.status==200){//成功了且服务端返回成功
            console.log(xhr.responseText)//服务端返回内容
        }
    }
    xhr.send()

*IE兼容性问题（了解）

状态码（readyState）

- 0:未初始化，还没有调用send()方法
- 1:载入，正在发送请求
- 2:载入完成，已经接收到响应请求
- 3:交互, 正在解析响应内容
- 4:完成，解析完成，可以在客户端调用了
  status
  - 2xx—表示成功处理请求
  - 3xx—需要在重定向，浏览器直接跳转
  - 4xx—客户端请求错误，404
  - 5xx—服务器端错误

跨域

	浏览器有同源策略，不允许ajax访问其他域接口

	协议，端口，域名

跨域注意事项

	1.所有的跨域请求必须经过信息提供方允许

	2.如果未经允许获取到了，那是浏览器同源策略的bug

可以跨域的三个标签

- img
  - 用于打点统计，统计网站可能是其他域
- link
  - cdn
- script
  - cdn
  - 用于JSONP

JSONP

    	<script>
            var script=document.createElement("script")
                script.src = "url+ '&callback=' + funcName"
            document.body.appendChild(script)
    
            window[funcName] = function (data) {
            callback(data）
          }
        </script>
    
    
    	header('Content-Type: application/javascript');//服务器端
    



服务器端设置 http header

存储

- cookie
  - 本身用于客户端和服务器端通信
  - 但是有本地存储的功能
  - 容量为4kb
  - 所有http请求都带着
  - api简单，需要封装 document.cookie=...
- sessionStorage
  sessionStoragesetItem(key,value);sessionStorage.getItem(key);
- localStorage(常用)
  HTML5专门为存储而设计，最大5MB
  api简单易用
  localStorage.setItem(key,value);localStorage.getItem(key);
  注意：在IOS Safari隐藏模式下localStorage.getItem(key);会报错，建议使用try-catch
  区别
  容量
  是否会携带到ajax中（cookie所有都要带）
  api易用性（cookie要封装，其他两个可以直接用）

关于开发环境

IDE

- webstorm：大牛 逼格 大咖 
- sublime：普通 低调 
- vscode：文艺小清新
- atom：文艺小清新
  插件插件插件快捷键快捷键快捷键！！！

Git

网络Git服务器如 coding.net github.com

Git基本操作必须很熟练



常用Git命令

- git add
- git checkout
- git commit -m "xxx"
- git push orgin master
- git pull orgin master
- git branch
- git checkout -b xxx/git checkout xxx
- git merge xxx

模块化

- 不使用模块化
- 使用模块化
- amd
- commonjs



运行环境

浏览器通过访问链接得到页面的内容

通过绘制和渲染，显示出页面的最终样子

页面加载过程

从输入url到html的详细过程

	加载资源的形式

		输入url加载html

		www.demo.com

		加载html中的静态资源

		<script src="url"></script>

	加载一个资源的过程

		浏览器根据dns服务器得到域名的ip地址

		向这个ip的机器发送http请求

		服务器收到、处理并返回http请求

		浏览器得到返回内容

	浏览器渲染页面的过程

		根据HTML结构生成DOM tree

		根据CSS生成CSSOM

		将DOM和CSSOM整合成RenderTree

		根据RenderTree开始渲染和展示

		遇到<script>会阻塞渲染

window.onload和DOMContentLoaded

    

	

性能优化

原则：1、多使用内存、缓存或者其他方法

	    2、减少cpu计算，减少网络请求，减少I/O，减少硬盘读写

从加载页面和静态资源和页面渲染中入手

1、静态资源的合并压缩（例如：将三个JS文件合并成一个，在用工具使代码压缩）

2、静态资源缓存

3、使用cdn让资源加载更快

4、使用SSR后端渲染，数据直接输出到html中

渲染优化

1、CSS放前面，JS放后面

2、懒加载

    <img id = "img1" src="name1.png" data-realsrc="abc.png">
    <script type="text/javascript">
    	var img1 =document.getElementById('img1')
    	img1.src=img1.getAttribute('data-realsrc')
    </script>

3、减少dom查询

    var i
    for (i=0;i<document.getElementById('p').lenth;i++)
    {
        
    }
    /*********************************/
    var pList=document.getElementById('p')
    var i 
    for(i=0;i<pList.lenth;i++)
    {
        
    }

4、减少dom操作

    var listNode=document.getElementById('list')
    
    var frag=document.createDocumentFragment();
    var x,li;
    for (x=0;x<10;x++)
    {
        li=document.createElement('li');
        li.innerHTML = "List item" + x;
        frag.appendChild(li);
    }
    listNode.appendChild(frag);

5、事件节流

6、尽早使用DOMContentLoaded

安全性

XSS跨站请求攻击

XSRF跨站请求伪造
