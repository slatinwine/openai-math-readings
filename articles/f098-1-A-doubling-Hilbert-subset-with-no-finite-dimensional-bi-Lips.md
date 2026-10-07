---
layout: default
title: "A doubling Hilbert subset with no finite-dimensional bi-Lipschitz embedding"
family: "098"
discipline: "Convex and metric geometry"
formalized: true
source: null
pdfname: ""
---

{% raw %}
# 解读 | A doubling Hilbert subset with no finite-dimensional bi-Lipschitz embedding

> 结果族 098：Compact counterexamples to bi-Lipschitz dimension reduction　·　学科：Convex and metric geometry　·　验证状态：主结果已 Lean 形式化

## 一句话结论

论文构造实 \(\ell_2\) 中固定的加倍（doubling）子集 \(S\)，其加倍常数不超过 \(76800\)，却不能以任何有限失真（distortion）双 Lipschitz 嵌入任何有限维欧氏空间，对 Lang–Plaut 问题给出否定回答；并推出每个无穷维 Banach 空间都有此类紧反例。

## 问题背景

一个度量空间称为加倍的（doubling），若存在常数 \(\lambda\) 使每个球都能被至多 \(\lambda\) 个半径减半的球覆盖；有限维欧氏空间的子集自动满足。Lang 与 Plaut（2001）问：Hilbert 空间的每个加倍子集是否都能双 Lipschitz 嵌入某个有限维欧氏空间？Gupta–Krauthgamer–Lee 也在算法降维语境下独立提出此问。肯定方向有 Assouad 定理：把距离换成雪花化（snowflaking）后的 \(d^\alpha\)（\(0<\alpha<1\)）便可嵌入，Naor–Neiman 还证明目标维数可只依赖加倍常数，但这些都不处理原始距离。否定方向上，Lafforgue–Naor 等对 \(p>2\) 的 \(L_p\) 构造了加倍反例，Hilbert 情形长期悬置；Schioppa 曾宣布解决，后因对偶论证存疑而撤稿。

## 主要结果

主定理：存在实 \(\ell_2\) 的固定子集 \(S\)（取诱导 Hilbert 距离），加倍常数至多 \(76800\)，且对任意正整数 \(k\) 与任意有限失真 \(D\)，都不存在双 Lipschitz 嵌入 \(S\to\R^k\)。因此，只依赖加倍常数的"维数加失真"联合界对所有加倍 Hilbert 子集不可能成立。两个推论推广之：其一，利用规范化高斯级数，同一度量空间等距实现于每个 \(L_p([0,1];\R)\)（\(1\le p<\infty\)），顺带回答 Lafforgue–Naor 记录为公开的 \(1<p\le2\) 情形；其二，借助 Dvoretzky 定理，每个无穷维实 Banach 空间都含紧集（compact set）\(K_B\)，加倍常数有万有上界 \(\Lambda=1+6\lambda^8\)，且不能双 Lipschitz 嵌入任何有限维赋范空间——Hilbert 空间内的紧集同样如此。

## 证明思路

构造独立于任何目标映射。取 \(\mathcal H=\R^2\oplus\bigoplus_j\R^{N_j}\)（等距于 \(\ell_2\)）与急减尺度 \(r_j=1000^{-j}\)：第 \(j\) 层把平面按宽 \(r_j\) 的水平条带与宽 \(W_jr_j\) 的垂直条带周期地染成 \(N_j\) 色，每个数对 \((N_j,W_j)\) 无限次重现。点 \((p,w)\) 只在有限层取位移 \(w_j=r_je_{j,i}\)，且须基点 \(p\) 落在该色条带内。加倍性靠尺度分层：半径 \(t\) 处粗层（\(r_j>t\)）坐标冻结、中间层至多一层（相邻尺度比为 1000）且标签不足 300、细层贡献小于 \(t/32\)，底面分成 \(16^2\) 格即得 \(300\cdot16^2=76800\)。

反证时把嵌入 \(f\)（失真 \(D\)、下常数规范化为 1）切成"页"（sheet）：固定位移模式、让基点变动，\(F_w(p)=f(p,w)\) 是 \(\R^2\) 开集上的 \(D\)-Lipschitz 映射。由 Rademacher 定理与 Lebesgue 点，把所有页在好点（good point）处的 \((\|F_x\|^2,\|F_y\|^2)\) 取闭包得紧集 \(K\)，再取字典序最大值 \((A,B)\)（先第一坐标、再第二坐标）。紧性引理表明：若取值于 \(K\) 的可测对到 \(A\) 的平均亏差趋于零，则第二坐标均值上极限不超过 \(B\)。

固定 \(N>(1+2D)^k\)。对每个 \(n\)，先选近乎极值的页与好点，再用重现的 \((N,n)\) 层在误差极小的方块内铺出周期块（period block，宽 \(Nnr\)、高 \(Nr\)，含每色一行一列）；添加颜色 \(i\) 的位移得新页 \(F_i\)，且 \(\|F_i-F\|\le Dr\)。能量估计是各向异性的：水平方向沿整行积分得端点差 \(\le 2Dr\)，配合方差恒等式给出带因子 \(n^2\)（补偿长为 \(Nnr\) 的行）的均方变差趋于零；垂直方向先借宽 \(nr\) 条带把所选页的水平导数均方逼向 \(A\)，紧性引理随即给出垂直均方范数 \(\le B\)（无需速率），最终垂直变差亦趋于零。

收官是交叉点悖论：在能量最小的周期块上，由 Fubini 定理为每色各选一条误差小的行与列，绝对连续性使相对偏移 \(h_i=(F_i-F)/r\) 在线上振幅 \(\omega_n\to0\)。颜色 \(i\) 的行与颜色 \(m\) 的列交点处两个位移同时合法，源点距离恰为 \(\sqrt2\,r\)，下 Lipschitz 界给出 \(\|h_i-h_m\|\ge\sqrt2\)；沿线输送后得 \(N\) 个落在半径 \(D\) 球内、两两距离大于 1 的向量，与体积估计 \(N\le(1+2D)^k\) 矛盾。Banach 推论先以乘积紧性造出有限反例，再由 Dvoretzky 定理放入任意 Banach 空间并收缩为紧集。

## 可信度与备注

据任务文件，主结果已有 Lean 形式化证明；两个推论仅用高斯级数、Dvoretzky 定理与紧性等标准工具，与主定理共同构成结果族 098 的骨架。按 OpenAI 官方声明，未经形式化的结果可能存在问题，其余细节应以社区核验为准。

{% endraw %}
