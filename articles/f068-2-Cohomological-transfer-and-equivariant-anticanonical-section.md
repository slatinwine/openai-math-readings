---
layout: default
title: "Cohomological transfer and equivariant anticanonical sections"
family: "068"
discipline: "Algebraic and complex geometry"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | Cohomological transfer and equivariant anticanonical sections

> 结果族 068：Anticanonical nonvanishing in every dimension　·　学科：Algebraic and complex geometry　·　验证状态：暂无形式化证明，请以社区核验为准

## 一句话结论

对 `@@M@@-K_X@@` 带光滑半正度量的光滑射影复簇 `@@M@@X@@`，本文证明不变量转移定理：带固定伪有效误差的无界度数环面不变截断必产生某个正度数的无挠不变截断；结合紧环面单群结构作下降，最终得到任意维数的反典型非消没 `@@M@@H^0(X,-mK_X)\ne0@@`。

## 问题背景

反典型非消没（anticanonical nonvanishing）问：当反典型丛 `@@M@@L=-K_X=\det T_X@@` 具有曲率非负的光滑 Hermitian 度量（光滑半正）时，是否存在 `@@M@@m>0@@` 使 `@@M@@H^0(X,mL)\ne0@@`。问题可追溯到 Yau 1994 年问题清单（Problem 75）。结构层面，Demailly–Peternell–Schneider（1996）证明了此类簇万有覆盖的全纯等距分裂，Campana–Demailly–Peternell（2015）进一步识别紧因子为有理连通；LMPTX（2023）与 Müller（2025）分别在三维及附加半丰富假设的高维建立（数值）非消没，但数值有效并不保证线丛本身有截断。任意维数的无条件截面存在性长期悬置。若再引入群作用，还有第二重障碍：上同调方法造出的截断必须落在指定特征标（character）之上。

## 主要结果

主定理（不变量转移，Invariant transfer）：设 `@@M@@X@@` 光滑连通射影，`@@M@@L=-K_X@@` 带光滑半正度量，代数环面 `@@M@@T@@` 作用其上；`@@M@@P,M@@` 是带 `@@M@@T@@`-线性化（linearization）的线丛，`@@M@@P@@` 作为普通线丛就是 `@@M@@L@@`（其线性化可与自然切丛行列式作用相差一个特征标），`@@M@@-M@@` 伪有效（pseudoeffective，数值类落在有效锥的闭包中）。若有无界正整数集 `@@M@@I@@` 及非零不变截断 `@@M@@s_i\in H^0(X,M+iP)^T@@`，则存在 `@@M@@m>0@@` 使 `@@M@@H^0(X,mP)^T\ne0@@`：固定误差被消除而特征标被保留。推论一：若 `@@M@@\chi(X,\mathcal O_X)\ne0@@`，则自然线性化下 `@@M@@H^0(X,mL)^T\ne0@@`。推论二（标题性结论）：每个 `@@M@@-K_X@@` 光滑半正的光滑连通射影复簇，必有某个正幂 `@@M@@-mK_X@@` 的非零截断。

## 证明思路

转移定理的骨架是"比值域给出纤维化"。同线性化度数的不变截断乘积之比是不变有理函数，其公共域决定一个到射影基的有理映射；沿一般纤维，诸 `@@M@@s_i@@` 的除子随 `@@M@@i@@` 仿射变化，无界性迫使斜率有效，故商 `@@M@@s_j/s_i@@` 提供相对反典型截断。难点是跨过退化纤维：先在双有理模型 `@@M@@\mu:W\to X@@` 与正规等维模型 `@@M@@f_W:W\to Y@@` 上，对每个基素除子减去最小规范化阶数，得到 `@@M@@kP_W-f_W^*(kB)@@` 的正则截断；再让两个度量分工——高次数的伴随纤维积分取根后收敛到逐纤维最大值，给出 `@@M@@kB@@` 上有界半正度量；零次数处由 `@@M@@-M@@` 的伪有效性提供基方向曲率为正的另一度量，延拓为 `@@M@@-K_Y+D_*@@`，其中 `@@M@@D_*\ge0@@` 拉回后是 `@@M@@X@@` 上的例外除子。关键在于 `@@M@@\mathcal O_Y(-D_*)@@` 含于乘子理想（multiplier ideal）`@@M@@\mathcal J@@`，且与有界度量作张量后 `@@M@@\mathcal J@@` 不变；于是 Nadel 消没把 `@@M@@\mathcal O_Y(D_*+jkB)\otimes\mathcal J@@` 的截断维数化为 `@@M@@j@@` 的多项式，它在 `@@M@@j=0@@` 处取正值，故必在某个正整数处非零。所得截断经相对截断提升回 `@@M@@X@@`，例外修正自动消失。

上同调输入分三步。先由姊妹篇的不变反典型指标定理（其在零处的值是真实指标而非形式外推），加上连通环面在奇异上同调上作用平凡、`@@M@@\chi^T(X,\mathcal O_X)=\chi(X,\mathcal O_X)\ne0@@`，选出固定次数的无界不变上同调；再用半正硬化 Lefschetz 定理将其转为 `@@M@@\Omega_X^{n-q}\otimes L^{m+1}@@` 的不变截断（Bochner–Kodaira 论证可等变化）；最后按 Lazic–Peternell 行列式法把向量丛饱和化后的最高外积拧成线丛 `@@M@@M@@` 上的不变截断 `@@M@@M+a_iL@@`，而 LMPTX 余切张量定理保证 `@@M@@-M@@` 伪有效，套用主定理即得推论一。推论二依赖紧环面单群（compact torus monodromy）结构：万有覆盖分解 `@@M@@\widetilde X=\C^c\times V\times F@@`，取有限指标后覆盖变换群在 `@@M@@F@@` 上经紧环面 `@@M@@H@@` 作用；`@@M@@F@@` 无正次全纯形式，故 `@@M@@\chi(F,\mathcal O_F)=1@@`，于是在 `@@M@@F@@` 上得到 `@@M@@H@@`-不变截断，与 `@@M@@\C^c,V@@` 上的平行逆典范标架张量后下降到有限覆盖，再以有限 étale 范数（乘遍 Galois 变换的不变乘积）送回 `@@M@@X@@`。

## 可信度与备注

本文与族内姊妹篇互相咬合：紧单群结构与有限 étale 范数取自文中引作的 CompanionH，不变指标定理取自 CompanionI；本文的纤维化去误差机制又被同族另两篇复用为固定误差转化。全部结果暂无 Lean 形式化证明；按 OpenAI 官方声明，未经形式化的结果可能存在问题，结论请以社区核验为准。

{% endraw %}
