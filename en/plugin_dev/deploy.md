Release Plugins
---

All plugins of AntSword is hosted on [GitHub: AntSword-Store](https://github.com/AntSword-Store/) so that everyone could review it online.

> This section talks about backdoor of plugins and solution. Please read it very carefully.

### How To Release


1. Create a empty repository and upload source code of your plugins into it on [GitHub](https://github.com)

    > Please make sure that your plugin's name doesn't share the same name at [AntSword-Store](https://github.com/AntSword-Store/).

2. Commit an [issue](https://github.com/AntSword-Store/AntSword-Store.github.io/issues) about your application for uploading to [official AntSword Plugin Store](https://github.com/AntSword-Store/AntSword-Store.github.io)

3. Fill in basic informatin according to the template of issue

 ``` 
	## Application For New Plugin
	
	- [ ] I DO make sure this plugin is only for website management instead of ILLEGAL USE.
	- [ ] **THERE IS NO BACKDOOR EMBEDDED.**
	- [ ] I make sure that this doesn't share too much code with other plugins.
	- [ ] This plugin have been tested successfully without severe bugs.
	- [ ] I've writen `package.json` according to the code-style of plugins.
	- [ ] I've add `README.md` with details of how to use this plugin.
	
    The URL of my plugin: https://github.com/xxx/plugin
	
 ```
 
 Here is an example for reference: [New Plugin: PortScan](https://github.com/AntSword-Store/AntSword-Store.github.io/issues/1)
 
4. After finishing auditing, we'll fork your plugin into our official repository, which is [AntSword-Store](https://github.com/AntSword-Store)

### How To Update

1. The author update your plugin in your repository
2. Create a `Pull Request(PR)` to AntSword-Store
3. We will update after auditing

> Only accept the original author's PR. Other contributors could create a PR to original author if you want to update the plugin owned by others.

Here is an example for reference: [Update Plugin: AS_BugScan](https://github.com/AntSword-Store/AS_BugScan/pull/2)


### Report Abuse

Whether this plugin is embedded an backdoor is that everyone cares mostly.
Official AntSword-Store are trying to this kind of phenomenon by auditing all the applications and updates.


**It's HIGHLY RECOMMENDED NOT to use any plugins from the 3rd party.**

> Please choose HIGHLY carefully for high possibiliy that backdoors are embedded from 3rd party.

If you find any backdoors, pluease create an [issue](https://github.com/AntSword-Store/AntSword-Store.github.io/issues) to report abuse.

Template for reporting backdoors:

```
## Report backdoors:

- [ ] I've make sure that this plugin has backdoors embedded
- [ ] I've located the position of backdoors

URL: https://github.com/Medicean/AS_BugScan/blob/master/index.js#L8

### Details:

Please decribe it carefully and tell us how to reproduce.

```
