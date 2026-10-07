---
layout: default
title: "A negatively pinched Kähler threefold without bounded holomorphic coordinates"
family: "359"
discipline: "Differential geometry"
formalized: true
source: null
pdfname: ""
---

{% raw %}
# 解读 | A negatively pinched Kähler threefold without bounded holomorphic coordinates

> 结果族 359：Negative Kähler curvature without bounded holomorphic coordinates　·　学科：Differential geometry　·　验证状态：主结果已 Lean 形式化

## 一句话结论

在 `@@M@@\C^3@@` 中构造出可缩区域 (contractible domain)，配上完备 Kähler 度量后其实截面曲率 (sectional curvature) 被两个负常数上下夹紧，却不存在 Jacobi 行列式处处非零的有界全纯映射——"负夹紧 Kähler 流形必双全纯于有界域"的单值化问题由此得到否定回答。

## 问题背景

一维单值化定理 (uniformization) 说：完备、单连通、曲率不超过某负常数的黎曼面必双全纯 (biholomorphic) 于单位圆盘。高维时曲率条件还能否逼出有界域结构？H. Wu 1967 年在正规族工作中问：完备单连通、实截面曲率非正且全纯截面曲率一致负的 Kähler 流形是否双全纯于有界域；Wu 与 Yau 在 2019 年综述中给出两侧夹紧版本（猜想 4.3）。Mostow–Siu 以及 Deraux 的紧负曲率 Kähler 例子表明高维未必被球覆盖，但其万有覆盖仍可能双全纯于其他有界域——夹紧条件到底能否排除这一点，正是此前悬而未决之处。

## 主要结果

主定理：存在可缩区域 `@@M@@M\subset\C^3@@` 与光滑完备 Kähler 度量 `@@M@@g@@`，及有限常数 `@@M@@0<A\le B@@`，使得对每点、每个实二维平面 `@@M@@\sigma@@` 均有 `@@M@@-B\le K_g(\sigma)\le -A<0@@`；并且不存在 Jacobi 行列式处处非零的有界全纯映射 `@@M@@F:M\to\C^3@@`。特别地，`@@M@@M@@` 不与 `@@M@@\C^3@@` 中任何有界域 (bounded domain) 双全纯。值得注意：`@@M@@M@@` 本身是 Stein 流形——构造自带严格多次调和 (plurisubharmonic) 穷竭函数，由 Grauert 对 Levi 问题的解即得；且基坐标 `@@M@@z_1,z_2@@` 就是非常数有界全纯函数。因此受阻的既非全纯凸性 (holomorphic convexity)，也非有界全纯函数的存在性，而恰恰是"三个微分处处线性无关的有界坐标"。

## 证明思路

总体策略是几何与分析分治。区域取单位球 `@@M@@\B\subset\C^2@@` 上的哈托格斯域 (Hartogs domain)：`@@M@@M_\phi=\{(z,w)\in\B\times\C:e^{\phi(z)}|w|^2<1\}@@`，即 `@@M@@z@@` 上方圆盘半径为 `@@M@@e^{-\phi(z)/2}@@`；度量取位势 `@@M@@\lambda\psi-\log(1-e^{\phi}|w|^2)@@`（其中 `@@M@@\psi=-\log(1-|z|^2)@@`）的复 Hessian (complex Hessian)，属于 Calabi 型圆不变构造。证明只依赖两个输入。分析输入：造光滑实函数 `@@M@@\phi@@`，使其复 Hessian 两侧有界、在中心化球坐标下各分量导数有界（不假定该度量的曲率符号），且不存在全纯函数 `@@M@@H@@` 满足 `@@M@@\operatorname{Re}H\le C_H+4\log\frac1{1-|z|}+\phi@@`。几何输入：满足这些界的 `@@M@@\phi@@`，只要基参数 `@@M@@\lambda@@` 足够大，`@@M@@M_\phi@@` 可缩、度量完备且截面曲率一致负。

先看阻碍如何闭合：若有界全纯 `@@M@@F@@` 的 Jacobi 行列式处处非零，其限制在零截面上的行列式 `@@M@@d@@` 是 `@@M@@\B@@` 上无零点的全纯函数；`@@M@@\B@@` 单连通，故 `@@M@@d@@` 有整体全纯对数。对基方向圆盘与纤维圆盘分别用 Cauchy 估计，得 `@@M@@\log|d|^2\le C+4\log\frac1{1-|z|}+\phi@@`，恰好撞上 `@@M@@\phi@@` 所禁止的全纯实部上界，矛盾——有界全纯坐标因此不可能存在。

`@@M@@\phi@@` 的构造在度数 `@@M@@k_j=Q^j@@`（`@@M@@Q@@` 为一个固定大整数）上递归进行：先在每个度数往一批分离的复直线上叠加齐次峰值多项式 (peak polynomial)（其投影填充与幂和估计承自 Ryll–Wojtaszczyk），再做径向修正，得到保持原点处全纯赋值的正密度；正则化对数 `@@M@@\log\frac{|1-aP_k|^2+\epsilon^2}{1+\epsilon^2}@@` 对该密度有固定的负平均值，且相邻度数间的频率分离使这一负平均在后续所有修正下存活；再用足够大的固定系数求和，压倒 Cauchy 估计强加的对数边界项 `@@M@@4\log\frac1{1-r}@@`。低度数部分在中心化图里变化甚微、高度数部分呈指数小，由此凑齐曲率计算所需的四阶导数一致界。

曲率部分最 delicate 之处在于：取负后的主项非负，但可在水平与垂直投影复定向相反的"混合平面"上取零；恰在此类极限平面上，潜在最大的误差项（含三个水平指标者）因只能把水平块与混合块相配对而同样消失。分 `@@M@@q/\lambda\to0@@` 与 `@@M@@\lambda/q@@` 有界两个 regime 反证并辅以紧性论证，可得某个大 `@@M@@\lambda@@` 下曲率严格负；固定该 `@@M@@\lambda@@` 后，有界纤维段上的紧性与纤维边界处的一致极限张量共同给出上下两个有限的曲率界。

## 可信度与备注

本文主结果已由 Lean 形式化证明，是结果族 359 的核心篇目。同族姊妹篇（单侧版本）在某个充分大的有限维数构造出曲率 `@@M@@\le-1@@` 却只有常数有界全纯函数的区域，两文证明完全独立、互不引用：本文双侧夹紧但保留两个有界基坐标函数，姊妹篇单侧无下界且毫无非常数有界函数，从两侧分别否定这一族均匀化问题。按 OpenAI 官方声明，未经形式化的结果可能有问题，故姊妹篇结论宜以社区核验为准。

{% endraw %}
