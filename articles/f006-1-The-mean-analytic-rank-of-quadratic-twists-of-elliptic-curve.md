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

## 入门导读 🐣

一个班级若一半人得 0 分、一半人得 1 分，平均分是 0.5；可万一冒出一个考 100 分的天才，平均分就会被拉高。椭圆曲线的二次扭曲大家族也是如此：即便"秩 0 与秩 1 各占一半"，罕见的超高秩曲线会不会拖高平均？这篇论文证明：不会。全族的平均解析秩恰好是 `@@M@@1/2@@`，而且证明是无条件的——既不用黎曼假设，也不用 BSD 猜想。

**关键词卡片**

- 平均解析秩（mean analytic rank）：所有二次扭曲的解析秩取平均，相当于"全班平均分"。
- 二次扭曲（quadratic twist）：以无平方因子整数 `@@M@@d@@` 为参数的表亲曲线 `@@M@@E^{(d)}@@`；正负参数按绝对值一起计数。
- 尾部估计（tail estimate）：秩超过 `@@M@@R@@` 的曲线贡献的"总秩质量"不超过 `@@M@@C_E/R@@`——学霸再多也拉不动平均分的定量版本。
- 无条件（unconditional）：不依赖 GRH、BSD 等未证猜想；此前的精确平均 `@@M@@1/2@@` 都要附加假设才能得到。

**看个具体例子**

主定理：`@@M@@\dfrac{1}{\#\mathcal D(Y)}\sum_{d\in\mathcal D(Y)}a(E^{(d)})\to\dfrac12@@`。推论更有画面感：把秩看成随机变量，它渐近地表现得像一枚公平硬币——一半取 0、一半取 1，于是

`@@M@@D\frac1{\#\mathcal D(Y)}\sum_d e^{t\,r(E^{(d)})}\to\frac{1+e^t}{2},@@`

这正是掷硬币的特征函数（代入 `@@M@@t=1@@` 得 `@@M@@(1+e)/2\approx1.86@@`），代数秩的各阶矩平均也收敛到 `@@M@@1/2@@` 的幂。图示如下：

<div>

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 560 280"><line x1="70" y1="210" x2="520" y2="210" stroke="#333" stroke-width="2"/><line x1="70" y1="210" x2="70" y2="60" stroke="#333" stroke-width="2"/><line x1="110" y1="204" x2="110" y2="216" stroke="#333" stroke-width="2"/><line x1="210" y1="204" x2="210" y2="216" stroke="#333" stroke-width="2"/><line x1="310" y1="204" x2="310" y2="216" stroke="#333" stroke-width="2"/><line x1="410" y1="204" x2="410" y2="216" stroke="#333" stroke-width="2"/><line x1="490" y1="204" x2="490" y2="216" stroke="#333" stroke-width="2"/><text x="110" y="236" font-size="16" text-anchor="middle" fill="#222">0</text><text x="210" y="236" font-size="16" text-anchor="middle" fill="#222">1</text><text x="310" y="236" font-size="16" text-anchor="middle" fill="#222">2</text><text x="410" y="236" font-size="16" text-anchor="middle" fill="#222">3</text><text x="490" y="236" font-size="16" text-anchor="middle" fill="#222">4</text><circle cx="110" cy="185" r="7" fill="none" stroke="#2a5fd6" stroke-width="2.5"/><circle cx="110" cy="167" r="7" fill="none" stroke="#2a5fd6" stroke-width="2.5"/><circle cx="110" cy="149" r="7" fill="none" stroke="#2a5fd6" stroke-width="2.5"/><circle cx="110" cy="131" r="7" fill="none" stroke="#2a5fd6" stroke-width="2.5"/><circle cx="110" cy="113" r="7" fill="none" stroke="#2a5fd6" stroke-width="2.5"/><circle cx="210" cy="185" r="7" fill="none" stroke="#2a5fd6" stroke-width="2.5"/><circle cx="210" cy="167" r="7" fill="none" stroke="#2a5fd6" stroke-width="2.5"/><circle cx="210" cy="149" r="7" fill="none" stroke="#2a5fd6" stroke-width="2.5"/><circle cx="210" cy="131" r="7" fill="none" stroke="#2a5fd6" stroke-width="2.5"/><circle cx="210" cy="113" r="7" fill="none" stroke="#2a5fd6" stroke-width="2.5"/><circle cx="310" cy="185" r="7" fill="none" stroke="#2a5fd6" stroke-width="2.5"/><circle cx="310" cy="167" r="7" fill="none" stroke="#2a5fd6" stroke-width="2.5"/><circle cx="410" cy="185" r="7" fill="none" stroke="#2a5fd6" stroke-width="2.5"/><line x1="160" y1="70" x2="160" y2="196" stroke="#d64545" stroke-width="2" stroke-dasharray="5 4"/><polygon points="150,207 170,207 160,194" fill="#d64545"/><text x="160" y="60" font-size="16" text-anchor="middle" fill="#d64545">平均秩 = 1/2</text><text x="295" y="262" font-size="15" text-anchor="middle" fill="#222">解析秩（每个圆圈代表一批扭曲，示意）</text><text x="295" y="30" font-size="16" text-anchor="middle" fill="#222">一半秩 0、一半秩 1，高秩拖不动平均</text></svg>

