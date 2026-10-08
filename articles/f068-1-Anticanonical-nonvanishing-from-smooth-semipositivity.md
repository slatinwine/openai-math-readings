---
layout: default
title: "Anticanonical nonvanishing from smooth semipositivity"
family: "068"
discipline: "Algebraic and complex geometry"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | Anticanonical nonvanishing from smooth semipositivity

> 结果族 068：Anticanonical nonvanishing in every dimension　·　学科：Algebraic and complex geometry　·　验证状态：暂无形式化证明，请以社区核验为准

## 入门导读 🐣

每个空间都自带一把"体积尺"——反典范线丛 `@@M@@-K_X@@`。如果这把尺能配上曲率处处非负的光滑度量（气球处处不瘪），丘成桐 1994 年问：是否必有某个幂次的尺上真的出现刻度（非零截面）？本文在任意维数给出肯定答案，且不设任何额外假设。

**关键词卡片**

- 反典范丛 `@@M@@-K_X@@`（anticanonical line bundle）：切丛的最高外幂，空间的"体积尺"。
- 半正曲率度量（semipositive Hermitian metric）：度量曲率是非负形式，气球处处不瘪。
- 截面（section）：线丛上的全局"刻度函数"；存在非零截面，尺才算真正可用。
- 有效除子（effective divisor）：非零截面的零点集，刻度落地的痕迹。

**看个具体例子**

为什么必须是"某个幂次"？取 Enriques 曲面 `@@M@@E@@`（其 `@@M@@-K_E@@` 是非平凡的二阶挠线丛）与 `@@M@@P^1@@` 的乘积 `@@M@@X=E\times P^1@@`：`@@M@@-K_X@@` 由平坦度量与 Fubini–Study 度量拼出光滑半正度量，但一次幂没有截面，平方才有。数字版定理：

`@@M@@H^0(E\times P^1,-K_X)=0@@`，而 `@@M@@H^0(E\times P^1,-2K_X)\ne0@@`。

主定理：只要 `@@M@@-K_X@@` 有曲率半正的光滑度量，必有 `@@M@@m>0@@` 使 `@@M@@H^0(X,-mK_X)\ne0@@`，对任意维数一致成立。此前已知结果（数值有效性路线、三维非消没等）都需附加假设，本文首次在全维数、无附加条件下落地。

**为什么值得关心**

这是丘成桐 1994 年问题集（Problem 75）中非消没问题的完整解答，把"度量正性"与"截面存在性"这两大正曲率几何脉络接通。证明中锻造的有限体积定理与环面不变截面两条新器械，也可望在其他非消没问题里继续复用。

> 暂无形式化证明（AI 结果待核验）

## 一句话结论

证明了丘成桐 1994 年提出的反典范非消没问题：光滑连通射影复簇 `@@M@@X@@` 上若 `@@M@@-K_X@@` 容许曲率半正的光滑 Hermitian 度量，则存在正整数 `@@M@@m@@` 使 `@@M@@H^0(X,-mK_X)\ne0@@`，且对任意维数一致成立。

## 问题背景

对光滑射影复簇 `@@M@@X@@`，反典范线丛（anticanonical line bundle）`@@M@@-K_X=\det T_X@@` 是切丛的最高外幂。若它带有 Chern 曲率为非负实 `@@M@@(1,1)@@`-形式的光滑 Hermitian 度量，则其数值类必为 nef（数值有效）。丘成桐在 1994 年问题集（Problem 75）中问：这是否迫使 `@@M@@-K_X@@` 的某正倍数线性等价于有效除子？"正幂"不可省略：复 Enriques 曲面 `@@M@@E@@` 与 `@@M@@\mathbb P^1@@` 的乘积上，反典范线丛由平坦度量与 Fubini–Study 度量给出光滑半正度量，却没有一次幂截面，只有平方才有。此前卡在哪里：Demailly–Peternell–Schneider 与 Campana–Demailly–Peternell 的结构定理虽把万有覆盖分解为平坦、紧 Ricci 平坦与剩余因子，但剩余因子上残留的牌变换（deck transformation）作用——一个紧环面——可能阻碍截面下降；已知代数方法（LMPTX 2023 的数值有效性、Müller 2025 的三维非消没）都需要附加假设。

## 主要结果

