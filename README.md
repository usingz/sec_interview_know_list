**被虐经历**

**知识清单**

- **xss防御相关**
    - 编码防御
        - html实体编码
        - js编码
        - url编码
        - **输出点在标签内部应该怎么防御？**
        - **输出点在标签外部应该怎么防御？**
        - **三种编码的关系，以及什么地方用到什么编码**
        - **浏览器解码的过程**
        - **开启httponly的情况下如何利用XSS漏洞**
        - xss输出在注释里怎么利用 （换行符利用）
        - 如果页面是gbXXX 如何利用宽字节进行xss利用
        - 在xss利用过程中 讲 < 写成 \u003c 可以绕过安全防护 请问这个安全防护的思路是什么
        - XSS防御的7大原则
        - 心伤的瘦子
        - 如果 ”javascript“字符串被过滤了，你的绕过思路是什么？
            - 大小写
            - Tab 空格 回车(%0a)
            - 插入 “/**/” \0 \ 
            - 编码
        - CSS中expression表达式可以插入xss吗
        - 如果输出点在css style标签中 要注意expression表达式 import等之类

        - **XSS编码方案(方案普遍性很高，具体要看业务场景)**(大家自行思考为什么这么做？)
            - 当输出点出现在HTML标签属性：
            
             ```
                < -> &lt;
                > -> &gt;
                & -> &amp;
                " -> &quot;
                ' -> &#39
             ```
            
            - 当输出点出现在<script>标签中。这种情况相当危险，不需要考虑xss触发，只需要考虑编写js即可

            
            ``` 
                ' -> \';
                " -> \";
                \ -> \\;
                / -> \/;
                (换行符) -> \n;
                (回车符) -> \r;
            ```
            
            - 当输出点出现在body中
            
            ```
                < -> &lt;
                > -> &gt;
                & -> &amp;
                " -> &quot;
                ' -> &#39
            ```
            
            - 当输出点出现在js事件中(onClick="你的代码")
            
            ```
                < -> &lt;
                > -> &gt;
                & -> &amp;
                " -> &quot;
                ' -> &#39
                \ -> \\;
                / -> \/;
                (换行符) -> \n;
                (回车符) -> \r;
             ```
             
             - 输出在URL属性中<script src="你的代码">
                - URL编码
             
             
            
          
            
            

- **CSRF相关**
    - 只校验Refer可以吗
    - token放在哪里？放在cookie里可以吗？不失效可以吗？
    
- **XXE漏洞相关**
    - XML文件格式
    - XXE漏洞利用的方式
    - XXE漏洞修复方案
    - XXE漏洞
    
- **sql注入漏洞相关**
    - 注入的类型
    - 检查注入的思路
    - 方案(参数化查询会有问题吗？)
    - ORM
    - 如果检测被拦截了怎么绕过（比如sleep被waf拦了）
    - Mysql的提权都有哪些
    - Sqlmap原理

    
    
- **SSRF**
    - 说一个容易出现SSRF漏洞的场景
    - 如果过滤了以http开头的协议怎么绕过
    
    
- **CSP浏览器内容安全**
    - 略

- **Waf绕过**
    - 我不会
    
- **DDOS防御相关**
    - DDOS攻击的类型
    - DDOS云防御的方案
    - DDOS反射攻击基于的协议？为什么基于这个协议？
    
- **加密与解密**
    - https协议握手过程
    - burp 中间人攻击的原理
    - 分别说3个对称加密 非对称加密 哈希算法 
    
- **Java家族安全**
    - Spring安全 原理 利用方法
    - Struts2安全 原理 利用方法
    - JBoss安全 原理 利用方法
    - Tomcat安全 原理 利用方法
    - WebLogic安全 原理 利用方法
    - IIS(无处可放了)
    
- **android逆向相关**
    - 脱壳的原理
    - 如何查壳
    - smali语法
    - davilk指令
    - 如何防打包
    - 如何防签名校验
    - Android App加固原理分析(说一个加固的思路)
    - 防御思路
        - 对抗静态分析
            - 代码混淆技术 ProGuard
            - NDK保护
            - 壳
        - 对抗动态调试 
            - android:debuggable="false"，让程序不可调试
            - android.os.Debug.isDebuggerConnected()
            - 检测模拟器
        - 防止重编译
            - 检查签名 Eclipse自带的调试版密钥文件生成的apk文件的hash值,与上面的函数获取的hash比较
            - 检测Dex文件的Hash
            
    
    


