---
layout: default
title: "The sharp factor-of-IID threshold for the free Ising model on regular trees"
family: "236"
discipline: "Probability and statistical mechanics"
formalized: true
source: null
pdfname: ""
---

{% raw %}
# 解读 | The sharp factor-of-IID threshold for the free Ising model on regular trees

> 结果族 236：The exact factor-of-IID threshold for free Ising spins on trees　·　学科：Probability and statistical mechanics　·　验证状态：主结果已 Lean 形式化

## 入门导读 🐣

在一棵无穷大的"家谱树"上玩传话游戏：老祖宗掷一枚硬币，每个孩子以某个概率照抄爸爸的答案，否则随机改口。这篇论文问：不指定谁是祖宗、只给每个顶点发一个独立的随机数，再套一条对所有节点一视同仁的规则，能否把整棵树的传话结果原样造出来？答案是一条精确到含等号的分界线。

**关键词卡片**

- Ising 自旋（Ising spin）：顶点上放的 ±1 小磁针；铁磁（ferromagnetic）指相邻磁针倾向同向。
- d-正则树（d-regular tree）：每个节点恰好有 d 个邻居的无穷网络，没有边界也没有天然的"中心"。
- 广播模型（broadcast model）：根掷公平硬币，每个子节点以 `@@M@@(1+\theta)/2@@` 的概率照抄父节点，`@@M@@\theta=\tanh\beta@@` 度量"传话多忠实"。
- factor of IID：给每个顶点一个独立随机标签，用一条与图对称性兼容的统一规则把标签整场变成自旋——不靠任何根。
- 重建阈值（reconstruction threshold）：`@@M@@b\theta^2=1@@`（其中 `@@M@@b=d-1@@`）——越过它，根的信息能传到无穷远处残留不散。

**看个具体例子**

<div>

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 560 280"><circle cx="280" cy="45" r="16" fill="#e8f0fe" stroke="#336" stroke-width="2"/><text x="275" y="51" font-size="15" fill="#336" font-weight="bold">+</text><circle cx="180" cy="115" r="14" fill="#e8f0fe" stroke="#336" stroke-width="2"/><text x="176" y="121" font-size="14" fill="#336">+</text><circle cx="280" cy="115" r="14" fill="#e8f0fe" stroke="#336" stroke-width="2"/><text x="276" y="121" font-size="14" fill="#336">+</text><circle cx="380" cy="115" r="14" fill="#fdeaea" stroke="#933" stroke-width="2"/><text x="376" y="121" font-size="14" fill="#933">−</text><line x1="270" y1="59" x2="188" y2="103" stroke="#888" stroke-width="1.5"/><line x1="280" y1="61" x2="280" y2="101" stroke="#888" stroke-width="1.5"/><line x1="290" y1="59" x2="372" y2="103" stroke="#888" stroke-width="1.5"/><line x1="172" y1="128" x2="140" y2="168" stroke="#bbb" stroke-width="1.2"/><line x1="180" y1="129" x2="180" y2="168" stroke="#bbb" stroke-width="1.2"/><line x1="188" y1="128" x2="220" y2="168" stroke="#bbb" stroke-width="1.2"/><line x1="272" y1="128" x2="252" y2="168" stroke="#bbb" stroke-width="1.2"/><line x1="280" y1="129" x2="280" y2="168" stroke="#bbb" stroke-width="1.2"/><line x1="288" y1="128" x2="308" y2="168" stroke="#bbb" stroke-width="1.2"/><line x1="372" y1="128" x2="344" y2="168" stroke="#bbb" stroke-width="1.2"/><line x1="380" y1="129" x2="380" y2="168" stroke="#bbb" stroke-width="1.2"/><line x1="388" y1="128" x2="416" y2="168" stroke="#bbb" stroke-width="1.2"/><text x="404" y="70" font-size="13" fill="#444">子照抄父的概率 (1+θ)/2</text><text x="80" y="215" font-size="13" fill="#1a7a4a">θ 小：答案几步就忘光</text><text x="300" y="215" font-size="13" fill="#c0392b">θ 大：祖先痕迹残留</text><text x="90" y="250" font-size="14" fill="#333" font-weight="bold">分界线：tanh β ≤ (d−1)^(−1/2)（含等号）</text><text x="110" y="272" font-size="12" fill="#666">d=3 时即 θ ≤ 1/√2 ≈ 0.707，恰好落在分界线上仍可无根生成</text></svg>

