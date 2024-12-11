# 基岩版进服指南
首页 / 指南 / 基岩版

### 版本要求
由于基岩版更新频繁，支持的版本范围再不断变化，具体请看群公告

支持 Android、iOS、Windows 10/11 以及各游戏主机（需支持第三方服务器），版本号要求都是一样的，只要能够安装上即可。

Android / Windows 的基岩版安装教程可见：[Minecraft 安装和配置指南](?article=1919810/MCGuide/)

## 进服

**请从群公告获取服务器地址**，并留意其变更。

如果不会添加第三方服务器，可以查看该教程：[基岩版加入服务器](?article=1919810/MCGuide/connect/bedrock.js)

第一次进服需要下载专用的资源包。点击下载即可开始：

![正常进服](./bedrock/res-download.webp)

![正常进服](./bedrock/res-download-start.webp)

之后便会进入服务器，除非清除缓存，否则只有当资源包更新时才会要求重新下载。

![正常进服](./bedrock/finish.webp)

### 特别注意
基岩版玩家进服后**请不要更改自己的游戏名**（Xbox 玩家代号），否则会因记分板失效而导致数据异常！除了背包数据还在，其他的就什么都没了，重生转生都不行！这号就相对于废了。。。

#### 进服后不要改名！

#### 进服后不要改名！

#### 进服后不要改名！

### 错误“无法连接到世界”

- 地址不正确/网络异常：请确保网络正常，并检查地址是否输入正确。
- 网络环境限制：可能是由于运营商的限制所导致，请尝试使用群公告中的其它地址。
  - 强烈建议大家把全部地址加上，以便在某个地址不可用时切换到另一地址进服，所有地址**均指向同一服务器，玩家数据是相通的**。

### 错误“请登录Xbox账户”

请先确保确保游戏中的 Microsoft（Xbox）账户已经登录，否则会被拒绝连接。（不同于 Java 版，基岩版的账户不等同于正版，可以免费注册登录）

如果已经登录但仍是如此，请尝试连接其它同样需要登录的服务器，如果也出现类似错误，那么非常不幸，你暂时无法连接到微软验证服务器，请尝试更换网络、刷新 DNS 或魔法等手段。

### 错误“登录系统出现异常”、“数据流终止”或 Java 代码

这是服务器系统的 Bug，问题并不出自你身上，重新连接即可（使用同样地址也没问题）

## 绑定到 Java 版账户
如果你想**使 Java 版和基岩版共用同一个玩家数据**，那么你可以使用 Floodgate 插件的账户绑定功能，它能使你的基岩版使用指定 Java 版玩家的档案，从而实现基岩和 Java 版下游戏数据同步。（无需正版）

有关其操作，可见：[账户绑定](./linkaccount.md)

**请在开始游玩前先决定好了!** 因为绑定以后基岩版将使用 Java 版玩家的数据，而原先基岩版玩家的数据不会在 Java 版使用！

## 有关 HUD 无缝生命值条

为了解决玩家血量过高，导致原版生命值条遮挡画面的问题，本服启用了重新设计的 HUD 无缝生命值条，如果您在使用过程中遇到了 Bug，或者想用回原版样式，可以通过以下命令切换：
- 原版生命条: `/trigger bhud_disable set 1`
- 无缝生命条: `/trigger bhud_disable set 0`

## UI 界面出现 Bug
这很有可能是与第三方UI资源包发生冲突导致的。请检查 UI 冲突（懂点英文还可以通过内容日志来分析），当然最好就不要添加第三方 UI 了。

目前经过测试 Ty-el's UI 和 Cube UI 虽然会影响界面美观，但是不影响交互体验。对 VDX（Vanilla deluxe，仿 JE 界面）做了特别适配，可以完美兼容。

## 交易常见问题解决方法
### 交易项图标都一样，触屏该如何区分？
服务器的资源包对UI进行了修改，在左侧选栏中**每个图标按住都会显示其详细信息**：

<video autoplay loop muted><source src="./bedrock/problem/trade/get-info.mp4" type="video/mp4"/></video>

### 选择交易项后，自动放入槽位的物品图标相同但不正确
比如用五枚木元素换一枚精炼木元素，此前身上已经有数枚精炼木元素了，那么在选择交易项后可能会自动将图标和普通木元素相同的精炼木元素放入槽位：

<video autoplay loop muted><source src="./bedrock/problem/trade/same-icon-incorrect.mp4" type="video/mp4"/></video>

这是由于基岩版对 NBT 的支持不完善导致的，但其实**只要背包中有足够的正确物品，就能无视槽位上的错误物品，进行正确的交易**。

也就是说，即使放入槽位的是精炼木元素，但背包中还有足够的普通木元素，那么交易时就会**消耗背包中的普通木元素，而不是槽位中的精炼木元素**。

但如果自动放入的物品数量不够，基岩版会将**交易物品变红不能交易**，即使正确的物品足够。

