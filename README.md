
## 常用模块收集 ##

1.截取url上面的参数

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
		
		
2.媒体查询 @media

	@media screen and (max-width: 320px) {
		.commodityListBox ul li{
			width: 75px;
		}
	}﻿