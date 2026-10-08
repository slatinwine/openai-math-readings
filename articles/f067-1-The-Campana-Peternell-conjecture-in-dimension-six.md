---
layout: default
title: "The Campana–Peternell conjecture in dimension six"
family: "067"
discipline: "Algebraic and complex geometry"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | The Campana–Peternell conjecture in dimension six

> 结果族 067：The Campana–Peternell conjecture in dimension six　·　学科：Algebraic and complex geometry　·　验证状态：暂无形式化证明，请以社区核验为准

## 入门导读 🐣

有一类高维空间"处处顺滑不粘滞"（切丛 nef：朝任何方向移动都不亏），猜想说：这样顺滑的正曲率空间必然高度对称，是李群轨道式的标准空间。Campana–Peternell 猜想在五维以下早已解决，本文攻克六维：六维顺滑 Fano 流形只能是有理齐性空间；最难的一个缺口被精确识别为 Grassmannian `@@M@@\operatorname{Gr}(2,5)@@`。

**关键词卡片**

- nef 切丛（nef tangent bundle）：切丛在每条曲线上度数非负，"处处顺滑不粘滞"。
- 有理齐性空间（rational homogeneous variety）：李群陪集空间 `@@M@@G/P@@`，如射影空间、Grassmannian，完美对称的标准空间。
- 伪指标（pseudoindex）：有理曲线反典范度的最小值，顺滑空间的"身材尺码"。
- VMRT（variety of minimal rational tangents）：过一点的最小有理曲线方向集合，识别空间的指纹。

**看个具体例子**

`@@M@@\operatorname{Gr}(2,5)@@` 是"五维复空间中所有二维平面"组成的空间：维数 `@@M@@2\times(5-2)=6@@`，伪指标 5、Picard 数 1——正是六维最后剩下的缺口情形。论文算出：若六维 `@@M@@X@@` 伪指标为 5，过一般点的 VMRT 必是 `@@M@@\mathbb P^5@@` 里的 Segre 三维体 `@@M@@\mathbb P^1\times\mathbb P^2@@`，而这恰是 `@@M@@\operatorname{Gr}(2,5)@@` 的指纹，于是 `@@M@@X\simeq\operatorname{Gr}(2,5)@@`。关键一步是一串交点数逼出 `@@M@@(u-4)(3u-8)=0@@`，再排除 `@@M@@u=4@@` 得 `@@M@@u=8/3@@`、`@@M@@L^3=3@@`；这部分有限消元附有可执行证书（矩阵秩在有限域上逐点核验），属"机器辅助、证书可查"的类型。

<div>

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 560 280">
  <text x="240" y="44" text-anchor="middle" font-size="16" fill="#204060">C⁵（五维复空间）</text>
  <polygon points="80,90 360,60 480,120 200,150" fill="#eaf2fb" stroke="#35618f" stroke-width="2"/>
  <polygon points="215,100 335,88 390,112 270,124" fill="#f5c88a" stroke="#8a4b00" stroke-width="2"/>
  <path d="M 335 88 Q 362 96 356 116" stroke="#8a4b00" stroke-width="2" fill="none"/>
  <polygon points="356,116 348,106 361,105" fill="#8a4b00"/>
  <path d="M 215 100 Q 193 108 201 127" stroke="#8a4b00" stroke-width="2" fill="none"/>
  <polygon points="201,127 204,113 213,120" fill="#8a4b00"/>
  <line x1="270" y1="122" x2="150" y2="176" stroke="#8a4b00" stroke-width="1.5"/>
  <text x="52" y="192" font-size="14" fill="#7a3d00">一个二维平面</text>
  <text x="280" y="230" text-anchor="middle" font-size="15" fill="#204060">Gr(2,5)＝所有这种二维平面的集合</text>
  <text x="280" y="256" text-anchor="middle" font-size="15" fill="#204060">维数 2×3=6，伪指标 5：六维缺口 ⇒ X≅Gr(2,5)</text>
</svg>

</div>

**为什么值得关心**

"数值正性推出极大对称性"是几何学的母题；六维落地后，顺滑 Kähler 流形的万有覆盖分解（单值化型定理）随之推进到差距不超过 6 的情形。

> 暂无形式化证明（AI 结果待核验）

## 一句话结论

