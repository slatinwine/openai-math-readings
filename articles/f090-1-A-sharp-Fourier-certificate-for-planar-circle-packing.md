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

## 一句话结论

本文构造了一个显式径向 Schwartz 函数 \(f\)：在 \(|x|\ge1\) 处非正、Fourier 变换处处非负、且 \(f(0)/\widehat f(0)=2/\sqrt3\)，使 Cohn–Elkies 线性规划上界在平面达到精确的最优堆密度 \(\pi/(2\sqrt3)\)，解决其二维 sharpness 猜想，并从零点结构恢复周期等号情形三角堆积的唯一性。

## 问题背景

平面等圆堆的最优密度 \(\pi/(2\sqrt3)\) 是 Thue 定理（Hales 给出基于 Rogers 思想的初等证明）。Cohn 与 Elkies 2003 年的 Fourier 线性规划（linear programming）框架把堆密度上界化为寻找一个"变换前后符号相容"的辅助函数：要求 \(f(x)\le0\) 在排除半径之外、\(\widehat f\ge0\)；其猜想 7.3 问二维是否也存在使界达到最优的 sharp 证书。该框架在 8 维与 24 维由 Viazovska 及 CKMRV 的模形式"魔法函数"达到最优。平面多一重障碍：三角壳上的值与导数数据并不唯一确定径向 Schwartz 函数（CKMRV 猜想 7.5，Sardari 证实了非唯一性），因此不能照搬高维插值路线，必须在一个显式函数族内另行求解。

## 主要结果

定理（sharp Fourier 证书）：存在实径向 Schwartz 函数 \(f\) 满足

\[\widehat f(0)=1,\qquad f(0)=\frac{2}{\sqrt3},\qquad \widehat f(\xi)\ge0\ \ (\xi\in\mathbb R^2),\qquad f(x)\le0\ \ (|x|\ge1).\]

代入 Cohn–Elkies 定理得密度上界 \(\frac{\pi}{4}\cdot\frac{2}{\sqrt3}=\frac{\pi}{2\sqrt3}\)，恰为 \((1,0)\) 与 \((1/2,\sqrt3/2)\) 生成的三角格所达到的值——经典密度定理由此被新证书重新推导，并非新的密度结论；该证书适用于任意堆积，不限于周期的。零点结构被完全确定：物理侧零点的平方半径恰为模 \(12\) 节点集 \(\mathcal N\)（整数），Fourier 侧零点位于 \(\frac43\mathcal N\)；\(r=1\) 处是单零点，径向导数精确为 \(-2/(3\sqrt3)\)，原点值由 Poisson 恒等式精确给出为 \(F(0)=\widehat F(0)=6Q_1e^{-\pi h}>0\)。推论：周期堆积若达到 \(\pi/(2\sqrt3)\)，其中心集必为标准三角格在欧氏运动下的像。

## 证明思路

先把协体积一三角格的壳坐标 \(s_a=b|a|^2=j^2+jk+k^2\) 覆盖进模 \(12\) 剩余类节点集 \(\{0,1,3,4,7,9\}\)（\(b=\sqrt3/2\)；覆盖是严格的——如 \(15\) 是节点却非壳值，证明用"\(2\) 不是模 \(5\) 的平方数"）。符号区域内部的零点必为零导数，故 Fourier 侧全部节点、物理侧第一壳以外的全部壳都规定为二阶零点；第一壳位于符号区域边界，允许单零并规定其负导数，用以锁定整体归一化。构造上，正弦平方乘积 \(P(s)\)（系数显式）在每个节点有二阶零点，除以线性与二次因子得到可独立规定值与导数的 Hermite 基数函数（Hermite-cardinal，模式承自 Carneiro–Littmann–Vaaler 的高斯 Beurling–Selberg 构造）；乘固定高斯（阻尼 \(h=2/5\)）得径向 Schwartz 函数，其 Fourier 变换具有额外高斯衰减的积分表示。耦合的 Fourier 插值方程用有限矩阵处理前若干节点、用显式估计控制无穷尾部，并在整个无权 \(\ell^1\) 系数空间上求逆（唯一性限于所选系数族）。符号证明处理"精确零点对有限计算"的落差：每个系数列表带 \(\ell^1\) 误差界连到精确解；零点附近先把误差的低阶 Taylor 项减去再除以消失幂，避免奇异放大；正 Bernstein 系数在完整半胞上认证符号，无界区域用正弦乘积屏障加二阶导数估计收尾。归一化不用数值：对 Poisson 求和的伸缩恒等式求导，\(t=1\) 时非零项全消失，导数中仅第一壳的六个向量存活，精确得到原点值。周期等号情形：由零点集知任意两中心距离的平方为整数，平移伸缩后经极化恒等式得整内积，中心集生成秩二格 \(\Gamma\)，其 Gram 行列式为正整数且只能达到 \(3\)，而行列式恰为 \(3\) 的整格必是三角格。

## 可信度与备注

本文主结果暂无形式化证明；证书的计算部分见两份附录：一份给出有限数据与区间算术（interval arithmetic）主证书，含连接有限和与精确矩的解析积分误差；另一份汇集独立的有理数替代验证。本文是本族两篇能量论文的方法源头——其高斯基数函数、有限块与无穷尾求逆及 Bernstein 符号认证框架被后两者改编。作者如实指出局限：等原点形式的证书 \(g\) 不满足 Cohn–Elkies 猜想 8.1 的附加零集要求；与 Zhitniaia 2026 年学士论文摘要所宣布的 \(\Gamma_0(12)\) 模形式构造的关系，因仅见机构摘要而尚待全文核对。按 OpenAI 官方声明，未经形式化的结果可能有问题，请以社区核验为准。

{% endraw %}
