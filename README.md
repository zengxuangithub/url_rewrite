# url重写功能
  可以用于实现伪静态网站
  
## 步骤
1  -   下载jar包  在tuckey.com 网站 放入项目三方库中  如lib    
   -    下载urlrewrite.xml   网站同上  放入WEB-INF 路径下
   
2  在项目web.xml 中配置filter

```
 <filter>
    <filter-name>UrlRewriteFilter</filter-name>
    <filter-class>org.tuckey.web.filters.urlrewrite.UrlRewriteFilter</filter-class>
</filter>
<filter-mapping>
    <filter-name>UrlRewriteFilter</filter-name>
    <url-pattern>/*</url-pattern>
    <dispatcher>REQUEST</dispatcher>
    <dispatcher>FORWARD</dispatcher>
</filter-mapping>

```


3  在urlrewrite.xml中修改url的 重写规则

```
	<rule>
        <note>
           	this is description
        </note>
		<!--过滤所有后缀名为.html 的请求-->
        <from>/(\w*).html</from>
		<!--将其forward 到index.jsp 页面-->
        <to type="forward">/index.jsp</to>
    </rule>
```