Introduce to Source of Plugins
---

The plugins will be installed in `antsword/antData/plugins`.
Every plugin has its own directory, while its name is the same as that on Github.
The directory of plugins can get created by any author. Howevert, `antsword/antData/plugins-dev` is RECOMMENDED.


> Make sure that names that you are gonna use has no conflicts with other plugins.

All files of a simplest plugin of AntSword are as follows:

```
.
├── README.md     // Introduction to this plugin.
├── package.json  // basic dependies(ESSENTIAL)
└── index.js      // entrance to plugins. Named asigned by package.json
```

### package.json

This file includes basic information, which is needed when core framework loading list of plugins.
Also, this file must be under the root directory of plugins.

Let's take [CopyShell](https://github.com/AntSword-Store/CopyShell) as an example:

```
{
  "name": "Copy Shell配置",
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

Field | Instruction | Comment
:--|:--|:--
name | name by Chinese|
name_en | name by English|
main | entrance file | 
icon | icon | More: [FontAwesome](http://fontawesome.io/icons/)
version | version | coding style: `X.Y.Z` ( You can omit `Z` when `Z` is `0`)
description | description by Chinese | 
description_en | description by English | explain what your plugin do simply.
author | author's information | stored as `list` type
author["name"] | author's name |
author["email"] | author's email |
category | categories by Chinese | 
category_en | categories by English | The plugin will show up under `Default`.
multiple | whether support multiple plugins, value: `true`, `false` |  Case sensitive.`false` ==> only call the object you selected; `true` ==> call the list of multiple objects.
scripts | value: `php `、`asp`、`aspx`、`custom` | CASE SENSITIVE

### index.js

entrance file, named by the field of `main` of `package.json`.

Template：

```
class Plugin {
  constructor(opt) {  // constructor
	 // coding here
	 // ...
	 console.log(opt);
  }
}

module.exports = Plugin;
```

`opt` will be the selected webshell object if `multiple` is setted as `false`.
Otherwise it should be a list.
You can see the difference when you are debugging.

> Next section will guide you to develop your first plugin, named `myphpinfo`.
