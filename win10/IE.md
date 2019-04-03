#01 -老ASP系统在win10上用IE的时候遇到"_doPostBack is not function"之类的问题.

##reason: 
       例如"ASP:LinkButton"之类的控件会尝试_doPostBack方法,然而因为WinServer服务器时根据请求的User-Agent(浏览器)的不同来采取不同的解析方式,而在IE7以后的版本中,解析方式不同了,导致获得不了_doPostBack方法,网站报错.

##baidu: 
       1.Microsoft .net 2.0 sp2,3.0 sp1,4.0 有BUG,有补丁可以修复,但是补丁已经不提供了.
       官方链接:https://support.microsoft.com/en-us/help/2600100/a-hotfix-is-available-for-the-asp-net-browser-definition-files-in-the

##isolution: 
          step 1. 查看并修改组策略-计算机配置-管理模板-Internet Explorer-自定义用户代理字符串,设置为"MSIE 7.0".
          step 2. 打开IE,在兼容性视图设置中加入要访问的网站.
          ps: IE11浏览器在兼容性视图下会假装成IE7,这个可以在User-Agent中看到,而某些软件(大数字浏览器)可能会更改组策略中的自定义用户代理字符串为MSIE 9.0,导致兼容性视图设置无效.

                  
          
          