# 异步调用Lambda函数

================

## 知识点

+ 通过命令行工具，异步调用Lambda函数

## 实战演习

>看图说话

+ 使用 AWS CLI 异步调用 Lambda 函数
+ 确认执行日志

## 操作步骤

```bash
# 异步调用
$ aws lambda invoke --function-name YoungLambdaFunc01 \
    --invocation-type Event \
    --payload 'eyAiaGVsbyI6ICJsYW1iZGEiIH0=' \
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
