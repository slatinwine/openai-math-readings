---
layout: default
title: "An unconditional first moment for cubic Gauss sums"
family: "023"
discipline: "Number theory"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | An unconditional first moment for cubic Gauss sums

> 结果族 023：Patterson's first moment for cubic Gauss sums　·　学科：Number theory　·　验证状态：暂无形式化证明，请以社区核验为准

## 一句话结论

在不依赖 GRH 等任何未证假设的前提下，本文证明了 Patterson 第一矩猜想：全体本原 Eisenstein 素数上规范化三次 Gauss 和之和有显式主项 \(\frac65c_*X^{5/6}/\log X\)，且每个固定非零角 Fourier 模式在此尺度相消，将 Dunn–Radziwiłł 的 GRH 条件结果无条件化。

## 问题背景

对有理素数 \(p\equiv1\pmod3\)，Kummer 和（Kummer sum）\(S_p=\sum_{x\bmod p}e(x^3/p)\) 自 Kummer 1846 年的数值观测起就显示出偏向正值的迹象。在现代语言中，它对应 Eisenstein 整环 \(\mathcal O=\mathbb Z[\omega]\) 上的三次剩余符号（cubic residue symbol）\(\chi_b\) 与规范化三次 Gauss 和 \(G(b)=\frac{1}{\sqrt{N(b)}}\sum_{v\bmod b}\chi_b(v)e(\Tr(v/b))\)；在素数处 \(|G(\pi)|=1\)。Heath-Brown 与 Patterson（1979）证明这些值在单位圆上等分布，但那只控制素数计数尺度 \(X/\log X\)，与一个更小而持续的偏差相容。Patterson（1978）预测在 \(X^{5/6}/\log X\) 尺度上存在显式偏置；Heath-Brown 的三次大筛法（cubic large sieve，2000）只给出 \(O_\epsilon(X^{5/6+\epsilon})\) 上界。Dunn 与 Radziwiłł（Annals of Mathematics 2024）在 Hecke \(L\)-函数的广义黎曼假设（GRH）下证明了光滑化版本的第一矩；如何去掉 GRH 并处理尖截断（sharp cutoff），正是此前卡住的两大难点。

## 主要结果

记 \(c_*=(2\pi)^{2/3}/(3\Gamma(2/3))\)。主定理断言：当 \(X\to\infty\) 时
\[\sum_{\substack{N\pi\le X\\ \pi\equiv1\pmod3\ \mathrm{prime}}}G(\pi)=\frac65c_*\frac{X^{5/6}}{\log X}+o\!\left(\frac{X^{5/6}}{\log X}\right),\]
求和遍历 \(\mathcal O\) 中所有本原素数（primary，即同余 \(1\bmod3\) 的素数），包括分裂有理素数上方的两个共轭素理想；惯性素数（inert prime）总贡献仅 \(O(\sqrt X)\)。由配对公式 \(G(\pi)+G(\bar\pi)=S_p/\sqrt p\) 立得有理素数形式
\[\sum_{p\le X,\;p\equiv1\pmod3}\frac{S_p}{2\sqrt p}\sim\frac35c_*\frac{X^{5/6}}{\log X}=\frac{(2\pi)^{2/3}}{5\Gamma(2/3)}\frac{X^{5/6}}{\log X},\]
这正是 Wan 猜想 4.13 的系数。附录定理进一步证明：对每个固定整数 \(\ell\)，插入角 Fourier 模（angular Fourier mode）\(\theta_\ell(\pi)=(\pi/|\pi|)^\ell\) 后，\(G(\pi)\) 与初等模型 \(c_*N(\pi)^{-1/6}\) 的比较仍成立；且 \(\ell\ne0\) 时扭矩为 \(o_\ell(X^{5/6}/\log X)\)。结合恒等式 \(G(\pi)^3=-\pi/|\pi|\)，对一切 \(3\nmid k\)、\(|k|>1\) 的固定整数 \(k\) 也有 \(\sum G(\pi)^k=o(X^{5/6}/\log X)\)，即 Patterson 互补猜想（关于 \(G(\pi)^k\)，\(k\notin\{0,\pm1\}\)）中 \(3\nmid k\) 的部分；\(k\) 为 3 的非零倍数的情形仍然开放。

