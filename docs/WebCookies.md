# 获取 Cookies (WebCookies)

获取当前网页会话的 Cookie 信息，支持提取全量 Cookie 或指定名称的单项 Cookie。

## 运行参数

* **浏览器会话 (driver)**
> 浏览器会话句柄标识。若不填写，默认使用当前活动会话。

* **Cookie 名称 (
ame)**
> 待提取的 Cookie 字段名称。若留空，则提取全量 Cookies。

* **输出格式 (ormat)**
> 数据序列化格式，支持 JSON、Raw、Header 等。

## 输出

> 提取到的 Cookie 文本信息（字符串或 JSON 格式）。