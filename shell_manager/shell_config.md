Shell 配置
---

蚁剑追求「自由、灵活、高扩展」的 Shell 配置理念，提供了更为强大、丰富的 Shell 配置选项。

#### 基础配置

基础配置是 Shell 最基本的信息，如果配置有误会导致 Shell 连接出错。

![][img_shell_config_1]

* **URL地址**

 Shell 的 URL 地址，后续数据包都会发送到该 URL

* **连接密码**

 当前 Shell 的连接密码

* **编码设置**

 当前 Shell 的文字编码设置，如果设置不当会导致对返回包文字解码时乱码。

 > 在 windows 下（测试系统 Win7）
 >
 > cmd 是 GBK 编码，而文件编码默认用的 ANSI，有些源代码文件使用的是 UTF-8 编码。
 >
 > 如果遇到**中文乱码**问题，可参考下表尝试解决  


  Shell 类型 | Windows XP/7/8/Server 2003 中文版| Windows 10 中文版| 类 Unix 
  :-:|:-:|:-:|:-:
  ASP | GBK | - | -
  ASPX | UTF8 | UTF8 | -
  PHP | GBK(虚拟终端)/UTF8(文件管理) | UTF8 | UTF8
  CUSTOM: JSP | UTF8 | UTF8 | UTF8

  > 韩文（Euc-KR），日文（Euc-JP 或 Shift_JIS）

 **注意：**修改编码后，需要手动清空缓存

* **连接类型**

 当前 Shell 解释器类型，可选 PHP, ASP, ASPX, CUSTOM(自定义类型)

 > 如果选择 CUSTOM 类型，需要使用特定的接口的服务端脚本，参考[Shell 范例](https://github.com/antoor/antSword/tree/master/shells)

 用户可根据当前服务端环境自行编写 CUSTOM 类 Shell，详情参考[CUSTOM 类服务端开发](../core_dev/shell/custom_shells.md)

* **编码器**

 编码器用于蚁剑客户端与 Shell 通信时的加密、编码操作，是蚁剑一大核心功能。

 > 灵活使用编码器功能，在连接防火墙后的服务端时有奇效

 * default(默认)

   通信过程不采编码与加密操作，明文传输（**不推荐**，特殊字符会被转义导致出错）

 * random(随机编码器)

   通信过程中在当前 Shell 类型支持的编码器中随机选取一种进行通信编码

 * base64

   通信时使用 base64 编码对通信数据进行编码操作（**不推荐**，已被WAF作为特征）

 * **chr**

   PHP 类型独有，通信时使用 `chr` 函数对传输的字符串进行处理拼接（**推荐**）

 * **hex**

   ASPX, CUSTOM 类独有，将通信数据字符转成16进制数据传输（**推荐**）

 * **xxxxdog**

   自定义编码器示例，ASP 类型独有，需要配合 [asp_eval_xxxxdog.asp](https://github.com/antoor/antSword/tree/master/shells/asp_eval_xxxxdog.asp) 服务端使用(**推荐**)

 除了在通信中编码处理外，还可对传输数据使用 古典密码、DES、AES 等对称加密算法加密通信数据。详见[编码器开发](../core_dev/encoder/README.md)

#### 请求信息配置

![][img_shell_config_2]

#### 其它设置

![][img_shell_config_3]


[img_shell_config_1]: http://7xtigg.com1.z0.glb.clouddn.com/doc/shell_manager/shell_config_1.jpg
[img_shell_config_2]: http://7xtigg.com1.z0.glb.clouddn.com/doc/shell_manager/shell_config_2.jpg
[img_shell_config_3]: http://7xtigg.com1.z0.glb.clouddn.com/doc/shell_manager/shell_config_3.jpg
