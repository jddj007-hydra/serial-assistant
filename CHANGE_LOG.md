
# 更新日志
## 2016年1月24日 周日 Version 1.3
### 功能
* 新增 支持多种编码方式，中文收发测试正常
* 新增 支持发送追加特殊内容，如换行(\n)等，参见“设置->发送追加”菜单项
* 新增 软件配置信息新增配置项的保存和复原
* 新增 状态栏新增数据接收状态指示

### Bug修复
* 修复 状态栏显示问题：自动发送时状态栏不能正常提示
* 修复 工具包函数库有时出现字符串转换异常的问题

### 其他
* 无需再像上一个版本那样，发送换行符时需要手动添加ASCII码，简化了操作
* 程序的稳定性进一步提升

## 2016年1月21日 周四 Version 1.2
### 功能
* 新增 接收到的串口数据可以选择使用某种方式显示：`字符串`，`二进制`，`八进制`，`十进制`，`十六进制`等形式
* 新增 串口发送可以选择`字符串`和`十六进制`两种模式
* 新增 给部分面板添加了可滚动的布局，可以自适应窗口尺寸，增加了窗口变化的灵活性
* 新增 串口数据处理时，采用了一个缓冲区来暂存接收到的数据，当到达一定阈值后，会启动数据处理的线程在后台处理和分析数据，而不会阻塞接收线程，提高了程序的稳定性和可靠性

### Bug修复
* 修复 某些情况下因为接收数据缓冲区数据没有到达指定阈值而迟迟得不到处理的问题
* 修复 部分界面显示问题
* 修复 串口数据接收稳定性问题

## 其他
* 如何发送带有特殊转义字符的文本数据？
 * 首选选择发送方式为`字符`模式，然后在发送框中输入要发送的文本`Hello world!`
 * 然后选择发送方式为`十六进制`模式，然后再文本输入框中追加要发送的转义字符ASCII码，如换行符`0A`
 * 接下来再次切换到`字符`模式，此时再进行发送时便会将换行符号一并发送了。

* 测试发现，即使发送间隔为1ms，由于采用了多线程模式，软件整体运行正常，数据显示正常，没有卡顿的现象


## 2015年9月20日 周日 Version 1.1
### 功能
* 新增 软件启动后自动查找可用端口号功能
* 新增 保存接受区数据到指定存储路径功能
* 新增 软件退出前自动关闭已开启的端口号；询问是否保存软件的配置功能
* 新增 快捷保存数据功能(左Ctrl+S)
* 新增 快捷进入/退出“简洁视图模式”功能（左Ctrl+Enter)
* 新增 恢复通过菜单项进入或者退出“简洁视图模式”功能

### Bug修复
* 修复 软件启动后没有恢复到配置保存的上次关闭的位置
* 修复 退出菜单项无效的问题
* 修复 某种特别情况下，从简洁视图模式恢复时出现崩溃的现象

### 其他
* 移除菜单项“保存（S）”，该菜单项功能与面板中保存数据按钮功能重复
* 添加“关于”窗体
* 版本号升级到Version 1.1


## 2015年9月15日 周二 Version 1.0
### 功能
* 新增 配置信息保存功能，目前保存的配置信息有：
 * 波特率
 * 奇偶校验位
 * 数据位
 * 停止位
 * 字节编码
 * 发送区文本内容
 * 自动发送时间间隔
 * 窗口状态：最大化|高度+宽度
 * 面板显示状态

* 新增 软件启动后自动加载配置信息功能

### Bug修复
* 加载面板显示配置信息后，面板状态与对应菜单项显示不一致的问题 

### 其他
* 移除菜单“加载配置(L)”，改为软件启动后自动查找配置并加载
* 移除菜单“简洁模式”，当手动将三个面板全部隐藏后自动进入“简洁模式”，暂时去除一键进入“简洁模式”功能菜单
