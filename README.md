# MiniDialog 对话框

### 功能丰富、使用简单、灵活多样的轻量级对话框组件。

#### 在线示例： [http://minidialog.applinzi.com/](http://minidialog.applinzi.com/)

#### 兼容情况：Chrome45+，Firefox40+，Edge15+，Safari11+，IE11

#### 使用方法：

1. [四种信息提示对话框](#四种信息提示对话框)
2. [快捷方式](#快捷方式)
3. [自定义左右箭头](#自定义左右箭头)

<br>

##### 1. 四种信息提示对话框

```js
// 内容可选
Dialog.info( "标题", "内容" );
Dialog.success( "标题", "内容" );
Dialog.warn( "标题", "内容" );
Dialog.error( "标题", "内容" );
```

<br>

##### 2. 快捷方式
```js
// 只传入内容（此时将采用默认标题：网页消息）
Dialog( "内容" );

// 传入标题和内容
Dialog( "标题", "内容" );

// 传入标题、内容和对话框宽度（单位：px）
Dialog( "标题", "内容", 800 );
```
