# AndroidCheckStyle
it‘s android CheckStyle ，you  can use it in order to make your code prefect.

# Information

## 说明

config文件夹主要针对的是对一些代码检查和bug检测相关的配置文件，
后续如果要添加findbugs或者pmd，需要在config/quality 下创建相关文件夹，
并添加相关文件。
[the checkstyle rules](http://checkstyle.sourceforge.net/ )

## 使用

#### 1.gradle使用
直接将本项目下的checkStyle.gradle文件拷贝到别的项目的根目录下，同时，
拷贝本项目下的config文件夹至别的项目的根目录下。
在需要检查的module或者app下的build.gradle文件中，直接添加

***apply from: "${project.rootDir}/checkstyle.gradle"***

然后重新build即可。

checkstyle检查，你需要打开Terminal命令行，直接运行gradlew.bat checkstyle即可，
会在项目根目录下/build/html生成相关的html报表。

PS：这种方式主要针对测试人员，方便生成报表，对于测试人员在运行好项目环境之后，
可以将本项目的根目录下的checkstyle.bat文件拷贝至其他项目的根目录下，直接运行即可。

#### 2.使用插件模式

作为一只程序员，主要使用这种方式来查看代码中，方便解决单一类中的代码规范问题。

首先需要添加CheckStyle-IDEA插件，添加过程在这里就不缀叙了，使用时，需要打开
File-Settings-Other Settings-CheckStyle, 将config/quality/checkstyle/CheckStyleRules.xml
导入到相关的规则中，然后在需要检查的类中，直接根据IDEA的窗口运行即可。
[使用方式介绍](https://www.jianshu.com/p/9640f9c6dbf7)

PS：CheckStyleRules.xml主要检查的是一些Android开发过程中的书写规范，而此书写规范，主要针对的
其中的.java文件，目前好像还不支持检查相关的xml文件。
PS：后续将对findbugs和pmd相关检查进行添加，敬请期待。

