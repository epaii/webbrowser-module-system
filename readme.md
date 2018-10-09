## System某块

## 引用方式

### 1,复制dll文件到ext system 目录下。 模块dll文件（System.dll） ，其它dll文件（无）

### 2，在module.json文件中增加

```
"system":{"dll":'ext/system/System.dll',"class":"WenshiModule.SystemMoudle","methods":"alert"}

```

## 方法列表

### 1, alert

参数列表


参数|意义|默认
---|---|---
msg|消息内容|必填
title|标题内容| 默认为 "提示"

### 1, ajax

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