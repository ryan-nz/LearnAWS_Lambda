# 同步调用Lambda函数

=================

## 知识点

+ 通过命令行工具，同步调用Lambda函数

## 实战演习

>看图说话

+ 使用 AWS CLI 同步调用 Lambda 函数
+ 确认执行日志

## 操作步骤

```bash
# AWS CLI版本确认
$ aws --version
# 调用Lambda函数
$ aws lambda invoke --function-name YoungLambdaFunc01 \
    --region 'ap-southeast-2' \
    --payload '{ "helo": "lambda" }' \
    result.json
>Invalid base64: "{ "helo": "lambda" }"
# BASE64编码(https://www.base64decode.org/)
$ aws lambda invoke --function-name YoungLambdaFunc01 \
    --profile admin-cli \
    --region 'ap-southeast-2' \
    --payload 'eyAiaGVsbyI6ICJsYW1iZGEiIH0=' \
    result.json
# 确认返回结果
$ cat result.json

# 执行日志返回(--log-type)
$ aws lambda invoke --function-name YoungLambdaFunc01 \
    --region 'ap-southeast-2' \
    --payload 'eyAiaGVsbyI6ICJsYW1iZGEiIH0=' \
    out --log-type Tail
# 执行日志返回(base64解码)
$ aws lambda invoke --function-name YoungLambdaFunc01 \
    --region 'ap-southeast-2' \
    --payload 'eyAiaGVsbyI6ICJsYW1iZGEiIH0=' \
    out --log-type Tail \
    --query 'LogResult' --output text | base64 -d
```

## 小马部落

https://discord.gg/VSKw72P

## 课程文件

+ 小马部落Discord专区共享

## 小马视频频道

http://komavideo.com
