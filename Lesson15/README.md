Lambda并发限制
=============

## 知识点

* Lambda突增并发限制与设置

## 官网

https://docs.aws.amazon.com/zh_cn/lambda/latest/dg/configuration-concurrency.html

## Lambda突增并发限制

+ 3000 – 美国西部（俄勒冈），美国东部（弗吉尼亚北部），欧洲（爱尔兰）
+ 1000 – 亚太区域（东京）、欧洲（法兰克福）、美国东部（俄亥俄州）
+ 500 – 其他区域

## 并发类型

+ 预留并发(Reserve concurrency)
  - 从区域配额中独占一部分并发数量(例如：东京区，预留100给KomaLimitLambda函数，其他函数共享可用900)
+ 预配置并发(Provisioned concurrency)
  - 收费服务，独占资源
  - 为别名或版本单独配置执行环境资源(产品环境)

## 实战演习

+ 创建函数
  - Name: KomaLimitLambda
+ 设置预留并发
+ 设置预配置并发

## 设置并发后的节流错误(Throttle)

+ 429
  - Request throughput limit exceeded.

## 小马部落

https://discord.gg/VSKw72P

## 课程文件

+ 小马部落Discord专区共享

## 小马视频频道

http://komavideo.com
