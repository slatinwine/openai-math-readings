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

## 入门导读 🐣

想象一沓面额越来越大的代金券，每张兑换时都要被扣掉同一笔固定手续费；只要面额能无限增大，这篇论文证明：你一定能兑换出一张完全不扣手续费的纯券，而且原来享受的会员折扣（对称性）原样保留。它研究的是高维空间上"带固定误差、无限增长的对称截面"如何兑换出"纯的正度数对称截面"。

**关键词卡片**

- 线性化（linearization）：群作用在线丛上的同步抬升，像旋转桌面时连餐具朝向一起转。
- 不变截面（invariant section）：在对称操作后保持原样的截面，落在指定的"特征标签"上。
- 伪有效（pseudoeffective）：数值上落在有效锥闭包里的类，"极限意义不亏"，但未必真能兑现。
- 转移定理（invariant transfer）：无界度数的不变截面序列带着固定伪有效误差，必产出某个正度数的不变纯截面。
- 单值群（monodromy）：沿环路回到原地时自动多出的隐藏对称，此处表现为紧环面作用。

**看个具体例子**

把定理画出来：每一级台阶是一个度数 `@@M@@m_j@@` 的不变截面，红色方块是同一块固定误差 `@@M@@P@@`。度数越大，误差占比越小：`@@M@@m_j=10@@` 时占 `@@M@@1/10@@`，`@@M@@m_j=1000@@` 时占 `@@M@@1/1000@@`——被无限稀释。定理说这种稀释必然"结晶"出一个正度数 `@@M@@m@@` 的纯截面（完全不带红块）。

<div>

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 560 280">
  <text x="40" y="57" font-size="14" fill="#333">度数 m₁</text>
  <rect x="150" y="40" width="60" height="24" fill="#e05a4e"/>
  <rect x="210" y="40" width="140" height="24" fill="#9dbfdd"/>
  <text x="40" y="97" font-size="14" fill="#333">度数 m₂</text>
  <rect x="150" y="80" width="60" height="24" fill="#e05a4e"/>
  <rect x="210" y="80" width="210" height="24" fill="#9dbfdd"/>
  <text x="40" y="137" font-size="14" fill="#333">度数 m₃</text>
  <rect x="150" y="120" width="60" height="24" fill="#e05a4e"/>
  <rect x="210" y="120" width="280" height="24" fill="#9dbfdd"/>
  <text x="40" y="177" font-size="14" fill="#333">度数递增</text>
  <rect x="150" y="160" width="60" height="24" fill="#e05a4e"/>
  <rect x="210" y="160" width="340" height="24" fill="#9dbfdd"/>
  <line x1="280" y1="196" x2="280" y2="216" stroke="#555" stroke-width="2"/>
  <polygon points="274,214 286,214 280,226" fill="#555"/>
  <rect x="150" y="232" width="180" height="24" fill="#4a7dbd"/>
  <text x="345" y="250" font-size="14" fill="#333">正度数 m：纯截面 ≠ 0</text>
  <rect x="450" y="196" width="14" height="14" fill="#e05a4e"/>
  <text x="468" y="208" font-size="13" fill="#333">误差 P</text>
</svg>

</div>

再结合紧环面单值结构，把万有覆盖紧因子上造出的不变截面"下降"回原空间，就得到标题性结论：`@@M@@-K_X@@` 光滑半正的高维空间必有 `@@M@@H^0(X,-mK_X)\neq0@@`。

**为什么值得关心**

"固定误差被无界增长洗掉、特征标签被保留"是全新机制，是任意维数反典范非消没证明链的中枢一环。

> 验证状态：暂无形式化证明（AI 结果待核验）

## 一句话结论

对 `@@M@@-K_X@@` 带光滑半正度量的光滑射影复簇 `@@M@@X@@`，本文证明不变量转移定理：带固定伪有效误差的无界度数环面不变截断必产生某个正度数的无挠不变截断；结合紧环面单群结构作下降，最终得到任意维数的反典型非消没 `@@M@@H^0(X,-mK_X)\ne0@@`。

## 问题背景

反典型非消没（anticanonical nonvanishing）问：当反典型丛 `@@M@@L=-K_X=\det T_X@@` 具有曲率非负的光滑 Hermitian 度量（光滑半正）时，是否存在 `@@M@@m>0@@` 使 `@@M@@H^0(X,mL)\ne0@@`。问题可追溯到 Yau 1994 年问题清单（Problem 75）。结构层面，Demailly–Peternell–Schneider（1996）证明了此类簇万有覆盖的全纯等距分裂，Campana–Demailly–Peternell（2015）进一步识别紧因子为有理连通；LMPTX（2023）与 Müller（2025）分别在三维及附加半丰富假设的高维建立（数值）非消没，但数值有效并不保证线丛本身有截断。任意维数的无条件截面存在性长期悬置。若再引入群作用，还有第二重障碍：上同调方法造出的截断必须落在指定特征标（character）之上。

