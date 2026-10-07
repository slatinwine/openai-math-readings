---
layout: default
title: "Interior regularity of planar Mumford–Shah minimizers"
family: "366"
discipline: "Partial differential equations"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | Interior regularity of planar Mumford–Shah minimizers

> 结果族 366：The planar Mumford–Shah regularity conjecture and local weak-<i>L</i><sup>4</sup> gradient bounds　·　学科：Partial differential equations　·　验证状态：暂无形式化证明，请以社区核验为准

## 一句话结论

证明了二维 Mumford–Shah 猜想的内部正则性断言：对具界保真数据的既约绝对极小化子，裂缝集在内部每点附近只能是 \(C^{1,\alpha}\) 弧、以该点为端点的弧，或三条两两成 \(120^\circ\) 的弧；任一紧区域只与有限个整体连通分支相交，并附带弱 \(L^4\) 梯度估计。

## 问题背景

1989 年 Mumford 与 Shah 为图像分割提出泛函：在有界区域 \(\Omega\) 上极小化
\[\mathcal F_g(u,K)=\int_{\Omega\setminus K}|\nabla u|^2\,dx+\mathcal H^1(K)+\int_\Omega|u-g|^2\,dx,\]
其中 \(u\) 是分段光滑的图像重构，闭集 \(K\) 是允许 \(u\) 跳跃的边缘，三项分别惩罚区域内振荡、边缘总长度与偏离观测数据 \(g\)（保真项，fidelity term）。正则性猜想问：极小化本身是否迫使 \(K\) 在内部由正则弧组成，奇点只有自由端点与 \(120^\circ\) 三叉点？这是自由不连续问题（free discontinuity problem）的核心样本：设定只假设一维 Hausdorff 测度 \(\mathcal H^1(K)<\infty\)，不设任何可微性，连通分支还可能无限堆积。三十余年来，Bonnet 的爆破与单调性方法、David 与 Ambrosio–Fusco–Pallara 的正则弧理论、Bonnet–David 的裂缝尖端（crack tip）整体极小性、David–Léger 的整体分类逐步推进，但一般情形始终卡在爆破极限中可能残留的"有界分支"这一最后障碍上。

## 主要结果

定理 1.1：设 \((u,K)\) 是 \(\mathcal F_g\) 的既约绝对极小化子——"绝对极小化子"（absolute minimizer）指任何紧支撑的比较改变都不能降低局部能量，"既约"（reduced）指 \(K=\operatorname{spt}_\Omega(\mathcal H^1\llcorner K)\)，即不含零长度赘余部分——且 \(g\in L^\infty(\Omega)\)。则每个 \(x\in K\) 有邻域，使 \(K\) 在其中是三种局部模型之一：一条嵌入弧（embedded arc）而 \(x\) 在其内部；一条以 \(x\) 为端点的弧；或三条仅在 \(x\) 相遇、两两夹角 \(120^\circ\) 的弧，弧一律是 \(C^{1,\alpha}\) 的。此外，对每个 \(U\Subset\Omega\)，与 \(U\) 相交的 \(K\) 的整体连通分支（global connected components）只有有限多个。推论进一步给出弱 \(L^4\)（weak-\(L^4\)，即 Lorentz 空间 \(L^{4,\infty}\)）梯度界：水平集 \(\{|\nabla u|>t\}\) 的面积不超过 \(C_Ut^{-4}\)，因而 \(\nabla u\in L^p_{\mathrm{loc}}\) 对一切 \(0<p<4\) 成立；指数 \(4\) 恰对应裂缝尖端剖面 \(r^{1/2}\sin(\theta/2)\) 的 \(r^{-1/2}\) 梯度奇性。

## 证明思路

证明分五步。先归约（第 2 节）：截断比较给出 \(u\) 的局部有界性；用有限球覆盖把 \(u\) 纳入 \(SBV\)，其跳跃集（jump set）\(J_u\) 天然可求长；再在边界只与 \(K\) 交有限点的"好圆盘"上，用带光滑边界数据的 Dirichlet 替换作比较，让边界误差弧长趋于零，逼出 \(\mathcal H^1(K\setminus J_u)=0\)，故既约的 \(K\) 恰是 \(J_u\) 的闭包，从而可求长（rectifiable）。

