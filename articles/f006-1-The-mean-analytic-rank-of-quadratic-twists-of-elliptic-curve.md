---
layout: default
title: "The mean analytic rank of quadratic twists of elliptic curves"
family: "006"
discipline: "Number theory"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | The mean analytic rank of quadratic twists of elliptic curves

> 结果族 006：Goldfeld's conjecture: densities and mean analytic rank　·　学科：Number theory　·　验证状态：暂无形式化证明，请以社区核验为准

## 一句话结论

本文证明 Goldfeld 平均解析秩猜想：任一椭圆曲线 \(E/\mathbb{Q}\) 的二次扭曲在带符号平方自由参数、按绝对值计数下平均解析秩趋于 \(1/2\)；证明无条件（不用广义黎曼假设与 BSD 猜想），核心新工具是导数阶随高度增长的一致尾部估计。

## 问题背景

Goldfeld 在 1979 年猜想：固定椭圆曲线的二次扭曲（quadratic twist）族的平均中心零点阶应为 \(1/2\)。"秩 0 与秩 1 各占密度 1/2"（本族姊妹篇的结果）并不自动给出平均——解析秩 \(\ge2\) 的扭曲虽然罕见，仍可能携带不可忽略的"秩质量"。此前的平均结果都是条件性的：Heath-Brown 在"所有扭曲都满足黎曼假设"的条件下得到光滑平均的上界 \(3/2+o(1)\)；Fiorilli 在 GRH 加一个额外的非实零点平均相消假设下才得到精确的 \(1/2\)，且限制在与导子互素的参数上。无条件的精确平均长期缺位，难点正在于控制那些罕见的大秩扭曲。

## 主要结果

记 \(a(E^{(d)})=\operatorname{ord}_{s=1}L(E^{(d)},s)\)（解析秩 analytic rank），\(\mathcal D(Y)=\{d\in\mathbb Z:0<|d|\le Y,\ d\ \text{平方自由}\}\)，正负参数一起计数。

