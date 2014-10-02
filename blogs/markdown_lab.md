---
layout: post
title: Blogging Like a Hacker
---

markdown样式练习
================

[TOC]

##列表样式

###无序列表1
* 列表1
* 列表2
* 列表3

###无序列表2
- 列表1
- **列表2**
- 列表3

###有序列表
1. 列表1
2. 列表2
3. 列表3

##弹出式提示

把鼠标停留在**HTML**和**W3C**上看会发生什么。

*[HTML]: Hyper Text Markup Language
*[W3C]: World Wide Web Consortium

##列表定义

Apple
:   Pomaceous fruit of plants of the genus Malus in
    the family Rosaceae.

Orange
:   The fruit of an evergreen tree of the genus Citrus.

##源码片段

###python源码
```python
#!python
# -*- coding: utf-8 -*-
from flask import Flask, render_template

app = Flask(__name__)
app.debug = APP_DEBUG

#homepage just for fun
@app.route('/')
def home():
    return render_template('index.html')
```

###c源码
```c
#include <stdio.h>

int main(int argc, char **argv) {
	print("hello world!")
}
```

###java源码
```java
package com.zoweewifimusicbox;

import java.net.InetAddress;
import java.util.HashMap;
import android.app.Application;

import com.crashhelper.util.CrashHandler;
import com.httplibrary.log.HttpLogUtil;
import com.zoweewifimusicbox.bean.HbPacket;
import com.zoweewifimusicbox.task.TaskPool;
import com.zoweewifimusicbox.utils.LogUtil;

public class MyApplication extends Application {

    public HashMap<HbPacket, InetAddress> wifiBoxInfoMap = new HashMap<HbPacket, InetAddress>();

    /**
     * Remote wifi device address
     */
    private InetAddress remoteAddr;
    private static MyApplication instance;

    public static MyApplication getInstance() {
        return instance;
    }

    public void saveWifiboxInfo(HbPacket hbPacket, InetAddress address) {
        if (!wifiBoxInfoMap.containsKey(hbPacket)) {
            wifiBoxInfoMap.put(hbPacket, address);
        }
    }
    
    public void setCurRemoteAddr(HbPacket hbPacket){
        remoteAddr = wifiBoxInfoMap.get(hbPacket);
    }
    
    public InetAddress getCurRemoteAddr(){
        return remoteAddr;
    }

    @Override
    public void onCreate() {
        super.onCreate();
        instance = this;

        TaskPool.initPool();
        LogUtil.setDebugEnable();
        
        HttpLogUtil.setDebugEnable();
        CrashHandler.getInstance().init(this);
    }

}

```

##角注

Footnotes[^1] have a label[^@#$%] and the footnote's content.

[^1]: This is a footnote content.
[^@#$%]: A footnote on the label: "@#$%".

##表格

First Header  | Second Header
--------------|--------------
Content Cell  | Content Cell
Content Cell  | Content Cell

##警告

!!! Hint "警告的标题"
    This is hint

!!! Attention
    This is hint

!!! Caution
    This is hint

!!! Danger
    This is hint

!!! Question
    This is hint

!!! Note
    This is hint

##强调

这是**黑体**写法
这是*斜体*的写法

##链接

这是一个[链接](https://github.com/kamidox/blogs)
这是另外一种[链接][1]的形式

[1]: https://pythonhosted.org/Markdown/extensions/index.html

##引用

> 引用的文字内容
> 这是另外的引用内容

##图片

![图片描述](https://raw.githubusercontent.com/kamidox/blogs/master/kamidox_icon.png)
