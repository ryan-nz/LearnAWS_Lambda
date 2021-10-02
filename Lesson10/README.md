Lambda版本管理
=============

## 知识点

* 使用Lambda版本管理

## 实战演习

>看图说话

+ 建立Lambda函数
  - Name: KomaVerLambda
+ 使用版本管理功能
  - 修改代码 -> v1
  - 修改代码 -> v2
  - 修改代码 -> v3
+ 命令行方式调用
+ 确认动作

## 操作步骤

### 建立Lambda函数

```javascript
exports.handler = async (event, context, cb) => {
    var message = "Lambda版本管理: v1"
    console.log(message)
    return {
        result: message,
        event: event,
    }
};
```

### 命令行方式调用

```bash
# 调用最新版本($LATEST)
$ aws lambda invoke --function-name KomaVerLambda \
    result.json \
    && cat result.json
$ aws lambda invoke --function-name KomaVerLambda:\$LATEST \
    result.json \
    && cat result.json
# 调用v1版本
$ aws lambda invoke --function-name KomaVerLambda:1 \
    result.json \
    && cat result.json
# 调用v2版本
$ aws lambda invoke --function-name KomaVerLambda:2 \
    result.json \
    && cat result.json
```

## 小马部落

https://discord.gg/VSKw72P

## 课程文件

+ 小马部落Discord专区共享

## 小马视频频道

http://komavideo.com
