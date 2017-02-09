## 5.1	Dom基础


**DOM(Document Object Model)**： 文档对象模型文档本质上就是一个文本，就是字符串，js引擎会把文档解析成js中对象，提供给很多方法，根据提供的属性或方法就可以操作对应元素.


## 5.2 DOM节点

组成DOM树最基本的单元是：**节点**。

节点有许多不同的类型
						
### 节点类型
	1	ELEMENT_NODE                       元素节点
	2	ATTRIBUTE_NODE						属性节点
	3	TEXT_NODE							文本节点
	4	CDATA_SECTION_NODE
	5	ENTITY_REFERENCE_NODE
	6	ENTITY_NODE
	7	PROCESSING_INSTRUCTION_NODE
	8	COMMENT_NODE						注释节点
	9	DOCUMENT_NODE					文档节点
	10	DOCUMENT_TYPE_NODE
	11	DOCUMENT_FRAGMENT_NODE
	12	NOTATION_NODE
			
### 常用节点类型
	节点.nodeType  获取的是用数字的形式表示节点类型		
	元素节点    1      
	属性节点    2		
	文本节点    3		
	注释节点    8		
	文档节点    9		
		

### 查看节点类型 
**方法**：node.nodeType

**语法**: 节点.nodeType  获取的是用数字的形式表示节点类型
		
**实例**：

	window.onload = function(){
		var oDiv = document.getElementById("oDiv");

		//console.log( oDiv.nodeType );  // 1 

		//oDiv.id
		//attributes 元素身上属性集合
		//console.log( oDiv.attributes[0].nodeType ); //2
		//console.dir( oDiv.childNodes[0].nodeType );
		//console.log( oDiv.childNodes[0].nodeType );
		console.log( document.nodeType );
	};

### 查看节点名称
**方法**：节点.nodeName

		元素节点名称  元素标签名字 大写
		属性节点名称  属性名字
		文本节点名称  #text
		注释节点名称  #comment
		文档节点名称  #document
**实例**：

 	var oDiv = document.getElementById("oDiv");	
	console.log( oDiv.attributes[0].nodeName );
	

### 节点的层级关系
	>父子级关系
	>兄弟关系
	>祖先级关系
	>子孙级关系

### parentNode

**作用**：获取指定节点的父节点。

**语法**：node.parentNode			

*如果指定节点没有父节点，则返回 null。*



### children

**作用**：获取指定元素的子节点

**语法**：元素.children

**返回值**: 返回的是子元素的集合，类数组



### firstElementChild
**作用**：获取指定元素下的第一个子节点

**语法**：元素. firstElementChild

### lastElementChild
**作用**：获取指定元素下的最后一个子节点

**语法**：元素. lastElementChild

### previousElementSibling
**作用**：获取指定元素的上一个兄弟节点

**语法**：元素. previousElementSibling

### lastElementChild
**作用**：获取指定元素的下一个兄弟节点

**语法**：元素. previousElementSibling
	
### offsetParent
**作用**：获取与指定元素最近的有定位属性的祖先节点

*一个元素祖先节点没有一个是定位的，默认offsetParent是body*

**语法**：元素. offsetParent

### offsetLeft/offsetTop
**作用**：获取指定元素与其最近的有定位属性的祖先节点的距离(偏移量)*获取的值是相对于offsetParent的*
	    
**语法**：元素. offsetLeft/offsetTop

### offsetLeft/offsetTop

**作用**：方法返回元素的大小及其相对于视口的位置。

**语法**：元素. node.getBoundingClientRect()：

**返回值**

	{
		left: 211,  元素左边到浏览器左边的距离
		top: 11,    元素上边到浏览器上边的距离
		right: 311, 元素右边到浏览器左边的距离
		bottom: 111, 元素下边到浏览器上边的距离
		width: 100,
		height:100
	}























## 5.5	表格表单 ##

1. **获取表格**

		table.tHead							获取到表格头部
		table.tBodies[n]					获取到表格主体
		table.tFoot							获取到表格尾步
		table.tBodies[n].rows[n]  			获取某一行
		table.tBodies[n].rows[n].cells[n]	获取其中某个格