</div>

代入 `@@M@@d=3@@`：分界线是 `@@M@@\theta^2\le 1/2@@`。`@@M@@\theta@@` 很小时信息传两三代就遗忘干净，可以无根生成；越过阈值时根部信息长存，已被证明不可能；最难的临界点 `@@M@@\theta=1/\sqrt2@@` 本文证明仍然可行——这正是 Nam–Sly–Zhang 猜想的最后一块拼图。

**为什么值得关心**

它把"局部独立随机性能否重现全局平衡态"在树上彻底画上句号，连最刁钻的等号情形也一并解决，且构造的规则与树的全部对称性严格兼容。

> 已 Lean 形式化

## 一句话结论

本文完全确定了无穷 `@@M@@d@@`-正则树上自由零场铁磁 Ising 态作为"独立同分布标签的因子"（factor of IID）的精确门槛：当且仅当 `@@M@@\tanh\beta\le(d-1)^{-1/2}@@`，含临界等号情形。这证明了 Nam–Sly–Zhang 猜想，且构造的因子与每个树自同构在每个输入上交换。

## 问题背景

在无穷图的每个顶点放一个独立均匀标签 `@@M@@(U_v)@@`，用一个与图自同构可交换的可测映射 `@@M@@\Phi@@` 把整场标签变成自旋场，所得法律称为 factor of IID。Lyons 问：树上的自由 Gibbs 态能否这样"无根地"生成？无穷 `@@M@@d@@`-正则树上自由零场 Ising 态 `@@M@@\mu_{d,\beta}@@`（记 `@@M@@\theta=\tanh\beta@@`，`@@M@@b=d-1@@`）的广播描述是：任取一点掷公平自旋，沿边让子顶点以 `@@M@@(1+\theta)/2@@` 概率随父——法律与根无关、在全部自同构下不变，但规则里藏着一个根。阈值 `@@M@@b\theta^2=1@@` 恰是重建阈值（reconstruction threshold）：超过它时自由态不极端，Sly 借 Backhausz–Szegedy–Virág 的相关界证明不可能有因子表示；远低于它（`@@M@@\theta\le b^{-1}@@`，唯一性区域）Lyons 给出有限簇构造。中间区域连同临界点 `@@M@@\theta=b^{-1/2}@@` 一直悬置：Nam、Sly、Zhang 用后验漂移随机微分方程证明了大 `@@M@@d@@`、小 `@@M@@\theta@@` 时可行，并猜想完整阈值含等号。难点在于：因子法律的弱极限不必是因子，非重建也不提供生成规则，等号情形必须直接构造。

## 主要结果

主定理：对每个整数 `@@M@@d\ge3@@` 与 `@@M@@\beta\ge0@@`，自由零场 Ising 法律 `@@M@@\mu_{d,\beta}@@` 是 factor of IID——存在可测映射 `@@M@@\Phi:[0,1]^{\mathcal V}\to\{-1,1\}^{\mathcal V}@@`，使对每个固定自同构 `@@M@@g@@` 几乎必然有 `@@M@@\Phi(gU)=g\Phi(U)@@`——当且仅当 `@@M@@\tanh\beta\le(d-1)^{-1/2}@@`。论文证明正向（含等号），严格反向为已知结果。此外 `@@M@@\Phi@@` 可选成在每个标签输入上与每个自同构逐点交换；论文明确不主张有限半径编码（finitary coding）与编码半径估计。`@@M@@\theta=0@@` 时法律本就是独立公平符号，平凡成立。

## 证明思路

