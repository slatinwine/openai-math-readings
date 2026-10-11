---
layout: default
title: "A Capacity Criterion for Four-State Potts Reconstruction on Trees"
family: "229"
discipline: "Probability and statistical mechanics"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | A Capacity Criterion for Four-State Potts Reconstruction on Trees

> 结果族 229：Exact three- and four-state reconstruction thresholds and four-state tree capacity　·　学科：Probability and statistical mechanics　·　验证状态：暂无形式化证明，请以社区核验为准

## 入门导读 🐣

还是传话游戏，但家谱不再整齐：有的支系代代单传，有的枝繁叶茂、增长时快时慢。什么时候全体后代仍能拼出祖宗的颜色？这篇论文给出一个漂亮的"体检指标"——把家谱当电线网络，算一个叫"容量"的量：容量为正就能重构，为零就不能。

**关键词卡片**

- 有界度确定性树（bounded-degree deterministic tree）：孩子数有上限、形状固定且已知的家谱。
- 流到无穷（flow to infinity）：从根出发、每个节点流入等于流出的非负"信息流"。
- 边阻 λ^(-2|e|)（edge resistance）：第 |e| 层的边阻力为 λ^(-2|e|)——越深处的水管越细。
- L³ 容量（L³ capacity）：在"每条无穷路径的平方损耗不超过 1"约束下能送出的最大流量。
- 重构优势（reconstruction advantage）：后代的猜测比随机猜好出的那一截。

**看个具体例子**

取 λ=1/2：第 k 层边阻为 4^k，第 3 层已是 64。一条代代单传的链：容量为 0，无法重构；换成满二叉树，d·λ^2=2×0.25=0.5，仍小于 1，容量仍为 0；把 λ 提到 0.8，则 d·λ^2=1.28，超过 1，容量变正，重构成立。主定理：重构当且仅当容量为正，对任意形状的有界度树都成立——判据只看树的"电学性质"，连增长时快时慢的怪树也能一次判明。

<div>

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 560 280"><text x="280" y="26" font-size="14" fill="#333" text-anchor="middle">同一把"容量尺"量两棵树</text><line x1="140" y1="64" x2="140" y2="96" stroke="#333" stroke-width="2"/><line x1="140" y1="114" x2="140" y2="146" stroke="#333" stroke-width="2"/><line x1="140" y1="164" x2="140" y2="196" stroke="#333" stroke-width="2"/><circle cx="140" cy="55" r="9" fill="#333"/><circle cx="140" cy="105" r="8" fill="none" stroke="#333" stroke-width="2"/><circle cx="140" cy="155" r="8" fill="none" stroke="#333" stroke-width="2"/><circle cx="140" cy="205" r="8" fill="none" stroke="#333" stroke-width="2"/><text x="140" y="228" font-size="16" fill="#333" text-anchor="middle">⋮</text><text x="158" y="84" font-size="11" fill="#777">阻 4</text><text x="158" y="134" font-size="11" fill="#777">阻 16</text><text x="158" y="184" font-size="11" fill="#777">阻 64</text><text x="140" y="252" font-size="12" fill="#333" text-anchor="middle">单传链：容量 0，无法重构</text><line x1="410" y1="59" x2="340" y2="101" stroke="#333" stroke-width="1.5"/><line x1="410" y1="59" x2="480" y2="101" stroke="#333" stroke-width="1.5"/><line x1="340" y1="118" x2="305" y2="162" stroke="#333" stroke-width="1.5"/><line x1="340" y1="118" x2="375" y2="162" stroke="#333" stroke-width="1.5"/><line x1="480" y1="118" x2="445" y2="162" stroke="#333" stroke-width="1.5"/><line x1="480" y1="118" x2="515" y2="162" stroke="#333" stroke-width="1.5"/><circle cx="410" cy="50" r="9" fill="#333"/><circle cx="340" cy="110" r="8" fill="none" stroke="#333" stroke-width="2"/><circle cx="480" cy="110" r="8" fill="none" stroke="#333" stroke-width="2"/><circle cx="305" cy="170" r="7" fill="none" stroke="#333" stroke-width="2"/><circle cx="375" cy="170" r="7" fill="none" stroke="#333" stroke-width="2"/><circle cx="445" cy="170" r="7" fill="none" stroke="#333" stroke-width="2"/><circle cx="515" cy="170" r="7" fill="none" stroke="#333" stroke-width="2"/><text x="410" y="200" font-size="14" fill="#333" text-anchor="middle">⋯</text><text x="410" y="226" font-size="12" fill="#333" text-anchor="middle">二叉树 λ=0.8：d·λ^2 = 1.28 &gt; 1</text><text x="410" y="248" font-size="12" fill="#333" text-anchor="middle">容量为正，可以重构</text><text x="300" y="272" font-size="11" fill="#777" text-anchor="middle">（左例 λ=1/2：第 k 层边阻 4^k）</text></svg>

