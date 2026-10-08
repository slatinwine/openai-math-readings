---
layout: default
title: "The Quasi-Riemann Hypothesis: A Zero-Free Half-Plane $\\Re s>7/8$"
family: "003"
discipline: "Number theory"
formalized: true
source: null
pdfname: ""
---

{% raw %}
# 解读 | The Quasi-Riemann Hypothesis: A Zero-Free Half-Plane `@@M@@\Re s>7/8@@`

> 结果族 003：The quasi-Riemann hypothesis　·　学科：Number theory（数论）　·　验证状态：主结果已 Lean 形式化

## 入门导读 🐣

素数分布是否安稳，取决于黎曼 ζ 函数的零点藏在哪里——零点像乐曲里的杂音源，越靠近"右侧边界线" `@@M@@s=1@@`，素数的波动越诡异。黎曼猜想断言所有杂音都精确排在中线上，至今没人能证。这篇论文先拿下一个弱得多却压倒性的一步：右侧 7/8 以后，一根杂音都没有。

**关键词卡片**

- 黎曼 ζ 函数（Riemann zeta function）：`@@M@@\zeta(s)=1+1/2^s+1/3^s+\cdots@@`，编码素数分布的核心函数。
- 临界带（critical strip）：竖直条带 `@@M@@0<\Re s<1@@`，ζ 的非平凡零点全部落在其中。
- 无零点半平面（zero-free half-plane）：`@@M@@\Re s>7/8@@` 的区域，本文证明这里没有任何零点。
- Dirichlet L-函数（Dirichlet L-function）：ζ 的"带符号打分"版本，同样的禁区对它们全体成立。
- 最小二次非剩余（least quadratic nonresidue）：模 `@@M@@p@@` 下第一个不是平方数的正整数；本文顺带证明了 Vinogradov 关于它的猜想。

**看个具体例子**

把结论画在 `@@M@@s@@` 平面上：横轴是实部。所有非平凡零点只能住在临界带内，已知零点都排在中线 `@@M@@\Re s=1/2@@` 上（黎曼猜想：全部如此）；本文证明右侧灰色禁区 `@@M@@\Re s>7/8@@` 内没有零点（`@@M@@s=1@@` 处是极点，不计）。

<div>

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 560 280">
  <text x="280" y="26" font-size="17" text-anchor="middle" fill="#222">ζ(s) 的临界带与论文证明的无零点禁区</text>
  <rect x="370" y="56" width="40" height="160" fill="#dddddd" stroke="none"/>
  <rect x="90" y="56" width="320" height="160" fill="none" stroke="#333" stroke-width="2"/>
  <line x1="250" y1="56" x2="250" y2="216" stroke="#888" stroke-width="1.5" stroke-dasharray="6,5"/>
  <circle cx="250" cy="82" r="4" fill="#333"/>
  <circle cx="250" cy="106" r="4" fill="#333"/>
  <circle cx="250" cy="130" r="4" fill="#333"/>
  <circle cx="250" cy="154" r="4" fill="#333"/>
  <circle cx="250" cy="178" r="4" fill="#333"/>
  <circle cx="250" cy="202" r="4" fill="#333"/>
  <text x="240" y="70" font-size="14" text-anchor="end" fill="#222">Re s = 1/2（临界线）</text>
  <text x="100" y="180" font-size="14" fill="#555">已知零点都在虚线上</text>
  <text x="100" y="200" font-size="14" fill="#555">黎曼猜想：全部如此</text>
  <text x="452" y="128" font-size="15" fill="#222">Re s &gt; 7/8</text>
  <text x="452" y="150" font-size="15" fill="#222">无零点禁区</text>
  <text x="90" y="240" font-size="14" text-anchor="middle" fill="#222">0</text>
  <text x="250" y="240" font-size="14" text-anchor="middle" fill="#222">1/2</text>
  <text x="370" y="240" font-size="14" text-anchor="middle" fill="#222">7/8</text>
  <text x="410" y="240" font-size="14" text-anchor="middle" fill="#222">1</text>
  <line x1="90" y1="256" x2="500" y2="256" stroke="#333" stroke-width="1.5"/>
  <polygon points="500,251 510,256 500,261" fill="#333"/>
  <text x="510" y="274" font-size="13" fill="#555">实部</text>
  <text x="290" y="274" font-size="13" text-anchor="middle" fill="#555">s = 1 处是 ζ 的极点，不计为零点</text>
</svg>

</div>

