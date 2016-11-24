---
layout: post
title:  "javascript面向对象精要读书笔记"
date:   2016-11-24 14:08:07 +0800
categories: jekyll update
tags: [面向对象]
---
javascript面向对象精要读书笔记   
第一章原始类型和引用类型
第二章函数
一、字符串截取方式
{% highlight ruby %}
function paramOfUrl(url) {
	url = url || location.href;
	var paramSuit = url.substring(url.indexOf('?') + 1).split("&");
	var paramObj = {};
	for (var i = 0; i < paramSuit.length; i++) {
		var param = paramSuit[i].split('=');
		if (param.length == 2) {
			var key = decodeURIComponent(param[0]);
			var val = decodeURIComponent(param[1]);
			if (paramObj.hasOwnProperty(key)) {
				paramObj[key] = jQuery.makeArray(paramObj[key]);
				paramObj[key].push(val);
			} else {
				paramObj[key] = val;
			}
		}
	}
	return paramObj;
}
{% endhighlight %}

二、正则表达式方式    
{% highlight ruby %}
function getQueryString(name) {
	var reg = new RegExp("(^|&)" + name + "=([^&]*)(&|$)", "i");
	var r = window.location.search.substr(1).match(reg);
	if (r != null) return decodeURIComponent(r[2]);return null;
}
{% endhighlight %}