再爆破（第 3 节）：在 \(x\in K\) 处伸缩 \((K-x)/r_j\)，取整体广义极限（generalized limit）\((v,H,\{p_{kl}\})\)，极限数据还记录各余分支上加性常数的极限。De Lellis–Focardi 专著的紧致性与刚性定理把整体分类归结为唯一缺口：当 \(\mathbb R^2\setminus H\) 连通时，须排除 \(H\) 的有界分支。第 4 节用"分支是开闭邻域之交"的链式论证，把有界分支扩成与余部 \(B=H\setminus A\) 有正距离、长度有限的紧块 \(A\)。

核心是第 5 节排除 \(A\)：此时 \((v,H)\) 是全平面零保真能量 \(E_0\) 的绝对极小化子。先把 \(\nabla v\) 一分为二：取截断 \(\chi\) 令 \(h=\chi v\)，把 \(\nabla h\) 向整平面梯度场作正交投影（Hodge 型）得位势 \(\phi\)，置 \(F=h-\phi\)、\(f=(1-\chi)v+\phi\)，则 \(f\) 穿过 \(A\) 调和，\(F\) 的跳跃只落在 \(A\) 上且以 \(O(|x|^{-1})\) 衰减。再把 \(A\) 与 \(F\) 一起平移：长度与 \(F\) 自身能量都不变，远处用显式截断把比较函数缝回原状，还可叠加携带独立跳跃变差 \(\sigma P_t\) 的场。极小性化为交互能 \(I_p(t)=\int G\cdot p_t\)（其中 \(G=\nabla f\)）关于 \(t\) 与 \(\sigma\) 的二次不等式。由 \(\operatorname{curl}p\) 集中于 \(A\) 且 \(\Delta p=\nabla^\perp\operatorname{curl}p\)，\(I_p\) 关于平移参数 \(t\) 调和——这是 Earnshaw"无稳定平衡"静电类比的严格化。取 \(\sigma=0\) 知 \(I_p\) 在原点取最小值，极小值原理逼它为常数；二次部分对一切 \(\sigma\) 非负，又逼出交互恒等式。最后在 \(A\) 的一段正则弧上取迹差为任意 \(\beta\) 的变差，交互能恰化为 \(\nabla f\) 的法向通量；它对一切平移不变，逼 \(\nabla f\) 的某方向导数在弧旁恒定，二维中这强迫 \(f\) 局部仿射，唯一延拓把它推广到整个余集；能量增长估计 \(\int_{B_R}|G|^2\le C(1+R)\) 再逼 \(\nabla f=0\)，于是 \(v\) 为常数——删去 \(A\) 就白省长度 \(\mathcal H^1(A)>0\)，与极小性矛盾。

最后拼装（第 6 节）：分类定理给出爆破极限只能是直线、半直线或 \(120^\circ\) 三叉射线；\(\varepsilon\)-正则性（epsilon regularity）把这些模型传回原极小化子，得每点的局部模型；用有限个"整盘交 \(K\) 连通"的正则圆盘覆盖紧集，即得连通分支有限性；无非正则点这一事实经 De Lellis–Focardi 等价定理导出弱 \(L^4\) 梯度估计。

## 可信度与备注

本篇标注暂无形式化证明；论文是自足的数学论证，关键外部输入取自 De Lellis–Focardi 专著（2025 年 1 月作者版）的紧致性、\(\varepsilon\)-正则性、整体估计与弱 \(L^4\) 等价定理，以及 David–Léger 的整体分类。与 Deangelis 的平行工作互为印证：两者都用整平面投影和正则弧上可独立指定单侧迹的值变差，Deangelis 走松弛第二变分与全纯刚性，本文改用有限平移加显式截断得到标量调和交互能，路线独立而结论一致。按 OpenAI 官方声明，未经形式化的结果可能有问题，最终认定请以社区核验为准。

{% endraw %}
