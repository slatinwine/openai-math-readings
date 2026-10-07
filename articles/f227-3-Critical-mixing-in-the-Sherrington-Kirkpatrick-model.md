---
layout: default
title: "Critical mixing in the Sherrington–Kirkpatrick model"
family: "227"
discipline: "Probability and statistical mechanics"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | Critical mixing in the Sherrington–Kirkpatrick model

> 结果族 227：Critical SK autocorrelation processes and dynamics across the temperature transition　·　学科：Probability and statistical mechanics　·　验证状态：暂无形式化证明，请以社区核验为准

## 一句话结论
论文定出 SK 模型临界点 \(\beta=1\) 处最坏初态混合时间的精确指数：连续时间（每站点更新率 1）为 \(n^{2/3+o(1)}\)，离散尝试更新为 \(n^{5/3+o(1)}\)；同一指数还控制松弛时间与经典对数 Sobolev 常数，把严格混合界从高温区域推进到临界温度本身。

## 问题背景
SK 模型（Sherrington–Kirkpatrick model）的平衡态在临界逆温度 \(\beta=1\) 处发生自旋玻璃转变，而动力学在临界点附近如何弛豫是老问题：Kirkpatrick–Sherrington 早在 1978 年就用线性化平均场与蒙特卡洛研究单自旋 Glauber 弛豫，Sompolinsky–Zippelius（1982）发展了软自旋 Langevin 图像；数值上 Billoire–Campbell（2011）测得平衡自相关符合标度形式 \(q_c(n,t)\sim n^{-1/3}F(t/n^{2/3})\)，暗示 \(n^{2/3}\) 时标。严格结果此前都限于高温相：Bauerschmidt–Bodineau 的对数 Sobolev 不等式、Eldan–Koehler–Zeitouni 的谱判据（\(\beta<1/4\)），Wang 与 Boban–Li–Oveis Gharan 推到 \(\beta<1/2\) 及其邻域，谱隙姊妹篇覆盖每个固定 \(\beta<1\)——但都无法取极限到 \(\beta=1\)。临界姊妹篇定出线性观测量与"实现初态"的慢尺度为 \(n^{2/3}\)，本文补上与之匹配的上界，从而确定指数。

## 主要结果
定理 1.1：对每个固定 \(\varepsilon\in(0,1/2)\)，在无序变量（disorder）概率意义下
\[t_{\mathrm{mix},J}(\varepsilon)=n^{2/3+o(1)},\quad k_{\mathrm{mix},J}(\varepsilon)=n^{5/3+o(1)},\quad R_J=n^{2/3+o(1)},\quad C_{\mathrm{LS},J}=n^{2/3+o(1)},\]
其中 \(X_n=n^{a+o(1)}\) 意为对任意 \(\delta>0\) 都有 \(\mathbb P\{n^{a-\delta}\le X_n\le n^{a+\delta}\}\to1\)。\(t_{\mathrm{mix}}\) 是生成元 \(\mathcal L_J=\sum_i(Q_i-I)\)（每站点率一）的最坏初态混合时间，\(k_{\mathrm{mix}}\) 是每次均匀选点尝试更新的步数，\(R_J\) 是松弛时间（relaxation time，即 Poincaré 常数、谱隙倒数），\(C_{\mathrm{LS},J}\) 是经典对数 Sobolev 不等式（logarithmic Sobolev inequality）常数。推论还给出熵产生常数 \(C_{\mathrm{EP},J}=n^{2/3+o(1)}\)：对任意初始律 \(\nu\) 有 \(\mathrm{KL}(\nu e^{t\mathcal L_J}\Vert\mu_J)\le e^{-t/C_{\mathrm{EP},J}}\mathrm{KL}(\nu\Vert\mu_J)\)。下界来自姊妹篇：线性 Rayleigh 商 \(R_{\mathrm{lin},J}=n^{2/3+o(1)}\)，以及"实现初态"结论——凡 \(t_n=o(n^{2/3})\)，Gibbs 质量中距离仍超 \(1/4\) 的初态占比趋于 1。本文只断言指数，不断言存在 cutoff（突变式混合）、混合窗口或领先常数。

