Shell Configuration
---

AntSword prusues the `free, flexible, highly extendible` config of shells, which can make shells more powerful and colorful.

#### Basic Config

The basic config of shells includes basic information only. Connectivity of shell can encounter errors if you has wrong config.

![][img_shell_config_1]

* **URL**

 Every network package will be sent to this URL.

* **Password**

 This means password to webshell you want to connect.

* **Encoder Setting**

 You will get messy codes if encoder isn't chosen correctly.

 > Under Windows7
 >
 > Character encoding is `GBK` for `cmd`(only for Chinese users). `ANSI` is used by some files. However some source files could be edited by using `UTF-8`
 >
 > If you have **messy characters**, please solve it according the table below:


  Shell Character encoding | Windows XP/7/8/Server 2003 Chinese Version| Windows 10 Chinese Version| *nix 
  :-:|:-:|:-:|:-:
  ASP | GBK | - | -
  ASPX | UTF8 | UTF8 | -
  PHP | GBK(Terminal)/UTF8(File Management) | UTF8 | UTF8
  CUSTOM: JSP | UTF8 | UTF8 | UTF8

  > Korean（Euc-KR），Japanese（Euc-JP or Shift_JIS）

 **Notice: ** You have to clear cache manually after chaning the encoder.

* **Interpreter Categories**

 You can choose `PHP`, `ASP`, `ASPX`, `CUSTOM`.

 > If you choose use `CUSTOM`, please make sure that the server can interpret your scripts. Reference ==> [HERE](https://github.com/antoor/antSword/tree/master/shells)

 Users can write your own shells. More details.[Develop Custom Webshells](../core_dev/shell/custom_shells.md)

* **Encoder**

 Encoders are one of main cores of AntSword, which can be used to encryption of connectivity between AntSword and server webshells.

 > You may get an amazing advantage when you are trying to connect to servers behind firewalls.

 * default

   This will transfer plain data without using any encoders. **HIGHLY NOT REMCOMMENDED.** Special characters will get escaped, which may result in errors.

 * random

   AntSword will pick up encoders randomly to connect.

 * base64

   AntSword will use base64 to encode. **HIGHLY NOT REMCOMMENEDED.** This feature has already been marked by WAF.

 * **chr**

   AntSword will use `chr` function in PHP to communicate. (Only in PHP). **REMCOMMENEDED**

 * **hex**

   AntSword will transform data into hex to communicate in `ASPX` and `CUSTOME`. **REMCOMMENEDED**

 * **xxxxdog**

   Examples of cutomizeable encoder: (ONLY IN ASP) you have to use it with [asp_eval_xxxxdog.asp](https://github.com/antoor/antSword/tree/master/shells/asp_eval_xxxxdog.asp). **REMCOMMENEDED**

 除了在通信中编码处理外，还可对传输数据使用 古典密码、DES、AES 等对称加密算法加密通信数据。详见[编码器开发](../core_dev/encoder/README.md)

#### 请求信息配置

 有时候在连接特定 Shell 时，需要使用定制的 HTTP 请求头，常见的如Cookie、User-Agent 等，或者是需要在 POST 数据中添加特定的字段，此时需要使用「请求信息配置」

![][img_shell_config_2]

* HTTP HEADERS

 该部分为 HTTP 请求头部配置，`Name` 部分填写请求头的 Key，`Value`部分填该 Key 对应的值。

 > eg: 指定 `User-Agent` 为 `AntSword 2.0 dev`
 > 
 > Name 部分填 `User-Agent`
 >
 > Value 部分填 `AntSword 2.0 dev`

 如果需要添加的 HTTP 头部数据不止一个，可以点击工具栏上的「[+]Header」按钮

* HTTP BODY

 该部分为 HTTP 请求体配置，`Name` 部分填写 POST 的 Key，`Value`部分填该 Key 对应的值。

 > eg: 指定 POST 数据包中 `mypass` 为 `antsword`
 > 
 > Name 部分填 `mypass`
 >
 > Value 部分填 `antsword`

 如果需要添加的 HTTP 数据部分不止一个，可以点击工具栏上的「[+]Body」按钮


#### 其它设置

![][img_shell_config_3]

* **忽略HTTPS证书**

 若服务端使用的证书不被信任（自签名证书或者证书过期），会导致通信失败，此时可勾选此选项，忽略对 HTTPS 证书检查。

* **虚拟终端使用缓存**

 虚拟终端默认不对执行结果进行缓存，如果与服务端网络通信质量较差，或需要保存命令执行结果，可开启此选项。

 开启此选项后，若缓存中存在该命令，则会直接使用缓存。(**不推荐开启**)

* **请求超时**

 设置 HTTP 请求超时时间，单位 ms。默认为 10000ms，始 10s。根据当前网络通信质量设置。

* **自定义终端执行路径**

 虚拟终端默认使用的 shell 路径为 `/bin/sh` 和 `cmd`，根据实际情况设置，推荐使用绝对路径。

[img_shell_config_1]: http://7xtigg.com1.z0.glb.clouddn.com/doc/shell_manager/shell_config_1.jpg
[img_shell_config_2]: http://7xtigg.com1.z0.glb.clouddn.com/doc/shell_manager/shell_config_2.jpg
[img_shell_config_3]: http://7xtigg.com1.z0.glb.clouddn.com/doc/shell_manager/shell_config_3.jpg
