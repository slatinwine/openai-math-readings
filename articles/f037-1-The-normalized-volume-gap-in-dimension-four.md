---
layout: default
title: "The normalized-volume gap in dimension four"
family: "037"
discipline: "Algebraic and complex geometry"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | The normalized-volume gap in dimension four

> 结果族 037：The ordinary-double-point volume gap　·　学科：Algebraic and complex geometry　·　验证状态：暂无形式化证明，请以社区核验为准

## 入门导读 🐣

奇点"体检排行榜"的全维数版要靠数学归纳法一层层搭上去，而归纳大厦必须先有地基：四维这一层得单独夯实。这篇姊妹篇干的就是打地基的活——在四维房间里把账算到分毫不差：奇异四维芽的体检分数最多 `@@M@@162@@` 分，恰好由四维普通双重点摘得。

**关键词卡片**

- 四重芽（fourfold germ）：四维空间在一点附近的局部小碎片。
- 正规化体积（normalized volume）：奇点的健康分；光滑四维点满分 `@@M@@4^4=256@@`。
- 嵌入维数（embedding dimension）：把局部塞进平坦环境所需的最少坐标方向数。
- 超曲面（hypersurface）：只需一个方程就能切出来的空间，结构最简单。
- 稳定退化（stable degeneration）：把芽换成分数相同但形状规整的"锥"再研究的手续。

**看个具体例子**

把定理写成数字版：

`@@M@@D\widehat{\mathrm{vol}}(\text{光滑四维点})=4^4=256,\qquad
\widehat{\mathrm{vol}}(\text{四维双重点})=2\cdot 3^4=162;@@`

`@@M@@D\text{奇异 klt 四维芽}\;\Longrightarrow\;\widehat{\mathrm{vol}}\le 162,\quad
\text{等号}\iff z_0^2+z_1^2+z_2^2+z_3^2+z_4^2=0 .@@`

证明主线是一串漂亮的推理链：分数不小于 `@@M@@162@@` 迫使嵌入维数 `@@M@@\le 5@@`；奇异正规四重芽嵌入维数 `@@M@@\le 5@@` 就必为超曲面；再套用已知的完备交定理收网定案。全程不要求奇点孤立、完备交或可平滑。此前的进展都带结构假设：三维任意芽、完备交、环面芽各有各的证法，而无结构的四维孤立奇点既没有局部环表示也没有现成例外除子，正是最难啃的一块。

**为什么值得关心**

四维基例是全维数归纳的唯一跳板，缺它则"每维数成立"无从谈起；它还示范了如何从纯数值假设榨出结构约束，这套思路本身就有方法论价值。

> 暂无形式化证明（AI 结果待核验）

## 一句话结论

证明了四维情形的普通双重点体积间隙猜想：每个奇异的、边界为零的 klt 复代数四重芽的正规化体积至多 `@@M@@162=2\cdot3^4@@`，等号恰在四维普通双重点取到；这是全维度猜想的归纳基例。

## 问题背景

正规化体积（normalized volume）`@@M@@\widehat{\mathrm{vol}}(x,X)=\inf_v A_X(v)^n\operatorname{vol}(v)@@` 由 Chi Li 提出，用来给 klt 奇点"量尺寸"：Liu–Xu 证明光滑点恰取最大值 `@@M@@n^n@@`。Spotti–Sun 由奇异 Kähler–Einstein 极限的体积密度出发，猜想奇异的零边界 klt 芽体积不超过 `@@M@@2(n-1)^n@@`，等号刻划普通双重点（ordinary double point，即非退化二次型定义的解析超曲面芽）。此前已知：三维任意芽（Liu–Xu）、完备交情形（Liu）、`@@M@@\mathbb{Q}@@`-Gorenstein 环面芽（Moraga–Süß）、光滑极化底上的仿射锥（Li–Miao）。非孤立四维点已有更小的界 `@@M@@4096/27@@`（Liu），因此真正的难点是四维孤立奇点：它没有任何局部环结构假设，如何从"体积不小"这一数值假设榨出局部环的结构约束。

## 主要结果

**定理**：设 `@@M@@x\in X@@` 是四维正规复代数簇的奇异闭点，`@@M@@K_X@@` 为 `@@M@@\mathbb{Q}@@`-Cartier，`@@M@@X@@` 在 `@@M@@x@@` 附近 klt 且边界为零，则 `@@M@@\widehat{\mathrm{vol}}(x,X)\le162@@`；等号成立当且仅当解析芽同构于 `@@M@@\{z_0^2+z_1^2+z_2^2+z_3^2+z_4^2=0\}\subset\mathbb{C}^5@@`。定理不要求孤立性、完备交、商结构或可平滑性。

## 证明思路

