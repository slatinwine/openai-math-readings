---
layout: default
title: "A torsion-free hyperbolic group that is not residually finite"
family: "252"
discipline: "Group theory"
formalized: true
source: null
pdfname: ""
---

{% raw %}
# 解读 | A torsion-free hyperbolic group that is not residually finite

> 结果族 252：A torsion-free hyperbolic group that is neither residually finite nor linear over any field　·　学科：Group theory　·　验证状态：主结果已 Lean 形式化

## 入门导读 🐣

一个"剩余有限"的群，好比每位成员都持有能在某台小型刷卡机（有限群商）上刷出独特记录的工牌。Gromov 1987 年起大家追问：负曲率世界（词双曲群）里的成员是否人人有牌？这篇论文造出反例：一个无挠的双曲群里有固定一位成员，他在任何一台刷卡机上都刷出"1"，但他在完整的群里确凿非平凡——他隐身于一切有限商。

**关键词卡片**

- 剩余有限（residually finite）：每个非单位元都能被某个到有限群的同态"验明正身"
- 词双曲群（word-hyperbolic group）：词度量下呈粗负曲率、像树一样迅速散开的群
- 有限剩余（finite residual）：被所有有限商同时杀掉的那批元素组成的子群
- 矩形词（rectangular words）：构造中预先圈定的一小组特定词，其中一个注定隐身
- 线性群（linear group）：能实现为矩阵群的群；由 Malcev 定理，有限生成线性群必剩余有限

**看个具体例子**

反例群 `@@M@@G@@` 是一个只有三个顶点 `@@M@@O@@`、`@@M@@V@@`、`@@M@@W@@` 的有限欧氏三角形复形的基本群。数字版定理：存在固定的矩形词 `@@M@@w@@`，它满足 `@@M@@w\ne 1@@`，但对每一个有限群 `@@M@@Q@@` 与每一个同态 `@@M@@\varphi:G\to Q@@` 都有 `@@M@@\varphi(w)=1@@`。再进一步：若 `@@M@@G@@` 能写成某个域上的矩阵群，由 Malcev 定理其像剩余有限，会逼出 `@@M@@w=1@@`，矛盾——所以 `@@M@@G@@` 不线性于任何交换域。

<div>

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 560 280">
  <text x="20" y="28" font-size="15" fill="#333333">三顶点复形里的 w 不是单位元，却在所有有限商里隐身</text>
  <circle cx="120" cy="140" r="7" fill="#1565c0"/>
  <circle cx="230" cy="80" r="7" fill="#2e7d32"/>
  <circle cx="230" cy="200" r="7" fill="#c62828"/>
  <text x="92" y="168" font-size="14" fill="#1565c0">顶点 O</text>
  <text x="244" y="80" font-size="14" fill="#2e7d32">顶点 V</text>
  <text x="244" y="208" font-size="14" fill="#c62828">顶点 W</text>
  <path d="M 126 136 L 224 84" stroke="#90a4ae"/>
  <path d="M 126 144 L 224 196" stroke="#90a4ae"/>
  <path d="M 230 87 L 230 193" stroke="#90a4ae"/>
  <path d="M 150 122 L 206 102" stroke="#b0bec5"/>
  <path d="M 150 158 L 206 178" stroke="#b0bec5"/>
  <text x="52" y="244" font-size="13" fill="#555555">G 的完整世界：w 不等于 1</text>
  <line x1="290" y1="140" x2="330" y2="140" stroke="#37474f" stroke-width="2"/>
  <polygon points="330,140 318,134 318,146" fill="#37474f"/>
  <text x="284" y="126" font-size="13" fill="#37474f">一切有限商</text>
  <rect x="340" y="60" width="80" height="34" rx="6" fill="#eceff1" stroke="#546e7a"/>
  <text x="352" y="82" font-size="13" fill="#37474f">有限群 Q₁</text>
  <rect x="340" y="124" width="80" height="34" rx="6" fill="#eceff1" stroke="#546e7a"/>
  <text x="352" y="146" font-size="13" fill="#37474f">有限群 Q₂</text>
  <rect x="340" y="188" width="80" height="34" rx="6" fill="#eceff1" stroke="#546e7a"/>
  <text x="352" y="210" font-size="13" fill="#37474f">有限群 Q₃</text>
  <text x="440" y="82" font-size="13" fill="#c62828">w 映成 1</text>
  <text x="440" y="146" font-size="13" fill="#c62828">w 映成 1</text>
  <text x="440" y="210" font-size="13" fill="#c62828">w 映成 1</text>