## 证明思路
贡献全在上界，且给出两条独立路线，共同锚定在 GOE 谱边缘几何上：极限谱密度在边缘 2 附近按到边缘距离的平方根衰减，故宽 \(u\) 的边缘窗口约含 \(nu^{3/2}\) 个维度；球面自旋律可视为条件高斯，其预解式把边缘几何直接翻译为协方差估计。路线一（各向同性观测）：用高斯随机定位（Gaussian stochastic localization）在精度 \(s\)（记 \(r=\sqrt s\)，\(k=ns^{3/2}\)）下逐步观测自旋，先经 Comets 型与 Du–Huang 的临界态立方–球面比较建立参照；再对 TAP 型方程 \(y+(1-q)m-Jm=h_s\)、\(m=\tanh y\)、\(q=\|m\|^2/n\) 做条件 Kac–Rice 分析，条件矩阵计算分离出三个特殊方向（\(m\)、\(\mathbf 1\) 的正交分量、根场残量），其余方向留 Haar 旋转，四项符号组合 \(\mathcal R_{pp}-\mathcal R_{pg_0}-\mathcal R_{g_0p}+\mathcal R_{g_0g_0}\) 相消公共误差，得到多数定向满足协方差 \(\|\Sigma_s\|\le(1+\epsilon)/s\)；沿观测路径做放大（向后方差传输加集中），多对数窗口改用无约束旋转比较，底层尺度用带交错求和的有限 replicas 展开最后化为统一的支撑轮廓（support profile）：对一切支撑质量 \(p\le\frac12\) 的检验函数 \(f\)，\(\D_J(f)\ge c\,n^{-2/3-\omega}\log(1/p)\,\mu_J(f^2)\)。路线二（谱帽）：只观测软边缘方向，\(B_p=(p^2-d)_+\)，活跃帽秩约 \(np^3\)；关键增益是"径向亏损"——位势 \(\phi_p=\log Z_{J_p}(h)\) 的 Hessian 相对冻结预解式的修正 \(p^2(K_p-R_p)\) 在径向有 \(\le-0.30\) 的负项；精确高斯卷积把子尺度位势用父尺度表出，Brascamp–Lieb 上界与 Fisher 信息变分下界夹逼，配合仍隐藏特征标架的 Haar 压缩，从大帽向小帽归纳（初始化靠小场 TAP 展开与辅助位势），降至 \(np^3\asymp\sqrt{\log n}\)，再经熵保持与分层论证得经典对数 Sobolev 不等式 \(\Ent_{\mu_J}(f^2)\le n^{2/3+\rho}\D_J(f)\)。最后动力学转化：支撑轮廓经截断机制（密度 \(L^2\) 范数大时 \(V'=-2\D\) 指数下降、之后靠谱隙收尾），对数 Sobolev 经超压缩性（hypercontractivity）平滑；由 \(\mathcal L_J=n(P_J-I)\) 保持两种时钟间的因子 \(n\)，最小 Gibbs 质量 \(\ge\exp(-(3+\log2)n)\)；下界用最慢特征函数测试，\(\mathrm{TV}\ge\frac12e^{-t/R_J}\)。两条路线参数独立，结论互为印证。

## 可信度与备注
主结果暂无 Lean 形式化证明；上界依赖两份姊妹篇（临界伙伴的线性/实现初态下界、高温谱隙伙伴的 TAP 型场方程与字词估计工具，后者在 \(j=1\) 处仅在验证假设后使用，并非取 \(\beta\uparrow1\) 极限），请以社区核验为准。本篇与低温典型初态篇、障碍篇共同刻画跨温度转移的混合行为。按 OpenAI 官方声明，未经形式化的结果可能存在问题。

{% endraw %}
