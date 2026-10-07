---
layout: default
title: "Finite triangular approximation of radial sweeps"
family: "100"
discipline: "Convex and metric geometry"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | Finite triangular approximation of radial sweeps

> 结果族 100：Cylinder coverings below the half-area bound　·　学科：Convex and metric geometry　·　验证状态：暂无形式化证明，请以社区核验为准

## 一句话结论
本文证明满足对齐条件的径向扫掠集可用"每区间一个三角形底圆柱"的有限覆盖逼近，总底面积收敛于加权面积；据此构造出总底面积严格小于 \(A_{\min}(K)/2\) 的正四面体有限覆盖，同时否定 Bang 的半面积界与方向归一化的一维余维圆柱覆盖猜想。

## 问题背景
三维中的圆柱（cylinder）指集合 \(B+\R u\)：\(u\) 为单位方向，\(B\subset u^\perp\) 是垂平面上的可测底集，覆盖代价取底面积 \(\area(B)\)。对凸体（convex body）\(K\)，记 \(A_{\min}(K)=\min_{\norm u=1}\area(\pi_{u^\perp}K)\) 为最小正交投影面积。源自 Bang、经 Bezdek 问题 3.1 转述的半面积问题问：\(K\) 的任何有限圆柱覆盖，总代价是否至少为 \(A_{\min}(K)/2\)？正四面体上两根沿对棱方向的圆柱恰好达到此值，长期被视为最优。更强的 Bezdek–Khan 一维余维圆柱覆盖猜想（1-Codimensional Cylinder Covering Conjecture）断言方向归一化代价 \(\sum_i\area(B_i)/\area(\pi_{u_i^\perp}K)\ge 1/2\)，它蕴含半面积界；此前最好的下界只有 Bezdek–Litvak 对三维凸体的 \(1/3\)。这些问题是木板覆盖（plank covering）从板宽到底面积的自然延伸，症结在于：让圆柱方向随位置逐段变化，能否省出面积？

