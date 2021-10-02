Lambda函数触发SNS
================

## 知识点

* 使用Lambda函数触发SNS主题

## 实战演习

>看图说话

+ 修改Lambda执行角色，增加SNS调用权限
  - KomaLambdaRole
    * AmazonSNSFullAccess(最大权限，不推荐)
+ 建立Lambda函数
  - Name: KomaSNSLambda
+ 异步调用Lambda函数

### Lambda函数

*KomaSNSLambda*

```javascript
exports.handler = async (event, context, cb) => {
    console.log("SNS送信成功, 我是Lambda, 我怕谁！")
    return {
        result: 'SNS送信成功',
        event: event,
    }
};
```

### 异步调用Lambda函数

```bash
# 异步调用
$ aws lambda invoke --function-name KomaSNSLambda \
    --invocation-type Event \
    result.json
# 确认返回结果(因为是异步调用，不会立刻返回任何信息)
$ cat result.json
```

## 小马部落

https://discord.gg/VSKw72P

## 课程文件

+ 小马部落Discord专区共享

## 小马视频频道

http://komavideo.com
