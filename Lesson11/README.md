Lambda别名管理
=============

## 知识点

* 使用Lambda别名管理功能

## 实战演习

>看图说话

+ 利用上期建立的Lambda函数
+ 建立Lambda函数的别名
  - Name: Prod
+ 设置别名加权
  - v1:100%
  - v1:80%, v2:20%
  - v1:50%, v2:50%
  - v1:20%, v2:80%
+ 调用函数

## 操作步骤

### 建立Lambda函数的别名

+ Name: Prod

```bash
$ aws lambda invoke --function-name KomaVerLambda:Prod \
    result.json \
    && cat result.json
```

## 小马部落

https://discord.gg/VSKw72P

## 课程文件

+ 小马部落Discord专区共享

## 小马视频频道

http://komavideo.com
