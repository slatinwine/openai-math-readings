---
layout: default
title: "A sharp Fourier certificate for planar circle packing"
family: "090"
discipline: "Convex and metric geometry"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | A sharp Fourier certificate for planar circle packing

> 结果族 090：Triangular-lattice optimality, long-range Riesz and Coulomb energies, and spherical logarithmic energy　·　学科：Convex and metric geometry　·　验证状态：暂无形式化证明，请以社区核验为准

## 入门导读 🐣

同样大小的硬币在无限大的桌面上最多能摆多密？人人都猜蜂窝式最密——这早被 Thue 证明。这篇论文做的是另一件事：造一台"验钞机"。它构造出一个特殊函数，几个符号条件一经检查，密度上界就被钉死在蜂窝的数值上、分毫不差。Cohn–Elkies 方法提出二十多年，这台二维验钞机终于被造了出来。

**关键词卡片**

- 圆堆积密度（circle packing density）：硬币盖住桌面的面积占比。
- 线性规划界（linear programming bound）：Cohn–Elkies 框架——找一个辅助函数，其符号条件直接产出密度上界。
- Fourier 变换（Fourier transform）：把函数拆成各种频率的波；证书要求变换后处处非负。
- Schwartz 函数（Schwartz function）：衰减极快、极光滑的函数，造证书的材料。
- 区间算术（interval arithmetic）：用区间包住精确值做运算，验证不含浮点误差。

**看个具体例子**

蜂窝摆法里，每枚硬币恰好嵌进一个正六边形"包间"，包间的内切圆正是硬币本身，所以密度 `@@M@@=\dfrac{\pi r^2}{2\sqrt3\,r^2}=\dfrac{\pi}{2\sqrt3}\approx 0.9069@@`。论文构造的证书 `@@M@@f@@` 满足 `@@M@@f(0)/\widehat f(0)=2/\sqrt3@@`，代入 Cohn–Elkies 定理，上界 `@@M@@=\frac\pi4\cdot\frac{2}{\sqrt3}=\frac{\pi}{2\sqrt3}@@`，与蜂窝密度严丝合缝；而且对任意（不必周期的）堆积都有效。

<div>

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 560 280">
  <text x="280" y="26" font-size="15" text-anchor="middle" fill="#222">蜂窝摆法：每枚硬币一个六边形“包间”</text>
  <g fill="#cfe3f7" stroke="#5a86b8" stroke-width="1.5">
    <circle cx="170" cy="130" r="40"/>
    <circle cx="250" cy="130" r="40"/>
    <circle cx="210" cy="199" r="40"/>
    <circle cx="130" cy="199" r="40"/>
    <circle cx="90" cy="130" r="40"/>
    <circle cx="130" cy="61" r="40"/>
    <circle cx="210" cy="61" r="40"/>
  </g>
  <polygon points="210,153.1 170,176.2 130,153.1 130,106.9 170,83.9 210,106.9" fill="none" stroke="#d64545" stroke-width="2" stroke-dasharray="6,4"/>
  <text x="170" y="252" font-size="13" text-anchor="middle" fill="#444">六边形面积 = 2√3·r²，圆面积 = πr²</text>
  <text x="345" y="120" font-size="14" fill="#222">密度 = π/(2√3) ≈ 0.9069</text>
  <text x="345" y="150" font-size="14" fill="#222">证书比值 = 2/√3</text>
  <text x="345" y="180" font-size="14" fill="#222">上界恰好达到同一数值</text>
</svg>

</div>

**为什么值得关心**

它与 8 维、24 维的"魔法函数"一脉相承，补齐二维拼图；同一张证书还顺带恢复经典结论——周期堆积中只有三角格能达到这个密度。

> 暂无形式化证明（AI 结果待核验）

## 一句话结论

本文构造了一个显式径向 Schwartz 函数 `@@M@@f@@`：在 `@@M@@|x|\ge1@@` 处非正、Fourier 变换处处非负、且 `@@M@@f(0)/\widehat f(0)=2/\sqrt3@@`，使 Cohn–Elkies 线性规划上界在平面达到精确的最优堆密度 `@@M@@\pi/(2\sqrt3)@@`，解决其二维 sharpness 猜想，并从零点结构恢复周期等号情形三角堆积的唯一性。

## 问题背景

平面等圆堆的最优密度 `@@M@@\pi/(2\sqrt3)@@` 是 Thue 定理（Hales 给出基于 Rogers 思想的初等证明）。Cohn 与 Elkies 2003 年的 Fourier 线性规划（linear programming）框架把堆密度上界化为寻找一个"变换前后符号相容"的辅助函数：要求 `@@M@@f(x)\le0@@` 在排除半径之外、`@@M@@\widehat f\ge0@@`；其猜想 7.3 问二维是否也存在使界达到最优的 sharp 证书。该框架在 8 维与 24 维由 Viazovska 及 CKMRV 的模形式"魔法函数"达到最优。平面多一重障碍：三角壳上的值与导数数据并不唯一确定径向 Schwartz 函数（CKMRV 猜想 7.5，Sardari 证实了非唯一性），因此不能照搬高维插值路线，必须在一个显式函数族内另行求解。

