---
layout: default
title: "All-temperature pressure for orthogonally invariant Ising spin glasses"
family: "234"
discipline: "Probability and statistical mechanics"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | All-temperature pressure for orthogonally invariant Ising spin glasses

> 结果族 234：All-temperature pressure of orthogonally invariant Ising spin glasses　·　学科：Probability and statistical mechanics　·　验证状态：暂无形式化证明，请以社区核验为准

## 一句话结论

对无序矩阵为确定性谱经 Haar 正交旋转（特征向量方向均匀、无离群特征值）的 Ising 自旋玻璃，本文证明任意固定温度下压强几乎必然且按期望收敛到一个显式变分公式，并由此导出零场基态能量公式，把 SK 模型的 Parisi 理论推广到一般正交不变谱。

## 问题背景

自旋玻璃（spin glass）的中心问题是求热力学极限下的压强（pressure，即每自旋对数配分函数）。经典 SK 模型的无序矩阵是 GOE 高斯矩阵，分布在正交共轭下不变，其极限压强由 Guerra 上界与 Panchenko 基于 Ghirlanda–Guerra 恒等式（Ghirlanda–Guerra identities）和超度量性（ultrametricity）的工作合成 Parisi 变分公式。保留正交不变性（orthogonal invariance）而放开谱形——`@@M@@J_N=U_N^{\mathsf T}\Lambda_NU_N@@`，`@@M@@U_N@@` 为 Haar 正交矩阵，谱经验分布收敛于紧支撑律——是最自然的推广类，GOE 的半圆律只是其一。此前这类模型没有一般的 Parisi 型公式：卡在各特征空间内的投影重叠（projected overlap）如何与总重叠耦合、正确的变分泛函长什么样。本文在全部温度解决了这一问题。

## 主要结果

主定理（thm:main）：设谱经验分布弱收敛于紧支撑律 `@@M@@\mu@@`，且最大、最小特征值分别收敛到 `@@M@@\supp\mu@@` 的上、下边缘（无渐近离群值）。则压强 `@@M@@P_N@@` 几乎必然且按期望收敛于

`@@M@@D\mathcal F(\mu)=\inf_{p\in\mathcal P}\Big\{S(p)+\frac12\int_0^1R_\mu(D_p(r))\,dr\Big\},@@`

其中 `@@M@@\mathcal P@@` 是非降的重叠分位路径（Parisi 路径）；`@@M@@D_p@@` 是由 `@@M@@D_p(p(s))=1-sp(s)-\int_s^1p(u)\,du@@` 刻画的变换；`@@M@@R_\mu(x)=b_\mu(x)-1/x@@` 是 `@@M@@\mu@@` 的 Voiculescu `@@M@@R@@`-变换，`@@M@@b_\mu@@` 为预解方程 `@@M@@\int\mu(d\lambda)/(b-\lambda)=x@@` 的解，在上边缘之上无解时取边缘值；`@@M@@S(p)=\sup_h\{\ell(h)+\frac12\int_0^1p(s)h(s)\,ds\}@@`，而 `@@M@@\ell@@` 是 Ruelle 概率级联（Ruelle probability cascade）上以 `@@M@@\log\cosh@@` 为终端函数的分层高斯递归定义的 Ising 场泛函，即 SK 型 Parisi 项。推论包括：零场基态能量 `@@M@@M_N\to\lim_{\beta\to\infty}\mathcal F(\mu_\beta)/\beta@@`（极限存在）；确定性外场经验律按一阶矩传输距离收敛时的对应公式；以及谱为 Marchenko–Pastur 律的 Wishart/Hopfield 模型 `@@M@@J_N=cG_N^{\mathsf T}G_N/N@@` 的显式极限，附带得到随机矩阵 `@@M@@\ell_\infty\to\ell_2@@` 算子范数与带符号列和最小化（向量平衡）的极限值。文中反例显示：支撑无界时仅谱弱收敛不足以保证压强极限存在。

## 证明思路

