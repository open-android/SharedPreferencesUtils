

```
dependencies {
    compile 'com.white:easysp:1.0.0'
}
```
## Usage

- save data to sharedpreferences.xml   
```
SharedPreferencesUtils.init(context).putBoolean("boolean", true);

// you can also use string resource value as the key
SharedPreferencesUtils.init(context).putBoolean(R.string.key_bool, true);

// or specify a custom name for the preferences' name:
SharedPreferencesUtils.init(context,"Custom").putBoolean("boolean", true);
```

- save multiple data by one line of code
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

- read data
```
boolean booleanData = SharedPreferencesUtils.init(context).getBoolean("bool");

boolean booleanData = SharedPreferencesUtils.init(context).getBoolean(R.string.key_bool,defValue);
```

- remove data
```
SharedPreferencesUtils.init(context).remove(bool);

SharedPreferencesUtils.init(context).remove(R.string.key_bool);
```
- clear data
```
SharedPreferencesUtils.init(context).clear();
```


