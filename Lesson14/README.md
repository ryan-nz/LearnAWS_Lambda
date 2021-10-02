环境变量的加密和解密
==================

## 知识点

* 使用 KMS 加密与解密环境变量

## 实战演习

>看图说话

+ 使用KMS创建一个密钥对(CMK)
+ 使用CMK加密环境变量
+ 为Lambda执行角色赋予使用CMK解密的权利
+ 在Lambda函数中解密环境变量

## 操作步骤

### 使用KMS创建一个密钥对(CMK)

+ 密钥类型: 对称
+ Name: deeplearnaws_cmk
+ 密钥管理员: lcadmin
+ 定义密钥使用权限: KomaLambdaRole
  - 建立加密环境变量时设置效果相同

### 使用CMK加密环境变量

+ DBPwd
  - 12345678
+ 确认Lambda执行角色的权限
+ 确认解密代码样例

### 在Lambda函数中解密环境变量

```javascript
const AWS = require('aws-sdk');
AWS.config.update({ region: 'ap-northeast-1' });

const functionName = process.env.AWS_LAMBDA_FUNCTION_NAME;
const encrypted = process.env['DBPwd'];
let decrypted;

exports.handler = async (event) => {
    if (!decrypted) {
        // Decrypt code should run once and variables stored outside of the
        // function handler so that these are decrypted once per container
        const kms = new AWS.KMS();
        try {
            const req = {
                CiphertextBlob: Buffer.from(encrypted, 'base64'),
                EncryptionContext: { LambdaFunctionName: functionName },
            };
            const data = await kms.decrypt(req).promise();
            decrypted = data.Plaintext.toString('ascii');
        } catch (err) {
            console.log('Decrypt error:', err);
            throw err;
        }
    }
    // 输出密钥
    console.log("encrypted:", encrypted)
    console.log("decrypted:", decrypted)
};
```

## 小马部落

https://discord.gg/VSKw72P

## 课程文件

+ 小马部落Discord专区共享

## 小马视频频道

http://komavideo.com
