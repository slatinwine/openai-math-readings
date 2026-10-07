---
layout: default
title: "Hamiltonian Fixed Points Below the Stable Morse Number"
family: "347"
discipline: "Differential geometry"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | Hamiltonian Fixed Points Below the Stable Morse Number

> 结果族 347：Counterexamples to stable-Morse and strong Arnold fixed-point bounds　·　学科：Differential geometry　·　验证状态：暂无形式化证明，请以社区核验为准

## 一句话结论
本文构造出单连通闭凯勒流形（可取实维 \(1412\)）上的哈密顿微分同胚，其 \(318\,952\) 个非退化、轨道可缩的不动点比流形稳定 Morse 数 \(318\,968\) 恰少 \(16\) 个，首次推翻"非退化哈密顿不动点个数不低于稳定 Morse 数"的猜想；证明纯有限维，不依赖 Floer 理论。

## 问题背景
Arnold 不动点问题把哈密顿周期轨道与流形上函数的临界点理论联系起来：Conley–Zehnder 解决环面情形，Floer 用伪全纯曲线建立链复形并导出有理同调下界。一个更进一步的自然猜想是：流形的 Morse 型计数本身就是下界。Damian 发现普通 Morse 数与稳定 Morse 数（stable Morse number，允许附加二次变量稳定化后的最少临界点数）可以不同；Golovko 2020 年把稳定 Morse 版本写成明确猜想。Dimitroglou Rizell–Golovko 与 Pöder Balkeståhl 在辛面积类与第一陈类均消没于 \(\pi_2\) 的条件下证明了对 generic 哈密顿量成立——但这些假设排除了射影爆破流形。一般情形（尤其单连通凯勒世界）是否存在反例，是本结果族的起点，本文给出第一个。

## 主要结果
主定理：存在单连通闭凯勒（Kähler）流形 \((M,\omega)\) 与光滑 1-周期哈密顿量 \(H\)，使 \(\phi^1_H\) 的全部不动点非退化（nondegenerate），且
\[\#\Fix_0(\phi^1_H;H)=\#\Fix(\phi^1_H)=\SM(M)-16.\]
可取 \(\dim_\R M=1412\)，此时 \(\SM(M)=318\,968\)、\(\#\Fix(\phi^1_H)=318\,952\)。不动点轨道闭路皆可缩，故"只数可缩轨道"的版本与全不动点版本同时被否定。构造纯有限维：只用 Morse 理论与复几何爆破，不用 Floer 理论。

## 证明思路
第一步确立几何底线。对任何闭流形 \(W\)，\(\SM(W)\geq\lambda(W)=\sum_i r_i(W)+2\sum_i t_i(W)\)（\(t_i\) 为 \(\Tor H_i(W;\Z)\) 的最少生成元数）：把稳定化 Morse 函数截断在 \(W\times B_T\)、在侧边界取切向梯度式向量场，Morse 胶粘照常给出每个临界点一个胞腔的相对复形，收缩辅助坐标后其同调为 \(H_{*-d}(W;\Z)\)，Smith 正规形的秩不等式 \(\rank C_i\geq\rho_i+\tau_i+\tau_{i-1}\) 求和即得。Smale 的手柄定理又在维数足够高的单连通流形上给出恰有 \(\lambda(W)\) 个临界点的普通 Morse 函数，故 \(\SM=\Morse=\lambda\)。构造目标于是化为找 \(M\) 与其对合不动分支 \(C\)，使 \(\lambda(M)>4\lambda(C)\)。

第二步造挠。两个自由作用的商曲面 \(S_2,S_3\)（双椭圆曲面，bielliptic surface）在 \(H_1,H_2\) 上分别给出 \((\Z/2)^2\) 与 \(\Z/3\) 挠。\(X\) 由 \(\CP^N\)（\(N\geq704\)）沿两个不交中心逐次爆破而成：整爆破公式 \(H_i(\widehat A;\Z)\cong H_i(A;\Z)\oplus\bigoplus_{j=1}^{c-1}H_{i-2j}(Z;\Z)\) 保 Kähler 性与单连通性，并把中心挠原样搬入，得到逐度重数 \(a_j=2\)（2-素）与 \(q=(1,3,4,\ldots,4,3,1)\)（3-素，\(L=N-3\) 项）。

第三步造动力学。\(Y\) 是 \(\CP^1\times\CP^1\) 在四角 \(\{0,\infty\}\times\{0,\infty\}\) 的爆破；对角圆作用的半转 \(g_Y\) 是哈密顿对合（Hamiltonian involution），其不动集恰为 4 条例外直线。于是 \(g=\id\times g_Y\) 在 \(M=X\times Y\) 上有 4 个不动分支，均同构于 \(C=X\times\CP^1\)。把 \(C\) 上恰有 \(\lambda(C)\) 个临界点的 Morse 函数作 \(g\)-不变延拓再取小扰动 \(\psi^\epsilon\circ g\)：由 \((\psi^\epsilon\circ g)^2=\psi^{2\epsilon}\) 与 Lipschitz 型短周期引理，一切不动点被迫是不动分支上的平衡点，最终恰为 \(4\lambda(C)\) 个设计好的临界点；切向与法向的线性化论证保证全部非退化，单连通性保证轨道闭路可缩。

最后是决定性的组合算术：不同素数的挠可共享生成元，\(d\bigl((\Z/2)^a\oplus(\Z/3)^q\bigr)=\max(a,q)\)（中国剩余定理把 \(\Z/2\oplus\Z/3\) 配成 \(\Z/6\)）。乘 \(\CP^1\)、乘 \(Y\) 把逐度重数分别与 \((1,1)\)、\((1,6,1)\) 卷积。文章证明亏损只发生在重数序列的两端：令 \(c_j=\max(a_j,q_j)\)、\(S=\sum_j c_j=4N-18\)，则每个奇偶类上 \(C\) 与 \(M\) 的生成元总和分别为 \(2S-2\) 与 \(8S-4\)，而自由秩满足 \(b(M)=4b(C)\)，于是 \(\lambda(M)-4\lambda(C)=16\) 与 \(N\) 无关；代入 \(N=704\) 即得定理数值。文中还核对了 Bai–Xu 循环分次整 Floer 下界在此例中为 \(456N-2104\)、比不动点数少 \(32\)：反例不与任何已证下界冲突，恰落在整分度与循环分度的缝隙里。

## 可信度与备注
本文暂无形式化证明。它是族 347 的机制源头：姊妹篇之一把差额 \(16\) 放大为无界（\(16m\)、实维固定 \(22\)），另一篇则调节爆破中心使不动点数恰取等 Bai–Xu 循环整下界而稳定 Morse 界仍差 \(32\)；三篇共享双椭圆曲面、整爆破公式与"四例外线对合"三大部件，互相印证。据族内概述，同族还有用非平凡基本群构造的 12 维普通 Morse 界反例，以及复三维二次超曲面上仅 3 个不动点的 Arnold 型反例。按 OpenAI 官方声明，未经形式化的结果可能有问题，请以社区核验为准。

{% endraw %}
