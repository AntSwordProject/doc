插件参数
---

### opt

`multiple`为`false`时，用户选中一个Shell后才能加载该插件，传递给该插件的参数内容为当前先中的Shell的信息，详细如下：

```
{
    "category": "default",
    "url": "http://127.0.0.1:32769/ant.php",
    "pwd": "ant",
    "type": "php",
    "ip": "127.0.0.1",
    "addr": "IANA 保留地址用于本地回送",
    "encode": "UTF8",
    "encoder": "default",
    "httpConf": {
        "body": {},
        "headers": {}
    },
    "otherConf": {
        "command-path": "",
        "ignore-https": 0,
        "request-timeout": "5000",
        "terminal-cache": 0
    },
    "ctime": 1489506330997,
    "utime": 1489506351914,
    "_id": "Hm7Zls8KlCJegT39"
}
```

说明：

字段 | 说明
:-- | :--
category | Shell 分类
url | Shell 的 URL 地址
pwd | Shell 密码
type | Shell 类型，取值为 `php`、`asp`、`aspx`、`custom`
ip | IP地址
addr | 物理地址
encode | 字符编码
encoder | 编码器
httpConf | http 请求配置信息
otherConf | 其它选项
ctime | 创建时间
utime | 最后更新时间
_id | 数据库中唯一 ID


### opts

`multiple`为`true`时,用户选中至少一个Shell后才能加载该插件，传递给该插件的参数内容为选中的Shell的信息，详细如下：

> 与 opt 不同的是，opts是一个包含了多个opt的列表

```
[{
    "category": "default",
    "url": "http://127.0.0.1:32769/ant.php",
    "pwd": "ant",
    "type": "php",
    "ip": "127.0.0.1",
    "addr": "IANA 保留地址用于本地回送",
    "encode": "UTF8",
    "encoder": "default",
    "httpConf": {
        "body": {},
        "headers": {}
    },
    "otherConf": {
        "command-path": "",
        "ignore-https": 0,
        "request-timeout": "5000",
        "terminal-cache": 0
    },
    "ctime": 1489506330997,
    "utime": 1489506351914,
    "_id": "Hm7Zls8KlCJegT39"
}]
```