</div>

**为什么值得关心**

不需要任何正则性或增长率假设的精确判据，连"指数临界边界"上的怪树也能判定，把 Ising 情形的 Pemantle–Peres 容量定理推广到了四态 Potts。

> 暂无形式化证明（AI 结果待核验）。

# 过渡段 | A Capacity Criterion for Four-State Potts Reconstruction on Trees

## 由浅入深：从类比走向定理

**第一级台阶**

导读说这还是传话游戏，但家谱不再整齐：有的支系代代单传，有的枝繁叶茂、增长时快时慢。此时"平均传话保真度够不够"这类笼统指标失灵，论文给出的体检办法是把家谱当作一张电线网络：每层水管的粗细由传话保真度决定，从根往无穷远处能送出的最大"信息流"叫容量——容量为正，后代就仍能拼出祖宗的颜色；容量为零，信息彻底洗掉。

**第二级台阶**

精确化：树 `@@M@@T@@` 是每个顶点至多 `@@M@@B@@` 个孩子的无穷确定性生根树（允许零个或一个孩子），对观察者已知；通道为四态 Potts 型 `@@M@@P_\lambda(j\mid i)=\lambda\mathbf 1_{\{i=j\}}+(1-\lambda)/4@@`，`@@M@@0<\lambda<1@@`。重构优势 `@@M@@a_n=\E\,\mathrm{TV}(\Pr(\sigma_\rho\in\cdot\mid\sigma_{L_n}),\mathsf u)@@` 非增，其极限为正即重构。流到无穷是每个非根顶点流入等于流出的非负流 `@@M@@\theta@@`；射线 `@@M@@\xi@@` 上的势为 `@@M@@V_\lambda(\theta,\xi)=\sum_{e\in\xi}(\lambda^{-2|e|}\theta(e))^2@@`；`@@M@@L^3@@` 容量 `@@M@@\operatorname{Cap}_{3,\lambda}(T)@@` 即在"每条射线势不超过 1"约束下的最大流质量。

**第三级台阶**

定理断言：对 `@@M@@0<\lambda<1@@`，`@@M@@a_\infty(T,\lambda)>0@@` 当且仅当 `@@M@@\operatorname{Cap}_{3,\lambda}(T)>0@@`。判据不设任何正则性或增长率假设，连指数 Kesten–Stigum 边界上增长率检验失效的怪树也能一次判明。排除 `@@M@@\lambda=1@@` 是本质的：此时单条无穷射线即可完美重构，其容量却为零。与 Pemantle–Peres 的两个 Ising 判据相对照，此处指数取 `@@M@@L^3@@` 而边阻取平方的 `@@M@@\lambda^{-2|e|}@@`；证明的核心输入正是姊妹篇的封闭后验律类与矩节省不等式，四态处二次修正消失、三阶项起决定作用的结构在此被完全利用。

## 一句话结论
对 `@@M@@0<\lambda<1@@` 的铁磁四态 Potts 广播模型，证明在有界度确定性生根树上重构当且仅当树的带边阻 `@@M@@\lambda^{-2|e|}@@` 的 `@@M@@L^3@@` 容量为正：一个不依赖正则性或增长率假设的精确判据，连指数临界边界也能判定。

## 问题背景
正则树与泊松树上的重构阈值可由增长率 `@@M@@d\lambda^2@@` 刻画，但在任意形状的树（允许顶点只有零个或一个孩子、增长率恰在指数边界）上，单靠增长率无法判定。Evans–Kenyon–Peres–Schulman（2000）建立了广播与 Ising 模型、电容之间的联系；Pemantle–Peres（2010）用非线性容量刻画 Ising 临界判据：自由边界对应平方阻的 `@@M@@L^2@@` 容量、加号边界对应不平方阻的 `@@M@@L^3@@` 容量。四态 Potts 恰是谱阈值是否精确的边界情形（Sly 2011 证明 `@@M@@q\ge5@@` 失效；Mossel–Sly–Sohn 2025 覆盖大平均度的三、四态），且四态处二次修正项消失、高阶项起决定作用。本文给出四态模型在任意有界度树上的完整容量判据。

