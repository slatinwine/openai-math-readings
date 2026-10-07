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
# 解读 | The Quasi-Riemann Hypothesis: A Zero-Free Half-Plane \(\Re s>7/8\)

> 结果族 003：The quasi-Riemann hypothesis　·　学科：Number theory（数论）　·　验证状态：主结果已 Lean 形式化

## 一句话结论

本文证明 \(\mathbb Q(\sqrt{-3})\) 上全体有限阶 Hecke \(L\)-函数及全体 Dirichlet \(L\)-函数（含 \(\zeta(s)\)）在半平面 \(\Re s>7/8\) 内无零点（仅允许主特征在 \(s=1\) 的极点），从而肯定地解决拟黎曼猜想，并连带证明 Vinogradov 最小二次非剩余猜想。

## 问题背景

1859 年黎曼把 \(\zeta(s)\) 的零点与素数分布联系起来，并猜想非平凡零点全落在临界线 \(\Re s=1/2\) 上——黎曼猜想至今未决。一个弱得多的问法是：是否存在固定常数 \(\sigma_0<1\)，使 \(\zeta\) 在整个半平面 \(\Re s>\sigma_0\) 内无零点？这称为拟黎曼猜想（quasi-Riemann hypothesis，见 Billington 等 2025）；对所有 Dirichlet 特征一致的版本在 Friedlander–Goldston（1997）中已有明确表述。1896 年 Hadamard 与 de la Vallée Poussin 排除了 \(\Re s=1\) 上的零点从而得到素数定理，但经典无零点区域随导子与高度增大而缩向直线 \(\Re s=1\)，甚至允许一个例外实零点（Landau–Siegel 零点）；Guth–Maynard 型零点密度估计只限制零点个数，不能逐一排除。长期卡点是：没有手段能在固定半平面内一致排除全部零点。

## 主要结果

**主定理**：设 \(F=\mathbb Q(\sqrt{-3})\)。每个有限阶 Hecke 特征（finite-order Hecke character，即射线类群特征）的 Hecke \(L\)-函数 \(L_F(s,\eta)\) 在 \(\Re s>7/8\) 内无零点；每个 Dirichlet \(L\)-函数 \(L(s,\chi)\) 亦然——模 \(1\) 的特征即 \(\zeta(s)\)；主特征在 \(s=1\) 的极点除外。等价地，\(\zeta\) 非平凡零点实部的上确界不超过 \(7/8\)。边界线本身不在结论内，且这远弱于黎曼猜想。

**推论**：存在绝对常数 \(C,A>0\)，使每个奇素数 \(p\) 的最小正二次非剩余（least quadratic nonresidue）\(n(p)\le C(\log p)^A\)（论文取 \(A=32\) 即可），这证明了 Vinogradov 最小非剩余猜想；由此还得到求 \(\mathbb F_p\) 中平方根的确定性多项式时间算法。

## 证明思路

引擎是一个统一的"延拓判据"（continuation criterion）。令 \(\beta_*\) 为 \(F\) 上全体本原有限阶 Hecke \(L\)-函数在 \(1/2\le\Re s\le1\) 内零点实部的上确界，目标是证 \(\beta_*\le7/8\)。判据说：若对每个目标特征 \(\eta\) 都能构造探针 \(J_\eta(Z)\)（光滑化特征和），同时满足低估计 \(|J_\eta|\ll Z^{C(\sigma_0)+\omega}\) 与高估计 \(|J_\eta-f_\eta|\ll Z^{C(\beta_*)-\sigma}\)，其中 \(f_\eta\) 是含 \(H_\eta(s)/L_F^{\mathcal S}(s,\eta)\) 的 Mellin 积分（\(H_\eta\) 全纯且接近 \(1\)），且正余量 \(\omega,\sigma\) 与 \(\eta\) 无关，则 \(\beta_*>\sigma_0\) 必假：两式合并给出 \(|f_\eta|\ll Z^{C(\beta_*)-\varepsilon_*}\)，对其取 Mellin 变换便把 \(1/L_F^{\mathcal S}(s,\eta)\) 全纯延拓到 \(\Re s>\beta_*-\varepsilon_*\)；而按 \(\beta_*\) 的定义，某目标的 \(L\)-函数在那里有零点，其倒数应有极点，矛盾。

探针在艾森斯坦整数环 \(\mathcal O\) 上构造：把 Patterson 三次 theta 级数（cubic theta series）的磨光傅里叶系数对六次剩余特征（sextic residue character）与目标 \(\eta\) 平均，完成后的指标形如 \(cn^3\)。同一个和有两条独立表示。低估计一侧：经完备三次 theta 反射（源自 Kubota 的 metaplectic 理论）变形系数，二次大筛法（large sieve）控制反射行的均方；加性部分展开为 \(\mathbb C/\mathcal O\) 中的既约分数，由平面加性大筛法控制；再以柯西不等式合并。高估计一侧：对平均变量作 Poisson 求和，非零频率形如 \(ua^6\)（\(u\) 六次幂自由），局部 Euler 恒等式把每行写成 Hecke \(L\)-函数之商与受控 Euler 乘积，其中 \(u=1\) 的主行恰含 \(1/L_F(s,\eta)\)，其留数给出 \(f_\eta\) 的非零倍数。零点检测器（zero detector）为有限 Hecke 扭转族分配无零点矩形：在固定下限 \(51/100\) 之上选出零点的行会产生两个大 Dirichlet 多项式（一带理想 Möbius 系数的截断倒数，一不带），六次大筛法（发展自 Heath-Brown 等的递归思路）限制此类行的数目。

证明分两阶段推进。第一阶段取对称尺度 \(l_x=l_y=1/2\)、\(C_{\mathrm I}(s)=s-2/3\)，只用逆多项式行计数，在 \(\sigma_0=11/12\) 验证判据（余量 \(1/4800\)），先得 \(\beta_*\le11/12\)。第二阶段反设 \(\beta_*>7/8\) 并做三处改造：其一，素补偿——在探针中插入选定素数槽并作相消组合，抵消高侧多余的标量 Euler 贡献；其二，改用不对称尺度 \(l_x=17/48\)、\(l_y=23/48\) 与 \(C_{\mathrm{II}}(s)=s-11/16\)；其三，补两个独立的矩归纳（带素因子的逆矩与无标记矩），每步用两次有限 Poisson 变换缩短行区间，高度参数则最后选定以吸收全部高度因子。收尾经二次转移：\(\chi\) 与理想范数复合给出 \(F\) 上 Hecke 特征，且 \(L_F^{\mathcal S}=L^{S}(s,\chi)\,L^{S}(s,\chi\chi_{-3})\)（\(s=1\) 处由 \(L(1,\chi_{-3})=\pi/(3\sqrt3)>0\) 排除零极点相消），Hecke 半平面便转移到全体 Dirichlet \(L\)-函数。注意：即便只关心 \(\zeta\)，也须对整个 Hecke 族证明定理，因为 Poisson 行会引入目标特征的有限阶 Hecke 扭转。

## 可信度与备注

任务元数据标注本文 formalized=true，主结果已 Lean 形式化（家族文档附 Lean 链接），这是最强的可信度信号。同族姊妹篇互为支撑：另一篇手稿以不同方法独立证得 \(11/12\) 零自由半平面（未形式化），与本文第一阶段互相印证；第三篇把实特征例外零点的排除量化为一致界 \((1-\beta)\log q\ge c\)。按 OpenAI 官方声明，未经形式化的结果可能存在问题；矩归纳、检测器高度分配等细节技术性较强，此处从略，请以 Lean 证明与社区核验为准。

{% endraw %}
