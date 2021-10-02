Lambda连接VPC
=============

## 知识点

* 使用Lambda连接到VPC

## 实战演习

>看图说话

+ 修改Lambda执行角色权限
  - KomaLambdaRole
    * AWSLambdaVPCAccessExecutionRole
+ 建立安全组
  - Name: SG-Lambda
    * 入站规则: 无
    * 出站规则: 所有流量
+ 修改WEB安全组
  - 加入允许SG-Lambda访问80端口
+ 建立Lambda函数
  - Name: KomaVPCLambda
  - VPC:  deeplearnaws-vpc
  - SubNet: web-1a, web-1c
  - SG: SG-Lambda
  - 创建函数会花一点时间
    * 消息: 已成功创建函数 KomaVPCLambda。现在，您可以更改其代码和配置。要使用测试事件调用您的函数，请选择“Test”。
+ 编写测试函数
+ 确认执行结果

## 操作步骤

### KomaVPCLambda

```javascript
const http = require ('http')
exports.handler = function(event, context) {
    // 访问局域网内WEB服务器
    http.get("http://172.16.10.177", function(res) {
        console.log("服务器响应代码: " + res.statusCode);
    }).on('error', function(e) {
        context.done('error', e);
    });
};
```

## 小马部落

https://discord.gg/VSKw72P

## 课程文件

+ 小马部落Discord专区共享

## 小马视频频道

http://komavideo.com
