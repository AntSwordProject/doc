插件源文件介绍
---

插件安装后会出现在`antsword/antData/plugins`目录下,每个插件一个目录，文件名为github仓库名，插件的开发目录可由作者自由指定，建议插件目录为`antsword/antData/plugins-dev`

> 注意在创建之前确保无同名插件

一个最简单的 AntSword 插件的所有文件如下：

```
.
├── README.md     // 插件使用说明
├── package.json  // 插件基础信息文件(必需)
└── index.js      // 插件入口文件，文件名由package.json指定
```

### package.json 文件

该文件包含了该插件的基础信息，核心框架读取插件列表时也是基于该文件，该文件必需在插件根目录下。

以插件[CopyShell](https://github.com/AntSword-Store/CopyShell)为例：

```
{
  "name": "复制Shell配置",
  "name_en": "CopyShell",
  "main": "index.js",
  "icon": "clipboard",
  "version": "0.1",
  "description": "复制选中的WebShell配置到剪贴板",
  "description_en": "Copy WebShell URL to ClibBoard",
  "author": {
    "name": "Medici.Yan",
    "email": "Medici.Yan@gmail.com"
  },
  "category": "",
  "category_en": "",
  "multiple": false,
  "scripts": ["php", "asp", "aspx", "custom"]
}
```

字段名 | 说明 | 备注
:--|:--|:--
name | 中文名称|
name_en | 英文名称 |
main | 入口文件 | 
icon | 插件在菜单栏中的图标 | 图标为，参见[FontAwesome](http://fontawesome.io/icons/)
version | 版本号 | `X.Y.Z`风格，Z为 0 时可省略
description | 中文描述 | 一句话向别人介绍你的插件用途
description_en | 英文描述 |
author | 插件作者信息 | 字典类型
author["name"] | 作者名字 |
author["email"] | 作者邮箱 |
category | 中文插件分类 | 为空则会出现在`默认分类`子菜单下，作者可自由命名类型，建议4个汉字，如：`内网工具`、`信息获取`
category_en | 英文插件分类 | 为空则会出现在`Default`子菜单下
multiple | 是否支持多插件调用，取值为`true`、`false` | 注意小写，如果该值为false则在调用时会传递选中的Shell对象，如果为true则传递的参数为Shell对象列表
scripts | 支持的Shell类型列表，取值为`php `、`asp`、`aspx`、`custom` | 注意全小写

### index.js

插件入口文件，该文件名称由 `package.json` 的 `main` 字段指定

插件入口如下：

```
class Plugin {  // 插件类
  constructor(opt) {  // 构造函数
	 // 这里是插件代码
	 // ...
	 console.log(opt);
  }
}

module.exports = Plugin;
```

如果该插件的 `multiple` 为`false`则在 `opt` 为一个当前选中的Shell对象，如果为`true`则`opt`的值为选中的Shell对象列表。你可以打开菜单栏中的「`调试`」菜单下的「`开发者工具`」，来观察两者区别。

> 下一节将带你创建自己的第一个插件`myphpinfo`