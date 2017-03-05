## css命名规则

---
#### **整体划分**

整体规划参考[SMACSS](https://smacss.com/)，根据项目结构，分为以下5个大类：

    base —— reset界面默认样式
    layout —— 界面布局
    module —— 可复用的模块或者组件
    state —— 界面特定状态
    theme —— 界面主题

---
#### **具体细分**
一、reset界面默认样式
:    清除默认样式依据[normalize.css](https://necolas.github.io/normalize.css/)为基础,分离出`PC-reset.css`与`MB-reset.css`两套。

二、界面布局(layout)
:    布局以`'l-'`开头

    .l-content
      width:400px
      background:#efefef
    .l-sidebar
      float:right
---
三、复用模块或组件(module)
:    **方案一：**模块以`m-`开头

    m-search-form
      height:35px
      line-height:35px
---
:    **方案二：**遵循[BEM](https://en.bem.info/)规范。
`Block`, `Element`, `Modifier` 通常被称为[BEM](#)。`Block` 是一个独立的模块化的 UI 组件;`Element` 是 `Block`  的组成部分，服务于一个单一的目的;`Modifier` 用于改变 `Block`  和 `Element`  的默认样式。
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

---
四、状态修饰类(state)
:    采用全小写的形式,`is-`,`has-`作为类名的开头。

    .is-hidden
        display:none
    .is-highlighted
        color: #FF0000
        background-color: #F4F0BB
        border: 1px solid #CBBD15

---
五、主题类(theme)
:    采用全小写的形式，`t-`作为类名的开头。

    t-default-skin
        background: #1ab394
    t-blue-skin
        background: #0d8ddb
