# homework-group68project14
Project14: Implement a PGP scheme with SM2


实现方式：Python

成员：李丽敏-202100460130 （仅一人一组）

实验过程：

1：实验预备知识：PGP协议


  ![image](https://github.com/llmgroup68/homework-group68project14/assets/138642474/dfa2e647-66b8-4dca-8f8b-fc7510e21b16)


  PGP是一个加密程序，为数据通信提供加密隐私和身份验证。PGP 用于对文本、电子邮件、文件、目录和整个磁盘分区进行签名、加密和解密，并提高电子邮件通信的安全性。PGP加密使用散列，数据压缩，对称密钥加密，最后是公钥加密的串行组合。其中最关键的是两种形式的加密的组合：对称密钥加密和非对称密钥加密。

 具体实现流程如下：

   首先生成发送方和接收方的密钥对。使用get_key()函数生成随机的私钥d和对应的公钥P。
   
   发送方将要发送的消息进行数字签名，首先计算消息的哈希值，然后使用私钥d和公钥P调用sm3_sign()函数生成数字签名。
   
   发送方将数字签名和消息进行拼接并进行加密，使用SM4对称加密算法来加密数据，加密密钥为预设的key。
   
   接收方收到加密的数据后，使用对应的私钥d和公钥P进行验证。首先解密得到签名和消息，然后计算消息的哈希值，最后调用verif_sign()函数进行签名验证。
   
   如果签名验证通过，则输出解密后的消息。
2：实验过程：

在本代码中，写到了关于椭圆曲线的密码学部分，关于PGP协议，部分代码如下：

![image](https://github.com/llmgroup68/homework-group68project14/assets/138642474/ab9e84a8-ff38-48ff-9735-4c68f84951e3)

实验结果如下：

![image](https://github.com/llmgroup68/homework-group68project14/assets/138642474/38ef3662-4983-4d32-910c-9baa980227f3)