先搭观察框架（沿用 Nam–Sly–Zhang）：在辅助概率空间采出目标自旋构型 `@@M@@\sigma@@` 与独立布朗运动，观察 `@@M@@X_v(t)=t\sigma_v+B_v(t)@@`（属随机定位 stochastic localization 一脉），记后验均值 `@@M@@m_v(t)@@`，减去条件漂移得新息 `@@M@@W_v=X_v-\int_0^t m_v\,ds@@`。经典滤波理论保证各 `@@M@@W_v@@` 是独立布朗运动，但 Brown 性本身不保证 `@@M@@X@@` 是 `@@M@@W@@` 的函数，"新息决定观察"是全文枢纽。

再建立无穷新息方程：引入腔场 `@@M@@h_{j\to i}@@` 与路径响应系数 `@@M@@c_{vu}=\theta^r\prod_i a(h_{v_i\to v_{i-1}})@@`，其中 `@@M@@a(z)=\frac{1-\tanh^2z}{1-\theta^2\tanh^2z}@@`，场满足 `@@M@@dh_v=\sum_u c_{vu}\,dW_u+m_vA_v\,dt@@`，`@@M@@A_v=\sum_u c_{vu}^2@@`。无穷和的合法性靠"能量不逃逸到边界"：远离零时刻用逐顶点高斯衰减，零时刻附近用整体信息估计 `@@M@@\E m_v(t)^2\le C\sqrt t@@`（临界时 `@@M@@\E A_v(t)\le C/\sqrt t@@`），再以精确能量恒等式与检验论证排除残余鞅。

然后做条件副本比较：给定全部新息独立采两个观察副本，证明观察的过去只依赖新息的过去，故 `@@M@@W@@` 在联合过滤中仍是布朗、两副本由同一列布朗驱动。记 `@@M@@V(t)=\E[(h_o-h'_o)^2]@@`，`@@M@@V(0)=0@@`。次临界时壳层大小 `@@M@@db^{r-1}@@` 与 `@@M@@\theta^{2r}@@` 之积构成收敛几何级数，得 `@@M@@V'\le CV@@`，由 Gronwall 不等式得 `@@M@@V=0@@`。临界点处两因子恰好相消，需三项替补估计：完整侧枝在尺度 `@@M@@t^{-1/2}@@` 上衰减路径乘积；谱方法空间抵消把 `@@M@@\log a@@` 因子差之和的方差压到 `@@M@@rS(t)@@`；路径平均的集中。剩余的小时困难是主导噪声项 `@@M@@S(t)/t@@` 不可积：利用 `@@M@@p\ge3@@` 时 `@@M@@b\theta^p<1@@` 的严格压缩，把二阶矩尺度递归传播成所有整数矩 `@@M@@\E|h_{v\to w}|^p\le e^{Kp^2}t^{p/4}@@` 与小场尾估计，加上 `@@M@@(\log a)'@@` 在原点为零，改进 `@@M@@S@@` 与 `@@M@@V@@` 的比较，最终得 Osgood 型不等式 `@@M@@V'\le k_T(t)V(1+\log(K_T/V))@@`，系数 `@@M@@k_T@@` 可积，迫使 `@@M@@V\equiv0@@`。

最后恢复：副本相等说明给定新息的条件法律是点质量，存在 Borel 映射 `@@M@@F@@` 使 `@@M@@X=F(W)@@`；整时斜率 `@@M@@X_v(n)/n\to\sigma_v@@` 几乎必然，自旋从新息读出；把均匀标签经 Borel 采样变为布朗路径得到因子，再用有限球条件期望平均升级为逐点等变版本。

## 可信度与备注

任务元信息标注该主结果已有 Lean 形式化证明（族内文档 lean/docs/236.md）；反向障碍出自 Sly 并使用 BSV 相关界，为已知结果。文内引用的同系列自由均匀生成树森林（FUSF）姊妹篇用一致 Lipschitz 响应界因果反演新息，本篇改走条件副本相等性路线，方法互补。按 OpenAI 官方声明，未经形式化的结果可能存在问题；本篇主结果已形式化，其余技术细节仍以论文与社区核验为准。

{% endraw %}