</svg>

</div>

**为什么值得关心**

"是否所有双曲群都剩余有限"是几何群论最著名的公开问题之一，本文给出否定回答，还附带"不线性于任何交换域"的更强结论——能容纳这种反例的群，本身也是稀罕对象。

> 已 Lean 形式化

## 一句话结论

构造了一个无挠 (torsion-free)、词双曲 (word-hyperbolic) 却不剩余有限的群，对 Gromov 双曲群的剩余有限性问题给出否定回答；其有限剩余中有一个固定非单位元，被任何交换域上的全部有限维线性表示同时杀死，故该群不线性于任何交换域。

## 问题背景

一个群称为剩余有限 (residually finite)，如果每个非单位元在某个到有限群的同态下仍是非单位元，等价于所有这类同态核的交——有限剩余 (finite residual) `@@M@@R_f(G)@@`——平凡。自 Gromov 1987 年创立词双曲群理论以来，"是否每个双曲群都剩余有限"成为标志性公开问题：仅有粗负曲率，是否足以让有限商分离元素？Kapovich–Wise 证明它等价于"每个非平凡双曲群都有非平凡有限商"与"每个双曲群都有无挠有限指标子群"；Agol–Groves–Manning 证明肯定答案会蕴含所有拟凸 (quasiconvex) 子群可分 (separable)。另一面，Agol 的立方化定理表明容许 CAT(0) 立方结构的双曲群都剩余有限，故反例必不容许此类结构；而 Wise 的完全方形复形与 Burger–Mozes 群虽不剩余有限，万有覆盖却含欧氏平面、并不双曲。难点有二：几何既要证双曲性，又要证供障碍用的元素确实非平凡；代数必须把全部有限数据（含插值素域的特征）在知道任何有限商的阶之前一次固定。

## 主要结果

主定理：存在一个无挠且词双曲、但不剩余有限的群 `@@M@@G=\pi_1(K)@@`，其中 `@@M@@K@@` 是一个有限欧氏三角形复形 (finite Euclidean triangle complex)。论证是存在性的：固定由矩形词 (rectangular words) 组成的有限集 `@@M@@\mathcal R\subset G@@`，证明某个固定成员落在 `@@M@@R_f(G)@@` 内，但不指明是哪一个。结合 Kapovich–Wise 的等价刻画，随即得到：某些非平凡双曲群没有任何非平凡有限商，某些双曲群没有无挠的有限指标子群。推论（有限维线性障碍）：对每个交换域 `@@M@@K@@`、每个 `@@M@@n\ge 1@@` 与每个同态 `@@M@@\rho:G\to\mathrm{GL}_n(K)@@`，都有 `@@M@@R_f(G)\subseteq\ker\rho@@`；即一个固定非单位元被所有交换域、所有维数上的有限维表示同时杀死，故 `@@M@@G@@` 不线性于任何交换域。证明只需一步：`@@M@@\rho(G)@@` 是有限生成线性群，由 Malcev 定理剩余有限，把分离 `@@M@@\rho(g)@@` 的有限商与 `@@M@@\rho@@` 复合便与 `@@M@@R_f@@` 的定义矛盾。论文明确声明该推论不涉及除环与无穷维表示。与 Kapovich、Tholozan–Tsouvalas 的非线性双曲群先例相比，这里有限剩余非平凡是更强的性质：所有表示的核有公共非单位元。

## 证明思路