2. **获取表单**

		E.name	获取到element
		E.value	获取到element的值(用于text/radio/checkbox/select/textarea)
	

3. **表单事件**

		E.onchange 	当element有变化的时候会触发这个事件，一般用在select
		E.oninput 	当输入框里的内容有变化的时候触发
		E.onsubmit 	当表单被提交的时候会触发,当点击提交按钮的时候会触发，只能添加给form对象
		E.onreset 	当表单被重置的时候触发，当点击重置按钮的时候会触发，只能添加给form对象


4. **表单方法**

		Form.reset() 	作用为重置表单，会触发onreset事件，只能给form对象添加
		Form.submit()   作用为提交表单，不会触发onsubmit事件，只能给form对象添加


## DOM节点

----------

- DOM（Document Object Model ）文档对象模型
- 文档本质上就是一个文本，就是字符串，js引擎会把文档解析成js中对象，提供给很多方法，根据提供的属性或方法就可以操作对应元素

### 节点类型  

----------

1. E.nodeType  获取节点类型				 节点名称
		ELEMENT_NODE 			元素节点  	元素名大写
2.	ATTRIBUTE_NODE			属性节点	属性名字


	1	TEXT_NODE				文本节点	#text
	2.	CDATA_SECTION_NODE		
	3.	ENTITY_REFERENCE_NODE	
	4.	ENTITY_NODE
	5.	PROCESSING_INSTRUCTION_NODE
	6.	COMMENT_NODE			注释节点	#comment
	7.	DOCUMENT_NODE			文档节点	#document
	8.	DOCUMENT_TYPE_NODE
	9.	DOCUMENT_FRAGMENT_NODE
	10.	NOTATION_NODE

### 节点之间的关系

----------

- html 是根节点
- 父级关系		
- E.parentNode				获取父级节点
- 子级关系		
- E.childNodes				标准，获取到所有的子节点
- E.children					常用，只获取到子元素节点，是类数组
- E.firstChild 				获取到第一个子元素节点（I E下的方法)
- E.firstElementChild			获取到第一个子元素节点
- E.lastElementChild			获取到最后一个子元素节点
- 			————————当没有获取到时，返回值为null
- 兄弟关系
- E.previousElementSibling	获取到前一个兄弟元素节点
- E.nextnextElementSibling	获取到后一个兄弟元素节点
- ————————当没有获取到时，返回值为null
- 祖先级关系
- 子孙级关系

### 【DOM 方法】

----------

- document.getElementById("")			获取元素/节点	
- document.createElement("标签名")	创建元素/节点	
- E.appendChild(newElement)			追加元素/节点	在元素里追加一个新的子节点
- E.insertBefore(newElement,targetElement)	插入元素/节点	在元素里某个子节点前插入一个新的子节点。   两个参数都必须写，第二个可以为null，否则报错。当为null时在末尾追加
- E.replaceChild(newElement,targetElement)	替换元素/节点	在元素中用新的子节点替换掉某个子节点。	两个参数都必须写，并且都必须存在，否则报错。
- E.removeChild(targetElement)				删除元素/节点	在元素中删除某个子节点
- E.cloneNode(boolean)				克隆元素/节点	克隆某个节点,当实参为true时，包含子节点，当实参为false时，不包含子节点。默认为false。

- E.getAttribute("属性名")			获取行间属性	获取到元素的行间属性对应的值
- E.setAttributr(key,value)			设置行间属性	给元素添加行间属性
- E.removeAttribute(key)				删除行间属性	删除元素的某个行间属性


- E.offsetparent		获取到元素最近的带有定位属性的父级或祖先级
- E.offsetLeft		获取到元素左边框外缘距离offsetparent左边框内缘的距离		ps.浮动转定位时，注意清除margin
- E.offsetTop			获取到元素上边框外缘距离offsetparent上边框内缘的距离	
- E.offsetHeight		获取到元素所占高度			ps.包含border
- E.offsetWidth		获取到元素所占宽度

