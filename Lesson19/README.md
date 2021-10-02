使用Lambda层(Lambda Layers)
==========================

## 知识点

* 使用Lambda层, 把共同的操作抽象出来

## 实战演习

>看图说话

+ 建立层函数
+ 打包上传层函数
  - Name: KomaLambdaLayer
+ 建立Lambda函数，调用层函数
  - Name: KomaRunLayerLambda
  - 添加层 / 自定义层 / KomaLambdaLayer

## 操作步骤

### 建立层函数

```bash
$ mkdir myLambdaLayer
$ cd myLambdaLayer
$ npm init -y
$ nano utils.js
...
...
$ zip myLambdaLayer.zip utils.js
```

*utils.js*

```javascript
exports.add = function (x, y) {
    return x + y;
}
// console.log(this.add(10, 13))
```

### 建立Lambda函数，调用层函数

```javascript
const utils = require("/opt/utils")
exports.handler = async (event) => {
    console.log(utils.add(10, 20))
    const response = {
        statusCode: 200,
        body: JSON.stringify('Hello from KomaRunLayerLambda!'),
    };
    return response;
};
```

## 小马部落

https://discord.gg/VSKw72P

## 课程文件

+ 小马部落Discord专区共享

## 小马视频频道

http://komavideo.com