## 主要结果
设 `@@M@@T@@` 为每个顶点至多 `@@M@@B@@` 个孩子的无穷确定性生根树（对观察者已知），`@@M@@0<\lambda<1@@`，通道同四态 Potts。定义流到无穷（flow to infinity）：非负流 `@@M@@\theta@@` 在每个非根顶点处流入等于流出，其质量为根处流出总量；在约束"每条无穷射线 `@@M@@\xi@@` 上 `@@M@@\sum_{e\in\xi}(\lambda^{-2|e|}\theta(e))^2\le1@@`"下的最大流质量称为带边阻 `@@M@@\lambda^{-2|e|}@@` 的 `@@M@@L^3@@` 容量 `@@M@@\operatorname{Cap}_{3,\lambda}(T)@@`。主定理：重构优势极限 `@@M@@a_\infty(T,\lambda)>0@@` 当且仅当 `@@M@@\operatorname{Cap}_{3,\lambda}(T)>0@@`。与 Pemantle–Peres 的两个 Ising 判据相比，这里指数取 `@@M@@L^3@@` 而阻取平方的 `@@M@@\lambda^{-2|e|}@@`。排除 `@@M@@\lambda=1@@` 是本质的：单条无穷射线即可完美重构，但其容量为零。

## 证明思路
用二次信息 `@@M@@m=4\E|p-\unif|^2@@` 度量后验。关键输入是姊妹篇的封闭后验律类 `@@M@@\mathcal C@@` 及矩节省不等式：合并两个 `@@M@@\mathcal C@@` 中的实验时 `@@M@@m(\mu\star\nu)\le m(\mu)+m(\nu)-c(\E A^2m+m\E A^2)@@`，`@@M@@c=1/1000@@`。先证"重构 `@@M@@\Rightarrow@@` 容量为正"：对每个顶点 `@@M@@v@@` 取其后代信息的极限 `@@M@@m_v@@`，作变量替换 `@@M@@y_v=m_v+Km_v^3@@`，把分支处节省转化为即使在独生顶点处也有严格正节省（因子 `@@M@@r-r^3@@`，`@@M@@r=\lambda^2@@`）的非线性递推，再放大为 `@@M@@y_v\le r\sum_w y_w/\sqrt{1+2\delta y_w^2}@@`，这正是 Pemantle–Peres 容量递推的形式；据此逐边分配系数伸缩地构造流，沿射线求和与单调收敛给出势不超过 1、质量为正的容许流。反过来证"容量 `@@M@@\Rightarrow@@` 重构"：把容许流缩小 `@@M@@\epsilon@@` 倍，在每个深度 `@@M@@n@@` 的叶观测前额外加独立噪声，顶点 `@@M@@v@@` 处噪声参数取 `@@M@@t_v=\sqrt{X_v/3}@@`，其中 `@@M@@X_v=r^{-|v|}\Theta(v)@@` 是深度加权流；次可加性使传播信息保持在该流轮廓之下。为控制合并造成的信息损失，除 `@@M@@m@@` 外还跟踪带符号三阶矩 `@@M@@\tau=\E[x_1x_2x_3]@@`：在四态坐标下乘积公式中的混合二次项恰好抵消，剩余损失由三阶矩控制，而三阶矩沿边传播的因子是 `@@M@@\lambda^3@@` 而非 `@@M@@\lambda^2@@`。再按流采样一条射线，把累积损失化为单条路径上的和；两个传播因子的差留下可和核 `@@M@@\lambda^{j-i}@@`，容量约束控制路径平方和 `@@M@@\sum_jX_{v_j}^2\le Q\epsilon^2@@`。选取与深度无关的小 `@@M@@\epsilon@@` 使总损失至多 `@@M@@M/2@@`，从而每个深度都有 `@@M@@\widehat m_\rho\ge M/2@@`、`@@M@@a_n\ge M/16@@`，重构成立。整个论证不需要各分支规模可比，也不需要严格的指数增长不等式。

## 可信度与备注
本文与同族姊妹篇《The Reconstruction Threshold for the Ferromagnetic Four-State Potts Model》直接衔接：其封闭类与矩节省命题（命题 3.2）是本文的显式引用输入，本文其余论证全部在文内完成；同族三态论文则处理对称三态通道。主结果暂无形式化证明；本文自身的推导是解析的，但其核心输入在姊妹篇中由精确算术的多项式证书验证，请以社区核验为准。OpenAI 官方声明：未经形式化的结果可能有问题。

---

# 深入探讨 | A Capacity Criterion for Four-State Potts Reconstruction on Trees

## 深入探讨：像审稿人一样追问 🔍

**问 1：增长率判据 `@@M@@d\lambda^2>1@@` 在怪树上到底怎么失灵的，容量好在哪里？**

（答：不规则树上不存在单一的 `@@M@@d@@`：增长率沿路径忽快忽慢、或恰停在指数边界（`@@M@@d\lambda^2=1@@`）时，指数检验给不出答案。容量把整棵树的几何折叠进一个量——第 3 节的流构造只需标签满足 `@@M@@z_v\le\sum_w rz_w/\sqrt{1+z_w^2}@@`，无需各分支规模可比或严格指数增长不等式，故对任意有界度树一次判定。）

