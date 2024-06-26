# 基岩版进服指南
首页 / 指南 / 基岩版

### 版本要求
目前服务器支持的基岩版版本号为：1.20.40 ~ 1.20.72（文档更新不及时，具体请看群公告）

支持 Android、iOS、Windows 10/11 以及各游戏主机，版本号要求都是一样的，只要能够安装上即可。

Android / Windows 的基岩版安装教程可见：[Minecraft 安装和配置指南](?article=1919810/MCGuide/)

### 进服地址
提供多个指向同一服务器的地址，但它们不固定，需要您从群公告获取，并留意其变更。

## <span style="color:red">先别急着进服！！</span>
基岩版在游玩的过程中有不少常见的Bug，但是都有解决的方法，请往下看：

## 携带版或第三方 UI 导致界面异常
这将导致钱庄末影箱布局错乱、武器锻造无法正常使用。
### 钱庄末影箱、武器锻造台布局错乱
这是由于携带版 UI 的自适应布局导致的。

![武器锻造台-携带版对比常规](./bedrock/problem/ui/difference-in-weapon-forge.webp)

![钱庄末影箱-携带版对比常规](./bedrock/problem/ui/difference-in-enderbox.webp)

在设置 > 视频中将 UI 档案设置为经典即可解决。

![将 UI 档案设置为经典](./bedrock/problem/ui/set-classic-ui.webp)

### UI 界面出现 Bug
这很有可能是与第三方UI资源包发生冲突导致的。请检查 UI 冲突（懂点英文还可以通过内容日志来分析），当然最好就不要添加第三方 UI 了。

目前经过测试 Ty-el's UI 和 Cube UI 虽然会影响界面美观，但是不影响交互体验。对 VDX（Vanilla deluxe，仿 JE 界面）做了特别适配，可以完美兼容。

## 交易常见问题解决方法
### 交易项图标都一样，触屏该如何区分？
服务器的资源包对UI进行了修改，在左侧选栏中**每个图标按住都会显示其详细信息**：

<video autoplay loop muted><source src="./bedrock/problem/trade/get-info.mp4" type="video/mp4"/></video>

### 选择交易项后，自动放入槽位的物品图标相同但不正确
比如用五枚木元素换一枚精炼木元素，此前身上已经有数枚精炼木元素了，那么在选择交易项后可能会自动将图标和普通木元素相同的精炼木元素放入槽位：

<video autoplay loop muted><source src="./bedrock/problem/trade/same-icon-incorrect.mp4" type="video/mp4"/></video>

这是由于基岩版对 NBT 的支持不完善导致的，但幸好间歇泉对其做出了修复，**只要背包中有足够的正确物品，就能无视槽位上的错误物品，进行正确的交易**。

也就是说，即使放入槽位的是精炼木元素，但背包中还有足够的普通木元素，那么交易时就会**消耗背包中的普通木元素，而不是槽位中的精炼木元素**。

但如果自动放入的物品数量不够，基岩版会将**交易物品变红不能交易**。即使正确物品足够，槽位中的是错误物品。

<video autoplay loop muted><source src="./bedrock/problem/trade/same-icon-blocked.mp4" type="video/mp4"/></video>

这时就需要**手动将错误物品换成正确物品**，之后千万不要在左侧重新选择，否则又会被自动放错。

<video autoplay loop muted><source src="./bedrock/problem/trade/same-icon-rectify.mp4" type="video/mp4"/></video>

### 交易后有物品悬浮跟随手指
<video autoplay loop muted><source src="./bedrock/problem/trade/float-and-follow.mp4" type="video/mp4"/></video>

遇到此问题**可能是因为交易失败，但不完全是**，将悬浮物品放到背包中，再检查一下有没有交易得来的物品，如果有则交易成功，否则失败。

