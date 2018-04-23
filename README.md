使用步骤：
==========

在app目录下的build.gradle中添加如下代码
----

dependencies {<br>
      compile 'com.zh.network:frame:1.0.0' exclude group: 'com.android.support'//当前版本为1.0.0版本；<br>
}<br>


在project根目录下的build.gradle中添加如下代码
---

allprojects {<br>
      repositories {<br>
         maven{<br>
               url "https://github.com/NetworkFrame/NetworkFrame/raw/master"<br>
        }<br>
    }<br>
}<br>


混淆：
----
 -keepattributes InnerClasses<br>
 -dontoptimize<br>
 
 -dontwarn cn.finalteam.okhttpfinal.**<br>
 -keep public class cn.finalteam.okhttpfinal.**{*;}<br>

 -dontwarn okhttp3.**<br>
 -keep public class okhttp3.**{*;}<br>

 -dontwarn okio.**<br>
 -keep public class okio.**{*;}<br>

 #fastjson混淆---本包引用了fastjson.android包<br>
 -dontwarn com.alibaba.fastjson.**<br>
 -keep class com.alibaba.fastjson.**{*; }<br>



