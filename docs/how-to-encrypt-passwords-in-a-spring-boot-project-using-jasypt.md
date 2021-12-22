# 如何使用 Jasypt

在 Spring Boot 项目中加密密码

> 原文:[https://www . geesforgeks . org/如何加密密码-春季开机-项目-使用-jasypt/](https://www.geeksforgeeks.org/how-to-encrypt-passwords-in-a-spring-boot-project-using-jasypt/)

[Spring boot](https://www.geeksforgeeks.org/introduction-to-spring-boot/) 是一个基于 Java 的框架，用来开发[微服务](https://www.geeksforgeeks.org/microservices-introduction/)，以构建企业级应用。

您经常会遇到这样的开发项目，您必须连接到数据库，如 [MongoDB](https://www.geeksforgeeks.org/mongodb-an-introduction/) 等，并将数据库连接的真实密码存储在 spring boot 项目的配置文件(application.yml 或 application.properties)中。甚至授权进行其他应用编程接口调用所需的密码或令牌也以相同的方式存储。

实际上，您可以避免在配置文件中添加实际密码，而使用 java 库“ [jasypt-spring-boot](https://mvnrepository.com/artifact/com.github.ulisesbocchio/jasypt-spring-boot-starter) ”。

**什么是雅斯密特？**
**[雅斯密斯](http://www.jasypt.org/) (Java 简化加密)**，为 Spring Boot 应用中的财产来源提供加密支持。它将帮助您以非常少的工作量将基本的加密功能添加到您的项目中，并且不需要借助项目中的一些附加功能来编写任何代码。Springboot 是一个非常强大的框架，它将帮助您在不实现任何加密方法的情况下增加加密能力。Jasypt 是高度可配置的。

**使用加密添加加密的步骤:**

1.  **Add maven dependency of jasypt:** In the pom.xml file, add maven dependency which can be found easily at [maven repository](https://mvnrepository.com/artifact/com.github.ulisesbocchio/jasypt-spring-boot-starter/2.0.0).

    [![](img/893004b2cd728491428f9a91757643f5.png)](https://media.geeksforgeeks.org/wp-content/uploads/20200209230601/1406-3.png)

2.  **Add annotation in the Spring Boot Application main Configuration class:** **@EnableEncryptableProperties** annotation needs to be added to make the application understand the encryptable properties across the entire Spring Environment.

    [![](img/771fc8249d927bd048e1c5aed963ec4e.png)](https://media.geeksforgeeks.org/wp-content/uploads/20200209231418/223-1.png)

3.  **决定一个密钥用于加密和解密**该密钥用于加密密码，之后可用于解密加密值以获得实际密码。您可以选择任何值作为密钥。
4.  **生成加密密钥**加密密钥可以通过以下两种方法之一生成:
    1.  **Use the Jasypt Online Tool :**

        这个[链接](https://www.devglan.com/online-tools/jasypt-online-encryption-decryption)可以通过传递选择的密钥来生成加密密钥。

        [![](img/15bc8d7c27ad5d0e7503c551a88cfaf6.png)](https://media.geeksforgeeks.org/wp-content/uploads/20200209232148/3164-1.png)

        *   **要加密的密码** : abcd1234
        *   **选择加密类型:**双向加密(默认使用 PBEWithMD5AndDES 和 DES)
        *   **秘钥**:你好(可以是任意值)
        *   **加密字符串**:拥抱 1 个七个七个七个七个七个七个七个七个七个七个七个七个七个七个七个

        您实际上可以使用该工具通过解密来加密和检查加密的密钥。

    2.  **Use the jasypt Jar:** Download the jasypt jar file from the maven repository and run it through the following command:

        > Java-CP//jas ypt-1 . 9 . 3/lib/jas ypt-1 . 9 . 3 . jar org . jas ypt . intf . CLI . jas ypt pbestringencryptionli input = " XYZ 123 " password = secrettkey 算法=PBEWithMD5AndDES

        [![](img/2fb587727d6dfe82ac454394ae5b5656.png)](https://media.geeksforgeeks.org/wp-content/uploads/20200209232355/4107.png)

        以下是为运行 jar 而传递的命令行参数的重要性:

        *   **输入** : abcd1234(需要加密的实际密码)
        *   **密码**:您好(您选择的密匙)
        *   **算法**:pbewithmd5 和 DES(使用默认算法)
        *   **输出**:scejmhosjc/hja8 sat 7y 6uc 65 bs0 swg(输入的加密值)

        **注**:虽然 3.1 和 3.2 中的加密值即加密字符串& OUTPUT 分别不同，但由于密钥相同，解密后会得到相同的值(abcd1234)。

*   **Add the encrypted key in the config file (application.yml or application.properties):** Now instead of adding the actual password ie. “abcd1234” as per the above eg., you need to add the encrypted value generated by either of the above methods. But how will the jasypt dependency understand that the particular property of the config file needs to be decrypted? Hence to make Jasypt aware of your encrypted values, it uses a convention which you need to add in the following format:

    > 加密密钥(enc):enc(scem JC/hja 8 sat 7 和 6uC65bs0swg)

    [![](img/c5176a3dfc830573cd20e5ce2c793789.png)](https://media.geeksforgeeks.org/wp-content/uploads/20200209232814/675.png)

    在上图中，完成了数据库密码的加密。您可以在任何需要隐藏实际密码的情况下使用它。

    *   **选择的密钥需要在运行时传递才能解密:**让加密者知道您用来形成加密值的密钥。因此，以下是传递密钥的不同方法:
    1.  **Pass it as a property in the config file. Run the project as usual and the decryption would happen.**

        [![](img/dab791de3e9afd36738e4573b1a1979d.png)](https://media.geeksforgeeks.org/wp-content/uploads/20200209232944/746.png)

    2.  **使用以下命令运行项目:**

        > $ mvn-djassypt。加密器。密码=密匙弹簧启动:运行

    3.  **导出 jassypt 加密器密码:**

        > jassypt _ Encryptor _ Password = hello