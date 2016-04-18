---
layout:     post
title:      "Android修炼书册 · 基础篇之一"
subtitle:   "Activity的生命周期"
date:       2016-04-18 00:00:00
author:     "Julian"
header-img: "img/about-bg.jpg"
tags:
    - Android
---

* TOC
{:toc}

## 简述
每个 Activity 实例都有其**生命周期**。在其生命周期内，Activity 在运行、暂停和停止三种可能的状态简进行转换。每次状态发生转换时，都有一个 Activity 的方法将状态改变的消息通知给 Activity。下图是 Android api 中提供的 Activity 的生命周期图。

![activity的生命周期图解](http://7xlo4n.com1.z0.glb.clouddn.com/Activity_lifecircle.jpg)


## 实例详解
下面通过一个简单的Demo来详细探究一下Activity的生命周期，测试代码如下：

```java
package com.julian.maintest;

import android.app.Activity;
import android.os.Bundle;
import android.util.Log;

public class TestActivity extends Activity {

    public static final String TAG = "TestActivity";

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_test);
        Log.i(TAG,"onCreate() called");
    }

    @Override
    protected void onStart() {
        super.onStart();
        Log.i(TAG,"onStart() called");
    }

    @Override
    protected void onRestart() {
        super.onRestart();
        Log.i(TAG,"onRestart() called");
    }

    @Override
    protected void onResume() {
        super.onResume();
        Log.i(TAG,"onResume() called");
    }

    @Override
    protected void onPause() {
        super.onPause();
        Log.i(TAG,"onPause() called");
    }

    @Override
    protected void onStop() {
        super.onStop();
        Log.i(TAG,"onStop() called");
    }

    @Override
    protected void onDestroy() {
        super.onDestroy();
        Log.i(TAG,"onDestroy() called");
    }
}
```
### 应用启动
运行上述代码，app 启动，在 Android Studio 的 logcat 中我们会看到如下信息：

```
I/TestActivity: onCreate() called
I/TestActivity: onStart() called
I/TestActivity: onResume() called
``` 

可以看到在应用启动并完成 TestActivity 实例创建后有三个方法 onCreate() 、onStart() 和 onResume() 依次被调用了。

### 点击 Home 键
下面我们点击手机 Home 键，从 logcat 中可以看到如下信息：

```
I/TestActivity: onPause() called
I/TestActivity: onStop() called
```

在 Home 键被点击后，应用进入到了后台，此时 onPause() 和 onStop() 方法依次被调用。

下面我们点击应用图标或者在任务管理器中再次回到应用，可以从 logcat 中看到如下信息：

```
I/TestActivity: onRestart() called
I/TestActivity: onStart() called
I/TestActivity: onResume() called
```

可以看到当我们再次回到应用时 onRestart() 、onStart() 和 onResume() 方法会被依次调用。

### 点击 Back 键
最后我们点击 Back 键退出应用，从 logcat 中会看到如下信息：

```
I/TestActivity: onPause() called
I/TestActivity: onStop() called
I/TestActivity: onDestroy() called
```

也就是说在我们退出应用时系统会依次调用 onPause()、onStop() 和 onDestroy() 方法。










 