**问 2：证明里最脆弱的一步是什么？**

（答：充分方向（容量 `@@M@@\Rightarrow@@` 重构）的"流校准噪声"方案：把容许流缩 `@@M@@\epsilon@@` 倍，在每个深度 `@@M@@n@@` 的叶观测前加独立噪声，参数 `@@M@@t_v=\sqrt{X_v/3}@@`（`@@M@@X_v=r^{-|v|}\Theta(v)@@` 为深度加权流）。为控制合并损失，除二次信息 `@@M@@m@@` 外还须跟踪带符号三阶矩 `@@M@@\tau=\E[x_1x_2x_3]@@`——四态坐标下乘积公式中的混合二次项恰好抵消，剩余损失由三阶矩控制，而它沿边传播的因子是 `@@M@@\lambda^3@@` 而非 `@@M@@\lambda^2@@`。两个传播因子之差留下可和核 `@@M@@\lambda^{j-i}@@`，配合路径平方和 `@@M@@\sum_jX_{v_j}^2\le Q\epsilon^2@@` 才把总损失压到 `@@M@@M/2@@` 以下。这组嵌套常数（`@@M@@C,C_1,C_2,Q,\epsilon@@`）中任何一处放缩脱手，与深度无关的 `@@M@@\epsilon@@` 选取即不可能。）

**问 3：变量替换 `@@M@@y=m+Km^3@@` 为什么是必要方向的关键一招？**

（答：姊妹篇的矩节省只在"两个有信息量的分支合并"时出现，单传顶点处退化为 `@@M@@m_v\le rm_{child}@@`，无任何节省可用。替换 `@@M@@y_v=m_v+Km_v^3@@` 后（取 `@@M@@KB^3\le c@@`），\eqref 式 (10) 的修正项 `@@M@@-Kr(1-r^2)\sum m_w^3@@` 在单传处也留下严格正节省（因子 `@@M@@r-r^3@@`），恰化成 Pemantle–Peres 容量递推 `@@M@@y_v\le r\sum_w y_w/\sqrt{1+2\delta y_w^2}@@` 的形式，流构造随后接手。）

**问 4：`@@M@@\lambda=1@@` 的排除和有界度假设，哪个更本质？**

（答：`@@M@@\lambda=1@@` 的排除是逻辑必需：单条无穷射线即可完美重构，其容量却为零，等价性直接破产。有界度 `@@M@@B@@` 则是技术性的：`@@M@@B@@` 出现在三次和估计 `@@M@@S^3\le\sum b_w^3+B^3D@@` 与常数 `@@M@@C_1=C_1(B,\lambda)@@` 中，用于把有限个孩子的混合单项式全部收纳；无界度情形论文未讨论。）

**问 5：与 Pemantle–Peres 的 Ising 判据相比，新意在哪里？**

（答：PP 的两个 Ising 临界判据分别是平方阻的 `@@M@@L^2@@` 容量（自由边界）与不平方阻的 `@@M@@L^3@@` 容量（加号边界）；本文四态判据是"平方阻 `@@M@@\lambda^{-2|e|}@@` + `@@M@@L^3@@` 指数"的第三种组合，源于四态处二次修正消失、三阶项决定性行为。非线性递推本身是 PP 递推的 `@@M@@p=3@@` 特例，但流构造与概率输入均为本文自有。）

**问 6：AI 生成证明最可能出错的模式是什么？**

（答：本文解析部分层层嵌套的常数递推（引理 4.3 的 `@@M@@C=7@@`、式 (26)–(27) 的 `@@M@@C_1@@`、展开损失 `@@M@@C_2@@`、路径能量 `@@M@@Q@@`）最易出现"差一个常数"的连锁错误；且其承重输入——姊妹篇命题 3.2 的封闭类与矩节省——靠精确算术程序验证而非 Lean。全文未形式化，任何一处不等式方向或量词错位都可能沉默地毁掉与深度无关的 `@@M@@\epsilon@@` 选取。）

**问 7：谁会用到这个判据？**

（答：任何在不规则树上问四态广播信息存留的人：容量是树的单个可计算指标（由递推式即可数值逼近），系统发育推断与鲁棒重构（文中所引 JM04 一脉）中"哪些观测拓扑保信息"的问题由此获得完整解答；它也把 Ising 的容量理论补齐到四态，是 `@@M@@q\ge5@@` 谱判据失效前最后一块拼图。）

**总评**

这是把四态重构判据从正则/泊松树推广到一切有界度树的收官之作，"平方阻 `@@M@@L^3@@` 容量"这一新组合漂亮且完整；最大风险是它坐在姊妹篇计算机验证输入之上，且自身多层常数递推未经形式化，等价性两翼中充分方向的流校准论证最值得优先复核。

{% endraw %}
