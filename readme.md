## System某块

## 引用方式

### 1,复制dll文件到ext system 目录下。 模块dll文件（System.dll） ，其它dll文件（无）

### 2，在module.json文件中增加

```
"system":{"dll":"ext/system/System.dll","class":"WenshiModule.SystemModule","methods":"alert,ajax,setRunningValue,getRunningValue"}

```

## 方法列表

### 1, alert

参数列表


参数|意义|默认
---|---|---
msg|消息内容|必填
title|标题内容| 默认为 "提示"

案例

```
 JsBridge.require("system").alert({"msg":"这是提示消息"});//方法一
  JsBridge.require("system").alert("这是提示消息");//方法二
```
### 2, ajax

参数列表


参数|意义|默认
---|---|---
method|类型|默认 "POST"
url|请求地址| 必填
dataType|返回类型| 默认 “json”,支持 json,text
data|post请求参数|post请填写参数

案例

```
 JsBridge.require("system").ajax(
			 {
				url:"http://api.master.bigdata_guiji.wenshi.jt/token/getToken",
				"method":"post",
				// dataType:"json",
				data:{
					phone:"zhagnsan",
					password:"1111111",
					imei:"333333"
					}
			 },function(data){
				alert(data.body.msg);
			});
```

### 3, setRunningValue  设置运行时候变量，可在多html页面中共享

参数列表


参数|意义|默认
---|---|---
key|变量name| 必填
value|值| 必填
 

案例

```
 JsBridge.require("system").setRunningValue({"key":"username","value":"zhangsan"});//方法一
 
 JsBridge.require("system").setRunningValue({"username":"zhangsan"});//方法二
 JsBridge.require("system").setRunningValue({"username":"zhangsan","age":"18"});//多变量设置
```

### 3, getRunningValue   

参数列表


参数|意义|默认
---|---|---
key|变量name| 必填
 
 

案例

```
 JsBridge.require("system").getRunningValue({"key":"username"});//方法一
  JsBridge.require("system").getRunningValue("username");//方法二
```

### 4, pwd   

当前文件目录


参数|意义|默认
---|---|---

 
 

案例

```
 JsBridge.require("system").pwd();
```


### 5, getModuleConfig   

参数列表


参数|意义|默认
---|---|---
name|某块名称| 必填
 
 

案例

```
 JsBridge.require("system").getModuleConfig({"name":"system"});//方法一
  JsBridge.require("system").getModuleConfig("system");//方法二
```


### 6, getPathInModuleConfig   

参数列表


参数|意义|默认
---|---|---
name|某块名称| 必填
 key|键| 必填
 

案例

```
 JsBridge.require("system").getPathInModuleConfig({"name":"system","key":"image_dir"});
```

### 7, parseHtmlToPdf   

解析模板并生成pdf文件

参数列表


参数|意义|默认
---|---|---
url|本地文件地址| 必填
 data|数据| 必填
 toFile|pdf绝对路径|
 pageSize|pdf大小A43|
 

案例

```
  JsBridge.parseHtmlToPdf({
 "url":"e:/1/1.html",
 "data":{
	"name":"张三",
	"age":"19sui"
 },
 "pageSize":"A4",
 "toFile":"e:/1/aaaaa.pdf"
 },function(ret){
 alert(ret);
 
 })
```

其中1.html

```
你好{{name}},我的年龄是:{{age}},
你好{{name}},我的年龄是:{{age}}
```

### 8 getRootConfig,getPathInRootConfig
