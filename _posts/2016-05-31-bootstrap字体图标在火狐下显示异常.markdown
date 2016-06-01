---
layout: post
title:  "bootstrap字体图标在firefox下显示异常"
date:   2016-05-31 21:23:07 +0800
categories: jekyll update

---
今天在使用bootstrap的过程中遇到问题，使用本地bootstrap.css时Firefox浏览器glyphicons显示异常，其他浏览器正常。
原因是Firefox对于本地文件也进行了同源访问的安全设置。解决方法有两种：第一，通过CDN引用bootstrap.css；第二，
Firefox对于本地文件也进行了同源访问的安全设置,配置参数是：security.fileuri.strict_origin_policy。
通过about:config修改该参数值为“false”即可。这样可以使本地项目正常使用bootstrap的glyphicons，而在服务中使用是不会出现这个问题的。
[解决方法]

[解决方法]: http://stackoverflow.com/questions/19085942/boootstrap-glyphicons-firefox-issues