## 主要结果
**定理 1.1（径向扫掠的有限三角逼近）**：对径向扫掠集（radial sweep）
\[\mathcal S=\{p_0+\rho(a+tb)+s(e+w(t)):\ t\in J,\ 0\le\rho\le R(t),\ |s|\le L\},\]
若方向扰动满足对齐条件（alignment condition）\(w'(t)=\lambda(t)(a+tb)\)，则对 \(J\) 的任意带标签分割（tagged partition）\(\alpha=t_0<\cdots<t_N=\beta\) 与任意标签 \(c_i\)，存在 \(N\) 个圆柱覆盖 \(\mathcal S\)：第 \(i\) 个的轴平行于冻结方向 \(e+w(c_i)\)，底为非退化紧三角形；当网格 \(\delta\to 0\) 时，总底面积一致收敛于加权面积
\[\mathcal A=\kappa\int_\alpha^\beta\frac{R(t)^2}{2\sqrt{1+\norm{w(t)}^2}}\,dt,\qquad \kappa=|\det_P(a,b)|,\]
且把底换成各段实际扫掠的垂直投影时，极限相同。

**推论 1.2（四面体反例）**：任何正四面体 \(K\subset\R^3\) 都有有限圆柱覆盖 \(B_i+\R u_i\)（\(B_i\) 为非退化紧三角形底），使得
\[\sum_i\area(B_i)<\frac{A_{\min}(K)}2,\qquad \sum_i\frac{\area(B_i)}{\area(\pi_{u_i^\perp}K)}<\frac12 .\]
半面积问题与三维方向归一化猜想由此同时得到否定回答。

## 证明思路
**第一步：冻结方向，给每个区间包一个三角形（第 2 节）。** 在区间 \(I\) 上把方向冻结为 \(v_I=e+w(c_I)\)，将扫掠点沿 \(v_I\) 平行移回平面 \(P\)：径向坐标 \(u=\rho+s\int_{c_I}^t\lambda\) 可游动 \(O(d_I)\) 甚至变负，而横向偏差 \(|v-m_Iu|\) 只是区间长度 \(d_I\) 的二阶小量——这正是对齐条件的几何内核：方向的一阶变化恰好沿既有射线推动截距，可被径向坐标吸收。于是取三角形 \(T_I\)：径向范围放宽为 \(-Cd_I\le u\le R_I+Ad_I\)，横向半宽取 \(\frac{d_I}2(u+Cd_I)\)，在负端收拢为零，从而同时包住横向误差与负向"领子"（negative collar），且 \(R_I=0\) 时仍非退化。\(T_I\) 沿 \(v_I\) 投影到垂平面仍是非退化三角形，柱体 \(T_I+\R v_I\) 覆盖不变；精确面积公式中领部只添 \(O(d_I^2)\)，而 \(\sum_I d_I^2\le\delta(\beta-\alpha)\to 0\)，故总面积收敛于 \(\mathcal A\)。再以 \(s=0\) 截面的径向扇形（面元 \(\kappa\rho\,d\rho\,dt\)）提供匹配下界，两面夹逼出"实际投影底"的同一极限。

**第二步：四面体上两片重叠扫掠（第 3 节）。** 先由 Cauchy 投影公式 \(\area(\pi_{u^\perp}K)=\frac12\sum_jS_j|n_j\cdot u|\) 算得 \(A_{\min}(K)=4\sqrt2\)，经典的两对棱圆柱恰达一半。上扫掠取方向场 \((1,-\eps G(q),\eps\sqrt2\,q)\)，其中 \(G(q)=\frac{1+q^2}2\) 使 \(G'(q)=q\)，对齐条件以 \(\lambda=-\eps\) 精确成立；径向帽 \(R_\eps(q)=1+\eps^2(H(q)+5\eps)\)，\(H(q)=\frac{q^2+q^4}2\)。覆盖论证用一条穿越引理（\(C^1\) 函数过中值可在导数非负处取到）：\(K\) 中每点都被两片扫掠各一条线段穿过；若两条线段的径向参数同时越界，一串一致估计最终逼出 \((p^2+q^2)/2+p^2q^2\le H(p)+H(q)\)，而帽中三次填充 \(10\eps\) 恰好压过累积误差 \(9\eps\)，矛盾。代价展开给出 \(I(\eps)=1-\frac{\eps^2}{30}+10\eps^3+O(\eps^4)<1\)：方向倾斜带来的投影二阶节省（\(-\eps^2/30\)）胜过保证覆盖的三次填充（\(10\eps^3\)）。先固定小 \(\eps\)，再取足够细的分割，即得总代价严格低于 \(A_{\min}(K)/2\) 的有限覆盖；又因每个方向的投影面积都 \(\ge A_{\min}(K)\)，归一化代价随之 \(<1/2\)。

**第三步：备选的"短梁"路线（第 4 节）。** 把两条梁（beam）各缩短 \(a\)，中间剩余斜带改用水平矩形底圆柱覆盖；一阶节省与带的代价精确抵消，总代价 \(C(a)=4-\bigl(\frac{\sqrt2}2-\frac{19}{30}\bigr)a^2+O(a^3)\) 的二阶项为负，同样严格省钱，与主构造互相印证。

## 可信度与备注
本篇任务标注为未形式化，主结果暂无 Lean 证明，请以社区核验为准；不过全文是初等显式构造——四面体坐标、覆盖不等式与代价展开均可逐步复算，附录还给出有限包裹的显式公式与多边形备选。它与结果族 100 的姊妹篇互相支撑：本文的定理 1.1 直接保证"指定标签、每区间一个圆柱、三角形底"，同伴文章（关于直纹集的 RuledApproximation2026）把同类逼近纳入更一般的框架。按 OpenAI 官方声明，未经形式化的结果可能存在问题，读者引用前宜核对关键不等式。

{% endraw %}
