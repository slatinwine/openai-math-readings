---
layout: default
title: "A closed Ricci flow with bounded scalar curvature and finite-time curvature blowup"
family: "351"
discipline: "Differential geometry"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | A closed Ricci flow with bounded scalar curvature and finite-time curvature blowup

> 结果族 351：Scalar curvature and finite-time Ricci-flow singularities　·　学科：Differential geometry　·　验证状态：暂无形式化证明，请以社区核验为准

## 一句话结论

作者在足够高维的闭流形 \(\Sp^2\times\Sp^{q+1}\) 上构造出一条光滑 Ricci flow：其标量曲率（scalar curvature）直到有限极大时刻始终一致有界，全曲率张量却同时发散。这推翻了"任何维数下标量曲率都能探测有限时间奇点"的无限制延拓猜想。

## 问题背景

Ricci flow 是满足 \(\partial_t g=-2\Ric\) 的度量族，是几何化纲领的核心工具。Hamilton 的经典结果断言：闭流形上的流在有限时刻 \(T\) 无法光滑延续，唯一可能的原因是全曲率 \(\Rm\) 无界。那么作为 \(\Ric\) 痕量的标量曲率 \(R=\tr_g\Ric\) 是否也必然无界？这就是 Bamler 文中讨论的标量曲率延拓猜想（scalar-curvature extension conjecture）。Šešum 定理已证明 \(\Ric\) 一致有界即可延拓，但 \(R\) 携带的信息少得多：极端情形下曲率可以集中在近似 Ricci-flat（Ricci 平坦）锥的区域里，使 \(R\) 在重标度下消失。此前 Angenent–Knopf 的颈缩（neckpinch）、Gu–Zhu 与 Angenent–Isenberg–Knopf 的 Type-II 奇点、Stolarski 的锥奇点流都实现了任意快的全曲率爆炸，却都没能给出标量曲率的一致上界。本文补上这块拼图，给出否定回答。

## 主要结果

**主定理**：存在整数 \(q\ge10\)、时刻 \(T>0\)，以及闭连通流形 \(M=\Sp^2\times\Sp^{q+1}\)（维数 \(q+3\)）上带光滑初始度量的光滑 Ricci flow \(g(t)\)，\(0\le t<T\)，使得

\[\sup_{M\times[0,T)}|R_{g(t)}|<\infty,\qquad \lim_{t\uparrow T}\max_M|\Rm_{g(t)}|=\infty .\]

**推论**：在同一个固定的高维数里，这类流的全曲率有双侧幂律速率 \(c(T-t)^{-2k/d_q}\le\max_M|\Rm|\le C(T-t)^{-2k/d_q}\)，指数 \(2k/d_q\) 随模指标 \(k\) 可任意大，均为 Type-II 奇点。反例只出现在足够高的维数，论文不主张任何四维结论。

## 证明思路

底层构造直接取自 Stolarski 的双翘曲（doubly warped）共齐一度量 \(ds^2+\phi(s,t)^2 g_{\Sp^2}+r(s,t)^2 g_{\Sp^q}\)：奇点发生在两个极点轨道处，\(\Sp^q\) 因子先光滑坍缩，剩余半径为 \(\phi(0,t)\) 的 \(\Sp^2\) 轨道随后收缩。分析围绕两个尺度展开：在抛物尺度 \(\sqrt\delta\)（\(\delta=T-t\)）上，重标度流逼近一个 Ricci-flat 锥（cone），这只保证固定抛物环上 \(\Ric\) 很小；而极点处的光滑性由远小于它的帽尺度（cap scale）\(\theta=\delta^\sigma\)（\(\sigma>1/2\)）控制——锥近似管不住帽。

作者在其上新增两条关键估计。先做帽估计：改造 Stolarski 的标量符号障碍并利用对数斜率的单调性，定量控制帽的大小，再用曲率取点论证与 Shi 导数估计，得到帽尺度上的全曲率界 \(|\Rm|\le C\theta^{-2}\)；全程不假设流收敛到某个帽模型。再做反应估计：在随主导径向漂移 \(R_c(t)=\sqrt{r_c^2+2(q-1)(t_c-t)}\) 运动的柱体上施加一维抛物内估计（Calderón–Zygmund 型 \(L^s\) 热估计加迭代），常数与维数 \(q\)、模指标 \(k\) 均无关；再把曲率对对角张量的作用写成带重数的矩阵，其最大特征值不超过 \(q-1+C\sqrt q\)，从而 Ricci 范数方程的反应商满足 \(c\le(2(q-1)+C\sqrt q)/r^2\)。

最后是比较论证，精髓在"大维数边际"：取 \(a=5/2\)，当 \(q\) 充分大时边际量 \((a-2)(q-1)-C\sqrt q-2a^2-1>0\)，于是内障碍函数 \(H=\delta^L(r^2+b_0\theta^2)^{-a/2}\) 的扩散系数 \(a(q-1)\) 严格压过反应系数 \(2(q-1)\)，最大值原理给出 \(|\Ric|\le Cr^{-e}\)，指数 \(0<e<1\)。而标量曲率满足 \(\partial_t R=\Delta R+2|\Ric|^2\)，其源 \(2|\Ric|^2\le Cr^{-2e}\) 恰可被 \(-C_2r^{\,2-2e}\) 型上解吸收（\(2-2e\in(0,2)\)），令正则化参数 \(\varepsilon\downarrow0\) 即得 \(R\le C_1\)；外部区域用 \(1-b_1\delta/r^2\) 型障碍处理。另一面，帽尺度引理给出 \(\phi(0,t)\le C\theta\to0\)，故极点切向截面曲率 \(j(0,t)=\phi(0,t)^{-2}\to\infty\)。标量有界与全曲率爆炸并存，反例成立，速率推论随之而来。

## 可信度与备注

主结果暂无形式化证明。族内三篇互相咬合：姊妹篇《Bounded scalar curvature and smooth extension of four-dimensional Ricci flow》证明闭四维流形上标量有界必可光滑延拓，说明本反例只能存在于足够高的维数；第三篇（静态树不等式）则是四维定理的关键外部输入。按 OpenAI 官方声明，未经形式化的结果可能有问题，请以社区核验为准。

{% endraw %}
