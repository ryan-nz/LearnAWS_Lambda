# 命令行建立Lambda函数

==================

## 知识点

+ 使用 AWS CLI 命令行工具建立Lambda函数

## 实战演习

>看图说话

+ 本地建立函数文件
+ 压缩本地文件ZIP
+ 命令行建立Lambda函数
+ 管理控制台确认动作

## 操作步骤

### 本地建立函数文件

*index.js* File

```javascript
exports.handler = async (event) => {
    var message = "你好, AWS Lambda函数。"
    console.log(message)
    return message;
};
```

### 建立函数

```bash
$ mkdir mylambda
$ cd mylambda
# 压缩函数
$ zip mylambda.zip index.js
# 建立函数
$ aws lambda create-function --function-name KomaCLILambda \
    --zip-file fileb://mylambda.zip \
    --handler index.handler \
    --runtime nodejs14.x \
    --timeout 10 \
    --memory-size 128 \
    --role arn:aws:iam::360056582034:role/YoungLambdaRole
# 调用函数
$ aws lambda invoke --function-name KomaCLILambda result.json
# 确认返回结构
$ cat result.json
```

## 小马部落

https://discord.gg/VSKw72P

## 课程文件

+ 小马部落Discord专区共享

## 小马视频频道

http://komavideo.com
