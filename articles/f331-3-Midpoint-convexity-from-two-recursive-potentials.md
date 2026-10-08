---
layout: default
title: "Midpoint convexity from two recursive potentials"
family: "331"
discipline: "Functional analysis"
formalized: true
source: null
pdfname: ""
---

{% raw %}
# 解读 | Midpoint convexity from two recursive potentials

> 结果族 331：Reflexive midpoint convexity and diamond distortion　·　学科：Functional analysis　·　验证状态：主结果已 Lean 形式化

## 入门导读 🐣

想象一场"自下而上打分"的比赛：树上每个位置放一个数，两个非负的分数从叶子往根逐层汇报——兄弟的分数先按勾股定理合并，再与本位置的数比大小，一个向量有多长，就看根处读出的总分。这套递归计分造出的空间有个惊人属性：中点意义下凸，却无论怎么换等价尺子都得不到强凸，而且空间还是最规矩的自反空间。

**关键词卡片**

- 递归位势（recursive potentials）：自叶向根逐层计算的一对非负"势"，向量长度在根处读出
- 勾股合并（Euclidean aggregation）：兄弟节点的势按 `@@M@@\sqrt{P_1^2+P_2^2+\cdots}@@` 汇总，像直角三角形求斜边
- 渐近中点一致凸（AMUC）：只在线段中点处检验的凸性；本文给出 `@@M@@t^3/128@@` 的立方下界
- 渐近一致凸（AUC）：强得多的凸性；本文证明换任何等价尺子都得不到
- 自反空间（reflexive space）：泛函分析中最规矩的一类空间；本文把两种凸性的分离做进了这里

**看个具体例子**

计分规则：叶子上放数 `@@M@@v@@`，则两个势为 `@@M@@(v^+,v^-)@@`；往上一层，先把子节点的势各自勾股合并成 `@@M@@A,B@@`，再取 `@@M@@P=\max\{A,\,v+B\}@@`、`@@M@@Q=\max\{B,\,-v+A\}@@`。比如两个叶子放 `@@M@@3@@` 和 `@@M@@4@@`：合并 `@@M@@A=\sqrt{3^2+4^2}=5@@`，根处（`@@M@@v=0@@`）读出长度 `@@M@@N=P+Q=5+5=10@@`。

<div>

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 560 280">
<text x="20" y="30" font-size="16" fill="#333">自叶向根打分：长度在根处读出</text>
<line x1="280" y1="90" x2="160" y2="200" stroke="#c33" stroke-width="3"/>
<line x1="280" y1="90" x2="400" y2="200" stroke="#c33" stroke-width="3"/>
<circle cx="280" cy="90" r="8" fill="#333"/>
<circle cx="160" cy="200" r="8" fill="#c33"/>
<circle cx="400" cy="200" r="8" fill="#c33"/>
<text x="248" y="70" font-size="15" fill="#333">根：(P,Q)=(5,5)</text>
<text x="60" y="235" font-size="15" fill="#c33">叶子 v=3：(3,0)</text>
<text x="330" y="235" font-size="15" fill="#c33">叶子 v=4：(4,0)</text>
<text x="150" y="138" font-size="14" fill="#c33">勾股合并</text>
<text x="360" y="122" font-size="14" fill="#c33">勾股合并</text>
<text x="30" y="165" font-size="13" fill="#555">A=√(3²+4²)=5</text>
<text x="60" y="270" font-size="15" fill="#333">根处读出长度 N = P + Q = 5 + 5 = 10</text>
</svg>

</div>

把主定理代入数字：当 `@@M@@N(x)=N(z)=1@@` 时，齐次三次不等式给出 `@@M@@\frac{N(x+z)+N(x-z)}{2}\ge 1+\frac{1}{8\cdot3^2}=1+\frac1{72}@@`——两端点的平均至少比中心长这些。

**为什么值得关心**

它把"中点凸却不可再赋范成强凸"的反例做进自反空间，范数显式且带多项式定量下界，正面回应了 2016 年提出的公开重赋范问题。

> 已 Lean 形式化

## 一句话结论

本文用两个递归定义的非负"势"之差在树上构造出显式 Banach 范数：联根空间自反、平均渐近中点模有立方下界 `@@M@@t^3/128@@`，却不容许任何等价的渐近一致凸范数，把 Baudier 的非自反分离反例推进到自反空间。

## 问题背景

能否重赋范（renorming）以获得更好的凸性，是 Banach 空间几何的经典问题。渐近一致凸（asymptotically uniformly convex, AUC）要求沿有限余维（finite-codimensional）子空间方向的单侧扰动使范数严格上升；渐近中点一致凸（asymptotically midpoint uniformly convex, AMUC）只要求 `@@M@@x+ty@@` 与 `@@M@@x-ty@@` 两端范数的平均值上升，条件更弱，由 Dilworth 等五人于 2016 年引入。他们在 `@@M@@\ell_2@@` 上分离了两者，并提出重赋范问题：容许 AMUC 范数的空间是否也容许 AUC 范数？Baudier 借助 Kadets–Werner 对 Bourgain–Rosenthal 构造的改造给出否定答案，但该例非自反（nonreflexive）。本文的联根构造补上自反情形，且范数显式、带多项式下界。

## 主要结果

