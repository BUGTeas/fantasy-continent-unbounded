# 交易常见问题解决方法
首页 / 指南 / 基岩版 / 游戏内已知问题

### 交易项图标都一样，触屏该如何区分？
服务器的资源包对UI进行了修改，在左侧选栏中**每个图标按住都会显示其详细信息**：

<video autoplay loop muted><source src="./trade/get-info.mp4" type="video/mp4"/></video>

### 选择交易项后，自动放入槽位的物品图标相同但不正确
比如用五枚木元素换一枚精炼木元素，此前身上已经有数枚精炼木元素了，那么在选择交易项后可能会自动将图标和普通木元素相同的精炼木元素放入槽位：

<video autoplay loop muted><source src="./trade/same-icon-incorrect.mp4" type="video/mp4"/></video>

这是由于基岩版对 NBT 的支持不完善导致的，但幸好间歇泉对其做出了修复，**只要背包中有足够的正确物品，就能无视槽位上的错误物品，进行正确的交易**。

也就是说，即使放入槽位的是精炼木元素，但背包中还有足够的普通木元素，那么交易时就会**消耗背包中的普通木元素，而不是槽位中的精炼木元素**。

但如果自动放入的物品数量不够，基岩版会将**交易物品变红不能交易**。即使正确物品足够，槽位中的是错误物品。

<video autoplay loop muted><source src="./trade/same-icon-blocked.mp4" type="video/mp4"/></video>

这时就需要**手动将错误物品换成正确物品**，之后千万不要在左侧重新选择，否则又会被自动放错。

<video autoplay loop muted><source src="./trade/same-icon-rectify.mp4" type="video/mp4"/></video>

### 交易后有物品悬浮跟随手指
<video autoplay loop muted><source src="./trade/float-and-follow.mp4" type="video/mp4"/></video>

遇到此问题**可能是因为交易失败，但不完全是**，将悬浮物品放到背包中，再检查一下有没有交易得来的物品，如果有则交易成功，否则失败。

造成交易失败常见原因：
1. 书本未阅读：在梦回盘灵中，为确保剧情完整，只有书本被阅读过才能用于交易；
2. 背包中没有交易所需的原材料：在上一个问题中提到，基岩版会将图标相同但未必正确的物品放入槽位，而背包中又没有正确的物品。

### 交易丹药
由于梦回盘灵的丹药一次交易至少几份叠放，**这导致在交易时只有其中一个落入背包，其余的都会悬浮跟随**，需要将其扔出再捡回才能正常叠放。

<video autoplay loop muted><source src="./trade/potion-float.mp4" type="video/mp4"/></video>

但如果点交易无响应，则是因为背包中的空间不足以丹药逐个存放导致的，这也是间歇泉的一个 Bug 。

比如要换**五个新手疗愈丹**，那么背包中就至少要有**五个空位**，即使交易后是叠放的。

![预留空位](./trade/potion-request-space.webp)

### 选择交易项后总是自动跳转
如果我没猜错的话，交易时最折磨人的问题非它莫属了：

<video autoplay loop muted><source src="./trade/auto-redirects.mp4" type="video/mp4"/></video>

此问题只**发生在需要提供两个物品进行交易的场景**，包括皇城铁匠铺的武器销售员。

解决的方法也是非常简单，**重新打开交易界面，一次性选择好交易项，哪都别点**，即可正常交易：

<video autoplay loop muted><source src="./trade/auto-redirects-solve1.mp4" type="video/mp4"/></video>

又或者**把槽位上的物品拿下来，再一次性选择好交易项**，也同样可以正常交易：

<video autoplay loop muted><source src="./trade/auto-redirects-solve2.mp4" type="video/mp4"/></video>