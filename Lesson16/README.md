Lambda的死信队列
===============

## 知识点

* Lambda处理失败时的死信队列

## 实战演习

>看图说话

+ 建立SQS死信队列
  - Name: KomaDeadLetterSQS
+ 建立Lambda函数
  - Name: KomaFailureLambda
+ 方法1: 建立Lambda函数目标
  - 失败时发送 KomaDeadLetterSQS(需要授权向SQS发送消息)
  - "您的函数的执行角色无权将结果发送到目标。单击“保存”后，我们将尝试为您添加该角色的权限。"
+ 方法2: 异步调用 / 编辑异步配置 / 死信队列
  - 设置重试次数: 0
  - 失败时发送 KomaDeadLetterSQS(需要授权向SQS发送消息)
+ 异步调用Lambda函数

## 操作步骤

### KomaFailureLambda

```js
exports.handler = async (event) => {
    // 程序出错
    throw new Error('不好，你的Lambda出错了!')

    const response = {
        statusCode: 200,
        body: JSON.stringify('Hello from Lambda!'),
    };
    return response;
};
```

### 异步调用Lambda函数

```bash
# 异步调用
$ aws lambda invoke --function-name KomaFailureLambda \
    --invocation-type Event \
    result.json \
    && cat result.json \
    && rm result.json
```

## 小马部落

https://discord.gg/VSKw72P

## 课程文件

+ 小马部落Discord专区共享

## 小马视频频道

http://komavideo.com