## 证明思路

证明的总目标，是在每个二进素数区间上把 \(G(\pi)\) 与初等模型 \(c_*N(\pi)^{-1/6}\) 比较——由素理想定理与分部求和，模型和恰好给出 \((6/5)c_*\) 主项。难点在于必须使用尖截断：论文用 Fourier 截断把区间示性函数换成光滑版本，代价是引入高达 \(T\ll X^{1/6+\rho}\) 的 Mellin 高度（Mellin height），于是估计按"普通块"（\(T\ll X^{0.01}\)）与"高块"分别准备。先做精确的素数分解：用精确素检测器暴露一组中等大小的素数，再用按范数分袋（bin）的停止规则与替代乘积（surrogate product）控制 Möbius 展开，并以二项式权重 \(\binom{k_++k_-}{k_+}^{-1}\) 把跨袋因子精确分摊，使素数和恒等分解为 Type I 项（外层水平 \(r\) 受控、内层 \(u\) 自由）与双线性项（\(AB\asymp X\)，\(B\ll\sqrt X\)），两侧系数严格独立——避免了传统做法中最小素数截断把两侧耦合的困境。再逐类估计：Type I 项在低高度使用 Dunn–Radziwiłł 的无条件 level Voronoi 公式，Möbius 反演去掉立方补全后，其留数与模型的格点计数完全一致，弃去的立方因子由三次大筛法控制；高 Mellin 高度上不再扣除模型，改用 Heath-Brown 的 metaplectic 均方估计直接压制 Gauss 和项。双线性项经开方与 Poisson 求和后发现：非零频率中恰为立方的部分不是误差，而精确重现模型项——"修正色散（corrected dispersion）"把它扣掉，其格点渐近常数经 Riesz 核计算恰为 \(c_*^2\)；剩余频率用两类大筛法控制，只余两个例外导体长度构型 \((P,Q)=(Y,1)\) 与 \((Y^{1/3},Y^{1/3})\)。这两个构型专章处理：利用系数是素数序列独立光滑卷积的结构，先以短卷积恒等式 \(\Lambda=(2m-m*m*1)*\log N\) 拆分权重，满长度因子由 Hecke \(L\)-函数的函数方程缩短为对偶短多项式，再对不同长度的矩做鸽笼与极限指数反证，最后用 Bombieri–Halász–Montgomery 型非对角 Gram 估计导出矛盾。最后组装：低高度用修正色散加 Cauchy 不等式；高高度把两个范数变量同时切成宽 \(1/J\) 的胞腔，乘积边界附近的胞腔只有 \(O(1)\) 个邻居，局部化对角线由此获得 \(J^{-1/2}\) 节省，远离边界则对高度积分反复分部积分；唯一的对数过渡——三个范数几乎相等的素数之积——由素数稀疏性给出 \(L^{-3/2}\) 节省，足以吸收分解产生的多项式个片段。附录把上述接口移植到固定角模式，关键新输入是具固定无穷型（infinity type）Hecke 特征的函数方程与相应素数定理。

## 可信度与备注

本文主结果暂无形式化证明，验证状态以社区核验为准；OpenAI 官方亦声明"未经形式化的结果可能有问题"。论文明确列出全部外部输入（三次互反律、Heath-Brown 的三次大筛法与 metaplectic 均方、Dunn–Radziwiłł 的无条件 Voronoi 公式与留数），并强调不使用任何依赖 GRH 的取消估计；对所引 DR2024 版本中两处打印系数的矛盾，作者以备注如实指出而非默认调和。本批任务中该结果族仅此一篇手稿，族概述（主项阶 \(X^{5/6}/\log X\)、固定非零素角模式更低阶）与本文两个定理一一对应。

{% endraw %}
