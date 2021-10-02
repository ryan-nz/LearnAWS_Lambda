ELB配合Lambda
=============

## 知识点

* 使用ELB负载转发Lambda

## 官网

https://docs.aws.amazon.com/zh_cn/elasticloadbalancing/latest/application/lambda-functions.html

## 实战演习

>看图说话

+ 建立Lambda函数
  - Name: KomaELBLambda
+ 建立目标组
  - Name: TG-Lambda
+ 建立ALB
  - Name: ALB-Lambda

## 操作步骤

### KomaELBLambda

```javascript
exports.handler = async (event) => {
    const response = {
        "isBase64Encoded": false,
        "statusCode": 200,
        "statusDescription": "200 OK",
        "headers": {
            "Set-cookie": "cookies",
            "Content-Type": "application/json"
        },
        "body": "{ 'result': 'ok, i love u.' }"
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