证明分五步。第一步先驯服重叠结构：给哈密顿量加强度 `@@M@@e_N=N^{-1/16}@@` 的微扰（线性项加高斯单项式核），使任意子列的投影重叠向量 `@@M@@(A^1,\dots,A^m)@@` 与级联层次满足联合 GG 恒等式；再沿用超度量性与同步化（synchronization）理论得到同步非降分位 `@@M@@p_a@@`，`@@M@@\sum_ap_a=p@@`（总重叠分位）。第二步是全新环节：在 Haar 旋转群上做平面旋转的无穷小微分，得 Ward 型恒等式 `@@M@@\rho_bL_a-\rho_aL_b=t(\lambda_a-\lambda_b)(L_a\star L_b)@@`，其中复制乘积 `@@M@@\star@@` 的符号（symbol）恰是普通乘法（Parisi 矩阵代数）；用谱律预解式解出 `@@M@@p_a(s)=\int_0^{p(s)}f_a'(D_p(r))\,dr@@`、`@@M@@f_a=\rho_a/(b_t-t\lambda_a)@@`，即各谱群重叠被总重叠完全决定，模型折叠回单重叠世界。第三步证上界：以协方差水平为 `@@M@@h@@` 的级联高斯场增广模型，对带惩罚的期望目标泛函取确定性极小。极小点的最优性条件一方面（对 `@@M@@h@@` 变分）迫使极限路径 `@@M@@p@@` 的上尾压过试探路径 `@@M@@q@@`，而相互作用能 `@@M@@\mathcal E_t(p)=\frac12\int_0^1F_t'(D_p)@@`（`@@M@@F_t(x)=xR(tx)@@`，凸性源自预解式导数的 Cauchy–Schwarz 不等式）随上尾增大而减小，故 `@@M@@\mathcal E_t(p)\le\mathcal E_t(q)@@`；另一方面（对 `@@M@@t@@` 变分）给出反向的严格不等式，矛盾即得上界。第四步下界用 Aizenman–Sims–Starr 空腔法（cavity method），但需新耦合：让 `@@M@@N@@` 与 `@@M@@N+n@@` 两系统共享特征空间，新增自旋方向在各谱群中生成"特殊轴"，腔自旋看到协方差路径为 `@@M@@H(x)=(b(x)I-A_0)^{-1}@@` 的高斯标记。腔因子的二次项是级联上的非交换高斯二次倾斜，论文精确算得 `@@M@@\E\log Z_K=-\frac12\int_0^1\frac{d}{dx}\log\det(I-H(x)K)\big|_{x=D_p(r)}\,dr@@`，且倾斜后仍是级联高斯，只是 `@@M@@H@@` 换为 `@@M@@(b(x)I-A)^{-1}@@`；Schur 补恒等式表明有效腔场的协方差路径恰为 `@@M@@h_p(s)=\int_0^{p(s)}R'(D_p(r))\,dr@@`，增量被严格算成 `@@M@@\ell(h_p)+\frac12\int ph_p+G_1(p)@@`。再由全模型的位点对称性做腔自旋测试，证得条件磁化 `@@M@@B_{h_p}=p@@`，配合 `@@M@@\ell@@` 凹性的切线不等式（凹性证明用折叠高斯转移的似然比随机单调与 Auffinger–Chen 式径向论证）可知 `@@M@@h_p@@` 恰好达到 `@@M@@S(p)@@` 的上确界；沿维数等差数列望远镜求和、对微扰参数取平均即得下界。第五步去掉有限谱限制：`@@M@@R_\nu@@` 关于谱律（含边缘分支）连续，特征空间内的旋转对称性稳定多重数扰动，有限字母逼近加夹逼完成期望收敛；`@@M@@SO(N)@@` 上 Poincaré 不等式给出的四阶矩集中不等式加 Borel–Cantelli 升级为几乎必然收敛；零温极限由 `@@M@@P_N(\beta)/\beta\le M_N\le P_N(\beta)/\beta+\log2/\beta@@` 夹出。

## 可信度与备注

主结果暂无形式化证明，请以社区核验为准；OpenAI 官方声明"未经形式化的结果可能有问题"。本文大量复用久经检验的构件——GG 与超度量框架、Ruelle 级联标记演算、ASS 空腔法——并自包含重证了与 Ho (2026) 协方差路径定理相容的场泛函凹性。同批姊妹篇互相印证：本文算出高斯模式 Hopfield（Wishart 谱）的变分值，与 Ising 感知机手稿在 `@@M@@c<1@@` 时完全一致（`@@M@@\mathcal F(\mu_{\alpha,c})=\mathcal P_{f_c}(\alpha)@@`）。本解读精读了数组、场泛函、旋转恒等式、上界、空腔、一般谱共六章；外场推广章节与 invariant-sk 文件未逐行核验，相关表述依据摘要。

{% endraw %}
