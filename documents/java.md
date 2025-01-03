# Java 版进服指南
首页 / 指南 / Java 版

### 版本要求
目前支持以下 MC 版本：**1.20.2-1.21.1**
- 原版客户端推荐：1.20.2
- Mod 客户端推荐：1.20.3/1.20.4
- 不再支持 1.20/1.20.1 !!!

Java 版对平台要求不限（万物皆可），但相比基岩版对配置的要求更高，且对触屏不友好。

### 进服地址
需要您从群公告获取，并留意其变更。

### 资源包要求
由于Java版像基岩那样进服自动加载资源会导致告示牌变英文代码，需要玩家自行下载并添加：[showLink](https://www.123pan.com/s/0nHvjv-uyqHh.html)

由于专用资源包不包含材质和音乐，**两个资源包都需要添加**，按照下图顺序。**标红不兼容不用管**，在专用包中都做了修复。

![资源包加载顺序](./java/res-pack-order.webp?v=2)

你也可以添加第三方的美化包，但必须在专用包下方，因为部分美化包针对某些 DLC 服务器修改过的游戏规则，**对原版梦回盘灵的语言文本文件进行了修改**，这些修改过的文本内容中提到的规则显然**不同于原版梦回盘灵**，对玩家造成极大的误解。

如果资源包未正确添加，进服后你会看到这样的画面：

![资源包未正确添加](./java/no-resource-pack.webp)

**注意：** 如果要进入其他同样拥有专用包的服务器，请先将我们服的专用包卸载！

## 进服
<!--Java 版登录通道使用 LittleSkin 外置登录系统，并开启白名单。

### 注册
**LittleSkin 的使用教程见**：[外置认证设置指南 (LittleSkin 皮肤站)](?article=1919810/MCGuide/skinSite/littleskin.js)

如果您曾在凭据登录下游玩过，则角色名必须和原来在凭据登录网页中的玩家名一致，且区分大小写，否则数据将不同步。（已有同名角色的可跳过）

![示例图](./java/move-account/name.webp)

### 白名单申请
为了更高效地管理服务器，新登录系统启用了**白名单系统**。

添加好角色后，请填写腾讯文档提交白名单申请：[showLink](https://docs.qq.com/form/page/DR0JIYnh5Ykt6ZG9V)

注意：允许一个 QQ 号申请两个玩家账户，多出的一律不批，除非向我申请注销原有的玩家。

### 登录进服-->

目前支持 Java 微软账户正版以及 [LittleSkin](?article=1919810/MCGuide/skinSite/littleskin.js) 第三方验证登录进服，不支持离线模式

添加群公告中的 Java 版地址，之后大概显示如下：

![服务器MOTD](./java/motd.png)

直接点击进服即可开始。

## 常见问题

### 皮肤不可见

目前已知的皮肤显示问题：
- JE 正版玩家看不到 JE 外置登录玩家的皮肤
- BE 玩家看不到 JE 外置登录玩家的皮肤，但玩家可以通过菜单书第三页的功能进行修复
- BE 皮肤有概率加载失败，对方重新进服就能恢复
- JE 玩家看不到 BE 玩家的非标准模型皮肤（4D/5D），BE 玩家看不到 JE 玩家的披风

### 丹药叠放
服务器添加了物品增量叠放插件，将**各类丹药、退火符、击退符、佛跳墙、万春羹、兔肉煲的叠放上限调整到了 64 个**，可以和其他物品一样正常移动。

<!--当玩家直接连接服务器时，会返回以下错误：

![需要通过登录插件](./java/JERefused.webp)

这是因为Java版登录通道虽然使用离线账户系统，但出于安全性考虑，我为其部署了依靠网页进行验证的 WebAuth 登录插件，此时我们需要在指定的网页中完成登录操作。首先打开链接 [showLink](http://fcub-login.eo.mk/) 进入登录页面：

![网页登录界面](./java/JELogin1.webp)

如果未进行注册，需要您进行注册，点击下方的“没有账号，去注册”进入注册界面：

![进入注册界面](./java/JELogin2.webp)

此处的“账号/玩家名”最短长度为4位，**只能包含数字、大小写英文、下划线、英文横杠**。将密码设置完毕后点击“立即注册”即可完成注册，之后会回到登录界面，输入刚才注册的账号和密码：

![登录](./java/JELogin3.webp)

点击“立即登录”，进入账户资料界面。这里的玩家名默认是注册时的账号，可以修改但需慎重，修改后原来的玩家数据会被释放，可被他人占用，而您也将因为新建玩家数据而回到新人广场重新开始（改回去即可恢复）

“登录凭据”只能查看一次，之后需通过点击旁边的“刷新”将其重置后才能查看，之后原来的凭据将失效。在超出下方的“过期时间”后凭据会自动刷新重置，需要你回到网站重新获取。

![获取凭据](./java/JELogin4.webp)

在启动器上使用凭据作为名称，新建一个离线账户。这里以 HMCL 为例：

![使用凭据新建离线账户](./java/JELogin5.webp)

使用该离线账户启动游戏，之后方可进入服务器：

![进入服务器](./java/finish.webp)

在凭证过期前，你可以直接使用凭证登录服务器，而无需打开网页。

### 登录异常
由于实现区分 Java / 基岩版玩家的 Floodgate 插件时常摸鱼，导致服务器**有时不能正确地辨认玩家**。如果弹出以下提示，则表明**您被误判为基岩版玩家**，导致配置出错。这会影响到您的正常游戏，**请退出重新进入，否则将无法正常游玩**：

![登录错误](./java/error.webp)-->

## 绑定基岩版账户
如果你想**使 Java 版和基岩版共用同一个玩家数据**，那么你可以使用 Floodgate 插件的账户绑定功能，它能使你的基岩版使用指定 Java 版玩家的档案，从而实现基岩和 Java 版下游戏数据同步。（无需正版）

有关其操作，可见：[账户绑定](./linkaccount.md)