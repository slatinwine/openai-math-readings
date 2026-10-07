---
layout: default
title: "Cylinder loop weights and planar nesting"
family: "237"
discipline: "Probability and statistical mechanics"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | Cylinder loop weights and planar nesting

> 结果族 237：The three-quarter exponent for honeycomb self-avoiding walk　·　学科：Probability and statistical mechanics　·　验证状态：暂无形式化证明，请以社区核验为准

## 一句话结论

对任意固定环路逸度（loop fugacity）\(\chi>0\)，确定了临界蜂窝柱面上"分隔两个标记点的不交多边形族"配分函数的增长指数 \(\tau(\chi)\)；\(\chi=2\) 时为 \(1/6\)，对应平面嵌套指数 \(1/12\)，严格证明了 Gamsa–Cardy 的库仑气预言。

## 问题背景

临界活性 \(\rho=(2+\sqrt2)^{-1/2}\) 固定了每个蜂窝多边形的权重，但围绕一点的不交多边形嵌套族（nest）的配分函数需要对所有空间尺度同时求和，其增长长久以来只是预言。Gamsa 与 Cardy 2006 年在高斯场标度描述的假设下，从库仑气（Coulomb gas）方法导出电 exponent：\(\chi=2\cos\eta\)（\(0<\chi\le2\)）时标度维数 \(x=\eta^2/(3\pi^2)-1/12\)，两点幂 \(-2x\) 即本文的 \(\tau(\chi)\)；Cardy 的环带计算给出类似的径向幂。这些论证依赖未经证明的标度极限图像，且缺少有限格点的归一化。本文在平衡柱面（balanced cylinder）几何上严格完成这一纲领：把平面按周期 \(iN\sqrt3/2\)（\(N=2m\)）作商，标记 \(0\) 与 \(me^{2\pi i/3}\) 两点，紧化柱面两端得球面，称多边形"分隔标记"若两标记落在其余集的两个不同分支。

## 主要结果

对分隔多边形族（含空族）赋权 \(\prod_P \chi\rho^{|P|}\)，定理 2.1 证明：沿偶数 \(N\)，

\[Z_N(\chi)=N^{\tau(\chi)+o(1)},\qquad \tau(\chi)=\begin{cases}\frac16-\frac{2}{3\pi^2}\bigl(\arccos(\chi/2)\bigr)^2,&0<\chi\le2,\\[4pt] \frac16+\frac{2}{3\pi^2}\bigl(\operatorname{arcosh}(\chi/2)\bigr)^2,&\chi\ge2.\end{cases}\]

平面版本：围绕一个固定面心、直径 \(\le r\) 的嵌套质量 \(P_\chi(r)\) 满足双侧比较 \(P_\chi(c_0N)^2\le Z_N(\chi)\le C\,P_\chi(c_0N)^2\)，故 \(P_\chi(r)=r^{\tau(\chi)/2+o(1)}\)——平方来自几何：剥去本质（缠绕）多边形与大可收缩多边形只花有界因子，剩下的分解为靠近两个标记的独立小嵌套。特别地 \(Z_N(2)=N^{1/6+o(1)}\)、\(P_2(r)=r^{1/12+o(1)}\)，带中央面心的嵌套质量 \(S_k=k^{1/12+o(1)}\)。另有均匀计数界 \(w_N(a)\le\exp(C\log N-ca^2/\log N)\)（\(w_N(a)\) 为恰含 \(a\) 个分隔多边形的非归一质量），以及带内路径长度：原始一阶矩 \(\sum\rho^{n}n\le h^{13/12+o(1)}\)，条件于到达底部 \(h/4\) 带的顶部的期望长度为 \(h^{4/3+o(1)}\)——两指数之差恰源于条件事件本身 \(\asymp h^{-1/4}\) 的质量。

## 证明思路

路线分两段：先走代数与分析得到柱面指数，再用独立的压力估计回到平面。代数侧：由配套论文的多项式开带态构造柱面真空（vacuum，记录割一侧路径对端口的配对），两半柱面态按分隔规则收缩恰得 \(Z_N\)；写 \(\chi=2\cos\eta\)，有限围道变形把分子表为带相位 \(e^{i\eta M}\) 的粒子积分，不平衡整数 \(M\) 固定两组基本粒子数 \(m\mp M\)。分析侧：把主粒子群中心化到平均密度 \(m\varrho(u)\)，在距离 \(O(\log N)\) 处设墙，涨落的实二次能量控制失衡与远粒子；以 Legendre 正交多项式系综为正参照律，减去其对数交互以消除对角奇性。\(\log N\) 的系数逐项记账：形变行列式贡献 \(7/8\)、两个参照配分质量贡献 \(-1/2\)、标量真空分母贡献 \(-5/24\)，合计恰为 \(1/6\)；要得到 \(\eta\) 的二次项，必须在积分中保留相位 \(e^{i\eta M}\)——通过真实移动粒子并计算雅可比、再对整数维积分作全纯插值，把相位转化为实作用上的二次贡献，最终得上界包络 \(\log|Z_N(2\cos\eta)|/\log N\le\frac16-\frac{2}{3\pi^2}\operatorname{Re}(\eta^2)+o(1)\)。匹配下界不走逐扇区估计：锚点 \(\eta=\pi/2\) 处 \(Z_N(0)=1\) 精确成立，上界使 \(v_N=\mathcal H+\epsilon_N-u_N\) 为非负上调和函数，经圆盘链的平均值不等式把近饱和性从锚点传播到任意圆盘，再用系数非负性 \(Z_N(2)\ge|Z_N(2\cos\eta_N)|\) 把复点近等式转化为正实逸度处的下界。平面侧用两条压力估计：环形转移中本质环权的第一、二阶压力导数控制其总质量与横向跨度矩；开带中全部环权的一阶导数在 \(N\) 上仿射（误差 \(O(N^{-1})\)），推出大多边形直径尾 \(\sum_{\diam P>r}\rho^{|P|}\le C(1+r)^{-2}\)，两条合起来完成 \(Z_N\asymp P_\chi^2\) 的比较与长度—嵌套恒等式。

## 可信度与备注

本文主结果暂无 Lean 形式化证明；按 OpenAI 官方声明，未经形式化的结果可能有问题，请以社区核验为准。开带多项式态等关键输入来自同族配套论文（文中引作 [StripCompanion]，含临界带穿越定理），与姊妹篇《Radial transfer estimates…》的多边形直径尾 \(-2\)（本文亦独立证得同阶估计）及《Critical honeycomb chords…》的 \(4/3\) 长度定律互相衔接，是族 237 中负责"嵌套与环权"一侧的支柱。

{% endraw %}
