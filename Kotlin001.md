> ### 入门

* Kotlin优势(对比Java)

1. Kotlin更简洁，完成同样业务功能，Kotlin代码比Java少一大半
2. Kotlin更安全，编码阶段自动检测常见问题，如空指针引用
3. Kotlin更完善，提供了扩展函数、默认参数、接口委托、属性代理等Java所不具备的高级特性

* 配置Java环境

1. 如果终端运行 ``` java -version ```能看到版本，可不往下进行
2. 下载[jre-8u221-macosx-x64](https://www.lanzous.com/i5xao1i)，或[官网下载](https://www.java.com/en/download/mac_download.jsp)
3. 安装后终端运行``` java -version ```能看到版本，可不往下进行
4. 打开环境变量描述文件 open -e ~/.bash_profile
5. 追加

    ```
    # Java 
    export JAVA_HOME="/Library/Internet Plug-Ins/JavaAppletPlugin.plugin/Contents/Home"
    export PATH=${JAVA_HOME}/bin:$PATH
    
    ```
6. 使配置生效 source ~/.bash_profile

* 常用编辑器

1. [Sublime Text](https://www.sublimetext.com/)
2. [IntelJ IDEA](https://www.jetbrains.com/idea/download/)
3. [Android Studio](https://developer.android.com/studio/preview/index.html)

* Hello Kotlin（终端版）

1. 下载Release版[Kotlin Compiler 1.3.5](https://github.com/JetBrains/kotlin/releases/download/v1.3.50/kotlin-compiler-1.3.50.zip)，其他版本请自行[下载](https://github.com/JetBrains/kotlin/releases/)
2. 创建kotlin目录 ``` mkdir ~/kotlin ```
3. 进入kotlin目录 ``` open ~/kotlin ```
4. 将步骤1下载的压缩包复制到创建的kotlin目录并解压
5. 打开环境变量描述文件 ``` open -e ~/.bash_profile ```
6. 添加路径 ``` export PATH=~/kotlin/kotlinc/bin:$PATH ```
7. 使配置生效 ``` source ~/.bash_profile ```
8. 新建HelloKotlin.kt文件，输入
	
	```
	fun main (args:Array<String>) {
		println("Hello Kotlin");
	}	
	```
9. 在终端使用kotlinc编译文件为jar文件 ``` kotlinc HelloKotlin.kt -include-runtime -d HelloKotlin.jar ```
10. 运行HelloKotlin.jar ``` java -jar HelloKotlin.jar ```


* Hello Kotlin（终端简化）

1. 进入用户根目录 ``` cd ~/ ```
2. 新建一个文件 KotlincRun 内容为

	```
	#!/usr/bin/env bash 
	#!bin/bash
	if [ $# != 1 ];
  		then echo "Usage : bash KotlinRun filename"
	else
  		kotlinc "$1.kt" -include-runtime -d "$1.jar"
  		java -jar "$1.jar"
	fi
	```
3. 打开环境变量描述文件 ``` open -e ~/.bash_profile ```
4. 追加配置 ``` alias KotlinRun='bash ~/KotlincRun' ``` 保存
5. 使配置生效 ``` source ~/.bash_profile ```
6. 终端编译HelloKotlin.kt文件 ``` KotlinRun HelloKotlin ```

* 使用Sublime Text 3编译

1. 下载[Sublime_3.2.1_3208](https://www.lanzous.com/i5wuygh)
2. 安装后 ``` open ~/Library/Application\ Support/Sublime\ Text\ 3/Packages/User ``` 
3. 下载[SublimeKotlinPackage](https://www.lanzous.com/i5wy5wd)
4. 将解压后的三个文件放到上面打开的目录
5. 打开Sublime选择顶部菜单中Tools-->Build System--> Kotlin
6. 右下角文本支持点击选择Kotlin
7. 用Sublime打开HelloKotlin.kt，Command + B 编译



