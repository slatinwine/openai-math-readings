---
layout: default
title: "The Poisson-Dirichlet law for prime predecessors"
family: "011"
discipline: "Number theory"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | The Poisson-Dirichlet law for prime predecessors

> 结果族 011：Prime-factor statistics of `@@M@@`p-1`@@`　·　学科：Number theory　·　验证状态：暂无形式化证明，请以社区核验为准

## 一句话结论

证明了素数前驱的因子定律：均匀取素数 `@@M@@p\le x@@`，把 `@@M@@p-1@@` 的素因子（计重数）降序排列，其对数除以 `@@M@@\log(p-1)@@` 后依一切有限联合分布收敛到参数为一的 Poisson–Dirichlet 律 `@@M@@\mathrm{PD}(1)@@`，解决了 Ford–Konyagin–Luca 猜想与 Granville 的移位 Dickman 猜想。

## 问题背景

一个典型整数的素因子取对数后构成单位质量的一个随机分拆（random partition）；对均匀取的整数，这个极限分拆早已由光滑数（smooth number）理论、Billingsley 的联合极限定律与 Donnelly–Grimmett 的折棍（stick-breaking）构造完全刻画。把整数换成素数的前驱（predecessor）`@@M@@p-1@@` 后难度陡增：要求一串大素数之积整除 `@@M@@p-1@@`，等于把 `@@M@@p@@` 关进以该乘积为模的剩余类，而已有的分布水平（level of distribution）型估计只覆盖 `@@M@@x@@` 的固定幂以下的模数，完整的因子分拆却要用到整个 `@@M@@x@@` 以下的乘积。Ford、Konyagin、Luca 在 2010 年研究素数链与 Pratt 树时猜想：前驱的规整因子序列收敛于 `@@M@@\mathrm{PD}(1)@@`。此前最好的无条件结果只是 `@@M@@x/(\log x)^C@@` 量级的下界（Baker–Harman、Lichtman 的光滑前驱定理）；Bharadwaj–Rodgers 证明该定律在 Elliott–Halberstam 猜想之下成立，无条件仅得到对数坐标和小于 `@@M@@1/2@@` 的部分区域，而本文达到了坐标和小于 `@@M@@1@@` 的整个开单形的紧子集。

## 主要结果

主定理：设 `@@M@@p\ge3@@` 为素数，把 `@@M@@p-1@@` 的素因子按重数降序排为 `@@M@@q_1(p)\ge q_2(p)\ge\cdots@@`（取尽后令 `@@M@@q_j=1@@`），令 `@@M@@V_j(p)=\log q_j(p)/\log(p-1)@@`，则 `@@M@@V_j(p)\ge0@@` 且 `@@M@@\sum_jV_j(p)=1@@`。对每个固定 `@@M@@k\ge1@@` 与有界连续函数 `@@M@@F:[0,1]^k\to\mathbb{R}@@`，

`@@M@@D\lim_{x\to\infty}\frac1{\pi(x)-1}\sum_{\substack{3\le p\le x\\ p\ \mathrm{prime}}}F\bigl(V_1(p),\ldots,V_k(p)\bigr)=\mathbb{E}F(L_1,\ldots,L_k),@@`

其中 `@@M@@(L_1,L_2,\ldots)@@` 是折棍片段 `@@M@@B_1=1-U_1@@`、`@@M@@B_j=\bigl(\prod_{i<j}U_i\bigr)(1-U_j)@@`（`@@M@@U_i@@` 为独立均匀随机变量）的降序重排，即参数一的 Poisson–Dirichlet 分布 `@@M@@\mathrm{PD}(1)@@`；极限对一切实 `@@M@@x\to\infty@@`、按素数等权成立。由最大分量即可读出 Granville 的猜想：对固定 `@@M@@u\ge1@@`，`@@M@@\#\{p\le x:P^+(p-1)\le x^{1/u}\}\sim\pi(x)\rho(u)@@`，其中 `@@M@@P^+@@` 是最大素因子、`@@M@@\rho@@` 是 Dickman 函数（Dickman function）；`@@M@@L_1@@` 本身服从连续 Dickman 分布。这比原先只涉及最大因子的单点预言更强，给出全部有限维联合分布。

