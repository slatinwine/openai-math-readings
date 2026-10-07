---
layout: default
title: "Critical strip-crossing mass on the honeycomb lattice"
family: "237"
discipline: "Probability and statistical mechanics"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | Critical strip-crossing mass on the honeycomb lattice

> 结果族 237：The three-quarter exponent for honeycomb self-avoiding walk　·　学科：Probability and statistical mechanics　·　验证状态：暂无形式化证明，请以社区核验为准

## 一句话结论
在蜂巢格点临界权重下，证明高 `@@M@@N@@` 条带的自避行走穿越质量 `@@M@@\mathcal B_N\asymp N^{-1/4}@@`、返回拱的水平位移一阶矩 `@@M@@m_N\asymp N^{3/4}@@`：首次以固定常数上下界锁定悬置四十余年的预言幂次 `@@M@@-1/4@@`。

## 问题背景
临界权重下的自避行走（self-avoiding walk）做长距离穿越不必付出指数代价，但路径越长权重越小，两者的平衡决定"穿越质量"如何随条带高度衰减。Lawler–Schramm–Werner 的共形不变标度图景给出边界指数 `@@M@@5/8@@`，预言边界两点质量幂为 `@@M@@-5/4@@`，沿对边求和即预言穿越幂为 `@@M@@-1/4@@`（这一推导也明确写在 Duminil-Copin–Smirnov 的文中）。但严格结果长期远落后：DCS 的条带论证只把穿越质量夹在 `@@M@@1/N@@` 与 `@@M@@1@@` 之间，定不出幂；Beaton 等人证明它趋于零；Glazman–Manolescu 得到子序列上的对数界；Krachun–Panagiotis 2026 年也只得到指数 `@@M@@10^{-10}@@` 的多项式上界。预言的精确幂始终未证。本篇另辟蹊径：不直接攻穿越质量，而是先精确计算一个辅助可观测量——返回路径的位移矩——再由增量关系反推。

## 主要结果
模型取蜂巢格点（三角密铺的对偶），路径端点在边界边中点（港口，port），每访问一个对偶顶点付权重 `@@M@@\rho@@`，`@@M@@\rho=1/\sqrt{2+\sqrt2}@@` 为 Duminil-Copin–Smirnov 定出的临界值。在 `@@M@@N@@` 个三角带高的无限条带 `@@M@@\mathcal S_N@@` 中，从底部固定港口出发、终点在顶部任一港口且其余部分严格居于条带内部的路径称为桥（bridge），返回底边的称为拱（arch）；`@@M@@\mathcal B_N@@` 为桥的总权重，`@@M@@m_N=\sum_{k\ge1}kK_N(k)@@` 为拱的水平位移一阶矩。定理（临界条带质量）对一切 `@@M@@N\ge1@@`：`@@M@@c\mathcal A_N+\mathcal B_N=1@@`（`@@M@@c=\cos(3\pi/8)@@`，边界恒等式）；`@@M@@m_{N+1}-m_N\asymp\mathcal B_N@@`；`@@M@@m_N\asymp N^{3/4}@@`；`@@M@@\mathcal B_N\asymp N^{-1/4}@@`；且 `@@M@@\mathcal B_N@@` 关于 `@@M@@N@@` 单调不增。这里 `@@M@@\asymp@@` 表示比值被夹在两个与 `@@M@@N@@` 无关的正常数之间，即"有界因子"（bounded-factor）幂律，远强于对数精度或仅幂指数的结论。注意 `@@M@@m_N@@` 是对所有长度求和的非归一化矩，以条带高度为尺度。

## 证明思路
总体路线是"先算 `@@M@@m_N@@`，再用增量恢复 `@@M@@\mathcal B_N@@`"，因为边界恒等式本身定不出幂。先建立条带传递框架：闭游程相消给出边界恒等式并控制有限高度的传递矩阵（transfer matrix）；引入每行一个谱参数的菱形权重（属于稀疏回路模型 dilute loop 的可积结构，承 Ikhlef–Cardy 与 Glazman 的工作），切口状态记录空位与路径碎片造成的配对，由此定义平稳真空向量与带源向量。再用一个标量 Pfaffian `@@M@@p_N@@` 把平稳真空变成有界度数的多项式向量——度数界是关键，它把后续插值变成恒等式论证。接着证明拱公式：在两个端点之间的每一列处切割右向拱，一条位移为 `@@M@@k@@` 的拱恰好被计数 `@@M@@k@@` 次，从而把 `@@M@@m_N@@` 化为源态的配对、再化为首一多项式 `@@M@@g_X=p_{N+1}/p_N@@` 的系数 `@@M@@m(X)=\sum_i a_i-\eta[z^{N-1}]g_X(z)@@`；并由阶梯边界上的通量恒等式证得 `@@M@@m_{N+1}-m_N\asymp\mathcal B_N@@`（下界来自从侧港立即下拐接一条桥，上界来自路径对界面访问的有序配对与几何级数）。然后把合并参数的极限问题转化为 `@@M@@0<y_1<\cdots<y_N<1@@` 上的正定积分：密度为 `@@M@@\prod_i\omega(y_i)\prod_{i<j}\frac{(y_j-y_i)^2}{y_i+y_j}@@`，其中 `@@M@@\omega(x)=\frac12\sqrt{\sqrt{\frac{1+x}{2x}}-1}@@`；解的唯一性由 Cauchy 双矩行列式严格为正（Cauchy 行列式乘两个正 Vandermonde）保证，于是合并极限非奇异，`@@M@@m_N@@` 等于含 `@@M@@\prod_i\frac{y_i-x}{y_i+x}@@` 期望的一个显式积分——该成对相互作用恰是广义 Bures 系综（generalized Bures ensemble）的核。最后做硬边界（hard edge）比较：用 Schur 的 Pfaffian 恒等式与 de Bruijn 积分公式求出 Bures–Laguerre 参考律的显式归一常数，用正结合性（positive association，MTP`@@M@@_2@@`）得到随机序比较；最小坐标的逆矩估计一边给上界一边给下界，得到 `@@M@@m_N\asymp N^{3/4}@@`。再由单调性与增量恒等式收尾：`@@M@@(N-1)\mathcal B_N\lesssim m_N@@` 给出 `@@M@@\mathcal B_N\lesssim N^{-1/4}@@`，取固定倍数高度差作比较给出反向不等式，完成 `@@M@@\mathcal B_N\asymp N^{-1/4}@@`。

## 可信度与备注
本篇暂无形式化证明。同一个条带幂 `@@M@@h^{-1/4}@@` 在姊妹篇《Uniform marked-polygon estimates and sharp finite bridge moments》中由有限传递计算加缝合论证独立得出，两路线互相印证；本篇的 `@@M@@m_N\asymp N^{3/4}@@` 正是 `@@M@@3/4@@` 指数在非归一化矩层面的体现。按 OpenAI 官方声明，未经形式化的结果可能有问题，请以社区核验为准。

{% endraw %}