本文证明：切丛为 nef 的光滑复射影 Fano 六维流形必定是有理齐性空间 `@@M@@G/P@@`，从而解决六维 Campana–Peternell 猜想；核心新步骤是伪指标为 `@@M@@5@@` 的情形，最终识别出 `@@M@@X\simeq\operatorname{Gr}(2,5)@@`，并附带 nef 切丛紧 Kähler 流形的万有覆盖分解定理。

## 问题背景

Fano 流形（Fano manifold）指反典范线丛 `@@M@@\omega_X^{-1}@@` 为丰裕（ample）的光滑射影流形；向量丛称为 nef（numerically effective，数值有效），若其射丛化上的重言线丛在每条曲线上度数非负。有理齐性空间（rational homogeneous variety）形如 `@@M@@G/P@@`，即连通半单复代数群 `@@M@@G@@` 关于抛物子群 `@@M@@P@@` 的商，如射影空间、二次超曲面与 Grassmannian。这类空间的切丛由整体截面生成，必然 nef。1979 年 Mori 用切丛的丰裕性刻画射影空间之后，Campana 与 Peternell 于 1991 年提出猜想：切丛 nef 的光滑 Fano 流形必为有理齐性空间——一个纯粹数值的正性条件能否决定流形容许传递代数群作用？此前三维以下（Campana–Peternell）、四维（Mok、Hwang）与五维（Watanabe、Kanemitsu）相继解决，Kanemitsu 又证明 `@@M@@\rho(X)>n-5@@` 时猜想成立；于是六维只剩 Picard 数（Picard number）`@@M@@\rho(X)=1@@` 且伪指标（pseudoindex，即有理曲线反典范度的最小值）为 `@@M@@4@@` 或 `@@M@@5@@` 的两个缺口。

## 主要结果

主定理（Theorem 1.1）：每个切丛 nef 的光滑连通复射影 Fano 六维流形都是有理齐性空间。作为推论（Kähler 单值化）：设 `@@M@@X@@` 是切丛在解析意义下 nef 的紧 Kähler 流形，`@@M@@\widetilde q(X)@@` 为所有连通有限平展覆盖（finite étale cover）上不规则度的最大值，则当 `@@M@@\dim_{\mathbb C}X-\widetilde q(X)\leq6@@` 时，`@@M@@X@@` 的万有覆盖双全纯同构于 `@@M@@F\times\mathbb C^{\widetilde q(X)}@@`，其中 `@@M@@F@@` 是有理齐性流形；相应地，某个有限平展覆盖的 Albanese 映射是以 `@@M@@F@@` 为纤维的局部平凡全纯丛。此外，正维数不超过六的这类 Fano 流形都容许正 Kähler–Einstein 度量。

## 证明思路

先归约：`@@M@@\rho(X)\geq2@@` 时 Kanemitsu 的定理（`@@M@@\rho(X)>n-5@@` 则猜想成立）直接给出结论，故设 `@@M@@\rho(X)=1@@`。记伪指标为 `@@M@@d@@`。`@@M@@d=2@@` 会导出与 `@@M@@\rho=1@@` 矛盾的 `@@M@@\mathbb P^1@@`-纤维化；`@@M@@d=3@@` 时极小有理切线簇（variety of minimal rational tangents，VMRT）是一维的，Mok–Hwang 分类只给出 `@@M@@\mathbb P^2@@`、`@@M@@Q^3@@` 与 `@@M@@G_2@@` 型齐性接触流形，均非六维；`@@M@@d\geq6@@` 时 Dedieu–Höring 的数值刻画给出 `@@M@@\mathbb P^6@@` 或 `@@M@@Q^6@@`。于是只剩 `@@M@@d=4,5@@`。

公共骨架是极小有理曲线的泛族 `@@M@@\pi:U\to V@@` 与求值映射 `@@M@@e:U\to X@@`。nef 性使每条极小曲线都是自由曲线（free curve），由此 `@@M@@U,V@@` 光滑、`@@M@@\pi@@` 是 `@@M@@\mathbb P^1@@`-纤维化、`@@M@@e@@` 光滑且纤维维数 `@@M@@d-2@@`，并且 `@@M@@e@@` 的相对切丛沿每条曲线同构于 `@@M@@\mathcal O_{\mathbb P^1}(-1)^{\oplus(d-2)}@@`。

