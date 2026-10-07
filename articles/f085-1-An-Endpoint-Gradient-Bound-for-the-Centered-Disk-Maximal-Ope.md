---
layout: default
title: "An Endpoint Gradient Bound for the Centered Disk Maximal Operator"
family: "085"
discipline: "Real and complex analysis"
formalized: true
source: null
pdfname: ""
---

{% raw %}
# 解读 | An Endpoint Gradient Bound for the Centered Disk Maximal Operator

> 结果族 085：Endpoint Sobolev regularity of centered disk averages　·　学科：Real and complex analysis　·　验证状态：主结果已 Lean 形式化

## 一句话结论

论文证明：对平面上每个实值 \(f\in W^{1,1}(\mathbb R^2)\)，中心圆盘极大函数 (centered disk maximal function) 满足 \(\|\nabla Mf\|_1\le C\|\nabla f\|_1\)，\(C\) 为绝对常数。\(Mf\) 局部属于 \(W^{1,1}\) 且具有全局可积的弱梯度 (weak gradient)，正面解决了 Hajłasz–Onninen 端点正则性问题的平面中心圆盘情形。

## 问题背景

中心圆盘极大函数 \(Mf(x)=\sup_{r>0}\frac1{\pi r^2}\int_{B(x,r)}|f|\) 取所有以 \(x\) 为心的圆盘平均的上确界，是调和分析的基本算子。Kinnunen 在 1997 年证明它对 \(1<p<\infty\) 在 Sobolev 空间 \(W^{1,p}\) 上有界：梯度被 \(M(|\nabla f|)\) 逐点控制，再结合强 \(L^p\) 极大不等式即得。但 \(p=1\) 时强 \((1,1)\) 极大不等式失效，这条路线在端点 (endpoint) 处断裂。Hajłasz 与 Onninen 2004 年提问：梯度估计 \(\|\nabla Mf\|_1\le C\|\nabla f\|_1\) 本身是否仍然成立？一维已有 Tanaka（非中心）与 Kurka（中心）等肯定结果；高维仅对径向输入、非中心算子、二进或轴平行方体、以及分数阶情形成立。平面中心圆盘的零阶端点情形悬置多年，症结在于一维证明里区间的线性排序无法组织一族相互重叠的中心圆盘。

## 主要结果

主定理：存在绝对常数 \(C\)，使每个实值 \(f\in W^{1,1}(\mathbb R^2)\)（不要求径向、不要求紧支撑）的极大函数 \(Mf\) 局部可积、属于 \(W^{1,1}_{\mathrm{loc}}\)，且
\[\int_{\mathbb R^2}|\nabla Mf|\,\dd x\le C\int_{\mathbb R^2}|\nabla f|\,\dd x,\]
其分布导数 (distributional derivative) 由全局可积的函数表示。常数不追求最优。核心中间结果是"带符号有限频带估计"：对实值 \(g\in C_c^\infty(\mathbb R^2)\) 与 \(b/a\) 为二的幂，记 \(S_{a,b}g=\sup_{a\le t\le b}A_tg\)（\(A_t\) 为带符号圆盘平均），则 \(\int|\nabla S_{a,b}g|\le C\int|\nabla g|\)，常数与频带内尺度数目无关。推论把有界变差 (bounded variation, BV) 输入纳入：\(f\in BV(\mathbb R^2)\) 时 \(Mf\in L^2\cap BV_{\mathrm{loc}}\) 且 \(|D(Mf)|(\mathbb R^2)\le C|Df|(\mathbb R^2)\)；对有限周长 (perimeter) 的集合 \(E\) 还有 \(\int_0^1P(\{M\mathbf 1_E>t\})\,\dd t\le CP(E)\)。

## 证明思路

证明先对光滑紧支撑的带符号 \(g\) 建立有限频带估计，伸缩归一到半径带 \([2^{-m},1]\)，最后延拓到 Sobolev 输入。骨架分四层。

