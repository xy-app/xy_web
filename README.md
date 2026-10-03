# 🌐 Web 自动化组件套件 (Web Automation Suite)

[![Plugin Version](https://img.shields.io/badge/version-0.50.5-blue.svg)](manifest.json)
[![Group](https://img.shields.io/badge/group-Web-cyan.svg)](#)
[![Platform](https://img.shields.io/badge/platform-All-green.svg)](#)
[![License](https://img.shields.io/badge/license-Freeware-brightgreen.svg)](#)

官方原生现代浏览器与网页自动化交互套件。专为高并发 Web RPA 机器人、数据采集、表单批量录入及端到端自动化测试打造。提供免沉重依赖的浏览器启动与接管、全能 DOM 元素智能拾取、复合鼠标键盘拟人化动作链 (ActionChains)、智能动态显式等待 (Explicit Waits)、表格/列表结构化抓取、无弹窗静默文件上传、嵌套 iframe 上下文穿透及脚本注入执行等全链路能力。

---

## 📖 简介 (Overview)

`xy_web` 提供工业级浏览器操控标准与低延迟网页交互引擎：
- **浏览器会话与多标签调度**：支持 Chrome、Edge 等主流浏览器实例启动或用户配置目录接管（`WebOpen`），通过正则或标题关键词实现毫秒级多标签页切换（`WebSwitchTab`），以及全页面/元素级高清截图（`WebScreenshot`）。
- **复合拟人化动作链 (ActionChains)**：提供直观高效的链式微动作构造器，支持平滑悬停（`WebActionMoveTo`）、鼠标长按拖拽与滑块验证（`WebActionClickHold` / `WebActionDragDrop` / `WebActionRelease`）、修饰键组合按压（`WebActionKeyDown` / `WebActionKeyUp`）以及模拟真人击键间隔与微停顿（`WebActionPause`）。
- **全智能显式等待体系 (Explicit Waits)**：内置 6 种工业级异步等待算子，支持超时控制与轮询检测元素可点击（`WebWaitClickable`）、可见性翻转（`WebWaitVisibilityByLocator` / `WebWaitVisibilityByElement`）、DOM 呈现/消失（`WebWaitPresence`）、标题变化（`WebWaitTitle`）、页面 Alert 弹窗现身（`WebWaitAlert`）及 iframe 就绪自动切入（`WebWaitFrameAvailable`）。
- **DOM 操作与自动化支持**：支持元素点击、表单提交、文本键入清空、单选复选状态判定（`WebElementSelected`）、属性嗅探提取（`WebElementAttribute`）、会话 Cookie 导出（`WebCookies`）及页面脚本注入执行（`WebExecute`）。
- **企业级特殊场景支持**：
  - **静默文件上传 (`WebUploadFile`)**：直接指定本地文件路径上传，彻底规避操作系统原生文件选择弹窗阻塞。
  - **嵌套 iframe 穿梭 (`WebSwitchToFrame` / `WebFocusDefaultFrame`)**：多层级内联框架自由进入与一键退出回退顶层。
  - **原生 Alert / Confirm / Prompt 对话框响应 (`WebHandleDialog`)**：自动化接受、拒绝或回填内容。
  - **表格/列表数据智能提取 (`WebExtractTable`)**：自动解析表格与列表结构为行列矩阵。

---

## ✨ 核心特性 (Features)

- **原生轻量交互**：轻量高效架构，执行流畅稳定，资源占用极低。
- **全链拟人化交互**：通过 `WebActionChains` 编排连续微动作，支持平滑轨迹与自定义物理微延时，轻松应对复杂网页交互与滑块验证。
- **静默文件上传**：解决自动化中无法跨进程控制操作系统的 “文件选择” 弹框痛点。
- **丰富的显式等待守卫**：拒绝粗暴机械硬编码等待，依托精确的状态轮询守卫，将流程执行耗时压缩至极限并消除网络抖动引发的偶发错误。
- **免登录态迁移**：支持指定 `user_data_folder` 与 `profile_directory` 继承本地已登录账号会话，搭配 `WebCookies` 快速提取认证信息。

---

## 🛠️ 动作指令全景速查 (Action Catalog)

| 动作标识 (Tag) | 功能名称 | 描述 | 输出类型 |
| :--- | :--- | :--- | :--- |
| `WebOpen` | 打开网页 | 启动或接管浏览器并加载目标 URL，支持指定 Profile 目录 | `string` |
| `WebSwitchTab` | 切换标签页 | 根据标题关键词或 URL 规则快速切换当前活跃标签页 | `string` |
| `WebScreenshot` | 网页截图 | 截取整页视口或指定 DOM 元素的画面存为图像 | `string` |
| `WebCookies` | 获取 Cookies | 提取当前网页会话的 Cookie 信息（JSON / Raw / Header） | `string` |
| `WebExecute` | 执行 JS 脚本 | 在网页上下文中执行自定义 JavaScript 脚本并捕获返回值 | `string` |
| `WebGetElement` | 获取网页元素 | 通过 CSS / XPath / ID / Text / Role 智能选择器定位元素 | `string` |
| `WebElementClick` | 点击网页元素 | 触发指定网页元素的点击交互 | `string` |
| `WebElementSendText` | 输入文本 | 向输入框/文本域填入给定的文本内容 | `string` |
| `WebElementClear` | 清空输入框 | 清除指定输入控件中的已有文字内容 | `string` |
| `WebElementSendKey` | 发送按键 | 向指定元素发送特殊功能按键（如 Enter、Tab、Escape） | `string` |
| `WebElementSubmit` | 提交表单 | 触发目标表单或输入控件的 Submit 动作 | `string` |
| `WebElementAttribute` | 获取元素属性 | 提取 DOM 节点的指定属性值（如 href, src, innerText, value） | `string` |
| `WebElementSelected` | 元素是否选中 | 判定 Radio 单选框或 Checkbox 复选框当前的选中状态 | `string` |
| `WebExtractTable` | 提取表格数据 | 自动识别解析网页表格或列表为结构化数据矩阵 | `string` |
| `WebUploadFile` | 静默上传文件 | 静默上传本地文件至网页上传控件，无需触发系统文件选择弹窗 | `string` |
| `WebHandleDialog` | 处理网页弹窗 | 自动响应并确认/取消页面 Alert、Confirm、Prompt 对话框 | `string` |
| `WebSwitchToFrame` | 切换到框架 | 按索引、名称或元素切入指定的 iframe / frame 嵌套环境 | `string` |
| `WebFocusDefaultFrame` | 返回主框架 | 从嵌套子框架跳出，恢复至页面顶层主 HTML 上下文 | `string` |
| `WebActionChainsPerform`| 执行动作链 | 按编排次序整体提交并回放已组装的连续动作链 | `string` |
| `WebActionClick` | 动作链.点击 | 向当前动作链追加指定元素的鼠标单击指令 | `string` |
| `WebActionDoubleClick` | 动作链.双击 | 向当前动作链追加指定元素的鼠标双击指令 | `string` |
| `WebActionClickHold` | 动作链.按住鼠标 | 向当前动作链追加鼠标左键按住不放指令（拖拽起点） | `string` |
| `WebActionRelease` | 动作链.释放鼠标 | 向当前动作链追加释放鼠标按键指令（拖拽终点） | `string` |
| `WebActionMoveTo` | 动作链.移动鼠标 | 向动作链追加平滑鼠标移动与悬停（Hover）指令 | `string` |
| `WebActionDragDrop` | 动作链.拖拽 | 向动作链追加源节点拖动至目标节点的复合手势 | `string` |
| `WebActionKeyDown` | 动作链.按下修饰键 | 向动作链追加长按 Ctrl / Shift / Alt / Meta 键 | `string` |
| `WebActionKeyUp` | 动作链.释放修饰键 | 向动作链追加释放 Ctrl / Shift / Alt / Meta 键 | `string` |
| `WebActionSendText` | 动作链.输入文本 | 向动作链追加指定元素的逐字敲击输入指令 | `string` |
| `WebActionPause` | 动作链.暂停 | 向动作链追加毫秒级拟人化操作停顿等待 | `string` |
| `WebWaitClickable` | 等待元素可点击 | 显式等待指定元素在超时内变为可见并处于可用状态 | `string` |
| `WebWaitVisibilityByLocator`| 等待元素可见(定位符)| 通过选择器显式等待元素呈现可见或完全隐藏 | `string` |
| `WebWaitVisibilityByElement`| 等待元素可见(元素) | 针对已有元素句柄显式等待其可见性状态变更 | `string` |
| `WebWaitPresence` | 等待元素呈现 | 显式等待目标节点加入 DOM 树或自 DOM 树中被移除 | `string` |
| `WebWaitTitle` | 等待标题 | 显式等待网页 Title 标题完全匹配或包含关键词 | `string` |
| `WebWaitAlert` | 等待弹窗 | 显式等待页面原生 JavaScript 弹窗出现 | `string` |
| `WebWaitFrameAvailable`| 等待框架可用 | 显式等待 iframe 框架渲染完毕并自动切入其上下文 | `string` |

---

## 📚 详细参数说明与使用参考 (Detailed Reference)

### 1. 浏览器生命周期与基础会话 (Browser & Session)

#### `WebOpen` - 打开网页
- **输入参数：**
  | 参数名 (Field) | 显示名称 | 类型 | 说明 |
  | :--- | :--- | :--- | :--- |
  | `url` | 网页地址 (URL) | `String` | 待访问的目标网页地址（如 `https://www.example.com`） |
  | `user_data_folder`| 用户数据目录 | `FolderPicker` | 浏览器 User Data 路径，用于加载本地已存插件与缓存 |
  | `profile_directory`| 配置文件目录 | `FilePicker` | 指定的 Profile 文件夹（如 `Default`, `Profile 1`） |
  | `browser` | 浏览器类型 | `String` | 目标浏览器（如 `Chrome`, `Edge`） |
- **输出类型：** `string`（生成的会话实例标识句柄）

#### `WebSwitchTab` 与 `WebScreenshot`
- **`WebSwitchTab`**：传入 `driver` 句柄与 `title_or_url`，根据标题关键词或网址部分内容实现活动 Tab 切换。
- **`WebScreenshot`**：传入 `source`（目标元素句柄或 `driver` 自身），输出全屏视口或指定控件的截图数据。

#### `WebCookies` 与 `WebExecute`
- **`WebCookies`**：传入 `driver`，可选 `name`（单项名）与 `format`（`JSON`, `Raw`, `Header`），导出用户会话状态。
- **`WebExecute`**：传入 `driver` 与 `value`（JavaScript 脚本源码），直接在当前页面执行并回传计算结果。

---

### 2. 元素定位与基础交互 (DOM Interaction)

#### `WebGetElement` - 获取网页元素
- **输入参数：**
  - `driver`: 浏览器会话句柄。
  - `by`: 定位策略（如 `css`, `xpath`, `id`, `name`, `text`, `class`）。
  - `element`: 定位表达式（如 `#username` 或指定选择器）。
- **输出类型：** `string`（目标 Element 对象句柄）

#### 常用交互算子
- **`WebElementClick`**：传入 `element`，执行点击交互。
- **`WebElementSendText`**：传入 `element` 与待输入的文字 `value`。
- **`WebElementClear`**：传入 `element`，快速清空文本框输入内容。
- **`WebElementSendKey`**：向 `element` 发送控制键 `key`（如 `Enter`, `Backspace`, `Tab`）。
- **`WebElementSubmit`**：对表单内节点触发表单提交。
- **`WebElementAttribute`**：传入 `element` 与 `attribute` 名称（如 `href`, `src`, `value`, `class`），获取其属性字符串。
- **`WebElementSelected`**：传入 `element`，检测复选框或单选框是否被勾选（返回布尔字符串）。

---

### 3. 高级场景支持：上传、弹窗、表格与框架 (Advanced Control)

#### `WebUploadFile` - 静默上传文件
- **作用：** 直接将文件路径设置到页面上传控件，无需触发操作系统原生文件选择器。
- **输入参数：** `driver`、`element`（定位到上传控件）及 `file_path`（本地物理文件绝对路径）。

#### `WebHandleDialog` - 处理网页弹窗
- **作用：** 自动响应由页面触发的原生 JavaScript 弹窗（Alert / Confirm / Prompt）。
- **输入参数：**
  - `driver`: 驱动会话句柄。
  - `accept`: 是否点击确认（`"true"` 为确定/OK，`"false"` 为取消/Cancel）。
  - `prompt_text`: 若为 Prompt 弹窗，在此填写待回填的文本内容。

#### `WebExtractTable` - 提取表格数据
- **输入参数：** `driver`、`element`（指向表格或列表容器）。自动解析表格数据并转换为二维矩阵文本输出。

#### `WebSwitchToFrame` 与 `WebFocusDefaultFrame`
- **`WebSwitchToFrame`**：传入 `driver` 与 `value`（iframe 的索引、ID 或 Name），将自动化控制焦点切入嵌套页面内部。
- **`WebFocusDefaultFrame`**：传入 `driver`，将上下文从嵌套子 iframe 中直接跳出，重置回最外层主页面。

---

### 4. 复合拟人化动作链 (ActionChains Suite)

当面对滑块拖动、手势签名或多键联动等复杂操作时，动作链提供流畅的连续操作模拟：

```
[构造阶段]
WebActionMoveTo (移动鼠标至滑块)
   └── WebActionClickHold (按住鼠标左键)
         └── WebActionMoveTo (按轨迹平移 X, Y)
               └── WebActionPause (停顿模拟物理微延时)
                     └── WebActionRelease (松开鼠标)
[提交执行]
WebActionChainsPerform (按序批量回放上述动作)
```

- **`WebActionMoveTo`**：移动至指定 `element` 或按 `offset` 像素偏移（如 `100,0`）。
- **`WebActionDragDrop`**：传入 `source` 起点元素与 `target` 终点元素，一键完成拖拽释放。
- **`WebActionKeyDown` / `WebActionKeyUp`**：长按或释放修饰键（`Control`, `Shift`, `Alt`, `Meta`），实现组合键交互。
- **`WebActionPause`**：在连续动作之间注入指定秒数（`value`）的操作停顿。
- **`WebActionChainsPerform`**：提交并驱动浏览器回放执行动作链队列。

---

### 5. 显式动态等待守卫 (Explicit Waits)

通过细粒度的动态条件轮询，替代不稳定的机械延时，保障流程平稳运行：

- **`WebWaitClickable`**：等待元素在指定 `timeout` 时间内被加载渲染且处于可用可点击状态。
- **`WebWaitVisibilityByLocator`**：基于定位表达式等待目标节点在画面中呈现或隐藏。
- **`WebWaitVisibilityByElement`**：基于已有元素句柄等待其自身可见性发生变化。
- **`WebWaitPresence`**：等待元素节点加载到 DOM 树结构中。
- **`WebWaitTitle`**：等待网页标题变成指定 `text`（`method` 支持包含或完全匹配）。
- **`WebWaitAlert`**：等待网页出现 JavaScript 对话框弹窗。
- **`WebWaitFrameAvailable`**：等待指定的 iframe 渲染完成并自动无缝切入框架内部。

---

## 📦 插件清单定义 (Manifest Reference)

```json
{
  "plugin_id": "xy_web",
  "name": "网页与浏览器自动化 (Web Automation)",
  "version": "0.50.5",
  "group": "Web",
  "group_icon": "🌐",
  "description": "提供自动打开 Chrome/Edge 浏览器、点击网页元素、自动填写表单、提取网页表格、处理弹窗与多标签页管理等功能",
  "actions": [...]
}
```

---

## 📄 许可证 (License)

本插件遵循免费专有许可协议 (Freeware)。供 小友+ 用户免费下载与使用，未经官方书面授权，严禁对二进制文件进行逆向工程、反编译或二次打包转售。