禁区离边界只剩 1/8，看似很小，却是质变：1896 年素数定理以来的经典无零点区域会随导子增大而缩向直线 `@@M@@\Re s=1@@`，而这是第一个固定的半平面。

**为什么值得关心**

"零点离 1 有多远"直接控制素数分布的误差；固定禁区还顺带导出最小二次非剩余的多项式对数上界与求平方根的快速确定性算法。

> 主结果（7/8 无零点半平面）已 Lean 形式化；同族 11/12 备择证明路线暂无形式化证明（AI 结果待核验）

## 一句话结论

本文证明 `@@M@@\mathbb Q(\sqrt{-3})@@` 上全体有限阶 Hecke `@@M@@L@@`-函数及全体 Dirichlet `@@M@@L@@`-函数（含 `@@M@@\zeta(s)@@`）在半平面 `@@M@@\Re s>7/8@@` 内无零点（仅允许主特征在 `@@M@@s=1@@` 的极点），从而肯定地解决拟黎曼猜想，并连带证明 Vinogradov 最小二次非剩余猜想。

## 问题背景

1859 年黎曼把 `@@M@@\zeta(s)@@` 的零点与素数分布联系起来，并猜想非平凡零点全落在临界线 `@@M@@\Re s=1/2@@` 上——黎曼猜想至今未决。一个弱得多的问法是：是否存在固定常数 `@@M@@\sigma_0<1@@`，使 `@@M@@\zeta@@` 在整个半平面 `@@M@@\Re s>\sigma_0@@` 内无零点？这称为拟黎曼猜想（quasi-Riemann hypothesis，见 Billington 等 2025）；对所有 Dirichlet 特征一致的版本在 Friedlander–Goldston（1997）中已有明确表述。1896 年 Hadamard 与 de la Vallée Poussin 排除了 `@@M@@\Re s=1@@` 上的零点从而得到素数定理，但经典无零点区域随导子与高度增大而缩向直线 `@@M@@\Re s=1@@`，甚至允许一个例外实零点（Landau–Siegel 零点）；Guth–Maynard 型零点密度估计只限制零点个数，不能逐一排除。长期卡点是：没有手段能在固定半平面内一致排除全部零点。

## 主要结果

**主定理**：设 `@@M@@F=\mathbb Q(\sqrt{-3})@@`。每个有限阶 Hecke 特征（finite-order Hecke character，即射线类群特征）的 Hecke `@@M@@L@@`-函数 `@@M@@L_F(s,\eta)@@` 在 `@@M@@\Re s>7/8@@` 内无零点；每个 Dirichlet `@@M@@L@@`-函数 `@@M@@L(s,\chi)@@` 亦然——模 `@@M@@1@@` 的特征即 `@@M@@\zeta(s)@@`；主特征在 `@@M@@s=1@@` 的极点除外。等价地，`@@M@@\zeta@@` 非平凡零点实部的上确界不超过 `@@M@@7/8@@`。边界线本身不在结论内，且这远弱于黎曼猜想。

**推论**：存在绝对常数 `@@M@@C,A>0@@`，使每个奇素数 `@@M@@p@@` 的最小正二次非剩余（least quadratic nonresidue）`@@M@@n(p)\le C(\log p)^A@@`（论文取 `@@M@@A=32@@` 即可），这证明了 Vinogradov 最小非剩余猜想；由此还得到求 `@@M@@\mathbb F_p@@` 中平方根的确定性多项式时间算法。

## 证明思路

引擎是一个统一的"延拓判据"（continuation criterion）。令 `@@M@@\beta_*@@` 为 `@@M@@F@@` 上全体本原有限阶 Hecke `@@M@@L@@`-函数在 `@@M@@1/2\le\Re s\le1@@` 内零点实部的上确界，目标是证 `@@M@@\beta_*\le7/8@@`。判据说：若对每个目标特征 `@@M@@\eta@@` 都能构造探针 `@@M@@J_\eta(Z)@@`（光滑化特征和），同时满足低估计 `@@M@@|J_\eta|\ll Z^{C(\sigma_0)+\omega}@@` 与高估计 `@@M@@|J_\eta-f_\eta|\ll Z^{C(\beta_*)-\sigma}@@`，其中 `@@M@@f_\eta@@` 是含 `@@M@@H_\eta(s)/L_F^{\mathcal S}(s,\eta)@@` 的 Mellin 积分（`@@M@@H_\eta@@` 全纯且接近 `@@M@@1@@`），且正余量 `@@M@@\omega,\sigma@@` 与 `@@M@@\eta@@` 无关，则 `@@M@@\beta_*>\sigma_0@@` 必假：两式合并给出 `@@M@@|f_\eta|\ll Z^{C(\beta_*)-\varepsilon_*}@@`，对其取 Mellin 变换便把 `@@M@@1/L_F^{\mathcal S}(s,\eta)@@` 全纯延拓到 `@@M@@\Re s>\beta_*-\varepsilon_*@@`；而按 `@@M@@\beta_*@@` 的定义，某目标的 `@@M@@L@@`-函数在那里有零点，其倒数应有极点，矛盾。