造成交易失败常见原因：
1. **书本未阅读**：在梦回盘灵中，为确保剧情完整，只有书本被阅读过才能用于交易；
2. **背包中没有交易所需的原材料**：在上一个问题中提到，基岩版会将图标相同但未必正确的物品放入槽位，而背包中又没有正确的物品。

### 交易丹药
在 0.4 版本后，丹药交易得到了很大的改善。完美解决了丹药散开问题。

但是其原理是交易一份标有叠放数值的虚假丹药，放入物品栏后再自动转换为真正叠放的丹药，所以交易时要**确保背包始终至少留有一格空位**，否则点击交易时会无响应。（键鼠可无视）

### 【严重问题】选择交易项后总是自动跳转到其他项
如果我没猜错的话，交易时最折磨人的问题非它莫属了：

<video autoplay loop muted><source src="./bedrock/problem/trade/auto-redirects.mp4" type="video/mp4"/></video>

此问题只**发生在需要提供两个物品进行交易的场景**，包括皇城铁匠铺的武器销售员。

解决的方法也是非常简单，**重新打开交易界面，一次性选择好交易项，哪都别点**，即可正常交易：

<video autoplay loop muted><source src="./bedrock/problem/trade/auto-redirects-solve1.mp4" type="video/mp4"/></video>

又或者**把槽位上的物品拿下来，再一次性选择好交易项**，也同样可以正常交易：

<video autoplay loop muted><source src="./bedrock/problem/trade/auto-redirects-solve2.mp4" type="video/mp4"/></video>

**建议在每次交易前都按下紫色“轻拍”按钮**，确认是否为所需物品，减少不必要的损失：

![轻拍查看信息](./bedrock/problem/trade/ensure.webp)

注：该按钮在 0.4 更新后全局显示

## 漏斗投放问题
### 漏斗投放物品后自动传送，导致界面消失
**该问题貌似随版本更新得到了解决，发生的概率极低。**

在传送过程中，如果玩家打开了漏斗界面，那么可能会触发 Bug 导致进入摄像机模式，界面被隐藏，**需要退出重进才能恢复**。

<video autoplay loop muted><source src="./bedrock/problem/hopper/bug.mp4" type="video/mp4"/></video>

### 最大程度避免
在被传送的一瞬间不要进行任何操作，如果还是出现的话，请退出重进并向我反馈。

<video autoplay loop muted><source src="./bedrock/problem/hopper/avoid.mp4" type="video/mp4"/></video>

## 丹药等物品无法移动
为确保基岩版可正常使用丹药，并优化游戏体验，服务器添加了物品增量叠放插件，将**各类丹药、退火符、击退符、佛跳墙、万春羹、兔肉煲的叠放上限调整到了 64 个**。

但是在基岩版中由于间歇泉互通的限制，这些调整过的物品**在移动和扔出时会出现问题**。

### 移动物品位置（0.5 更新后大幅优化）
键鼠操作可以像 Java 原版一样**指向目标物品，按住 Shift + 鼠标左键**进行快速移动，触屏操作**直接双击目标物品**也是一样。

<video autoplay loop muted><source src="./bedrock/problem/stack/move-touch.mp4" type="video/mp4"/></video>

不过有时候会看到**物品短暂被打散，然后再自动恢复正常**，这只是网络延迟造成的，并不影响实际操作，服务器**依旧认为你将所有物品正确移动**了。(该问题主要发生在钱庄末影箱)

<video autoplay loop muted><source src="./bedrock/problem/stack/move-delay.mp4" type="video/mp4"/></video>

### 合并物品到同一个槽位
（仅限触屏）将需要合并的物品**都移动到底部快捷栏**，之后就能按常规操作进行合并。

<video autoplay loop muted><source src="./bedrock/problem/stack/hotbar-marge.mp4" type="video/mp4"/></video>

也可以**使用菜单书中的“强制叠放背包物品”功能**，将背包中所有散开的物品强制叠放，每个槽位上限为 64 个。

