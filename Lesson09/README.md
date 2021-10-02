S3事件触发Lambda函数
===================

## 知识点

* 通过S3事件触发Lambda函数

## 实战演习

>看图说话

+ 建立S3存储桶
  - Name: s3-for-lambda
+ 建立S3事件触发
  - Name: s3-for-lambda-objectcreated
  - 所有对象创建事件
    * s3:ObjectCreated:*
  - 目标
    * Lambda: KomaSNSLambda
+ S3上传文件，事件触发Lambda
+ 确认Lambda执行结果
  - CloudWatch
  - EMail

## 小马部落

https://discord.gg/VSKw72P

## 课程文件

+ 小马部落Discord专区共享

## 小马视频频道

http://komavideo.com