<video autoplay loop muted><source src="./bedrock/problem/trade/same-icon-blocked.mp4" type="video/mp4"/></video>

这时就需要**手动将错误物品换成正确物品**，之后千万不要在左侧重新选择，否则可能又会被自动放错。

<video autoplay loop muted><source src="./bedrock/problem/trade/same-icon-rectify.mp4" type="video/mp4"/></video>

### 交易后有物品悬浮跟随手指
<video autoplay loop muted><source src="./bedrock/problem/trade/float-and-follow.mp4" type="video/mp4"/></video>

遇到此问题**可能是因为交易失败，但不完全是**，将悬浮物品放到背包中，再检查一下有没有交易得来的物品，如果有则交易成功，否则失败。

造成交易失败常见原因：
1. **书本未阅读**：在梦回盘灵中，为确保剧情完整，只有书本被阅读过才能用于交易；
2. **背包中没有交易所需的原材料**：在上一个问题中提到，基岩版会将图标相同但未必正确的物品放入槽位，而背包中又没有正确的物品。

### 交易丹药（键鼠可无视）
本服务器安装有优化修改组件，避免了丹药交易时出现的某些问题，但其原理是交易一份标有叠放数值的虚假丹药，放入物品栏后再自动转换为真正叠放的丹药，所以交易时要**确保背包始终至少留有一格空位**，否则点击交易时会无响应。

### 【严重问题】选择交易项后总是自动跳转到其他项
如果我没猜错的话，交易时最折磨人的问题非它莫属了：

<video autoplay loop muted><source src="./bedrock/problem/trade/auto-redirects.mp4" type="video/mp4"/></video>

此问题只**发生在需要提供两个物品进行交易的场景**，包括皇城铁匠铺的武器销售员。但只要在**打开交易界面以后一次性完成选择，不要有第二下**，就不会发生这种问题。

<video autoplay loop muted><source src="./bedrock/problem/trade/auto-redirects-solve1.mp4" type="video/mp4"/></video>

又或者**把槽位上的物品拿下来，再一次性选择好交易项**，也同样可以正常交易：

<video autoplay loop muted><source src="./bedrock/problem/trade/auto-redirects-solve2.mp4" type="video/mp4"/></video>

**建议在每次交易前都按下紫色“轻拍”按钮**，确认是否为所需物品，减少不必要的损失：

![轻拍查看信息](./bedrock/problem/trade/ensure.webp)

注：该按钮通常在触屏下全局显示，除非和某些第三方 UI 冲突

## 丹药等物品无法移动
为确保基岩版可正常使用丹药，并优化游戏体验，服务器添加了物品增量叠放插件，将**各类丹药、退火符、击退符、佛跳墙、万春羹、兔肉煲的叠放上限调整到了 64 个**。

但是在基岩版中由于间歇泉互通的限制，这些调整过的物品**在移动和扔出时会出现问题**。

### 移动物品位置
键鼠操作可以像 Java 原版一样**指向目标物品，按住 Shift + 鼠标左键**进行快速移动，触屏操作**直接双击目标物品**也同样。

<video autoplay loop muted><source src="./bedrock/problem/stack/move-touch.mp4" type="video/mp4"/></video>

### 合并物品到同一个槽位
（仅限触屏）将需要合并的物品**都移动到底部快捷栏**，之后就能按常规操作进行合并。

<video autoplay loop muted><source src="./bedrock/problem/stack/hotbar-marge.mp4" type="video/mp4"/></video>

也可以**使用菜单书中的“强制叠放背包物品”功能**，将背包中所有散开的物品强制叠放，每个槽位上限为 64 个。

<video autoplay loop muted><source src="./bedrock/problem/stack/forcestack.mp4" type="video/mp4"/></video>

### 按“Q”或长按扔出后物品消失不见？
手持超过标准叠放上限的物品，按“Q”或长按将其扔出，却发现物品并未扔出去，而是消失了？！

<video autoplay loop muted><source src="./bedrock/problem/stack/throw-out-on-hand.mp4?ver=040" type="video/mp4"/></video>

其实它并没有消失，服务器依旧认为它还在原位，只需要打开一下物品栏，它就会立刻刷新出来。

如果您真的需要将其扔出，请**在界面中进行操作，不要手持按“Q”或长按**。

## 钱庄末影箱，触屏点击没有响应
### 触屏没有响应
箱子中的按钮**单击选中**，界面右侧会显示按钮名称：

<video autoplay loop muted><source src="./bedrock/problem/enderbox/select.mp4" type="video/mp4"/></video>

如需按下它，只需**将按钮扔出去**即可：

<video autoplay loop muted><source src="./bedrock/problem/enderbox/drop-out.mp4" type="video/mp4"/></video>

未选中状态下，也可以**直接双击**，但物品栏至少要有一格空位：

<video autoplay loop muted><source src="./bedrock/problem/enderbox/double-click.mp4" type="video/mp4"/></video>