<video autoplay loop muted><source src="./bedrock/problem/stack/forcestack.mp4" type="video/mp4"/></video>

### 按“Q”或长按扔出后物品消失不见？
手持超过标准叠放上限的物品，按“Q”或长按将其扔出，却发现物品并未扔出去，而是消失了？！

<video autoplay loop muted><source src="./bedrock/problem/stack/throw-out-on-hand.mp4?ver=040" type="video/mp4"/></video>

其实它并没有消失，服务器依旧认为它还在原位，只需要打开一下物品栏，它就会立刻刷新出来。

如果您真的需要将其扔出，请在界面中进行操作，不要手持按“Q”或长按。

## 钱庄末影箱，触屏点击没有响应
### 触屏没有响应
箱子中的按钮**单击选中**，界面右侧会显示按钮名称：

<video autoplay loop muted><source src="./bedrock/problem/enderbox/select.mp4" type="video/mp4"/></video>

如需按下它，只需**将按钮扔出去**即可：

<video autoplay loop muted><source src="./bedrock/problem/enderbox/drop-out.mp4" type="video/mp4"/></video>

未选中状态下，也可以**直接双击**，但物品栏至少要有一格空位：

<video autoplay loop muted><source src="./bedrock/problem/enderbox/double-click.mp4" type="video/mp4"/></video>

## 如果您已经知晓以上问题及其解决方法，那就继续往下看吧。

### 进服
如果不会添加第三方服务器，可以查看该教程：[基岩版加入服务器](?article=1919810/MCGuide/connect/bedrock.js)

在进服前您需要确保游戏中的 Microsoft（Xbox）账户已经登录，否则会被拒绝连接。（不同于 Java 版，基岩版的账户不等同于正版，可以免费注册登录）

第一次进服需要下载专用的资源包。点击下载即可开始：

![正常进服](./bedrock/res-download.webp)

![正常进服](./bedrock/res-download-start.webp)

之后便会进入服务器，除非资源包更新，否则下次进服不会要求重新下载。

![正常进服](./bedrock/finish.webp)

**特别注意：基岩版玩家请不要随意更改自己的 ID，否则会导致记分板失效**，除了背包数据还在，其他的就什么都没了，重生转生都不行！这号就相对于废了。。。

由于实现区分 Java / 基岩版玩家的 Floodgate 插件时常摸鱼，导致服务器**有时会加载错误的玩家数据**。如果弹出以下提示，则表明登录错误，服务器未能正确加载玩家数据，且误判为了 Java 玩家。（见左上角消息）请退出重新进入，否则**游玩数据将不会保存**：

![登录错误](./bedrock/error.webp)

**有关“无法连接到世界”，通常是由于以下问题：**

1. 地址/网络异常：请确保网络正常，并检查地址是否输入正确。
2. 地址暂时不可用：由于运营商对基岩版连接有一定限制，在某些情况下**会直接阻断连接**。为了改善游戏体验，我提供了基于 FRP 实现的备用地址，由于隧道不是长期有效的，若出现问题需再次更换，所以**地址不固定，需要您从群公告获取，并留意其变更**。**强烈建议大家添加多个地址**，以便在某个地址不可用时切换到另一地址进服，所有地址均指向同一服务器，玩家数据是相同的。
3. 游戏 Bug：发出请求后服务器能接收得到，但客户端异常一直反复请求，导致连接失败。需要重启游戏。（网络不稳定的情况下容易发生）

### 绑定 Java 版账户
如果你想**使 Java 版和基岩版共用同一个玩家数据**，那么你可以使用 Floodgate 插件的账户绑定功能，它能使你的基岩版登录到指定的 Java 版账户，从而实现基岩和 Java 版下游戏数据同步。（无需正版）

有关其操作，可见：[绑定 Java 版账户](./linkaccount.md)

/showNav();console.log("2024.4.21 随幻域无界 0.5.0 版本更新")