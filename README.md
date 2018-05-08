使用步骤：
==========
在Application中做如下初始化：

                  private void initOkHttpUtils() {
                      try {
                          //是否开启debug模式
                          OkHttpUtils.debug(AppUtils.isDebug(), "Okhttp");
                          //设置超时时间   OkHttpUtils.getInstance().setConnectTimeout(OkHttpUtils.DEFAULT_MILLISECONDS).setReadTimeOut(OkHttpUtils.DEFAULT_MILLISECONDS).setWriteTimeOut(OkHttpUtils.DEFAULT_MILLISECONDS);
                      } catch (Exception e) {
                          e.printStackTrace();
                      }

                  }



在app目录下的build.gradle中添加如下代码
----

            dependencies {
                compile 'com.zh.network:frame:1.0.0' exclude group: 'com.android.support'//当前版本为1.0.0版本；
            }


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



