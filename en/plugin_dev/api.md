Arguments
---

### opt

When `multiple` is setted as `false`, User has to choose a webshell to load this plugin.
The details of arguments are as follows:

```
{
    "category": "default",
    "url": "http://127.0.0.1:32769/ant.php",
    "pwd": "ant",
    "type": "php",
    "ip": "127.0.0.1",
    "addr": "IANA's reserved address",
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

Explanation：

Field | Explanation
:-- | :--
category | which category your webshell belongs to
url | your webshell's URL
pwd | password for your webshell
type | type of webshells, value: `php`、`asp`、`aspx`、`custom`
ip | IP address
addr | address in the real world
encode | character encoding
encoder | encoder
httpConf | http request config
otherConf | other configs
ctime | create time
utime | last update time
_id | the unique ID


### opts

When `multiple` is setted as `true`, users have to choose at least one webshell to load it.
The arguments are as follows:

> It is remarkable that `opts` is a list type including multiple `opt`.

```
[{
    "category": "default",
    "url": "http://127.0.0.1:32769/ant.php",
    "pwd": "ant",
    "type": "php",
    "ip": "127.0.0.1",
    "addr": "IANA's reversed address",
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
