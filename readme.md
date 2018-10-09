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

