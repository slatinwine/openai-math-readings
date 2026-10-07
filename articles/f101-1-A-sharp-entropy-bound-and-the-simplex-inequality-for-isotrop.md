---
layout: default
title: "A sharp entropy bound and the simplex inequality for isotropic constants"
family: "101"
discipline: "Convex and metric geometry"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | A sharp entropy bound and the simplex inequality for isotropic constants

> 结果族 101：The sharp simplex conjecture for isotropic constants　·　学科：Convex and metric geometry　·　验证状态：暂无形式化证明，请以社区核验为准

## 一句话结论

证明强迷向常数猜想：每个维度中单纯形（simplex）都是凸体迷向常数的唯一最大值点；同时建立对数凹密度的锐熵下界 `@@M@@h(f)\ge m+\tfrac12\log\det\Cov(f)@@`，等号恰为一侧指数律乘积的可逆仿射像。

## 问题背景

凸体（convex body）`@@M@@K\subset\R^n@@` 的迷向常数（isotropic constant）为 `@@M@@L_K=(\det\Sigma_K/|K|^2)^{1/(2n)}@@`，`@@M@@\Sigma_K@@` 是 `@@M@@K@@` 上均匀分布的协方差矩阵，且 `@@M@@L_K@@` 仿射不变。Bourgain 在 1986 年提出的切片问题（slicing problem）问：`@@M@@L_K@@` 是否有与维数无关的上界？经随机定位（stochastic localization）等工作，Klartag–Lehec 最终得到维数无关的界。但"强迷向常数猜想"问的是锐形式：每维中是否恰由单纯形最大化 `@@M@@L_K@@`，极值常数与极值体是什么。二维已解决（Campi–Colesanti–Gronchi、Saroglou），高维仅有 Rademacher 等部分限制；本文对所有凸体证明完整不等式并分类全部等号。

## 主要结果

**定理一（单纯形不等式）**：每个整数 `@@M@@n\ge1@@`、每个凸体 `@@M@@K\subset\R^n@@` 都满足

`@@M@@DL_K\le\frac{(n!)^{1/n}}{(n+1)^{(n+1)/(2n)}\sqrt{n+2}},@@`

等号当且仅当 `@@M@@K@@` 是单纯形，右端即正则单纯形的取值。由 Klartag 的蕴含关系，它同时给出非对称 Mahler 不等式（nonsymmetric Mahler inequality）`@@M@@|K|\,|K^\circ|\ge\frac{(n+1)^{n+1}}{(n!)^2}@@`，`@@M@@K^\circ@@` 为极体（polar body）。

**定理二（锐熵界）**：`@@M@@\R^m@@` 上任意对数凹（log-concave）概率密度 `@@M@@f@@` 的微分熵（differential entropy）满足

`@@M@@Dh(f)\ge m+\tfrac12\log\det\Cov(f),@@`

等号当且仅当 `@@M@@f@@` 几乎处处是 `@@M@@M(E_1,\ldots,E_m)^{\mathsf T}+b@@` 的密度：`@@M@@M@@` 可逆、`@@M@@b\in\R^m@@`、`@@M@@E_i@@` 独立且服从密度 `@@M@@e^{-u}\mathbf 1_{\{u\ge0\}}@@`。该命题与单纯形界跨维等价（Fradelizi–Marín Sola），一维已证明（Melbourne–Nayar–Roberto）；本文在每个维度给出不等式与完整等号分类。

## 证明思路

证明先证熵不等式，再化归到凸体。设 `@@M@@f=e^{-V}@@`，`@@M@@V@@` 光滑且 `@@M@@0<c_-I\le D^2V\le c_+I@@`。Brenier 定理给出高斯到目标的梯度传输 `@@M@@\nabla\phi@@`，Caffarelli 理论提供 Jacobian `@@M@@J=D^2\phi@@` 的谱上下界；以一维高斯到均值一指数律的传输 `@@M@@t(a)=-\log\Phi(-a)@@`（`@@M@@q=t'@@`）为标量模型，由谱演算定义矩阵场 `@@M@@A=q^{-1}(J)@@`。

先由同伦与 Brouwer 度的紧性论证选取目标仿射坐标，使非线性条件 `@@M@@\E A=0@@` 成立——普通协方差规范化做不到。再对二阶传输方程求导并用 `@@M@@V@@` 的凸性得能量估计，其中保留特征值分离（eigenvalue separation）盈余 `@@M@@\mathcal C@@`，以防后续对不可交换矩阵函数求导失控。然后按高斯混沌（Gaussian chaos）分解 `@@M@@A=\sum_r x_rX_r+Y@@`：线性部分无 Poincaré 能量盈余，改用其常矩阵 `@@M@@X_r@@` 构造 `@@M@@\log\det\Cov@@` 的支撑平面；高阶混沌 `@@M@@Y@@` 提供严格谱隙。熵亏由 Helffer–Sjöstrand 协方差表示写成两部分之和。

收尾时，交换子平方控制非交换矩阵项；两条精确有理常数的标量不等式分别吸收支撑平面的代价，并把均差（divided difference）项的非对角误差记账到 `@@M@@\mathcal C@@` 上抵消。于是熵亏被一个在每个高阶混沌上非正的二次式控制，并留下严格余项 `@@M@@\frac1{500}\E\tr(Y^2)+\frac1{1000}\sum_i\omega(\lambda_i)@@`，把 `@@M@@B=\sum_rX_r^2@@` 的特征值逼向 `@@M@@1@@`。

再以 Moreau 包络加磨光逼近一般对数凹位势，去掉光滑性。等号分类靠刚性：余项趋零迫使 `@@M@@A_j@@` 在高斯 `@@M@@L^2@@` 中收敛到线性场且 `@@M@@\sum_rX_r^2=I@@`，再恢复映射收敛；若线性场的 `@@M@@q(A)@@` 是某 Jacobian，混合导数对称性与 `@@M@@q@@` 在原点的幂级数（只需 `@@M@@q'(0),q''(0)\ne0@@`）强制系数矩阵两两交换，同时对角化后得独立的一维指数传输。

最后，在锥 `@@M@@\mathcal C_K=\{(tx,t):x\in K,t\ge0\}@@` 上取指数密度 `@@M@@f_K=\frac{e^{-t}}{n!\,|K|}\mathbf 1_{\mathcal C_K}@@`，算得 `@@M@@h(f_K)=n+1+\log(n!|K|)@@`、`@@M@@\det\Cov(f_K)=(n+1)^{n+1}(n+2)^n\det\Sigma_K@@`，故 `@@M@@n+1@@` 维熵不等式逐字翻译为 `@@M@@L_K@@` 的单纯形界；等号时该锥必为仿射正卦限，高度 1 截面给出 `@@M@@n+1@@` 个仿射无关点，故 `@@M@@K@@` 是单纯形，反之亦然。

## 可信度与备注

主结果尚无 Lean 形式化证明；论文数值常数均为精确有理数，附录 certificate 的验证原则上机器可复核，但整体仍需社区核验。本文是结果族 101 的核心手稿，族内两项宣称都在本篇证明；所依赖的等价性与锥化归等均为已发表文献，互相印证。按 OpenAI 官方声明，未经形式化的结果可能有问题。

{% endraw %}
