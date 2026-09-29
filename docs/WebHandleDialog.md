# 处理网页弹窗 (WebHandleDialog)

自动处理由页面触发的原生 JavaScript 对话框（如 alert、confirm、prompt）。

## 运行参数

* **浏览器会话 (driver)**
> 浏览器会话句柄标识。若不填写，默认使用当前活动会话。

* **响应操作 (ccept)**
> 是否确认或接受弹窗。填 	rue 为确认/接受（OK），填 alse 为取消/拒绝（Cancel）。

* **输入文本 (prompt_text)**
> 当弹窗为带输入的 Prompt 对话框时，自动回填的文本内容。

## 输出

> 无