主定理（Theorem 1.1）：设 `@@M@@X@@` 是光滑连通射影复簇，`@@M@@-K_X@@` 有半正曲率的光滑 Hermitian 度量，则存在整数 `@@M@@m>0@@` 使 `@@M@@H^0(X,-mK_X)\ne0@@`。技术核心是有限体积定理（Theorem 1.2）：若 `@@M@@Z@@` 无正度全纯形式，`@@M@@D\ge0@@` 为整除子，`@@M@@J=-K_Z+D@@` 带半正奇异度量且 `@@M@@\int_Z|s_D|_{h_J}^2<\infty@@`，线丛 `@@M@@L@@` 带局部有界权重的半正奇异度量，则存在 `@@M@@a>0@@`、`@@M@@b\ge0@@` 使 `@@M@@H^0(Z,aL+bD)\ne0@@`。另有自然不变版本（Theorem 7.2）：紧环面 `@@M@@T@@` 以微分诱导的自然线性化（natural linearization）作用时，可取到 `@@M@@T@@`-不变的截面 `@@M@@H^0(Z,mL)^T\ne0@@`。

## 证明思路

证明分四步。先做几何约化：Yau 的指定 Ricci 定理把给定半正曲率实现为某 Kähler 度量的 Ricci 形式，DPS/CDP 结构定理随即给出万有覆盖的等距乘积分解 `@@M@@\widetilde X=\mathbb C^a\times F\times Z@@`，其中 `@@M@@F@@` 紧 Ricci 平坦且典则丛有不变平行框架，`@@M@@Z@@` 有理连通、无正度全纯形式；Bochner 论证与 Bieberbach 定理把有限指标后的牌作用压缩成紧环面 `@@M@@T@@`，其 Zariski 闭包是代数环面 `@@M@@G@@`，且 `@@M@@T@@`-不变截面就是 `@@M@@G@@`-不变截面。再在 `@@M@@Z@@` 上构造 `@@M@@T@@`-不变反典范截面——这是全文核心，靠对维数归纳的有限体积定理完成：反设结论失败，则 `@@M@@L+D@@` 伪有效而不 big，由可移动锥（movable cone）对偶性找到非零可移动曲线类 `@@M@@\alpha@@` 使 `@@M@@L\cdot\alpha=D\cdot\alpha=0@@`；可移动斜率（slope）理论控制余切张量的最小斜率，配合带乘子理想子（multiplier ideal）的 Hard Lefschetz 定理产生无界序列截面 `@@M@@s_i\in H^0(Z,M+m_iL)@@`，`@@M@@m_i\to\infty@@`，其中 `@@M@@M@@` 是某个固定的余切行列式线丛且 `@@M@@M\cdot\alpha\le0@@`。然后在所有非空完全线性系 `@@M@@|uL+vM+wD|@@` 中取像维数极大者，得到严格更小的光滑射影基 `@@M@@S@@`，并证明任意两截面之比落在函数域 `@@M@@\mathbb C(S)@@` 中；插值恒等式 `@@M@@s_i^k s_1^{m_i-m_2}/s_2^{m_i-m_1}\in\mathbb C(S)@@` 进而消去水平极点，得无水平极点的有理截面 `@@M@@\rho@@`。接着是迁移（transfer）步骤：在正规等维模型上取除子阶数的最小值把 `@@M@@\rho@@` 规范化为正则截面 `@@M@@e@@`，在光滑消解上沿纤维对 `@@M@@e^j@@` 积分——Berndtsson–Păun 的相对 Bergman 度量（relative Bergman metric）半正性保证各阶矩的权是多重次调和的；零阶矩给出基上 `@@M@@-K_S+D_S@@` 的半正有限体积度量，高阶矩除以 `@@M@@j@@` 取上包络给出线丛 `@@M@@A@@` 的两侧局部有界半正度量，而 `@@M@@D_S@@` 只支在"坏"素除子上，保证基上截面乘 `@@M@@e@@` 后能提升回 `@@M@@Z@@` 且极点可控，与归纳假设矛盾完成归纳。环面不变版本把奇异系数的 Bergman 定理换成 Berndtsson 的光滑直像半正性：紧环面上平均是到不变线的正交全纯投影，不变线因此获得半正商度量；Rosenlicht 有理商上稠密轨道给出不变伴随秩一。最后把 `@@M@@Z@@` 上不变截面与 `@@M@@\mathbb C^a@@`、`@@M@@F@@` 的不变典则框架相乘，下降到有限 étale 覆盖，再用有限 étale 范数（norm）得到 `@@M@@X@@` 上 `@@M@@K_X^{-m\deg\nu}@@` 的非零截面。

## 可信度与备注

本文暂无形式化证明，请以社区核验为准。同族第二篇手稿从不变 Euler 特征多项式与扭曲微分形式的转换给出主定理的另一条独立路线，第三篇把结论推进到 klt 对上的局部有界度量判据，三篇互相印证核心结论。按 OpenAI 官方声明，未经形式化的结果可能有问题。

{% endraw %}
