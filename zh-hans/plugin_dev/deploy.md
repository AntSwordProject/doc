发布插件
---

蚁剑的所有上线的插件都将源代码托管在「[AntSword-Store](https://github.com/AntSword-Store/)」这个组织下，方便所有人在线查阅、审计插件源代码

> 本小节涉及到插件后门问题处理解决，请仔细阅读

### 如何发布插件

本地开发完毕的插件，想分享给更多小伙伴一起使用怎么办？本小节就来告诉你发布插件的具体流程。

1. 在[GitHub](https://github.com)上创建一个自己的插件仓库，并上传你的插件代码

	> 注意创建仓库之前，请先在「[AntSword-Store](https://github.com/AntSword-Store/)」搜索相关仓库名，不能出现重名仓库名

2. 在[AntSword 插件市场](https://github.com/AntSword-Store/AntSword-Store.github.io)仓库中提交一个上线插件的 [issue](https://github.com/AntSword-Store/AntSword-Store.github.io/issues)

3. 按照 issue 模版填写插件的信息

 ``` 
	## 新插件上架申请
	
	- [ ] 我确定我推出的插件是为了方便网站管理，而不是用于非法用途
	- [ ] **我保证该插件无后门植入**
	- [ ] 我确定不存在相同或者相似度很高的插件
	- [ ] 插件已经在本地测试成功且无较严重Bug
	- [ ] 我已经按照要求在插件源代码中编写了规范的 package.json 文件
	- [ ] 我在插件仓库中写了 README 文件，介绍该插件的使用方法等内容
	
	插件代码仓库地址是：
	
 ```
 
 给一个范例供大家参考：「[新增插件 PortScan](https://github.com/AntSword-Store/AntSword-Store.github.io/issues/1)」
 
4. 审核通过后，我们会在第一时间 fork 你的插件代码到 `AntSword-Store`这个组织下。

### 如何更新已发布插件

1. 作者自行更新自己插件仓库中的源代码
2. 向 AntSword-Store 组织下已经上架的插件仓库发起 Pull Request
3. 审核通过后会更新

> 仅接受来自插件作者的 Pull Request 请求，其它贡献者如想参与到某个插件的开发当中，可直接向插件原仓库发起 Pull Request 请求

更新插件范例参考:「[AS_BugScan更新](https://github.com/AntSword-Store/AS_BugScan/pull/2)」

### 举报后门插件

大家最关心的就是插件代码中是不是有后门，AntSword-Store 插件市场中每一次修改源代码操作都会经过审核，无论是上架新插件还是更新、升级原有插件，都是为了减少后门出现。

**强烈建议不要使用任何第三方下载渠道**

> 第三方渠道代码未经审核存在后门可能性非常高，请慎重选择

如果在使用当中发现有插件存在后门，可直接在[AntSword 插件市场](https://github.com/AntSword-Store/AntSword-Store.github.io)仓库新建一个后门举报的 [issue](https://github.com/AntSword-Store/AntSword-Store.github.io/issues)

后门举报 issue 模版如下：

```
## 后门插件举报

- [ ] 我确定这个插件存在后门，并且多次复现成功
- [ ] 我已经定位到这个后门代码位置

存在后门插件地址是：

### 后门详细说明

详细描述后门情况及触发过程

```