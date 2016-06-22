##RESTFul以及curl的介绍
* 什么是RESTFul
* CURL命令的讲解
* Elasticsearch API文档查看

### 什么是RESTFul
* API : Application Programming Interface的缩写，中文意思就是应用程序接口
* XML : 可扩展标记语言，是一种与程序之间传输数据的标记语言
* JSON : 英文javascript object notation的缩写，它是一种新型的轻量级数据交换格式


* GET : 用来获取资源
* POST : 用来新建资源 （也可用来更新资源）
* PUT : 用来更新资源
* DELETE : 用来删除资源


### CURL命令的讲解
* 就是以命令的方式来执行HTTP协议的请求工具
* 可以通过CURL操作HTTP的GET、POST、PUT、DELETE方法

### CURL相关操作
* 访问一个网页
    curl www.socialmaster.com
* 显示http response的头信息
    curl -i www.socialmaster.com
* 显示一次http请求的通信过程
    curl -v www.socialmaster.com
* CURL 执行GET/POST/PUT/DELETE操作
    curl -X GET/POST/PUT/DELETE www.socialmaster.com

### ES API
https://www.ellastic.co/guide/elasticsearch/reference/current/docs.html