第一层是几何抵消。内部极大半径处平均的径向导数为零，旋转矩在每个圆盘上恒为零；复数记号把两式合并成"零一次矩"恒等式，且被邻近圆盘的正混合（平衡核）保持。仿射抵消引理给核差乘上因子 \(W_z(y)=1-\frac{\overline{y-x}}{\overline{z-x}}\)，它在薄壳中的点 \(z\) 处为零，故集中于 \(z\) 附近小帽的壳层质量变得便宜。壳层集中引理用在 \(z\) 处相切的嵌套圆盘扫掠，给出一个对所有半径一致的例外集 (exceptional set)：壳层质量几乎全部落入一个小帽，且只需内部圆盘的正质量界。由此得三条局部估计——不利方向梯度、频带端点梯度、数值振荡 \(v_k\)——支撑尺度 \(s\) 的误差仅按 \((s/r)^{1/100}\) 计费。

第二层给梯度标价。在二进网格 (dyadic grid) 的帐篷函数 (tent function) 下，将每个标量坐标（按有限锥基展开）自最细层向上等量配对正负质量，伸缩求和得每格的"公共价格" \(D_Q\)，总预算 \(\sum_Q D_Q\le C\int|\nabla g|\)，一份价格对所有方向通用。

第三层为剩余向量质量选取方向。在精炼路径上构造带"出生层"标记的粒子测度 (particle measure)，精确实现各顶点的向量质量；再定义逐点的有限状态标签律，把方向相同的极大连续尺度区间称为一个 run。换向产生端点项，空间变化的权重求导产生行导数项，两者的打包估计由向量可加性亏损支付，合计 \(\le CV\)。

第四层装配频带。由锥代数与触碰原理 (touching principle)——极大半径处包络梯度等于该平均的梯度——把 \(|\nabla F|\) 拆成有利与不利投影：不利项由公共价格与打包估计付费；带符号投影扣除基线 \(u_{r_i}\) 后做加权分部积分。核心抵消在于转移行满足 \(\sum_{n'}\nabla_x\pi_k(x;n,n')=0\)，取绝对值前可减去前一前缀历史的势，差只含 run 的延长与新 run，被 \(\sum_{l\ge k}v_l\) 控制；\(v_l\) 带来尺度 \(r_l\)，求导的行带来尺度 \(1/r_k\)，比值恰是方向成本估计控制的几何权。

最后延拓：\(G_N=S_{2^{-N},2^N}|f|\) 递增收敛于 \(Mf\)，一致的变差界给出有限向量 Radon 测度 \(H=D(Mf)\)。再证 \(H\) 无奇异部分 (singular part)：固定紧零测集 \(K\)，在半径 \(t\) 处拆开——大半径包络 Lipschitz，贡献随邻域缩小而消失；小半径则把带符号估计用于 \(g_Q=\chi_Q(g-c_Q)\)（\(c_Q\) 为局部均值，包络梯度不变），由 Poincaré 不等式把成本化为 \(K\) 的 \(6t\)-邻域上 \(|\nabla g|\) 的积分。邻域缩小后令 \(t\to0\)，由内正则性得绝对连续性，Radon–Nikodym 定理给出 \(L^1\) 弱梯度与主不等式。

## 可信度与备注

按任务元信息，主结果已 Lean 形式化（族文档 lean/docs/085.md），这是对外部读者最强的核验保障；论文本身给出完整的分层证明（局部估计、公共价格、方向打包、装配、延拓五个模块）。延拓一节还注明：得到变差界后可改用 Lahti–Weigt 的条件正则性定理推出局部 Sobolev 正则性，但奇异部分的直接消除仍由本文的带符号局部分解完成。本批任务文件中该结果族仅此一篇手稿；文中常数未优化、最优值未知。按 OpenAI 官方声明，未经形式化的结果可能有问题——本文主结果已形式化，但读者仍应以社区核验与 Lean 证明为准。

{% endraw %}