</div>

**为什么值得关心**

`@@M@@1/2@@` 正是随机矩阵理论预言的"基准线"，本文在标准计数约定下无条件抵达它，宣告高秩曲线虽然存在、却拖累不了统计。

> 暂无形式化证明（AI 结果待核验）

## 一句话结论

本文证明 Goldfeld 平均解析秩猜想：任一椭圆曲线 `@@M@@E/\mathbb{Q}@@` 的二次扭曲在带符号平方自由参数、按绝对值计数下平均解析秩趋于 `@@M@@1/2@@`；证明无条件（不用广义黎曼假设与 BSD 猜想），核心新工具是导数阶随高度增长的一致尾部估计。

## 问题背景

Goldfeld 在 1979 年猜想：固定椭圆曲线的二次扭曲（quadratic twist）族的平均中心零点阶应为 `@@M@@1/2@@`。"秩 0 与秩 1 各占密度 1/2"（本族姊妹篇的结果）并不自动给出平均——解析秩 `@@M@@\ge2@@` 的扭曲虽然罕见，仍可能携带不可忽略的"秩质量"。此前的平均结果都是条件性的：Heath-Brown 在"所有扭曲都满足黎曼假设"的条件下得到光滑平均的上界 `@@M@@3/2+o(1)@@`；Fiorilli 在 GRH 加一个额外的非实零点平均相消假设下才得到精确的 `@@M@@1/2@@`，且限制在与导子互素的参数上。无条件的精确平均长期缺位，难点正在于控制那些罕见的大秩扭曲。

## 主要结果

记 `@@M@@a(E^{(d)})=\operatorname{ord}_{s=1}L(E^{(d)},s)@@`（解析秩 analytic rank），`@@M@@\mathcal D(Y)=\{d\in\mathbb Z:0<|d|\le Y,\ d\ \text{平方自由}\}@@`，正负参数一起计数。

**定理一（平均秩）**：对每条 `@@M@@E/\mathbb Q@@`，
`@@M@@D\lim_{Y\to\infty}\frac{1}{\#\mathcal D(Y)}\sum_{d\in\mathcal D(Y)}a(E^{(d)})=\frac12 .@@`
对复乘、有理挠、有理同源、约化类型均无限制。

**定理二（秩加权尾部估计）**：存在 `@@M@@C_E>0@@` 与整数 `@@M@@R_E\ge1@@`，使对每个 `@@M@@R\ge R_E@@`，
`@@M@@D\limsup_{Y\to\infty}\frac1Y\sum_{\substack{d\in\mathcal D(Y)\\a(E^{(d)})>R}}a(E^{(d)})\le\frac{C_E}{R}.@@`
这是本文的关键新断言，其证明独立于姊妹篇的密度定理。

**推论（代数秩的矩）**：固定实数 `@@M@@t@@`，`@@M@@\frac1{\#\mathcal D(Y)}\sum_d e^{t\,r(E^{(d)})}\to\frac{1+e^t}2@@`；固定正整数 `@@M@@m@@`，平均 `@@M@@\frac1{\#\mathcal D(Y)}\sum_d r(E^{(d)})^m\to\frac12@@`，其中 `@@M@@r@@` 是 Mordell–Weil 秩。这用姊妹篇的密度结论、密度 1 处的秩相等，以及 Koymans–Smith 的指数矩界。

## 证明思路

先化归：把任意平方自由参数的扭曲归结到有限辅助族 `@@M@@\mathcal F@@`（由 `@@M@@E@@` 对 `@@M@@2q_E@@` 中素数的平方自由扭转生成）上满足 `@@M@@d\equiv1\pmod4@@`、与 `@@M@@2q_E@@` 互素的"可容许"参数，且有精确导子公式 `@@M@@q_{F^{(d)}}=q_Fd^2@@` 与系数界 `@@M@@|\lambda_F(n)|\le\tau(n)@@`。

