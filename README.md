
## 常用模块收集 ##

### 1.截取url上面的参数 ###

	function GetQueryString(name)
	{
	    var reg = new RegExp("(^|&)"+ name +"=([^&]*)(&|$)");
	    var r = window.location.search.substr(1).match(reg);
	    if(r!=null)return  unescape(r[2]); return null;
	}
	
	参数：
 		1 . name : url上传递的参数名称
	注：
		GetQueryString(参数)  ：  传递参数是需要给 参数 加上引号传递
		
		
### 2.媒体查询 @media ###

	@media screen and (max-width: 320px) {
		.commodityListBox ul li{
			width: 75px;
		}
	}
	
### 3.Bootstrap省市区三级联动菜单 ###

	<div class="d_content_nr">
		<p>收 货 地 址</p>
		<form class="form-inline">
		  <div data-toggle="distpicker">
			<div class="form-group">
			  <select class="form-control" id="province1"></select>
			</div>
			<div class="form-group">
			  <select class="form-control" id="city1"></select>
			</div>
			<div class="form-group">
			  <select class="form-control" id="district1"></select>
			</div>
		  </div>
		</form>
		<input id="dizhixiangqiang" type="text" name="d_username" placeholder="请填写详细地址">
	</div>
	
### 4.后退按钮 return 上一级 ###

	historyPage(1,"titHeadBack","home.html");
	/**
	* [historyPage 单击后退按钮事件]
	* @param {[type]} classType [类别 class 和 id 标识 1->class 2->id]﻿
	* @param {[type]} id [class或id 名称]
	* @param {[type]} url [第一次进来是返回的 url]
	* @return {[type]} [description]
	*/
	function historyPage(classType,classname,url){
	    // classType: 1->class 2->id
	    var classT; //选择器类型
	    if(classType==1){
	        classT="."+classname;
	    }else if(classType==2){
	        classT="#"+classname;
	    }
	    $(classT).on("click",function(){
	        if(window.history.length > 1){ 
	            window.history.back( -1 ); 
	        }else{ 
	            location.href=url;
	        } 
	    })
	}
	
	参数：
		1 . classType : 选择器类型  
		                 值 : 1--->表示class    2--->表示id
		2 . classname : 选择器名称
		3 . url : 指定要调转的 URL
	按钮返回事件 方法 
		A页面跳转的B页面 ----单击返回按钮，返回到A页面
		直接进入B页面---为避免返回跳转出错  指定跳转到设定页面
		 
		积分(正负)  剩余积分()  积分说明
		
### 5.input 限制输入类型 onkeyup ###
	<input type="text" placeholder="输入金额" value="" onkeyup="this.value=this.value.replace(/[^0-9-]+/,'');" 
	onafterpaste="this.value=this.value.replace(/\D/g,'')" maxlength = 6>
	onkeyup:限制只能
	
### 6.vue.js 数据绑定  循环 ###
	*****
		使用前需要引入 vue.js 
   		<script type="text/javascript" src="js/vue.min.js"></script>
   	*****
   		
   	*****
   		图1 css
			解决 {{xxxxx}} 直接显示出来
			页面数据加载完成后才会显示出来  未加载完事页面绑定数据区域显示空白
		[v-cloak] {
		    display: none;
		}
   	*****
   	
   	*****
   		图2 html
			页面绑定数据使用  {{数据集 . 字段名}}
			v-cloak 使用在有 数据加载 的元素标签内部，使用时候该 元素 中的内容会在数据请求过程中显示为空白，避免页面直接显示{{xxx}}
		<div class="right">{{dataMsg.idcard}}</div>
		<div class="nrList" v-cloak></div>
   	*****
   	
   	*****
   		图3 js
			使用Vue.js之前需要先 new 一个Vue对象
			实例化时以对象形式传递参数或函数方法
			必须参数
			    el : 自定义的 id
			    data : 传递数据对象 页面 {{}}中使用    注：可以传递单个值和对象
		// vuejs 数据绑定
		var vm=new Vue({
		    el:'#app',
		    data:{
		       dataMsg:data.list
		    }
		});
   	*****
   	
### 7.meta 模式 ###
	<!--优先使用最新版本 IE 和 Chrome-->
	<meta http-equiv="X-UA-Compatible" content="IE=edge,chrome=1" />
	<!--360 使用Google Chrome Frame-->
	<meta name="renderer" content="webkit">
	<meta name="viewport" content="width=device-width,initial-scale=1.0,user-scalable=no" />
	<!-- 禁止百度转码 -->
	<meta http-equiv="Cache-Control" content="no-siteapp" />
	<!--状态栏的背景颜色-->
	<meta name="apple-mobile-web-app-status-bar-style" content="black-translucent" />
	<!-- uc强制竖屏 -->
	<meta name="screen-orientation" content="portrait">
	<!-- QQ强制竖屏 -->
	<meta name="x5-orientation" content="portrait">
	<!-- UC应用模式 -->
	<meta name="browsermode" content="application">
	<!-- QQ应用模式 -->
	<meta name="x5-page-mode" content="app">
	
### 8.Bootstrap省市区三级联动菜单 ###
	<div class="d_content_nr">
		<p>收 货 地 址</p>
		<form class="form-inline">
		  <div data-toggle="distpicker">
			<div class="form-group">
			  <select class="form-control" id="province1"></select>
			</div>
			<div class="form-group">
			  <select class="form-control" id="city1"></select>
			</div>
			<div class="form-group">
			  <select class="form-control" id="district1"></select>
			</div>
		  </div>
		</form>
		<input id="dizhixiangqiang" type="text" name="d_username" placeholder="请填写详细地址">
	</div>
	
### 9.媒体查询 @media ###
	@media screen and (max-width: 320px) {
		.commodityListBox ul li{
			width: 75px;
		}
	}
	
### 10.URL  参数  获取值 ###
	参数：
	 1 . name : url上传递的参数名称
	注：
	 GetQueryString(参数)  ：  传递参数是需要给 参数 加上引号传递
	 
	 // -------------------截取url上面的参数-----------------------
	function GetQueryString(name)
	{
	    var reg = new RegExp("(^|&)"+ name +"=([^&]*)(&|$)");
	    var r = window.location.search.substr(1).match(reg);
	    if(r!=null)return  unescape(r[2]); return null;
	}﻿
   	
   	﻿