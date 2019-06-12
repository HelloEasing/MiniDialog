# MiniDialog 对话框

### 功能丰富、使用简单、灵活多样的轻量级对话框组件。

#### 在线体验： [http://minidialog.applinzi.com/](http://minidialog.applinzi.com/)

#### 兼容情况：Chrome45+，Firefox40+，Edge15+，Safari11+，IE11

#### 代码示例：

1. [四种信息提示对话框](#四种信息提示对话框)
2. [快捷方式](#快捷方式)
3. [常规配置](#常规配置)
4. [自定义内容背景色](#自定义内容背景色)
5. [可拖动的对话框](#可拖动的对话框)
6. [全屏对话框](#全屏对话框)
7. [自动关闭](#自动关闭)
8. [嵌入Iframe](#嵌入Iframe)
9. [嵌入图片](#嵌入图片)
10. [嵌入多张图片](#嵌入多张图片)
11. [嵌入视频](#嵌入视频)
12. [确定按钮-加载中](#确定按钮-加载中)
13. [按钮事件](#按钮事件)
14. [开关事件](#开关事件)

#### 四种信息提示对话框

```js
// 内容可选
Dialog.info( "标题", "内容" );
Dialog.success( "标题", "内容" );
Dialog.warn( "标题", "内容" );
Dialog.error( "标题", "内容" );
```

#### 快捷方式
```js
// 只传入内容（此时将采用默认标题：网页消息）
Dialog( "内容" );

// 传入标题和内容
Dialog( "标题", "内容" );

// 传入标题、内容和对话框宽度（单位：px）
Dialog( "标题", "内容", 800 );
```

#### 常规配置
```js
Dialog({
    title: "标题",
    content: "内容",
    width: 800
});
```

#### 自定义内容背景色
```js
Dialog({
    title: "标题",
    content: "内容",
    width: 800
});
```

#### 可拖动的对话框
```js
Dialog({
    title: "标题",
    content: "内容",
    draggable: true
});
```

#### 全屏对话框
```js
Dialog({
    title: "标题",
    content: "内容",
    fullscreen: true
});
```

#### 自动关闭
```js
Dialog({
    title: "标题",
    content: "内容",
    autoClose: 5000
});
```

#### 嵌入 Iframe
```js
Dialog({
    title: "标题",
    width: 1100,
    iframeContent: {
        src: "http://www.baidu.com/",
        height: 600
    },
    showButton: false
});
```

#### 嵌入图片
```js
Dialog({
    width: 1100,
    imageContent: {
        src: "demo.png",
        height: 600
    },
    showButton: false,
    showTitle: false,
    maskClose: true
});
```

#### 嵌入多张图片
```js
Dialog({
    width: 700,
    imageContent: {
        src: [ "1.png", "2.png", "3.png", "4.png", "5.png" ],
        height: 400
    },
    showButton: false,
    showTitle: false,
    maskClose: true
});
```

#### 嵌入视频
```js
Dialog({
    width: 800,
    videoContent: {
        src: "demo.mp4",
        height: 450
    },
    showButton: false,
    showTitle: false,
    maskClose: true
});
```

#### 确定按钮 - 加载中
```js
Dialog({
    title: "标题",
    content: "内容",
    ok: {
        loading: true,
        loadingText: "等一会",
        click: function () {
            setTimeout(function () {
                Dialog.close();
            }, 3000)
        }
    }
});
```

#### 按钮事件
```js
Dialog({
    title: "标题",
    content: "内容",
    ok: {
        click: function () {
            alert( "确定" );
        }
    },
    cancel: {
        click: function () {
            alert( "取消" );
        }
    }
});
```

#### 开关事件
```js
Dialog({
    title: "标题",
    content: "内容",
    afterOpen: function () {
        alert( "打开了对话框" );
    },
    afterClose: function () {
        alert( "关闭了对话框" );
    }
});
```
<br>

### 全部属性及默认值：
```js
Dialog({
    title: "网页消息",               // 对话框标题
    content: "",                    // 对话框内容
    contentBgColor: "#fff",         // 内容区域的背景色
    iframeContent: null,            // 嵌入 iframe 的配置项，有必填两个属性 { src, height }
    videoContent: null,             // 嵌入图片的配置项，有必填两个属性 { src, height }
    imageContent: null,             // 嵌入视频的配置项，有必填两个属性 { src, height }，一个可选属性 { autoplay }
    fullscreen: false,              // 全屏显示
    draggable: false,               // 可以拖动（设置此属性后，mask 将自动设置为 false）
    maskClose: false,               // 点击遮罩层关闭对话框
    mask: true,                     // 显示遮罩层
    closable: true,                 // 显示右上角关闭图标
    bodyScroll: true,               // body 可以滚动
    showTitle: true,                // 显示标题
    showButton: true,               // 显示按钮
    autoCloseEffect: true,          // 当设置了自动关闭时，显示自动关闭的动画效果
    autoClose: 0,                   // 自动关闭的时长，单位：ms（默认：0 表示不开启自动关闭功能）
    parentsIframeLayer: 0,          // 在祖先级 iframe 中创建对话框，数字表示祖先 iframe 的级数
    borderRadius: 6,                // 对话框圆角值，单位：px
    width: 500,                     // 对话框宽度，单位：px
    ok: {
        text: "确定",
        loading: false,
        loadingText: "确定",
        notClose: false,
        callback: function () {}
    },
    cancel: {
        text: "取消",
        show: true,
        callback: function () {}
    },
    afterOpen: function () {},
    afterClose: function () {}
});
```

### 全局关闭方法：
```js
// 关闭指定对话框
var thisDialog = Dialog( "标题" );
Dialog.close( thisDialog );

// 关闭全部对话框
Dialog.close();
```