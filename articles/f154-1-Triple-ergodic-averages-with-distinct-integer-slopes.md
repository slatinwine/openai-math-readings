---
layout: default
title: "Triple ergodic averages with distinct integer slopes"
family: "154"
discipline: "Dynamical systems and ergodic theory"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | Triple ergodic averages with distinct integer slopes

> 结果族 154：Pointwise multiple ergodic averages for mixing transformations　·　学科：Dynamical systems and ergodic theory　·　验证状态：暂无形式化证明，请以社区核验为准

## 一句话结论

在仅假设混合的条件下，证明沿任意三个两两不同的非零整数斜率（可正可负）的三重遍历平均几乎处处收敛到积分之积；核心是把三线性 Hilbert 变换的局部四线性估计推广到任意系数配置。

## 问题背景

多重遍历平均的逐点收敛是遍历理论的著名难题：Bourgain 双重递归定理之后，三重情形在一般系统上悬而未决。弱混合情形由 Bergelson 的弱混合 PET 定理解决（含任意符号的互异整数斜率）；Host–Kra 与 Ziegler 的特征因子理论只给出范数收敛，不能解决逐点问题；此前的三重及以上逐点定理都需要 K-系统、谱限制或联结性质等附加结构假设。调和分析方法把"收敛"与"极限辨识"拆开：一致的振荡估计（oscillation estimate）给出逐点收敛，混合假设再经 `@@M@@L^2@@` 论证辨识极限。本族两篇更早的伴随手稿分别证明三线性 Hilbert 变换（trilinear Hilbert transform）的 `@@M@@L^3@@` 界（其图表检测用到 Leng–Sah–Sawhney 量化逆定理）与斜率 `@@M@@1,2,3@@` 情形的逐点收敛；但二者的局部形式都建立在四个坐标 `@@M@@x,x+t,x+2t,x+3t@@` 上，取变换的幂并置换函数无法把一般斜率化为这一配置，故需要本文的系数推广。

## 主要结果

主定理：设 `@@M@@T@@` 为可逆保测变换且混合，即 `@@M@@\mu(A\cap T^{-n}B)\to\mu(A)\mu(B)@@`；`@@M@@\lambda_1,\lambda_2,\lambda_3@@` 为两两不同的非零整数（可正可负），`@@M@@f_1,f_2,f_3@@` 为有界可测复值函数。则

`@@M@@D\frac1N\sum_{n=1}^N\prod_{j=1}^3 f_j(T^{\lambda_j n}x)\longrightarrow\prod_{j=1}^3\int_X f_j\,d\mu@@`

对 `@@M@@\mu@@`-几乎处处的 `@@M@@x@@` 沿全部正整数 `@@M@@N@@` 成立。例外零测集可依赖斜率与函数组；概率空间不必标准、甚至不必可数生成。

## 证明思路

先归一化：取 `@@M@@g=\gcd(|\lambda_1|,|\lambda_2|,|\lambda_3|)@@`、`@@M@@S=T^g@@`、`@@M@@b_j=\lambda_j/g@@`，化为四个互异整数 `@@M@@b_0=0,b_1,b_2,b_3@@` 且 `@@M@@\gcd(|b_1|,|b_2|,|b_3|)=1@@`。解析核心是带进度表的局部估计：在二进区间树上给每个区间配容许核（admissible kernel）`@@M@@w_I@@`，考察四线性形式 `@@M@@H_I@@`（输入取值于 `@@M@@z_j(x+b_jt)@@`），要求各输入在深度分块上变化量不超过 `@@M@@W_j^{-1/2}@@`，结论是 `@@M@@\sum_{I}|I|\,|H_I|\le C|J|@@`，常数对格平移、树、深度、子集与分块全部一致。为把伴随手稿（斜率 `@@M@@1,2,3@@`）的证明推广到任意 `@@M@@b_j@@`，文中给出三个系数装置。其一，用整个本原构型的整数左逆替代么模坐标对：Bézout 型整数 `@@M@@e_j@@` 满足 `@@M@@\sum e_j=0@@`、`@@M@@\sum e_jb_j=1@@`（本原不意味着某对坐标差为一，如 `@@M@@(0,6,10,15)@@`），它在格点与环面离散化中消除多余构型。其二，Vandermonde 关系 `@@M@@\sum_j c_jb_j^a=0@@`（`@@M@@a=0,1,2@@`）导出二次恒等式 `@@M@@\sum_j c_jy_j^2=0@@`，为任意四个互异斜率提供二次消没与 Fourier 随机化。其三，高底取整除全部两两之差，以保住分离频率计数中的整除性，且估计须保持维数的多项式规模——指数损失会破坏参数选择。转移部分：光滑平均轮廓（averaging profile）`@@M@@\varphi@@` 质量为一、1 至 3 阶矩为零且有 Gevrey 型导数界；尺度差 `@@M@@\Delta_k=\varphi_{2^{k+1}}-\varphi_{2^k}@@` 被精确实现为容许核——四个方向导数算子 `@@M@@L_j=\partial_\sigma-b_j\partial_z@@` 之积作用于紧支函数，四条线消没来自全导数积分。实线检验之后做整序列检验：把序列值"种"在半径 `@@M@@\rho@@` 的小区间上，用整数左逆证明同时落入四个小区间的构型必对应格点 `@@M@@p_j=m+b_jn@@`（相差小于 1 的整数相等）。再用 Calderón 转移原理在有限轨道段上得振荡不等式 `@@M@@\sum_i\int\max_{k_i\le\ell\le k_{i+1}}|V_\ell^\varphi-V_{k_i}^\varphi|\,d\mu\le C\sqrt w@@`，对每个确定性尺度列表成立，从而光滑二进平均 `@@M@@V_k^\varphi@@` 在一切可逆系统上几乎处处收敛——此处尚未用到混合。混合经 Hilbert 空间 van der Corput 判据与归纳法给出任意互异非零斜率的多重平均 `@@M@@L^2@@` 范数收敛到积分之积，于是逐点极限必为该乘积。最后以 Vandermonde 矩阵在大尺度上做矩修正，使轮廓在 `@@M@@L^1@@` 中逼近区间指示函数 `@@M@@h_c=c^{-1}\mathbf 1_{(0,c]}@@`，先得一切长度 `@@M@@\lfloor c2^k\rfloor@@`（有理 `@@M@@c\in[1,2]@@`）的收敛，有限网格比较再覆盖全部正整数 `@@M@@N@@`；全程不需要标准性或完备性假设。

## 可信度与备注

主结果暂无 Lean 形式化证明。本文是族内的解析基座：任意长度篇直接引用其任意互异斜率的三重逐点结果（在任意可逆系统上成立、不需混合），四重篇的三重输入与本文同源且其附录对 `@@M@@\{1,2,3,4\}@@` 的三元子集自行做了系数适配；本文自身又向下依赖两篇不在本批的伴随手稿（三线性 Hilbert 变换 `@@M@@L^3@@` 估计与斜率 `@@M@@1,2,3@@` 篇），文中明确区分了引用与新证。按 OpenAI 官方声明，未经形式化的结果可能有问题，请以社区核验为准。

{% endraw %}
