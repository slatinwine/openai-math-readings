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

## 入门导读 🐣

把一根一米长的棍子随机折断，断出的各段长度有一条著名的统计规律。这篇论文证明数论世界也有同样的"折棍定律"：随机取一个大素数 `@@M@@p@@`，把 `@@M@@p-1@@` 分解成素因子，每个因子的对数占 `@@M@@\log(p-1)@@` 的比例——这些比例按大小排好后，恰恰服从那条折棍分布。它证明了 Ford–Konyagin–Luca 在 2010 年提出的猜想。

**关键词卡片**

- 前驱（predecessor）：素数 `@@M@@p@@` 的前一项 `@@M@@p-1@@`。
- 泊松–狄利克雷分布（Poisson–Dirichlet law `@@M@@\mathrm{PD}(1)@@`）：随机折棍所得、按长短降序排列的片段长度的极限分布。
- 最大素因子（largest prime factor `@@M@@P^+@@`）：分解中最大的素数，对应最长的一截棍子。
- Dickman 函数（Dickman function `@@M@@\rho@@`）：度量"一个数的素因子都不超过某界"概率的经典函数。
- 联合收敛（joint convergence）：一切有限维统计量同时收敛，比只看单个量强得多。

**看个具体例子**

取 `@@M@@p=211@@`，则 `@@M@@p-1=210=2\times3\times5\times7@@`。四个因子的对数占比约为 `@@M@@36\%、30\%、21\%、13\%@@`，正好把"对数棍子"切成四段。主定理断言：让 `@@M@@p@@` 在不超过 `@@M@@x@@` 的素数里均匀抽取并让 `@@M@@x\to\infty@@`，这类比例向量的统计规律收敛到 `@@M@@\mathrm{PD}(1)@@`；由最大一段还能读出 Granville 的移位 Dickman 猜想。

<div>

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 560 280">
  <text x="280" y="38" font-size="15" text-anchor="middle">把 log(p−1) 看作一根棍子（例：p=211，p−1=210=2×3×5×7）</text>
  <text x="126" y="96" font-size="14" text-anchor="middle">7（36%）</text>
  <text x="285" y="96" font-size="14" text-anchor="middle">5（30%）</text>
  <text x="407" y="96" font-size="14" text-anchor="middle">3（21%）</text>
  <text x="489" y="96" font-size="14" text-anchor="middle">2（13%）</text>
  <rect x="40" y="108" width="173" height="46" fill="#dce9f7" stroke="#345"/>
  <rect x="213" y="108" width="144" height="46" fill="#f7e8d3" stroke="#345"/>
  <rect x="357" y="108" width="101" height="46" fill="#e3f2d9" stroke="#345"/>
  <rect x="458" y="108" width="62" height="46" fill="#f2e3ea" stroke="#345"/>
  <line x1="40" y1="154" x2="40" y2="168" stroke="#345"/>
  <line x1="520" y1="154" x2="520" y2="168" stroke="#345"/>
  <text x="40" y="184" font-size="13" text-anchor="middle">0</text>
  <text x="520" y="184" font-size="13" text-anchor="middle">1</text>
  <text x="280" y="184" font-size="12" text-anchor="middle">每段长度 = log(素因子) / log(210)</text>
  <text x="280" y="240" font-size="14" text-anchor="middle">主定理：随机大素数的这类切分比例收敛到折棍分布 PD(1)</text>
</svg>

</div>

**为什么值得关心**

普通整数的折棍规律半个多世纪前已经清楚，换成"素数的前一项"却难得多——本文在不附加任何猜想的前提下完成了完整刻画。

> 暂无形式化证明（AI 结果待核验）

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
