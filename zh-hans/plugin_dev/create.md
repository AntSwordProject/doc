创建插件
---

### 准备工作

创建插件前需要先打开「开发者模式」

进入「插件中心」，选择「设置中心」面板，打开「开发者模式」，设置好插件开发目录后，点击「保存」按钮。下次进入插件中心后会生效。

> Tips: 鼠标「右键」点击「插件中心的图标」可快速重新加载插件中心

![][img_create_1]

开启开发者模式后，插件中心会多出「开发仓库」面板，在这里可看到开发仓库中的插件。

### 创建 myphpinfo 插件

1. 打开插件开发目录（在准备工作中已经设置），新建目录 `myphpinfo`,然后进入该目录
2. 新建 `README.md` 文件，用于详细说明该插件
3. 新建 `package.json` 文件，用于格式化插件信息，内容如下：

 ```
{
  "name": "phpinfo 信息查看",
  "name_en": "myphpinfo",
  "main": "main.js",
  "icon": "rocket",
  "version": "0.1",
  "description": "我的第一个插件，查看 phpinfo 信息",
  "description_en": "show phpinfo",
  "author": {
    "name": "Medici.Yan",
    "email": "Medici.Yan@gmail.com"
  },
  "category": "信息获取",
  "category_en": "Infomation",
  "multiple": false,
  "scripts": ["php"]
} 

 ```
 
 说明：

  * 入口脚本为 `main.js`，后面我们会创建这个文件 
  * `icon`, 选个帅气的火箭 [rocket](http://fontawesome.io/icon/rocket/)
  * `miltiple` 的值为 `false`, 不支持同时处理多个 Shell，我们只查看一个Shell的就够了
  * `scripts` 的值仅支持 `php` 这一个类型
 
 > 具体其它字段含义请参考上一小节「[插件源文件说明](./source_files.md)」
 
4. 创建入口脚本 `main.js`，内容如下：

	```
	'use strict';
	
	class Plugin {
		constructor(opt) {
		// 这里是代码
		}
	}
	module.exports = Plugin;
	```
 > 文件名`main.js`是由`package.json`中的 `script`的值指定的

### 创建文件结束

现在整个目录树是这个样子：

```
plugins-dev
	|
	└── myphpinfo
	    ├── README.md
	    ├── main.js
	    └── package.json
```

进入「插件中心」，此时可以看到「开发仓库」面板下已经出现了我们刚刚创建的 `myphpinfo`插件，见下图：

![][img_create_2]

> 不过此时这个插件没有任何功能，我们下节再讲如何编写代码。

[img_create_1]: http://7xtigg.com1.z0.glb.clouddn.com/doc/plugin_dev/create_1.png
[img_create_2]: http://7xtigg.com1.z0.glb.clouddn.com/doc/plugin_dev/create_2.png