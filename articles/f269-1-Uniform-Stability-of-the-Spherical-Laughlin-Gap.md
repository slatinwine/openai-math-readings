---
layout: default
title: "Uniform Stability of the Spherical Laughlin Gap"
family: "269"
discipline: "Mathematical physics"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | Uniform Stability of the Spherical Laughlin Gap

> 结果族 269：Uniform Laughlin gap and stability under bounded scalar disorder　·　学科：Mathematical physics　·　验证状态：暂无形式化证明，请以社区核验为准

## 入门导读 🐣

分数量子霍尔效应里的电子，像在球面上跳一支规矩极严的华尔兹——彼此保持距离的 Laughlin 舞步；舞步与一切"乱跳"之间隔着一道能量沟。真实样品总有杂质，地面坑坑洼洼。论文证明：只要坑足够浅（与形状无关），这道沟不会被填平，舞步仍是唯一最省能量的跳法。

**关键词卡片**

- Laughlin 态（Laughlin state）：1/3 填充的分数量子霍尔基态，电子互相严格避让
- 谱隙（spectral gap）：基态与激发态之间的能量差，像一道保护沟
- 最低朗道能级（lowest Landau level）：强磁场下电子被限制其中的最低能层
- 无序势（disorder potential）：样品杂质造成的能量起伏，本文允许任意形状
- Toeplitz 扰动（Toeplitz perturbation）：无序势投影到最低能级后的量子算子形式

**看个具体例子**

N 个电子、磁通 q=3(N−1)，无序势幅度不超过 1（归一化），耦合 |λ|≤λ*。定理：对一切充分大的 N，扰动后最低两个能级之差仍不小于 Δ*（=1/50），基态依旧唯一。粒再多、势形再怪，沟的深度有保底。

<div>

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 560 280">
<circle cx="130" cy="115" r="72" fill="none" stroke="#333" stroke-width="2"/>
<circle cx="130" cy="43" r="5" fill="#23527c"/>
<circle cx="166" cy="53" r="5" fill="#23527c"/>
<circle cx="68" cy="79" r="5" fill="#23527c"/>
<circle cx="68" cy="151" r="5" fill="#23527c"/>
<circle cx="130" cy="187" r="5" fill="#23527c"/>
<circle cx="192" cy="151" r="5" fill="#23527c"/>
<text x="48" y="225" font-size="14" fill="#333">球面上的电子：严格避让的</text>
<text x="48" y="245" font-size="14" fill="#333">Laughlin 舞步（1/3 填充）</text>
<line x1="300" y1="150" x2="540" y2="150" stroke="#333" stroke-width="2.5"/>
<line x1="300" y1="245" x2="540" y2="245" stroke="#333" stroke-width="2.5"/>
<path d="M 310 197 q 12 -14 24 0 t 24 0 t 24 0 t 24 0 t 24 0 t 24 0 t 24 0 t 24 0" fill="none" stroke="#e67e22" stroke-width="2.5"/>
<text x="300" y="175" font-size="13" fill="#e67e22">弱无序势（幅度 ≤ 1，形状任意）</text>
<line x1="510" y1="150" x2="510" y2="245" stroke="#c0392b" stroke-width="2"/>
<polygon points="506,158 514,158 510,150" fill="#c0392b"/>
<polygon points="506,237 514,237 510,245" fill="#c0392b"/>
<text x="300" y="138" font-size="14" fill="#333">激发态 E₁</text>
<text x="300" y="266" font-size="14" fill="#333">基态 E₀（唯一）</text>
<text x="520" y="202" font-size="14" fill="#c0392b">Δ*</text>
</svg>

</div>

**为什么值得关心**

真实量子霍尔样品必有杂质，"间隙在弱无序下存活"是从理想模型走向现实的必答题。证明的关键不是硬碰硬地控制扰动总大小，而是让杂质项与相互作用能量"就地比价"——这也是连续投影子模型上第一个此类稳定性定理。

> 暂无形式化证明（AI 结果待核验）

## 一句话结论

证明球面上 1/3 填充的费米 Laughlin `@@M@@V_1@@` 哈密顿量在弱有界标量无序势下仍保有唯一基态与一致谱隙，且谱隙与无序阈值对所有充分大的粒子数、一切归一化势剖面一致成立。

## 问题背景

Laughlin 波函数描述分数量子霍尔效应（fractional quantum Hall effect）中 1/3 填充的强关联基态。在 Haldane 的球面几何中，每个电子对若处于相对角动量（relative angular momentum）1，就被投影算子 `@@M@@P_{ij}^{(1)}@@` 惩罚能量一，三次 Laughlin 多项式是其唯一零模。无微扰时的谱隙已由同族姊妹篇证明，但物理上更关键的是稳定性：真实样品总有杂质与外场，这层间隙能否在弱无序下存活？困难在于扰动的广延性——`@@M@@V_{N,q}(\varphi)=\sum_{i=1}^NT_q(\varphi)^{(i)}@@` 的范数可随粒子数增长到 `@@M@@N@@` 阶，朴素微扰论给出的无序区间随系统增大而塌缩为零；而格点上的著名稳定性定理（Bravyi–Hastings–Michalakis、Michalakis–Zwolak）依赖局域拓扑序等额外结构，无法直接移植到这个连续投影子模型。本文为球面最低朗道能级补齐了所需的局域控制。

## 主要结果