**定理一（平均秩）**：对每条 \(E/\mathbb Q\)，
\[\lim_{Y\to\infty}\frac{1}{\#\mathcal D(Y)}\sum_{d\in\mathcal D(Y)}a(E^{(d)})=\frac12 .\]
对复乘、有理挠、有理同源、约化类型均无限制。

**定理二（秩加权尾部估计）**：存在 \(C_E>0\) 与整数 \(R_E\ge1\)，使对每个 \(R\ge R_E\)，
\[\limsup_{Y\to\infty}\frac1Y\sum_{\substack{d\in\mathcal D(Y)\\a(E^{(d)})>R}}a(E^{(d)})\le\frac{C_E}{R}.\]
这是本文的关键新断言，其证明独立于姊妹篇的密度定理。

**推论（代数秩的矩）**：固定实数 \(t\)，\(\frac1{\#\mathcal D(Y)}\sum_d e^{t\,r(E^{(d)})}\to\frac{1+e^t}2\)；固定正整数 \(m\)，平均 \(\frac1{\#\mathcal D(Y)}\sum_d r(E^{(d)})^m\to\frac12\)，其中 \(r\) 是 Mordell–Weil 秩。这用姊妹篇的密度结论、密度 1 处的秩相等，以及 Koymans–Smith 的指数矩界。

## 证明思路

先化归：把任意平方自由参数的扭曲归结到有限辅助族 \(\mathcal F\)（由 \(E\) 对 \(2q_E\) 中素数的平方自由扭转生成）上满足 \(d\equiv1\pmod4\)、与 \(2q_E\) 互素的"可容许"参数，且有精确导子公式 \(q_{F^{(d)}}=q_Fd^2\) 与系数界 \(|\lambda_F(n)|\le\tau(n)\)。

反证的起点是一个精确恒等式：若 \(a(F^{(d)})>k\) 且函数方程符号 \(\epsilon_d=(-1)^k\)，则由 Mellin 逆变换与围道位移可得加权狄利克雷级数
\[\sum_{n\ge1}\frac{\lambda(n)\chi_d(n)}{\sqrt n}\,W_{k,d/X}\!\Big(\frac{\log n}{\ell}\Big)=0,\]
其中 \(\ell=\log X\)，权 \(W\) 是截断对数的 \(k\) 次幂经指数平滑而来（\((1-u+\log(C_F|x|v)/\ell)_+^k\)）。要证的是：对绝大多数 \(d\)，这个和其实非零。先用光滑截断把级数按 \(u=\log n/\ell\) 分成首段、约 \(\log\ell\) 个二进短段与末端级数；近似 \((1-u)^k\approx e^{-ku}\) 表明把 \(L\) 右移 \(s=k/\ell\) 后首段接近正主项 \(A_x=(C_F|x|)^s\Gamma(1+s)\)，于是对首段乘以短磨光子 \(H_j\)（按素数块截断的逆 Euler 积，Radziwiłł–Soundararajan 式构造），各短段用更短的磨光子，末端不加磨光。

难点在于让所有估计对大到 \((\log X)^{3/5}\) 的 \(k\) 一致成立，这需要两个一致性输入。其一是无磨光二阶矩只损失 \(\log\) 的幂：对扭曲高度做归纳，用 Poisson 求和、精确的规范化 Gauss 和公式与二变量 Euler 分解，把非零频率化成扭曲 \(L\) 函数之积 \(L_{F^{(\nu h_1)}}(s_1)L_{F^{(\nu h_1)}}(s_2)\) 乘有界修正；关键技巧是素数平方膨胀——把 \(d\) 换成 \(dp^2\)（\(p\) 取 \(\log\) 的充分大固定幂），使对偶参数不超过当前高度的一半，归纳得以闭合。其二是独立模型均方界：把奇素数上的特征值换成独立随机变量 \(Z(p)\)（取 \(0\) 概率 \(1/p\)、取 \(\pm1\) 概率各 \((1-1/p)/2\)），在整个概率空间上证明磨光后各段的均方界，再用 Poisson 比较把模型界搬到整数平均；"好事件"命题在除 \(O(X/k^2)\) 个参数外同时给出 \(1/2\le H_jP_j^{\rm eu}\le2\) 与 \(P_j^{\rm eu}\le2^{jk/8}P_0^{\rm eu}\)（\(P_j^{\rm eu}\) 为正 Euler 积）。

组装时，Chebyshev 不等式与几何求和把各例外集并成 \(O(X/k^2)\)；在好事件上首段被 \(P_0^{\rm eu}\) 的正常数倍控制下界，而其余各段与末端合计更小，故整个加权和非零——与恒等式矛盾。于是 \(\#\{d:a(F^{(d)})>k,\ \epsilon_d=(-1)^k\}\ll X/k^2\) 对 \(k\le(\log X)^{3/5}\) 一致成立；另一符号在 \(k-1\) 处处理。最后从计数到均值：导子一致的 Jensen 公式给逐点界 \(a\ll_E\log X\)，对整数尾部求和得 \(\sum_{a>R}a\ll_E X/R+X(\log X)^{-1/5}\)，再按二进区间分解。均值推导只用初等平方自由筛 \(\#\mathcal D(Y)=2Y/\zeta(2)+O(\sqrt Y)\)：姊妹篇的密度定理使秩 \(\ge2\) 的参数只有 \(o(Y)\) 个，固定 \(R\) 时秩 2 到 \(R\) 贡献 \(o(Y)\)，秩超过 \(R\) 的贡献由尾部估计压到 \(C_E/R\)，令 \(R\to\infty\) 即得总和为 \(N_1(Y)+o_E(Y)\)，除以 \(\#\mathcal D(Y)\) 就是 \(1/2\)。

## 可信度与备注

本篇主结果未经 Lean 形式化；OpenAI 官方声明：未经形式化的结果可能存在问题，请以社区核验为准。它与姊妹篇（解析密度猜想）互相支撑：本文只以姊妹篇的密度定理为输入，姊妹篇则需本文的尾部估计才能从"各占一半"过渡到"平均为 \(1/2\)"。证明不使用 BSD 猜想或 GRH；文中还特别声明不采用 Hanners 声称的完整 BSD 证明，理由是其桥梁条件尚未对每条曲线建立。部分技术估计（素数块磨光、Poisson 比较）此处从略。

{% endraw %}
