## 编译过程

1. 本人对 ant 不熟，因此选择通过 maven 编译，并在项目中已经提供了可用的 pom.xml。
2. JDK 版本必须在 17 以上，本工程选择了 JDK22，其他版本可自行尝试。
3. 为了方便测试，本项目在 org.apache.catalina.startup.ContextConfig 中启用了 JSP 功能。
4. 为了通过编译，本项目注释掉了 org.apache.jasper.compiler.JDTCompiler 中不存在的常量。
5. 启动 Bootstrap 时，需要添加以下 JVM 参数：
   ```shell
    -Dcatalina.home=catalina-home
    -Dcatalina.base=catalina-home
    -Djava.io.tmpdir=catalina-home\temp
    -Djava.util.logging.manager=org.apache.juli.ClassLoaderLogManager
    -Djava.util.logging.config.file=catalina-home\conf\logging.properties
    ```
6. 如果 maven 编译时存在乱码，可以在 IDEA Settings 中为 maven runner 添加 vm option：`-Dfile.encoding=GB2312`。