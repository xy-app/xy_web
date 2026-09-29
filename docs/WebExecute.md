# 执行脚本 (WebExecute)

在当前网页页面上下文中同步执行自定义 JavaScript 脚本，并捕获回传计算结果。

## 运行参数

* **浏览器会话 (driver)**
> 浏览器会话句柄标识。若不填写，默认使用当前活动会话。

* **脚本内容 (alue)**
> 待执行的 JavaScript 脚本代码（如 eturn document.title;）。

## 输出

> 脚本执行后返回的结果数据（字符串或 JSON 格式）。