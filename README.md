# proguard-dict
Oo0

# 使用

1. 下载 dictionary-airsaid.txt 混淆字典并放到项目的 app 目录下；

2. 将 Android/SDK/tools/proguard/ 目录下的 proguard-android.txt 拷贝到项目的 app 目录下；

3. 在 proguard-android.txt 文档的后面追加如下代码：
``` java
# ============== 新增规则 ==============

# 指定混淆字典
-obfuscationdictionary dictionary-airsaid.txt # 用作字段和方法名称
-classobfuscationdictionary dictionary-airsaid.txt # 用作类
-packageobfuscationdictionary dictionary-airsaid.txt # 用作包
```

4. 修改 Module 级别的 build.gradle：
``` java
release {
        minifyEnabled true
        proguardFile 'proguard-android.txt'
        proguardFile 'proguard-rules.pro'
}
```

# 效果

``` java
public class MainActivity extends t {
    private static final String O0000Ooo = MainActivity.class.getSimpleName();

    private void O000000o(String str) {
    }

    private void O0000OoO() {
    }

    protected void onCreate(Bundle bundle) {
        super.onCreate(bundle);
        setContentView((int) R.layout.activity_main);
        O0000OoO();
        O000000o(O0000Ooo);
    }
}
```