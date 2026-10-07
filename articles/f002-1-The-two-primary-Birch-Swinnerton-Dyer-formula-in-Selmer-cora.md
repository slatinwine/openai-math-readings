---
layout: default
title: "The two-primary Birch–Swinnerton-Dyer formula in Selmer corank at most one"
family: "002"
discipline: "Number theory"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | The two-primary Birch–Swinnerton-Dyer formula in Selmer corank at most one

> 结果族 002：The full BSD formula from low Selmer corank　·　学科：Number theory　·　验证状态：暂无形式化证明，请以社区核验为准

## 一句话结论

对每条 `@@M@@2@@`-幂 Selmer 群 `@@M@@\mathbb{Z}_2@@`-余秩 `@@M@@s_2(E)\le 1@@` 的有理椭圆曲线，本文证明代数秩、解析秩与 Selmer 余秩三者相等，Tate–Shafarevich 群有限，且 BSD 首项公式的 `@@M@@2@@`-进部分 `@@M@@v_2(Q_E)=v_2(\#\Sha)@@` 精确成立——对 `@@M@@E[2]@@` 结构与 `@@M@@2@@` 处约化类型零限制。

## 问题背景

BSD 猜想（Birch–Swinnerton-Dyer conjecture，源自 Birch 与 Swinnerton-Dyer 1965 年的计算）断言：椭圆曲线 `@@M@@L@@`-函数在 `@@M@@s=1@@` 处的首项系数由有理点、Tamagawa 数（Tamagawa numbers）与 Tate–Shafarevich 群共同决定。秩的断言与精确首项断言是两回事：Gross–Zagier 与 Kolyvagin 的经典定理在解析秩 `@@M@@\le 1@@` 时给出 Mordell–Weil 秩与 `@@M@@\Sha@@` 有限性，却不给出首项系数的整数值。在奇素数上，Skinner–Urban、张伟、Jetchev–Skinner–Wan 借助 Iwasawa 主猜想与 Heegner 点的积分理论得到精确公式，但均需剩余表示或局部假设。素数 `@@M@@2@@` 最为棘手：实分支数与整格指标都进入公式，以往结果（Zhao、Coates–Li–Tian–Zhai、Cai–Li–Zhai、Shu–Zhai、Kriz–Li 等）都附加基曲线、分裂或单位条件。本文在该 Selmer 余秩范围内一次性移除全部附加假设。

## 主要结果

主定理（论文 Theorem 1.1）：设 `@@M@@E/\mathbb{Q}@@` 为任意椭圆曲线，其含实位 Kummer 条件的 `@@M@@2@@`-幂 Selmer 群满足 `@@M@@s_2(E)=\corank_{\mathbb Z_2}\Sel_{2^\infty}(E/\mathbb Q)\le 1@@`，则
`@@M@@Dr=\operatorname{rank}E(\mathbb Q)=\operatorname{ord}_{s=1}L(E,s)=s_2(E),\qquad \#\Sha(E/\mathbb Q)<\infty,@@`
且
`@@M@@DQ_E=\frac{L^{(r)}(E,1)\,(\#T_E)^2}{r!\,\Omega_E\Reg_E\prod_{\ell}c_\ell(E)}\in\mathbb Q_{>0},\qquad v_2(Q_E)=v_2\bigl(\#\Sha(E/\mathbb Q)\bigr),@@`
其中 `@@M@@T_E@@` 为有理挠子群、`@@M@@\Omega_E@@` 为遍历全部实分支的实周期、`@@M@@\Reg_E@@` 为标准高度配对的行列式（regulator）、`@@M@@c_\ell@@` 为 Tamagawa 数。定理对 `@@M@@E[2]@@` 与 `@@M@@E@@` 在 `@@M@@2@@` 处的约化无任何限制。推论（任意素数判据）：只要存在某个素数 `@@M@@p@@` 使 `@@M@@s_p(E)\le 1@@`，同样结论即成立——先由姊妹篇的任意素数 Selmer 逆定理得出秩与 `@@M@@\Sha@@` 有限，再经 Kummer 正合列得 `@@M@@s_2(E)=r\le 1@@` 归入主定理。结合二次扭曲的 Selmer 余秩分布定理，还得到：对每条固定的 `@@M@@E/\mathbb Q@@`，按绝对值排序的带号无平方因子扭曲中密度一的集合上该精确 `@@M@@2@@`-进公式成立，公共秩为 `@@M@@0@@` 或 `@@M@@1@@`，各占密度一半。

## 证明思路