设 `@@M@@q=3(N-1)@@`，半径 `@@M@@\sqrt{q/2}@@` 的球面携带 `@@M@@q@@` 个磁通量子，`@@M@@U_q@@` 是最低朗道能级（lowest Landau level）。无微扰哈密顿量为 `@@M@@H_{N,q}=\sum_{i<j}P_{ij}^{(1)}@@`，每对系数为一。对实有界可测势 `@@M@@\varphi@@`（`@@M@@\|\varphi\|_\infty\le1@@`），经最低能级投影得到 Toeplitz 算子（Toeplitz operator）`@@M@@T_q(\varphi)=(\Pi_qM_\varphi\Pi_q)|_{U_q}@@`，并组成多体扰动 `@@M@@V_{N,q}(\varphi)@@`。主定理（一致标量无序稳定性）断言：存在常数 `@@M@@\lambda_*>0@@`、`@@M@@\Delta_*>0@@` 与 `@@M@@N_*@@`，使得对一切 `@@M@@N\ge N_*@@`、一切满足 `@@M@@\|\varphi\|_\infty\le1@@` 的实势、一切 `@@M@@|\lambda|\le\lambda_*@@`，微扰哈密顿量 `@@M@@H_{N,q}+\lambda V_{N,q}(\varphi)@@` 的最低两个本征值（计重数）之差不小于 `@@M@@\Delta_*@@`，特别地基态唯一。势可以随系统尺寸变化且无需任何对称性；常数只以存在性方式给出，证明不优化阈值。

## 证明思路

核心策略是不用整体范数控制扰动，而是把中心化的局域项与相互作用能量比较，这依赖两条新估计。第一条是零模（zero mode）空间中的局域观测量估计：对由一致局域化的中性（保粒子数）项组成的相互作用 `@@M@@W@@`，有 `@@M@@|\langle\psi,W\psi\rangle-\langle\Omega,W\Omega\rangle|\le C_W(N-n)@@`，其中 `@@M@@\psi@@` 属于 `@@M@@n@@` 粒子零模空间，`@@M@@\Omega@@` 是填满的 Laughlin 向量，常数对磁通一致，且对电子亏损的线性依赖至关重要。证明从一个磁极"读出"零模：末轨道为空则退掉一个磁通并记录一个旗标（flag），否则缩并掉一个电子并退掉三个磁通；旗标数即准空穴度（quasihole degree）`@@M@@h=q+3-3n@@`，在填充磁通处恰为电子亏损的三倍。在极点钉住零点（flux pinning）实现磁通变化，一致 Fock 谱隙沿该形变存活，给出局域酉输运；再沿分支选择的历史加权、旋转平均，即得上述估计。第二条是局域能量下降（local energy descent）：在整个 Fock 空间上构造快速局域的粒子损失算子 `@@M@@J_y@@`，满足 `@@M@@\int J_y^*J_y\,dy=H_q@@`、`@@M@@\int J_y^*H_qJ_y\,dy\le H_q^2-cH_q@@`，每次跳跃移除二至固定多个粒子；构造先用 `@@M@@B_0(g)@@` 在一点移除一对电子，再用保迹信道部分清空固定邻域，剩余对关联的账单由"保留四体块"支付——这正是对姊妹篇四体比较的强化版 `@@M@@H_q^2\ge c_0H_q+\mathcal L_4(W_4R_q^{\mathrm{hi}}W_4^*)@@`。相应的 Lindblad 演化使相互作用能指数衰减、期望粒子损失受初始能量控制，并使算子 `@@M@@G=H_q+\mu(N-\mathcal N)@@` 同时支配能量与粒子数的亏损或过剩。最后闭合成扰动论证：凡湮灭 `@@M@@\Omega@@` 的中性厄米局域项之和满足相对形式界 `@@M@@\pm\sum_xA_x\le CG@@`，证明归结为最优常数 `@@M@@K@@` 的二次不等式 `@@M@@K\le C+C\sqrt K@@`，其两处输入正是前两条估计。随后谱输运（quasiadiabatic 延拓的精确谱流形式）用光滑频率滤波 `@@M@@F@@`（`@@M@@|\omega|\ge g_0/2@@` 时取 `@@M@@-1/\omega@@`、`@@M@@|\omega|\le g_0/4@@` 时取零）构造酉 `@@M@@U(s)@@`，使拉回哈密顿量的导数逐项中心化而落入该适用类。在 `@@M@@N@@` 粒子扇区上 `@@M@@G=H@@`，积分得 `@@M@@U(s)^*H_sU(s)-E_0(s)I\ge(1-C|s|)H@@`，再用谱隙自举（bootstrap）把结论延伸到整个区间 `@@M@@[-\lambda_*,\lambda_*]@@`，取 `@@M@@\Delta_*=g_0/2@@`（`@@M@@g_0=1/25@@`）完成证明。

## 可信度与备注

本文暂无形式化证明。它的无微扰基石——一致 Fock 空间谱隙（至少 `@@M@@1/25@@`）——正是姊妹篇《A Fock-space inequality and the Laughlin spectral gap》，该篇主结果已 Lean 形式化；本文还复现并把其中的四体比较强化为"保留块"版本，为能量损失构造提供燃料。两篇互相咬合构成完整证明栈，但本文自身仍待核验：按 OpenAI 官方声明，未经形式化的结果可能有问题，请以社区核验为准。

{% endraw %}