## 证明思路

证明分四层。第一层是"内部统计"定理：取 `@@M@@d@@` 个素数槽区间（下端 `@@M@@\ge x^\varepsilon@@`、上端之积 `@@M@@\le x^{1-\varepsilon}@@`），记 `@@M@@f_x(u)@@` 为槽中互异素数 `@@M@@d@@` 元组之积整除 `@@M@@u@@` 的个数、`@@M@@C_x=\sum 1/\ell_1\cdots\ell_d@@` 为期望主项，证明 `@@M@@\sum_p\Phi((p-1)/x)(f_x(p-1)-C_x)=o(x/\log x)@@`。第二层是两个新的解析估计。其一是一侧带标记的 Type II 估计：只在前驱端 `@@M@@mn-1@@` 挂上记录小素数因子的除子标记（权重 `@@M@@\mathcal W@@`），并允许把另一侧的素数换成粗糙整数（rough integer）。先经预筛与 Cauchy 平方，把计数问题化为原始（primitive）格向量间的小行列式关系 `@@M@@t=bmn-ars=b-a@@`；再用根剩余公式——原始向量模 `@@M@@S@@` 在 `@@M@@\mathrm{SL}_2(\mathbb{Z}/S\mathbb{Z})@@` 中一致分布，其证明只靠一个初等的 Kloosterman 型四次矩估计——把根平均替换为独立射影线模型，每条线命中概率 `@@M@@1/(p+1)@@`。关键的"记忆展开"（memory expansion）把长路径写成算子历史：素数在两次使用之间作为待定粒子储存，其整除概率只记一次；干净边（clean edge）靠格箱上行列式指数和的范数衰减（Dirichlet 逼近加几何和估计），脏边（dirty edge）靠良好状态的相位分离做绝对估计，出生互异最后按等式约束的"秩"分级恢复——高秩提供许多小概率因子，低秩只扰动极少量边。其二是两侧带标记的相关估计：调用姊妹篇的加权膨胀图（weighted dilation graph）转移定理，新端点 Fourier 估计分频段处理——低 Mellin 频率用截断除子模型使中心化直接消去主项，高频率用小素数多项式圈出稀疏例外时刻集（Matomäki–Radziwiłł 策略），正元组项再由长素数多项式控制。第三层是抽取：先用块筛预筛掉小素数，再把复合项的每个素数槽换成粗糙代理，对候选组做"成功抛币"并以 Chebyshev 保证多数成功，使复合项落入两侧估计；最后对多个不相交标记阵列取均方消去标记，得到素数的内部阶乘矩渐近。第四层是概率过渡：矩形上的阶乘测度（factorial measure）收敛于 Dickman 强度 `@@M@@\prod\dd t_i/t_i@@`；顺序偏大小抽样（size-biased sampling）把内部测度化为总质量为一的密度，三角变换 `@@M@@A_i=t_i/(1-t_1-\cdots-t_{i-1})@@` 恰好把它识别为折棍片段并排除边界逃逸；未取质量的期望 `@@M@@2^{-d}@@` 控制排序误差，有限二进分解把单个 dyad 的结论拼合到一切实上端。

## 可信度与备注

本文主结果暂无 Lean 形式化证明。姊妹篇《Weighted dilation graphs, smooth shifted primes and totient fibers》提供膨胀图算子输入（该篇同时证得 Erdős 的 Euler `@@M@@\varphi@@` 函数最大纤维猜想），两文共用长素数多项式与对数相位估计（本文附录）；族内第三篇则证明存在无穷多个素数使 `@@M@@\mu(p-1)=1@@`。按 OpenAI 官方声明，未经形式化的结果可能存在问题，请以社区核验为准。

{% endraw %}
