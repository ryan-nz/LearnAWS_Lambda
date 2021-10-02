SQS触发Lambda函数
================

## 知识点

* 使用消息队列 SQS 触发 Lambda 函数

## 实战演习

>看图说话

+ 建立消息队列
  - Name: KomaSQS
+ 修改Lambda执行角色，增加SQS调用权限
  - KomaLambdaRole
    * AWSLambdaSQSQueueExecutionRole
+ 建立Lambda函数，接收处理SQS消息
  - Name: KomaSQSLambda
+ 增加Lambda触发器
  - SQS: KomaSQS
+ 从SQS发送消息
  - 你好，Lambda！我是SQS。
+ 确认处理日志

### Lambda函数

*KomaSQSLambda*

```javascript
exports.handler = async (event, context, cb) => {
    console.log("我是Lambda，我怕谁！")
    event.Records.forEach(record => {
        const {body} = record;
        console.log(body)
    })
    return {
        result: 'sqs ok.'
    }
};
```

## 小马部落

https://discord.gg/VSKw72P

## 课程文件

+ 小马部落Discord专区共享

## 小马视频频道

http://komavideo.com