## 主要结果

主定理（不变量转移，Invariant transfer）：设 `@@M@@X@@` 光滑连通射影，`@@M@@L=-K_X@@` 带光滑半正度量，代数环面 `@@M@@T@@` 作用其上；`@@M@@P,M@@` 是带 `@@M@@T@@`-线性化（linearization）的线丛，`@@M@@P@@` 作为普通线丛就是 `@@M@@L@@`（其线性化可与自然切丛行列式作用相差一个特征标），`@@M@@-M@@` 伪有效（pseudoeffective，数值类落在有效锥的闭包中）。若有无界正整数集 `@@M@@I@@` 及非零不变截断 `@@M@@s_i\in H^0(X,M+iP)^T@@`，则存在 `@@M@@m>0@@` 使 `@@M@@H^0(X,mP)^T\ne0@@`：固定误差被消除而特征标被保留。推论一：若 `@@M@@\chi(X,\mathcal O_X)\ne0@@`，则自然线性化下 `@@M@@H^0(X,mL)^T\ne0@@`。推论二（标题性结论）：每个 `@@M@@-K_X@@` 光滑半正的光滑连通射影复簇，必有某个正幂 `@@M@@-mK_X@@` 的非零截断。

## 证明思路

转移定理的骨架是"比值域给出纤维化"。同线性化度数的不变截断乘积之比是不变有理函数，其公共域决定一个到射影基的有理映射；沿一般纤维，诸 `@@M@@s_i@@` 的除子随 `@@M@@i@@` 仿射变化，无界性迫使斜率有效，故商 `@@M@@s_j/s_i@@` 提供相对反典型截断。难点是跨过退化纤维：先在双有理模型 `@@M@@\mu:W\to X@@` 与正规等维模型 `@@M@@f_W:W\to Y@@` 上，对每个基素除子减去最小规范化阶数，得到 `@@M@@kP_W-f_W^*(kB)@@` 的正则截断；再让两个度量分工——高次数的伴随纤维积分取根后收敛到逐纤维最大值，给出 `@@M@@kB@@` 上有界半正度量；零次数处由 `@@M@@-M@@` 的伪有效性提供基方向曲率为正的另一度量，延拓为 `@@M@@-K_Y+D_*@@`，其中 `@@M@@D_*\ge0@@` 拉回后是 `@@M@@X@@` 上的例外除子。关键在于 `@@M@@\mathcal O_Y(-D_*)@@` 含于乘子理想（multiplier ideal）`@@M@@\mathcal J@@`，且与有界度量作张量后 `@@M@@\mathcal J@@` 不变；于是 Nadel 消没把 `@@M@@\mathcal O_Y(D_*+jkB)\otimes\mathcal J@@` 的截断维数化为 `@@M@@j@@` 的多项式，它在 `@@M@@j=0@@` 处取正值，故必在某个正整数处非零。所得截断经相对截断提升回 `@@M@@X@@`，例外修正自动消失。

上同调输入分三步。先由姊妹篇的不变反典型指标定理（其在零处的值是真实指标而非形式外推），加上连通环面在奇异上同调上作用平凡、`@@M@@\chi^T(X,\mathcal O_X)=\chi(X,\mathcal O_X)\ne0@@`，选出固定次数的无界不变上同调；再用半正硬化 Lefschetz 定理将其转为 `@@M@@\Omega_X^{n-q}\otimes L^{m+1}@@` 的不变截断（Bochner–Kodaira 论证可等变化）；最后按 Lazic–Peternell 行列式法把向量丛饱和化后的最高外积拧成线丛 `@@M@@M@@` 上的不变截断 `@@M@@M+a_iL@@`，而 LMPTX 余切张量定理保证 `@@M@@-M@@` 伪有效，套用主定理即得推论一。推论二依赖紧环面单群（compact torus monodromy）结构：万有覆盖分解 `@@M@@\widetilde X=\mathbb{C}^c\times V\times F@@`，取有限指标后覆盖变换群在 `@@M@@F@@` 上经紧环面 `@@M@@H@@` 作用；`@@M@@F@@` 无正次全纯形式，故 `@@M@@\chi(F,\mathcal O_F)=1@@`，于是在 `@@M@@F@@` 上得到 `@@M@@H@@`-不变截断，与 `@@M@@\mathbb{C}^c,V@@` 上的平行逆典范标架张量后下降到有限覆盖，再以有限 étale 范数（乘遍 Galois 变换的不变乘积）送回 `@@M@@X@@`。

## 可信度与备注

本文与族内姊妹篇互相咬合：紧单群结构与有限 étale 范数取自文中引作的 CompanionH，不变指标定理取自 CompanionI；本文的纤维化去误差机制又被同族另两篇复用为固定误差转化。全部结果暂无 Lean 形式化证明；按 OpenAI 官方声明，未经形式化的结果可能存在问题，结论请以社区核验为准。

{% endraw %}
