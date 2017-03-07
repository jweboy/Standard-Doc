# css命名规则
## 整体规划
项目样式采用命名空间定义`block`之间的关系，根据各自职能划分为以下几块内容：

    base —— 重置默认样式,保证浏览器一致
    layout —— 界面布局、版面样式
    components —— 可复用的模块、组件样式
    state —— 界面状态、条件、js钩子样式
    themes —— 界面主题、字体样式
    untility —— 通用工具样式

## 具体细分

**base**<br />
依据[normalize.css](https://necolas.github.io/normalize.css/)作为参考,分离出`PC-reset.css`与`MB-reset.css`两套基本样式。

**layout - layout.css**<br />
布局以`.l-`开头,表示布局对象`layout`。

    .l-content
      width:400px
      background:#efefef
    .l-sidebar
      float:right

**components - 参照[BEM](https://en.bem.info/)规范**<br />
[BEM](#)通常分为`Block`, `Element`, `Modifier`。`Block` 是一个独立的模块化的 UI 组件;`Element` 是 `Block`  的组成部分，服务于一个单一的目的;`Modifier` 用于改变 `Block`  和 `Element`  的默认样式。
以下是命名规范:

-   .block
-   .block--modifier
-   .block__elemnt
-   .block__elemnt--modifier

示例如下:

    <form class="loginForm loginForm--errors">
      <label class="loginForm__username loginForm__username--error">
        Username <input type="text" name="username" />
      </label>
      <label class="loginForm__password">
        Password <input type="password" name="password" />
      </label>
      <button class="loginForm__btn loginForm__btn--inactive">
        Sign in
      </button>
    </form>

`loginForm`就是block模块
`loginForm`由以下3个`element`组成:

-   loginForm__username
-   loginForm_password
-   loginForm_btn

`loginForm`的3个`modifier`:

-   loginForm--errors 组件错误状态复数形式，登陆表单的错误状态样式;
-   loginForm__username--error 用户名元素错误状态的样式;
-   loginForm__btn--inactive 登陆按钮的不可用样式。

**state**
状态以`.is-`,`.has-`,`.js-`开头,`.js-`表示js操作dom时添加class。

    .is-hidden
      display:none
    .is-highlighted
      color: #FF0000
      background-color: #f4f0bb
      border: 1px solid #cbbd15
    .js-hover
      color:#f00
 
**themes**
状态以`.t-`开头,`skin`表示皮肤,`font`表示字体。

    .t-skin-default
      background: #1ab394
    .t-skin-blue
      background: #0d8ddb
    .t-font-black
      color:#000
    .t-font-gray
      color:#efefef

**untility**
工具类以`.u-`开头,表示主题对象`untility`。

    .u-hidden
      display:none
    .u-mt10
      margin-top:10px

## 命名规则
**页面结构**

| 头部 | header  | 主体  | main  |
| --- | --- | ---| ---|
| 底部 | footer  | 容器 | wrapper |
| 侧栏 | sidebar | 栏目 | column  |
