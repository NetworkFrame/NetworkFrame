使用步骤：

在app目录下的build.gradle中添加如下代码

dependencies {
   compile 'com.zh.network:frame:1.0.0' exclude group: 'com.android.support'//当前版本为1.0.0版本；
}


在project根目录下的build.gradle中添加如下代码
allprojects {
    repositories {
        maven{
            url "https://github.com/NetworkFrame/NetworkFrame/raw/master"
        }
    }
}


混淆：
 -keepattributes InnerClasses
 -dontoptimize
 
 -dontwarn cn.finalteam.okhttpfinal.**
 -keep public class cn.finalteam.okhttpfinal.**{*;}

 -dontwarn okhttp3.**
 -keep public class okhttp3.**{*;}

 -dontwarn okio.**
 -keep public class okio.**{*;}

 #fastjson混淆---本包引用了fastjson.android包
 -dontwarn com.alibaba.fastjson.**
 -keep class com.alibaba.fastjson.**{*; }



