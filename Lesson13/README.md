Lambda环境变量
=============

## 知识点

* 在Lambda中读取环境变量

## 实战演习

>看图说话

+ 建立Lambda函数
  - Name: KomaEnvLambda
+ 建立函数的环境变量
+ 在Lambda中读取环境变量

## 操作步骤

### KomaEnvLambda

```js
exports.handler = async (event) => {
    console.log(process.env.DBHost);
    console.log(process.env.DBUid);
    console.log(process.env.DBPwd);
    const response = {
        statusCode: 200,
        body: JSON.stringify('Hello from KomaEnvLambda!'),
    };
    return response;
};
```

### 建立函数的环境变量

+ DBHost
  - 192.168.20.10
+ DBUid
  - root
+ DBPwd
  - 12345678

## 小马部落

https://discord.gg/VSKw72P

## 课程文件

+ 小马部落Discord专区共享

## 小马视频频道

http://komavideo.com