在允许可数分支的有根树上，对有限支集向量 `@@M@@v@@` 自叶向上计算两个非负场：记 `@@M@@A_s=(\sum_c P_c^2)^{1/2}@@`、`@@M@@B_s=(\sum_c Q_c^2)^{1/2}@@`（`@@M@@c@@` 取遍子节点），令 `@@M@@P_s=\max\{A_s,\ v_s+B_s\}@@`、`@@M@@Q_s=\max\{B_s,\ -v_s+A_s\}@@`。归纳可知 `@@M@@(P,Q)@@` 是满足 `@@M@@P_s-Q_s=v_s@@` 且控制子节点欧氏范数的最小非负对，且每个节点至少一个子不等式取等。范数在根部读出：无限树上取 `@@M@@N_\Sigma=P_o+Q_o@@` 得 `@@M@@X_\Sigma@@`；所有有限高度树在公共根 `@@M@@\rho@@` 并联后得联根空间 `@@M@@X_0@@`（固定 `@@M@@v_\rho=0@@`，此时 `@@M@@P_\rho=Q_\rho@@`，取 `@@M@@N_0=P_\rho@@`）与 `@@M@@X_J@@`（根坐标自由，取 `@@M@@N_J=P_\rho+Q_\rho@@`）。

主定理（Theorem 2.1）断言：`@@M@@X_\Sigma@@` 与 `@@M@@X_J@@` 的平均渐近中点模（averaged asymptotic midpoint modulus）`@@M@@\widehat\delta_N(t)\ge t^3/128@@`（`@@M@@0<t<1@@`，由此即得 AMUC）；`@@M@@X_0@@` 满足齐次三次不等式 `@@M@@\frac{N_0(x+z)+N_0(x-z)}{2}\ge N_0(x)+\frac{N_0(z)^3}{8(2N_0(x)+N_0(z))^2}@@`，其中 `@@M@@z@@` 属于含 `@@M@@x@@` 支集的有限初始集的核；`@@M@@X_0@@` 与 `@@M@@X_J@@` 都自反；三者都不容许等价的 AUC 范数。末节把高度 `@@M@@h@@` 分量内的聚合换成 `@@M@@\ell_{1+1/h}@@`，所得空间 `@@M@@X_{\mathrm v}@@` 仍自反、仍无 AUC 重赋范，并给出六次方与三次估计，进而 `@@M@@\widehat\delta(t)\ge\frac{c_3}{24\sqrt2}t^3@@`（`@@M@@c_3=(6\mathrm e)^{-3}@@`）。`@@M@@X_J@@` 上还有分离中点族缝隙：若 `@@M@@N_J(x\pm z_j)\le1@@` 且 `@@M@@N_J(z_i-z_j)\ge\varepsilon@@`（`@@M@@i\ne j@@`），则 `@@M@@N_J(x)\le1-\eta(\varepsilon)@@`。

## 证明思路

定量核心是双场能量论证。先取中心 `@@M@@x@@`（有限支集）与尾向量 `@@M@@z@@`（在含支集的有限初始集 `@@M@@H@@` 上为零）。由凸性与坐标差恒等式，`@@M@@x\pm z@@` 的场取平均，恰好把 `@@M@@x@@` 的两个场同时抬高同一缺陷 `@@M@@d_s\ge0@@`。再定义能量 `@@M@@E_s=[d_s(2P_s+d_s)(2Q_s+d_s)]^{2/3}@@`，在取等节点上配合 Hölder 不等式可证 `@@M@@E_s\ge\sum_c E_c@@`。这使能量逐层向上求和无任何常数损失，估计因此对树高与分支度一致。迭代到 `@@M@@H@@` 的首出边界（first-exit boundary）：那里 `@@M@@x@@` 的场全为零，`@@M@@d_b=\frac12(P_b(z)+Q_b(z))@@`，边界平方和被根部量 `@@M@@[d_o(2P_o+d_o)(2Q_o+d_o)]^{2/3}@@` 控制，换算成尾范数得 `@@M@@N(z)^3\le64d(1+d)^2@@`，而平均端点增益为 `@@M@@2d@@`，故 `@@M@@N(z)\ge t@@`（`@@M@@0<t<1@@`）时增益 `@@M@@2d\ge t^3/128@@`；对一般中心用有限逼近过渡。自反性另走一条路：高度 `@@M@@n@@` 的分量空间与 `@@M@@\ell_2@@` 等价（`@@M@@\frac{\|v\|_2}{2\sqrt{n+1}}\le M_n(v)\le\sqrt{n+1}\|v\|_2@@`），联根空间是各分量的 `@@M@@\ell_2@@` 直和（`@@M@@X_J@@` 再添一维），故自反。

排除 AUC 重赋范用有界路径论证。路径指示向量的范数一致有界且下有界（场沿途为 `@@M@@P=1,Q=0@@`），相邻增量是兄弟坐标向量，经一个从 `@@M@@\ell_2@@` 出发的有界线性映射成为弱零（weakly null）序列。若等价范数 `@@M@@\alpha\|\cdot\|\le N\le\beta\|\cdot\|@@` 是 AUC 的，凸性迫使沿路径每走一步范数至少放大 `@@M@@1+\gamma/2@@` 倍，而路径可任意长、范数又被上下界夹住，矛盾——自反性对此无能为力。论文另给两种机制：停时（stopping time）规则配合 Burkholder 的可料鞅变换（martingale transform）证明序列式一致分离；对联根空间则用有界上鞅（supermartingale）的对数变换控制乘积比，导出分离中点族缝隙。变指数一节取 `@@M@@p_h=1+1/h@@`，使 `@@M@@p^h\le\mathrm e@@` 一致有界：归一化迭代给出六次方估计，累积出逃能量给出三次估计；其余技术性较强，此处从略。

## 可信度与备注

本文主结果已有 Lean 形式化证明，属最高验证层级。结果族 331 的姊妹篇在同一空间中证明：深度 `@@M@@k@@` 的可数分支菱形（diamond）失真至少 `@@M@@\sqrt{1+k/12}@@`，即中点一致凸加上自反性也不强制菱形失真一致有界。按 OpenAI 官方声明，未经形式化的结果可能有问题，文中各显式常数宜以形式化文档与社区核验为准。

{% endraw %}