`@@M@@d=4@@` 时由 Kanemitsu 的因子化定理化为带两个纤维化的流形，用 Hard Lefschetz 定理与相交论逐一排除纤维类型；最后的奇维二次超曲面丛情形，以"正交描述迫使某特征数为零，而第二纤维化迫使一个整除子具有非整度数"的矛盾排除。

`@@M@@d=5@@` 是全文核心。对一般点 `@@M@@x@@`，纤维 `@@M@@F=e^{-1}(x)@@` 是光滑三维流形，在标记点取切方向给出有限态射 `@@M@@\tau_x:F\to\mathbb P(T_x^*X)\simeq\mathbb P^5@@`，其像是 VMRT `@@M@@\mathcal C_x@@`，而 `@@M@@L=\tau_x^*\mathcal O(1)@@` 丰裕。目标是约束比值 `@@M@@u=c_1(T_F)\cdot L^2/L^3@@`。关键想法是把泛族"两用"：既当作参数空间 `@@M@@V@@` 上的曲线族，又当作 `@@M@@X@@` 上的三维流形族。一方面，下降到八维 `@@M@@V@@` 的类、来自六维 `@@M@@X@@` 的类，加上由 Deligne 固定部分定理（直接像的 Hodge 滤过常值，故正度陈特征消没）与相对 Grothendieck–Riemann–Roch 得到的两组消没，联合给出九权交点数之间的线性关系（矩阵 `@@M@@A@@` 为 `@@M@@1785\times581@@`）；另一方面，投影公式使部分交点数沿 `@@M@@e@@` 的积分分解为乘积 `@@M@@\xi_i\eta_j@@`，其中 `@@M@@\eta_1=u@@`。再把双线性约束乘到三次、在放松后的 `@@M@@6820@@` 维空间中消元：先在 `@@M@@\mathbb F_{10007}@@` 上算得维数上界 `@@M@@6@@`，再给出六个显式有理向量组成基，最终迫使 `@@M@@32-20u+3u^2=0@@`，即 `@@M@@(u-4)(3u-8)=0@@`。

最后做几何识别：Hwang–Mok 的分布理论（配合辛商反证）证明 `@@M@@\mathcal C_x@@` 线性张满 `@@M@@\mathbb P^5@@`，故 `@@M@@L^3\geq3@@`；截影亏格公式 `@@M@@g=1+(1-u/2)L^3@@` 排除 `@@M@@u=4@@`（亏格为负），从而 `@@M@@u=8/3@@`、`@@M@@L^3=3@@`、`@@M@@\deg\tau_x=1@@`。由 del Pezzo–Bertini 极小度分类，`@@M@@\mathcal C_x@@` 是三次滚动面；文中用不变量环论证其法性（normality），使 `@@M@@\tau_x@@` 成为同构，再用光滑性排除锥面，得 `@@M@@\mathcal C_x\simeq\mathbb P^1\times\mathbb P^2\subset\mathbb P^5@@`（Segre 三维流形）。这恰是 `@@M@@\operatorname{Gr}(2,5)@@` 的 VMRT（秩一同态的方向），于是 Mok 的识别定理给出 `@@M@@X\simeq\operatorname{Gr}(2,5)@@`。Kähler 推论则是把上述分类逐纤维用于 Demailly–Peternell–Schneider 的 Albanese 纤维化，再由有理齐性流形的形变刚性（`@@M@@H^1(T)=0@@`）、Fischer–Grauert 定理与 Claudon–Höring–Kollár 的万有覆盖分裂定理完成。

## 可信度与备注

本文主结果尚无 Lean 形式化证明；按 OpenAI 官方声明，"未经形式化的结果可能有问题"，请以社区核验为准。证明中有限消元部分附有完整可执行证书（附录）：矩阵秩在 `@@M@@\mathbb F_{10007}@@` 上验证，六个有理基向量逐点精确复核，属"机器辅助、证书可查"的类型。本结果族目前仅此一篇，其 `@@M@@\rho\geq2@@` 与低维部分完全引用已发表文献（Kanemitsu、Watanabe、Mok、Hwang 等）；新贡献集中在 `@@M@@\rho=1@@`、伪指标 `@@M@@4@@` 与 `@@M@@5@@` 两个缺口，其中伪指标 `@@M@@4@@` 的处理与 Watanabe 2021 的已有定理互为独立印证。

{% endraw %}
