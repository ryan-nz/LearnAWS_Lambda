# 建立第一个Lambda函数

==================

## 知识点

+ 使用管理控制台, 建立第一个Lambda函数

## 实战演习

>看图说话

+ 建立Lambda执行角色
  + Name: KomaLambdaRole
    + AWSLambdaBasicExecutionRole
+ 建立一个Lambda函数
  + Name: KomaLambdaFunc01
  + Lang: Node.js
+ 建立测试事件
  + Name: KomaLambdaFunc01TestEvent
+ 执行测试事件
+ 确认执行日志

## 函数代码

```javascript
exports.handler = async (event) => {
    // 日志输出
    console.log("你好, AWS Lambda函数。")
    const response = {
        statusCode: 200,
        body: JSON.stringify('Hello from KomaLambdaFunc01!'),
        // 输出接收到的参数
        event: event,
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