证明分几何、代数两条线。先证一个三角形复形判据：若有限欧氏三角形复形每个顶点的角链路 (link) 中非空循环约化闭路的角度总长至少 `@@M@@2\pi+\eta@@`，则基本群无挠且词双曲；且每步转角的链路距离不小于 `@@M@@\pi@@` 的闭路必不零伦。构造时固定 `@@M@@h=20@@`、`@@M@@c=100^{-h}@@` 与 `@@M@@r@@`（`@@M@@cr\ge 100@@`），在 `@@M@@P=\F_q^h@@` 中用 Erdős 式概率改造法得到 `@@M@@N@@` 条带标记点的仿射直线，使点—线关联图围长超过 12，例外集 `@@M@@E@@` 外每点至少 `@@M@@4r^2@@` 条入射线；素域特征 `@@M@@q@@` 连同全部数据自此一次固定，不再依赖任何有限商。复形只有三个顶点 `@@M@@O,V,W@@`：每个线标签 `@@M@@i@@` 给出 `@@M@@V\to W@@` 的 `@@M@@r\times r@@` 边阵列 `@@M@@x_{iuv}@@`，各点的块给出 `@@M@@O\to V@@`、`@@M@@O\to W@@` 的边；块坐标经移位 `@@M@@\alpha_b(i)+v@@`、`@@M@@\beta_b(i)+u@@` 编入三角形关系，使 `@@M@@V,W@@` 处的链路浸入关联图，大围长保证链路最短闭路至少 `@@M@@14\pi/5@@`，`@@M@@O@@` 处每对方向恰有一条链路边、给出 `@@M@@12\pi/5@@`，而三角形角度取 `@@M@@3\pi/5,\pi/5,\pi/5@@`，于是判据以 `@@M@@\eta=2\pi/5@@` 生效。同一链路估计还表明：矩形词 `@@M@@g_{iuv}g_{iu'v}^{-1}g_{iu'v'}g_{iuv'}^{-1}@@` 的四个转角链路距离均 `@@M@@\ge\pi@@`，故在 `@@M@@G@@` 中非单位。代数一侧反设某个有限商 `@@M@@Q@@`（`@@M@@D=|Q|@@`）保持全部矩形词非单位。在正则置换表示下令 `@@M@@Y_i=(U(g_{iuv}))_{u,v}@@`，两个迹恒等式加 Cauchy–Schwarz 得 `@@M@@\rank_{\mathbb{R}}Y_i\ge rD/2@@`；再用 Hadamard 行列式不等式与整数子式对 `@@M@@q@@` 的整除性，把一半实秩保进固定素域：`@@M@@\rank_{\F_q}Y_i\ge rD/4@@`，与 `@@M@@D@@` 无关——这正是特征先于商阶固定的均匀性。上界来自局部分解：正则点处每个块的求和分解为块列乘块行，故 `@@M@@\rank Z(z)\le 2D@@`，例外点用环境维数 `@@M@@rD@@` 兜底。最后用乘积 Lagrange 插值造多项式 `@@M@@f_i@@` 在诸标记点上取单位值或零值，令 `@@M@@H(z)=f(z)f(z)^{\mathsf T}@@`（秩 `@@M@@\le 1@@`）；有限域幂和恒等式使"去掉标记点的直线求和"恰好孤立出 `@@M@@-E_{ii}@@`。交换求和顺序得张量恒等式 `@@M@@\bigoplus_i Y_i=\sum_{z\in P}H(z)\otimes Z(z)@@`：左边秩至少 `@@M@@NrD/4@@`，右边至多 `@@M@@2mD+r|E|D@@`，消去 `@@M@@D@@` 便与初始预算 `@@M@@Nr/4>2m+r|E|@@` 矛盾。若每个矩形词各有一个保它非单位的有限商，取诸商之积即得同时保住全体的商——矛盾；故存在固定的 `@@M@@w\in\mathcal R@@` 被一切到有限群的同态杀死，而 `@@M@@w\ne 1@@`。双曲性判据的完整证明——重心重分、简约平面填充、角盈 Gauss–Bonnet、内径界、水平弧论证与拟测地稳定性——技术性较强，此处从略。

## 可信度与备注

按任务标注，本文主结果已有 Lean 形式化证明（结果族文档 lean/docs/252.md），在 OpenAI 官方"未经形式化的结果可能有问题"的提示下，这是重要的可信度背书。结果族 252 的标题概括了同一构造的两面——不剩余有限、不线性于任何交换域——后者正是本文推论经 Malcev 定理从前者直接导出，主定理与推论互为支撑。读者可留意表述边界：推论只覆盖交换域上的有限维表示，对除环与无穷维表示不作断言；被杀死的是哪一个矩形词，论文也未显式识别。

{% endraw %}