证明围绕偏差量 `@@M@@X(A)@@`——即 BSD 比值（含 `@@M@@\#\Sha@@`）的 `@@M@@2@@`-进赋值——组织为三个命题。（正比较）非 CM 曲线解析秩 `@@M@@\le 1@@` 时 `@@M@@X\ge 0@@`，且若某正基本判别式扭曲满足 `@@M@@X(A^a)=0@@`，该单位可沿同余转移回 `@@M@@A@@`。（分裂对锚点）存在正判别式 `@@M@@h@@` 与虚二次域 `@@M@@k@@`（`@@M@@2hN_A@@` 的素因子全分裂），使 `@@M@@\mathrm{an}(A^h)+\mathrm{an}(A^{hk})=1@@` 且 `@@M@@X(A^h)+X(A^{hk})=0@@`。（CM 比较）CM 曲线直接处理。因 `@@M@@k<0@@`，锚点两条扭曲之一必为正扭曲；`@@M@@X@@` 的非负性令和为零的两项各自为零，再经转移回到原曲线。核心障碍是积分困难：Euler 系构造往往只在乘以某个不定非零整数后才给出生成元，其未知 `@@M@@2@@`-进赋值无法定出 `@@M@@v_2(Q_E)@@`。对策是把两件事拆开：在 `@@M@@2@@` 可逆的高一素理想处做水平比较（允许通分），剩余集中化提供积分性，闭点处再独立证本性——如 `@@M@@U\in\mathbb Z_2[[u]]@@` 是单位需常数项为奇数。

正比较的实现：先取模曲线商 `@@M@@E'=E_0/C_{\mathrm{cusp}}@@`（Manin–Drinfeld 定理保证 `@@M@@C_{\mathrm{cusp}}@@` 有限）的整相对格，用 Kato 全水平 Siegel 单元（Siegel units）造整上同调类；显式互反律加 Hecke 展开给出未归一化周期律：对偶指数映射的坐标恰是挖去 `@@M@@M@@` 的 Euler 因子的 `@@M@@L@@`-值除以周期。再以 Poitou–Tate 指标与实分支、Haar 测度计算，把行列式赋值精确化为 `@@M@@X(A)@@`。在解析秩未知的余秩一中心，沿一个横截驯方向（极限 Frobenius 满足 `@@M@@k(g)-\beta(g)g_T(g_T-1)^{-1}x(g)\ne0@@`）变形：Selmer 复形在芽 `@@M@@\mathbb Q_2[[v]]@@` 上的极小微分 `@@M@@\delta(v)@@` 满足 `@@M@@\delta(0)=0@@`，若其阶数 `@@M@@\ge 2@@`，则闭上链 `@@M@@z_1\cup x+\lambda_i\cup k@@` 的各局部不变量除在选定动素数处趋于非零外全部趋零，违背整体不变量求和律，故 Selmer Bockstein `@@M@@\delta'(0)\ne0@@`。单位行列式加一阶 Bockstein 迫使对偶指数映射有单零点，从而 `@@M@@L'(E,1)\ne0@@`（否则 Heegner 迹为挠、谱检验迫使导数为零，矛盾）。

锚点以虚 `@@M@@S_3@@` 剩余像为例：先用有限 `@@M@@2@@`-下降配合 Chebotarev 逐步选新鲜素数扭曲，得到在分裂虚二次域上 Selmer 余秩为一的种子；同时取一条提升 `@@M@@E[2]@@` 的 CM 比较型，其 `@@M@@L@@`-函数的分裂单零点已知。再比较一条在 `@@M@@2@@` 上方一位严格局部条件下的行列式与一对"耗尽"的 CM 圆盘测度：剩余同余 `@@M@@B_E\equiv B_0@@`、`@@M@@D_E\equiv\epsilon D_0\pmod\pi@@` 把 CM 商的单位性转移到 `@@M@@E@@`；交错 Bockstein 配对 `@@M@@\langle x,\partial x\rangle=0@@` 强制剩余维数为偶，逐维下降必然终止，最终得整除关系且商为单位；Gross–Zagier 公式（配合 Tate 的限制-of-scalars 等变）检出单零点并给出 `@@M@@X(E^h)+X(E^{hk})=0@@`。其余剩余像（有理 `@@M@@2@@`-挠的纯量情形、循环立方像用 ray units、实 `@@M@@S_3@@` 用交错行列式与 Pfaffian 余子式提升）各有专门论证，技术细节本文从略。CM 情形则用椭圆单位（elliptic units）、Johnson-Leung–Kings 主猜想与 Kato 互反律：高阶 `@@M@@2@@`-幂特征值处赋值恒定，经 Weierstrass 预备定理逼出 `@@M@@\operatorname{ord}_v U=0@@`。

## 可信度与备注

本文主结果尚无 Lean 形式化证明；按 OpenAI 官方声明，未经形式化的结果可能存在问题，请以社区核验为准。族内姊妹篇互相支撑：任意素数的 Selmer 逆定理（*The Selmer converse for elliptic curves at every prime*）提供任意素数判据的秩与 `@@M@@\Sha@@` 有限性输入，本文再把精确 `@@M@@2@@`-进公式接上；配合同族二次扭曲 Selmer 分布的结果，即得每条固定曲线密度一扭曲族上的完整 BSD 公式。

{% endraw %}