全文枢纽是把数值假设转成局部环约束：`@@M@@\widehat{\mathrm{vol}}\ge162\Rightarrow@@` 嵌入维数（embedding dimension）`@@M@@\le5@@`；而奇异正规四重芽嵌入维数 `@@M@@\le5@@` 必为超曲面，再套用 Liu 已建立的完备交定理即得锐界与刚性。

第一步做锥化约。由稳定退化（stable degeneration，Xu–Zhuang 等）得到与原芽同密度、控制其嵌入维数的锥 `@@M@@C@@`：若锥在顶点外有奇点，其分次轨道闭包给出过顶点的正维奇异轨迹，被非孤立界 `@@M@@4096/27@@` 排除；若典范指标 `@@M@@d>1@@`，其循环指标覆盖结合有限次公式给 `@@M@@dV\le256@@`，与 `@@M@@V\ge162@@` 矛盾，故指标为 `@@M@@1@@`；klt 推出 Cohen–Macaulay，进而 Gorenstein。

第二步控制稳定子。构造分次提取 `@@M@@\pi:\widetilde C\to C@@`，例外除子 `@@M@@E@@` 满足 `@@M@@K_{\widetilde C}=\pi^*K_C+(r-1)E@@`。在横截光滑切片上取权 `@@M@@(1,\alpha,\alpha,\alpha)@@` 的单项式赋值：其差异为 `@@M@@r+3\alpha@@`，体积由切片 jet 计数估计——单一特征标的 jet 数为 `@@M@@\ell^3/6m@@` 量级——得 `@@M@@\operatorname{vol}\le h/(1+\alpha(mh)^{1/3})^3@@`。若某点稳定子阶 `@@M@@m\ge2r/5@@`，该估计在近极小分次处与 `@@M@@r^4h\to V@@` 矛盾，故 `@@M@@m<2r/5@@`。由此每个中心在顶点的本原除子 `@@M@@F@@` 满足 `@@M@@A_C(F)\ge3@@`。重标度使典范权为 `@@M@@5/2@@`，记 `@@M@@D=5/3@@`。

第三步是 Hilbert 级数对偶。把分次 Hilbert 系数与反射的典范模系数组成带号测度，由 Stanley 分次对偶与 Poisson 求和，任何带限（band-limited）测试函数对此测度的配对都等于一个显式多项式积分。选取平方 Fourier 变换乘以精心设计符号的多项式作测试（方法上与 Cohn–Elkies 球堆积线性规划同源，但不引用任何球堆积定理），使两侧符号相反，逼迫出权落在 `@@M@@(0,5/3)@@` 内的非零齐次函数；四维情形用显式测试函数与矩计算完成（核心数值不等式如 `@@M@@717687/160000>625/144@@`），二维、三维版本由典范模正性注入支撑。

第四步证明顶点的极大理想阈值 `@@M@@\operatorname{lct}_o(C;\mathfrak m_o)>3/2@@`。反设 `@@M@@\le3/2@@`，则低权函数可拼出总权 `@@M@@<5/2@@` 的齐次 lc 边界；顶点被差异估计排除，故存在正维极小 lc 中心 `@@M@@Z@@`；Fujino–Gongyo 仿射子伴随使 `@@M@@Z@@` 正规、Cohen–Macaulay 且带 klt 结构，而所有低权函数都在 `@@M@@Z@@` 上消失，与第三步在 `@@M@@Z@@` 上的低权非零性矛盾（曲线情形用稳定子界直接排除），阈值结论得证。

最后取一般超平面截面：由 `@@M@@A_C(F)\ge3@@` 与阈值 `@@M@@>3/2@@` 验证截面是 terminal Gorenstein 三维奇点，Reid 的分类把它归为孤立 cDV 点、必为超曲面，嵌入维数 `@@M@@\le4@@`，故 `@@M@@\operatorname{edim}(o,C)\le5@@`。传回原芽，用正则局部环的 UFD 性说明它是超曲面芽，Liu 的完备交定理给出 `@@M@@162@@` 界；等号情形由 ODP 处的体积 `@@M@@2\cdot3^4=162@@` 与完备交等号刻画封闭。

## 可信度与备注

本文暂无形式化证明，按 OpenAI 官方声明，未经形式化的结果可能存在问题，请以社区核验为准。姊妹篇《The ordinary-double-point gap in every dimension》以本文四维定理为唯一伴随基例，向上归纳出所有维数的猜想；两篇共用同一套稳定退化与锥化约框架。文中的 jet 计数、Poisson 求和恒等式与显式矩计算等技术引理均为本文自证，并标注了与 Buckley–Reid–Zhou、Cohn–Elkies 等工作的方法联系。

{% endraw %}
