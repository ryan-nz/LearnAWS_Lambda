添加外部依赖
==========

## 知识点

* 在Lambda函数中调用第三方库(cowsay)

## 实战演习

+ 本地开发Node.js - Lambda函数
+ 添加第三方库
+ 上载Lambda函数

## 操作步骤

### 本地开发Node.js - Lambda函数

```bash
$ mkdir mylambda
$ cd mylambda
$ npm init -y
$ npm install cowsay --save
$ nano index.js
...
...
$ zip -rq mylambda.zip index.js package.json node_modules/
# 建立函数
$ aws lambda create-function --function-name KomaCowsayLambda \
    --zip-file fileb://mylambda.zip \
    --handler index.handler \
    --runtime nodejs14.x \
    --timeout 10 \
    --memory-size 128 \
    --role arn:aws:iam::976591345876:role/KomaLambdaRole
# 更新函数
$ aws lambda update-function-code \
    --function-name KomaCowsayLambda \
    --zip-file fileb://mylambda.zip \
    --publish
```

*index.js*

```js
var cowsay = require("cowsay");

exports.handler = async (event) => {
    console.log("你好, AWS Lambda函数。")
    var message = cowsay.say({
    	text : "我是一只牛",
    	e : "oO",
    	T : "U "
    });
    console.log(message)
    return message
};

/*
// 本地测试
var message = cowsay.say({
	text : "我是一只牛",
	e : "oO",
	T : "U "
});
console.log(message)
*/
```

## 小马部落

https://discord.gg/VSKw72P

## 课程文件

+ 小马部落Discord专区共享

## 小马视频频道

http://komavideo.com