## 主要结果

定理（sharp Fourier 证书）：存在实径向 Schwartz 函数 `@@M@@f@@` 满足

`@@M@@D\widehat f(0)=1,\qquad f(0)=\frac{2}{\sqrt3},\qquad \widehat f(\xi)\ge0\ \ (\xi\in\mathbb R^2),\qquad f(x)\le0\ \ (|x|\ge1).@@`

代入 Cohn–Elkies 定理得密度上界 `@@M@@\frac{\pi}{4}\cdot\frac{2}{\sqrt3}=\frac{\pi}{2\sqrt3}@@`，恰为 `@@M@@(1,0)@@` 与 `@@M@@(1/2,\sqrt3/2)@@` 生成的三角格所达到的值——经典密度定理由此被新证书重新推导，并非新的密度结论；该证书适用于任意堆积，不限于周期的。零点结构被完全确定：物理侧零点的平方半径恰为模 `@@M@@12@@` 节点集 `@@M@@\mathcal N@@`（整数），Fourier 侧零点位于 `@@M@@\frac43\mathcal N@@`；`@@M@@r=1@@` 处是单零点，径向导数精确为 `@@M@@-2/(3\sqrt3)@@`，原点值由 Poisson 恒等式精确给出为 `@@M@@F(0)=\widehat F(0)=6Q_1e^{-\pi h}>0@@`。推论：周期堆积若达到 `@@M@@\pi/(2\sqrt3)@@`，其中心集必为标准三角格在欧氏运动下的像。

## 证明思路

先把协体积一三角格的壳坐标 `@@M@@s_a=b|a|^2=j^2+jk+k^2@@` 覆盖进模 `@@M@@12@@` 剩余类节点集 `@@M@@\{0,1,3,4,7,9\}@@`（`@@M@@b=\sqrt3/2@@`；覆盖是严格的——如 `@@M@@15@@` 是节点却非壳值，证明用"`@@M@@2@@` 不是模 `@@M@@5@@` 的平方数"）。符号区域内部的零点必为零导数，故 Fourier 侧全部节点、物理侧第一壳以外的全部壳都规定为二阶零点；第一壳位于符号区域边界，允许单零并规定其负导数，用以锁定整体归一化。构造上，正弦平方乘积 `@@M@@P(s)@@`（系数显式）在每个节点有二阶零点，除以线性与二次因子得到可独立规定值与导数的 Hermite 基数函数（Hermite-cardinal，模式承自 Carneiro–Littmann–Vaaler 的高斯 Beurling–Selberg 构造）；乘固定高斯（阻尼 `@@M@@h=2/5@@`）得径向 Schwartz 函数，其 Fourier 变换具有额外高斯衰减的积分表示。耦合的 Fourier 插值方程用有限矩阵处理前若干节点、用显式估计控制无穷尾部，并在整个无权 `@@M@@\ell^1@@` 系数空间上求逆（唯一性限于所选系数族）。符号证明处理"精确零点对有限计算"的落差：每个系数列表带 `@@M@@\ell^1@@` 误差界连到精确解；零点附近先把误差的低阶 Taylor 项减去再除以消失幂，避免奇异放大；正 Bernstein 系数在完整半胞上认证符号，无界区域用正弦乘积屏障加二阶导数估计收尾。归一化不用数值：对 Poisson 求和的伸缩恒等式求导，`@@M@@t=1@@` 时非零项全消失，导数中仅第一壳的六个向量存活，精确得到原点值。周期等号情形：由零点集知任意两中心距离的平方为整数，平移伸缩后经极化恒等式得整内积，中心集生成秩二格 `@@M@@\Gamma@@`，其 Gram 行列式为正整数且只能达到 `@@M@@3@@`，而行列式恰为 `@@M@@3@@` 的整格必是三角格。

## 可信度与备注

本文主结果暂无形式化证明；证书的计算部分见两份附录：一份给出有限数据与区间算术（interval arithmetic）主证书，含连接有限和与精确矩的解析积分误差；另一份汇集独立的有理数替代验证。本文是本族两篇能量论文的方法源头——其高斯基数函数、有限块与无穷尾求逆及 Bernstein 符号认证框架被后两者改编。作者如实指出局限：等原点形式的证书 `@@M@@g@@` 不满足 Cohn–Elkies 猜想 8.1 的附加零集要求；与 Zhitniaia 2026 年学士论文摘要所宣布的 `@@M@@\Gamma_0(12)@@` 模形式构造的关系，因仅见机构摘要而尚待全文核对。按 OpenAI 官方声明，未经形式化的结果可能有问题，请以社区核验为准。

{% endraw %}
