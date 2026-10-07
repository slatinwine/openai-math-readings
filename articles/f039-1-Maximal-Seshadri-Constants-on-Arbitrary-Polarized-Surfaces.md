---
layout: default
title: "Maximal Seshadri Constants on Arbitrary Polarized Surfaces"
family: "039"
discipline: "Algebraic and complex geometry"
formalized: true
source: null
pdfname: ""
---

{% raw %}
# 解读 | Maximal Seshadri Constants on Arbitrary Polarized Surfaces

> 结果族 039：Nagata's conjecture and maximal Seshadri constants　·　学科：Algebraic and complex geometry　·　验证状态：主结果已 Lean 形式化

## 一句话结论
对任意光滑整复射影曲面 \(S\) 与丰富线丛 \(L\)，本文证明当点数 \(r\) 超过仅依赖 \((S,L)\) 的阈值后，\(r\) 个非常一般点处的多点 Seshadri 常数恰等于体积上界 \(\sqrt{L^2/r}\)，正面解决曲面上的定性 Nagata–Biran 猜想。

## 问题背景
多点 Seshadri 常数（multipoint Seshadri constant）\(\varepsilon(S,L;\mathbf p)=\inf_C L\cdot C/\sum_i \mathrm{mult}_{p_i}C\) 度量丰富线丛（ample line bundle）在一组点处的局部正性；等价地，它是使爆炸曲面上 \(\pi^*L-\lambda\sum_i E_i\) 为 nef（与每条积分曲线交非负）的最大 \(\lambda\)。jet 计数给出万有上界 \(\sqrt{L^2/r}\)，定性 Nagata–Biran(-Szemberg) 猜想断言：\(r\) 充分大时等式在非常一般点组处成立。此前进展各有缺口：Biran 的辛堆满稳定性（symplectic packing stability，1999）不固定复结构，不是代数陈述；Harbourne 的极大性限于 \(rL^2\) 为平方数（且需很丰富性假设）；Roé 的转移方法与 Biran–Roé–Ross 乘积不等式均须借助相应平面常数的极大性。本文对任意丰富极化与阈值之后的全部整数 \(r\) 直接给出证明。

## 主要结果
主定理：对每对 \((S,L)\) 存在整数 \(r_0=r_0(S,L)\)，使得对每个 \(r\ge r_0\)，在非常一般点组（即可数个真 Zariski 闭子集之外、余集非空）处，实除子类 \(\pi^*L-\sqrt{L^2/r}\sum_i E_i\) 在爆炸曲面上是 nef 的，从而 \(\varepsilon(S,L;\mathbf p)=\sqrt{L^2/r}\)。推论将结论推广到不可数、特征为零的代数闭域。由于结论落在自交为零的 nef 边界类上，它排除了一切"次数与总重数之比低于该数值界"的曲线，包括重数不等的情形。

## 证明思路
全文把问题转化为代数环面 \(\mathbb T=(\mathbb C^*)^2\) 上的有限插值：目标是证明对所有满足 \(m\gt k\sqrt{H/r}\)（\(H=L^2\)）的正整数 \(k,m\)，\(kL\) 的截面在某组 \(r\) 个不同点处通过 \(m\) 阶单射 jet 测试——即只有零截面能在全部测试点消失到阶 \(\ge m\)。与 Alexander–Hirschowitz 渐近后置化定理不同，这里的阈值 \(r_0\) 必须对任意大的 jet 阶统一生效，这是新的困难点。

先建立传递机制：满秩的初始 Taylor 单项式 jet 矩阵在充分小的解析重标度下保持满秩；取一个带普通结点（node）的除子 \(V\in|dL|\)，其两分支局部即坐标轴，在权 \((1,t)\) 下截面的最小 Taylor 指数落入四边形 \(kQ_t\) 内；再作环面坐标替换并沿 \((1,1)\) 方向压缩切片，得到面积 \(k^2H/2\) 的三角形 \(kP_t\)。两级传递依次作用，便把三角形上的环面测试送回曲面截面。

核心是三角形的连续变形与有限子群测试：\(P_t\) 的面积恒为 \(H/2\)，令 \(t\) 连续变动，可为每个充分大的 \(r\) 调整形状，使某个本原格向量（primitive lattice vector）\(u\) 上行列式投影的长度恰为 \(\sqrt{rH}\)；取指标为 \(r\) 的子格，其特征子群 \(G\subset\mathbb T\) 恰有 \(r\) 个点（在坐标下即 \(X=1,Y^r=1\)，不必是方格）。若非零 Laurent 多项式在 \(G\) 上处处消失到阶 \(\ge m\)，对 \(G\) 取平均将其分解为陪集分量，每个分量的支撑落在面积 \((kw)^2/2\)、竖直范围 \(kw\)（\(w=\sqrt{H/r}\)）的三角形内；三角形重数引理——按水平切片长度论证并提取 \((U-1)^e\) 因子——给出它在单位元处的阶 \(\le kw\lt m\)，矛盾。故环面测试单射，且 \(t\) 与 \(G\) 在选定 \(k,m\) 之前固定。

最后组装：单射性是 Zariski 开条件，可数多个测试由 Baire 纲论证在某非常一般点组同时成立。再从齐次 jet 过渡到 nef：若 \(D_0=\pi^*L-w\sum_i E_i\) 非 nef，则有曲线 \(C\) 使 \(D_0\cdot C\lt 0\)；减去小 \(\delta C\)、并把 \(w\) 微扰为略大的有理数 \(s\)，得 \(D^2\gt 0\) 且 \(\pi^*L\cdot D\gt 0\)，由 Riemann–Roch 与 Serre 对偶使 \(kD\) 的倍数有效，加回 \(k\delta C\) 便得到 \(kL\) 的截面在所有点消失到阶 \(m=ks\gt kw\)，与测试矛盾。反向的上界 \(\sqrt{H/r}\) 由初等 jet 计数给出，两界合并即得定理。

## 可信度与备注
本文主结果已由 Lean 形式化证明。族内姊妹篇互相支撑：平面篇把阈值精确到 \(r\ge 10\) 并处理任意非齐次重数，本文引言将其引用为独立的精细化；高维篇沿用本文的"结点指数界 + 本原方向"机制推广到 \(n\ge 3\) 维（改用满射 jet 评估，且不以本文定理为输入）；据族概述，该族还包含正特征版本的对应结果。按 OpenAI 官方声明，未经形式化的结果可能有问题；本文已形式化。

{% endraw %}