反证的起点是一个精确恒等式：若 `@@M@@a(F^{(d)})>k@@` 且函数方程符号 `@@M@@\epsilon_d=(-1)^k@@`，则由 Mellin 逆变换与围道位移可得加权狄利克雷级数
`@@M@@D\sum_{n\ge1}\frac{\lambda(n)\chi_d(n)}{\sqrt n}\,W_{k,d/X}\!\Big(\frac{\log n}{\ell}\Big)=0,@@`
其中 `@@M@@\ell=\log X@@`，权 `@@M@@W@@` 是截断对数的 `@@M@@k@@` 次幂经指数平滑而来（`@@M@@(1-u+\log(C_F|x|v)/\ell)_+^k@@`）。要证的是：对绝大多数 `@@M@@d@@`，这个和其实非零。先用光滑截断把级数按 `@@M@@u=\log n/\ell@@` 分成首段、约 `@@M@@\log\ell@@` 个二进短段与末端级数；近似 `@@M@@(1-u)^k\approx e^{-ku}@@` 表明把 `@@M@@L@@` 右移 `@@M@@s=k/\ell@@` 后首段接近正主项 `@@M@@A_x=(C_F|x|)^s\Gamma(1+s)@@`，于是对首段乘以短磨光子 `@@M@@H_j@@`（按素数块截断的逆 Euler 积，Radziwiłł–Soundararajan 式构造），各短段用更短的磨光子，末端不加磨光。

难点在于让所有估计对大到 `@@M@@(\log X)^{3/5}@@` 的 `@@M@@k@@` 一致成立，这需要两个一致性输入。其一是无磨光二阶矩只损失 `@@M@@\log@@` 的幂：对扭曲高度做归纳，用 Poisson 求和、精确的规范化 Gauss 和公式与二变量 Euler 分解，把非零频率化成扭曲 `@@M@@L@@` 函数之积 `@@M@@L_{F^{(\nu h_1)}}(s_1)L_{F^{(\nu h_1)}}(s_2)@@` 乘有界修正；关键技巧是素数平方膨胀——把 `@@M@@d@@` 换成 `@@M@@dp^2@@`（`@@M@@p@@` 取 `@@M@@\log@@` 的充分大固定幂），使对偶参数不超过当前高度的一半，归纳得以闭合。其二是独立模型均方界：把奇素数上的特征值换成独立随机变量 `@@M@@Z(p)@@`（取 `@@M@@0@@` 概率 `@@M@@1/p@@`、取 `@@M@@\pm1@@` 概率各 `@@M@@(1-1/p)/2@@`），在整个概率空间上证明磨光后各段的均方界，再用 Poisson 比较把模型界搬到整数平均；"好事件"命题在除 `@@M@@O(X/k^2)@@` 个参数外同时给出 `@@M@@1/2\le H_jP_j^{\rm eu}\le2@@` 与 `@@M@@P_j^{\rm eu}\le2^{jk/8}P_0^{\rm eu}@@`（`@@M@@P_j^{\rm eu}@@` 为正 Euler 积）。

组装时，Chebyshev 不等式与几何求和把各例外集并成 `@@M@@O(X/k^2)@@`；在好事件上首段被 `@@M@@P_0^{\rm eu}@@` 的正常数倍控制下界，而其余各段与末端合计更小，故整个加权和非零——与恒等式矛盾。于是 `@@M@@\#\{d:a(F^{(d)})>k,\ \epsilon_d=(-1)^k\}\ll X/k^2@@` 对 `@@M@@k\le(\log X)^{3/5}@@` 一致成立；另一符号在 `@@M@@k-1@@` 处处理。最后从计数到均值：导子一致的 Jensen 公式给逐点界 `@@M@@a\ll_E\log X@@`，对整数尾部求和得 `@@M@@\sum_{a>R}a\ll_E X/R+X(\log X)^{-1/5}@@`，再按二进区间分解。均值推导只用初等平方自由筛 `@@M@@\#\mathcal D(Y)=2Y/\zeta(2)+O(\sqrt Y)@@`：姊妹篇的密度定理使秩 `@@M@@\ge2@@` 的参数只有 `@@M@@o(Y)@@` 个，固定 `@@M@@R@@` 时秩 2 到 `@@M@@R@@` 贡献 `@@M@@o(Y)@@`，秩超过 `@@M@@R@@` 的贡献由尾部估计压到 `@@M@@C_E/R@@`，令 `@@M@@R\to\infty@@` 即得总和为 `@@M@@N_1(Y)+o_E(Y)@@`，除以 `@@M@@\#\mathcal D(Y)@@` 就是 `@@M@@1/2@@`。

## 可信度与备注

本篇主结果未经 Lean 形式化；OpenAI 官方声明：未经形式化的结果可能存在问题，请以社区核验为准。它与姊妹篇（解析密度猜想）互相支撑：本文只以姊妹篇的密度定理为输入，姊妹篇则需本文的尾部估计才能从"各占一半"过渡到"平均为 `@@M@@1/2@@`"。证明不使用 BSD 猜想或 GRH；文中还特别声明不采用 Hanners 声称的完整 BSD 证明，理由是其桥梁条件尚未对每条曲线建立。部分技术估计（素数块磨光、Poisson 比较）此处从略。

{% endraw %}