- E.getBoundingClientRect		获取到元素本身的大小以及相对于视口的位置
{
 1. top:value,		元素上边框外缘到视口顶部的距离
 2. left:value,		元素左边框外缘到视口左侧的距离
 3. right:value,	元素右边框外缘到视口左侧的距离
 4. bottom:value,	元素下边框外缘到视口顶部的距离
 5. width:value,	元素本身的宽度		ps.包含padding，包含border
 6. height:value	元素本身的高度
}

- document.documentElement.clientWidth	获取到视口宽度
- document.documentElement.clientHeight	获取到视口高度

- document.documentElement.scrollTop		获取到页面被卷曲的高度  <适用IE，火狐>
- document.documentElement.scrollLeft		获取到页面被卷曲的宽度		可读可写


- document.body.scrollTop 				获取到页面被卷曲的高度  <适用chrome>
- document.body.scrollLeft				获取到页面被卷曲的宽度		可读可写

- E.clientWidth							获取到元素所占宽度			ps.包含padding，不包含border
E.clientHight
							获取到元素所占高度













## ==BOM 知识点==
##### BOM (Browser Object Model)浏览器对象模型
##### 方法有：
    1. window.open()打开一个新窗口
        调用：
            (1). 直接调用 火狐和谷歌会阻止(安全考虑)， IE直接打开新窗口
    2. 事件中调用 都可以直接打开新窗口
        注意：
            在ie下给document添加事件处理程序的时候，要加上window.onload
        参数： (3个) 都是可选的       
        参数1： 指定要打开的页面地址------
               本地页面地址或者远程页面地址
        参数2： 
            打开方式：
                _blank 在新窗口打开
                _self 在当前窗口打开
                iframName
                iframe的name，指定在哪一个iframe打开
        参数3:   浏览器的窗口特征 （宽，高，窗口位置等）
                 如果规定了浏览器的特征，第二个参数是_blank
                 
###### 参考: http://www.w3school.com.cn/jsref/met_win_open.asp 


1. window.location --- 获取地址栏信息 
   location是一个对象
    
        属性：
            (1). window.location.href
                     获取当前窗口地址栏中的地址
                    可读可写

            (2). window.location.search
                 地址栏查询信息 
                 （问号？到#号之间的所有内容）包含问号？
			   search改变的时候会刷新页面
                  可读可写
            (3).  window.location.hash 
                     锚点信息（#号后面的所有内容）
				  包含#号
			      hash改变的时候不会刷新页面
			      可读可写 
			      

#####  滚动条：
    滚动条滚动距离
        DOM: 都兼容 
        
             document.documentElement.scrollTop||document.body.scrollTop
             可读可写
             
        BOM: 只有高版本兼容
	         window.pageXOffset     
		 window.pageYOffset    
		 只能读不能够写 
		 window.scrollTo(x,y);  可写
		 
	   事件: window.onscroll  滚动条滚动触发的事件		
	     	 window.onresize  窗口大小改变的时候触发的事件 
		 可视区的宽高
	          
	    DOM: document.documentElement.clientWidth/clientHeigh
	    BOM: window.innerWidth / window.innerHeight
	    包含滚动条的宽度
	    
	   滚动距离:
	    DOM: 
	        document.documentElement.scrollLeft|| document.body.scrollLeft
	        document.documentElement.scrollTop || document.body.scrollTop
	   
	    BOM: window.pageXOffset / window.pageYOffset
	    设置滚动条滚动距离window.scrollTo(x,y);
	    
	    文档高度：
	         所包含的内容的高度
	         box.scrollHeight/scrollWidth
	         内容的高度，如果body中的内容没有可视区域的高度高，document.body.scrollHeight取到的值就是可视区域（文档）的高度
	   scrollHeight：
	        滚动条可滚动的部分还要加上border的高度，加上横向滚动条不可用的高度
	   BOM事件:
	        window.onscroll
	            滚动条滚动的时候触发的事件
	       window.onresize
	            当窗口改变大小的时候触发的事件
	            
