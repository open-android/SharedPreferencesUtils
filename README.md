
欢迎关注微信公众号、长期为您推荐优秀博文、开源项目、视频

![](http://oi5nqn6ce.bkt.clouddn.com/itheima/booster/code/qrcode.png)

## 使用步骤

### 1. 在project的build.gradle添加如下代码(如下图)

	allprojects {
	    repositories {
	        ...
	        maven { url "https://jitpack.io" }
	    }
	}
    
### 2. 在Module的build.gradle添加依赖    
```
dependencies {
    compile 'com.github.open-android:SharedPreferencesUtils:0.1.0
}
```


- 保存数据到sharedpreferences 
```
SharedPreferencesUtils.init(context).putBoolean("boolean", true);

//可以使用字符串资源作为保存的键
SharedPreferencesUtils.init(context).putBoolean(R.string.key_bool, true);

//可以自定义sharedpreferences的文件名
SharedPreferencesUtils.init(context,"Custom").putBoolean("boolean", true);
```

- 一句代码保存多条数据（链式调用）
```
SharedPreferencesUtils.init(context)
                .putBoolean(R.string.key_bool, true)
                .putInt(R.string.key_int, 1)
                .putString(R.string.key_string, "string")
                .putLong(R.string.key_long, 1000000000)
                .putFloat(R.string.key_float, 1.1f)
                .put("put", 100)
                .putStringSet(R.string.key_set, strings);
```

- 读取数据
```
boolean booleanData = SharedPreferencesUtils.init(context).getBoolean("bool");

boolean booleanData = SharedPreferencesUtils.init(context).getBoolean(R.string.key_bool,defValue);
```

- 移除某个键对应的数据
```
SharedPreferencesUtils.init(context).remove(bool);

SharedPreferencesUtils.init(context).remove(R.string.key_bool);
```
- 清除所有数据
```
SharedPreferencesUtils.init(context).clear();
```