探针在艾森斯坦整数环 `@@M@@\mathcal O@@` 上构造：把 Patterson 三次 theta 级数（cubic theta series）的磨光傅里叶系数对六次剩余特征（sextic residue character）与目标 `@@M@@\eta@@` 平均，完成后的指标形如 `@@M@@cn^3@@`。同一个和有两条独立表示。低估计一侧：经完备三次 theta 反射（源自 Kubota 的 metaplectic 理论）变形系数，二次大筛法（large sieve）控制反射行的均方；加性部分展开为 `@@M@@\mathbb C/\mathcal O@@` 中的既约分数，由平面加性大筛法控制；再以柯西不等式合并。高估计一侧：对平均变量作 Poisson 求和，非零频率形如 `@@M@@ua^6@@`（`@@M@@u@@` 六次幂自由），局部 Euler 恒等式把每行写成 Hecke `@@M@@L@@`-函数之商与受控 Euler 乘积，其中 `@@M@@u=1@@` 的主行恰含 `@@M@@1/L_F(s,\eta)@@`，其留数给出 `@@M@@f_\eta@@` 的非零倍数。零点检测器（zero detector）为有限 Hecke 扭转族分配无零点矩形：在固定下限 `@@M@@51/100@@` 之上选出零点的行会产生两个大 Dirichlet 多项式（一带理想 Möbius 系数的截断倒数，一不带），六次大筛法（发展自 Heath-Brown 等的递归思路）限制此类行的数目。

证明分两阶段推进。第一阶段取对称尺度 `@@M@@l_x=l_y=1/2@@`、`@@M@@C_{\mathrm I}(s)=s-2/3@@`，只用逆多项式行计数，在 `@@M@@\sigma_0=11/12@@` 验证判据（余量 `@@M@@1/4800@@`），先得 `@@M@@\beta_*\le11/12@@`。第二阶段反设 `@@M@@\beta_*>7/8@@` 并做三处改造：其一，素补偿——在探针中插入选定素数槽并作相消组合，抵消高侧多余的标量 Euler 贡献；其二，改用不对称尺度 `@@M@@l_x=17/48@@`、`@@M@@l_y=23/48@@` 与 `@@M@@C_{\mathrm{II}}(s)=s-11/16@@`；其三，补两个独立的矩归纳（带素因子的逆矩与无标记矩），每步用两次有限 Poisson 变换缩短行区间，高度参数则最后选定以吸收全部高度因子。收尾经二次转移：`@@M@@\chi@@` 与理想范数复合给出 `@@M@@F@@` 上 Hecke 特征，且 `@@M@@L_F^{\mathcal S}=L^{S}(s,\chi)\,L^{S}(s,\chi\chi_{-3})@@`（`@@M@@s=1@@` 处由 `@@M@@L(1,\chi_{-3})=\pi/(3\sqrt3)>0@@` 排除零极点相消），Hecke 半平面便转移到全体 Dirichlet `@@M@@L@@`-函数。注意：即便只关心 `@@M@@\zeta@@`，也须对整个 Hecke 族证明定理，因为 Poisson 行会引入目标特征的有限阶 Hecke 扭转。

## 可信度与备注

任务元数据标注本文 formalized=true，主结果已 Lean 形式化（家族文档附 Lean 链接），这是最强的可信度信号。同族姊妹篇互为支撑：另一篇手稿以不同方法独立证得 `@@M@@11/12@@` 零自由半平面（未形式化），与本文第一阶段互相印证；第三篇把实特征例外零点的排除量化为一致界 `@@M@@(1-\beta)\log q\ge c@@`。按 OpenAI 官方声明，未经形式化的结果可能存在问题；矩归纳、检测器高度分配等细节技术性较强，此处从略，请以 Lean 证明与社区核验为准。

{% endraw %}
