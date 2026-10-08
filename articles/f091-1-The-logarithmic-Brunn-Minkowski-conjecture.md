---
layout: default
title: "The logarithmic Brunn–Minkowski conjecture"
family: "091"
discipline: "Convex and metric geometry"
formalized: true
source: null
pdfname: ""
---

{% raw %}
# 解读 | The logarithmic Brunn–Minkowski conjecture

> 结果族 091：Logarithmic and `@@M@@L_p@@` Brunn–Minkowski inequalities and the B-conjecture　·　学科：Convex and metric geometry　·　验证状态：主结果已 Lean 形式化

## 入门导读 🐣

两块左右对称的"石头"按比例混合，经典结论保证混合体的体积不小于体积的加权平均。这篇论文证明更强的版本：按"几何平均"方式混合（每个方向的伸展取两种石头的几何平均），体积同样不缩水——相当于把"算术平均 ≥ 几何平均"这句口诀升级成任意维凸体的体积定律，一举解决 2012 年悬置的对数 Brunn–Minkowski 猜想。

**关键词卡片**

- 凸体（convex body）：有界、内部充实的凸集。
- 支撑函数（support function）：`@@M@@h_K(u)@@`，从原点看，方向 `@@M@@u@@` 上影子伸到的最远距离。
- Wulff 体（Wulff body）：按"每个方向给定半径"交出的包络体，晶体长成的形状。
- 对数凹测度（log-concave measure）：密度形如 `@@M@@e^{-V}@@`（`@@M@@V@@` 为凸函数）的概率分布。
- `@@M@@(B)@@`-猜想：`@@M@@t\mapsto\mu(e^tK)@@` 对数凹——指数放大凸体时测度先增后减。

**看个具体例子**

一维热身：取对称区间 `@@M@@K=[-1,1]@@`（长 2）与 `@@M@@L=[-2,2]@@`（长 4），`@@M@@\lambda=\tfrac12@@`。支撑函数的几何平均 `@@M@@1^{1/2}\cdot 2^{1/2}=\sqrt2@@` 给出 Wulff 体 `@@M@@[-\sqrt2,\sqrt2]@@`，长 `@@M@@2\sqrt2\approx 2.83@@`，恰为 `@@M@@\sqrt{2\times 4}@@`——一维情形定理取等；经典 Minkowski 混合则给出长 3 的区间（算术平均）。一维是等式，高维处处是硬仗：两个凸体没有公共的"法方向扇区"，此前只在平面等特殊情形得证，本文在任意维对称凸体上全线证明，并经转移定理自动推广到一切偶对数凹测度。

<div>

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 560 280">
  <text x="280" y="28" font-size="15" text-anchor="middle" fill="#222">一维版：几何平均混合的长度不缩水（此情形取等）</text>
  <rect x="100" y="58" width="360" height="18" rx="9" fill="#e8b78a" stroke="#b07b3a"/>
  <text x="110" y="71" font-size="13" fill="#222">L = [−2, 2]，长 4</text>
  <rect x="190" y="96" width="180" height="18" rx="9" fill="#9fc6e8" stroke="#5a86b8"/>
  <text x="200" y="109" font-size="13" fill="#222">K = [−1, 1]，长 2</text>
  <rect x="153" y="134" width="254" height="18" rx="9" fill="#a8d8a8" stroke="#4e8b4e"/>
  <text x="163" y="147" font-size="13" fill="#222">几何平均混合：长 2√2 ≈ 2.83</text>
  <rect x="145" y="172" width="270" height="18" rx="9" fill="#d8c8e8" stroke="#8a6ab0"/>
  <text x="155" y="185" font-size="13" fill="#222">Minkowski 混合：长 3</text>
  <line x1="80" y1="225" x2="480" y2="225" stroke="#555" stroke-width="2"/>
  <g font-size="13" fill="#333" text-anchor="middle">
    <text x="100" y="248">−2</text>
    <text x="190" y="248">−1</text>
    <text x="280" y="248">0</text>
    <text x="370" y="248">1</text>
    <text x="460" y="248">2</text>
  </g>
</svg>

</div>

**为什么值得关心**

一个证明同时收获三条定理：对数 BM 不等式、`@@M@@0<p<1@@` 的对称 `@@M@@L_p@@` 不等式与 `@@M@@(B)@@`-猜想——凸几何与测度集中领域的核心拼图就此落位。

> 已 Lean 形式化

## 一句话结论

本文证明了任意维数中原点对称凸体的对数 Brunn–Minkowski 不等式：以支撑函数几何平均定义的 Wulff 体，其体积不小于两端体积的几何加权；并连带得到 `@@M@@0<p<1@@` 的加性 `@@M@@L_p@@` 不等式与 `@@M@@(B)@@`-猜想。

## 问题背景

经典 Brunn–Minkowski 不等式断言 Minkowski 和 `@@M@@(1-\lambda)K+\lambda L@@` 的体积满足超强可加性，是凸几何的基石。Firey 的 `@@M@@p@@`-平均（1962）与 Lutwak 的 `@@M@@L_p@@` 混合体积理论（1993）以支撑函数（support function）的幂平均插值代替求和；当 `@@M@@p\downarrow 0@@` 幂平均退化为几何平均，Böröczky–Lutwak–Yang–Zhao 于 2012 年将相应体积不等式列为公开问题（Problem 1.1），即对数 Brunn–Minkowski 猜想，它与锥体积测度（cone-volume measure）及对数 Minkowski 问题关系密切。此前仅平面（BLYZ 2012）、同一正交基下无条件（unconditional，Saroglou 2015）、共享反射对称（Böröczky–Kalantzopoulos 2022）、复范数球（Rotem）等特例得证；一般情形的障碍在于两体没有公共法扇（normal fan），局部二阶变分与谱方法难以闭合为全局不等式。Stancu（2018）曾宣布全维数结果，但流渐近分析细节被搁置。

## 主要结果

记 `@@M@@h_K(u)=\max_{x\in K}\langle x,u\rangle@@` 为支撑函数；对球面上的正连续函数 `@@M@@f@@`，其 Wulff 体（Wulff body）为 `@@M@@\mathcal W[f]=\bigcap_{u\in S^{n-1}}\{x\in\mathbb R^n:\langle x,u\rangle\le f(u)\}@@`。

**定理（偶对数 Brunn–Minkowski 不等式）**：设 `@@M@@n\ge1@@`，`@@M@@K=-K@@`、`@@M@@L=-L@@` 为 `@@M@@\mathbb R^n@@` 中的凸体，则对一切 `@@M@@0\le\lambda\le1@@`，
`@@M@@D\bigl|\mathcal W[h_K^{1-\lambda}h_L^\lambda]\bigr|\ \ge\ |K|^{1-\lambda}|L|^\lambda .@@`
由算术–几何平均不等式 `@@M@@\mathcal W[h_K^{1-\lambda}h_L^\lambda]\subset(1-\lambda)K+\lambda L@@`，故该定理在对称框架下严格强于经典乘法形式；而 `@@M@@h_K^{1-\lambda}h_L^\lambda@@` 一般并不是支撑函数，Wulff 交必不可少。

**推论（对称 `@@M@@L_p@@` Brunn–Minkowski 不等式）**：对全维原点对称凸体与 `@@M@@0<p<1@@`，
`@@M@@D\Bigl|\mathcal W\bigl[\bigl((1-\lambda)h_K^p+\lambda h_L^p\bigr)^{1/p}\bigr]\Bigr|^{p/n}\ \ge\ (1-\lambda)|K|^{p/n}+\lambda|L|^{p/n}.@@`
对数端点经 BLYZ 记录的单调蕴含给出中间范围，再归一化与重加权即得加性形式。

**测度论推论**：由 Saroglou 的转移定理，Lebesgue 情形的定理自动迁移到一切偶对数凹（log-concave）Radon 测度 `@@M@@\mathrm d\mu=e^{-V(x)}\mathrm dx@@`；取单个对称凸体的两个标量伸缩 `@@M@@e^tK@@`，即得 `@@M@@(B)@@`-猜想：`@@M@@t\mapsto\mu(e^tK)@@` 在 `@@M@@\mathbb R@@` 上对数凹。论文还处理支撑在真子空间上的此类测度。

## 证明思路

整体是"光滑化—方差界—取极限"的三段式。

先把几何问题化为分析问题。对有限组约束 `@@M@@|\langle p_i,x\rangle|\le h_i(t)@@` 定义的对称多面体 `@@M@@P(t)@@`，令宽度按几何方式变化 `@@M@@h_i(t)=(h_i^0)^{1-t}(h_i^1)^t@@`，并用光滑权重 `@@M@@\exp\bigl(-\frac\eps2|x|^2-\sum_i(\langle p_i,x\rangle/h_i)^q\bigr)@@`（`@@M@@q\ge2@@` 偶，`@@M@@\eps>0@@`）替代指示函数。其积分 `@@M@@Z_{q,\eps}(t)@@` 满足 `@@M@@\frac{d^2}{dt^2}\log Z_{q,\eps}=\mathrm{Var}_\mu(\dot V)-\E_\mu\ddot V@@`，其中 `@@M@@\psi_i=(\langle p_i,x\rangle/h_i)^q@@`，`@@M@@\dot V=\sum_i b_i\psi_i@@`，`@@M@@\ddot V=\sum_i b_i^2\psi_i@@`。于是体积不等式归结为方差估计 `@@M@@\mathrm{Var}_\mu(\sum_i b_i\psi_i)\le\sum_i b_i^2\E_\mu\psi_i@@`。

再构造矩量坐标（moment coordinates）。从 Berman–Berndtsson 的紧矩量定理（截断到球）与 Klartag 的 Hessian 估计 `@@M@@0<D^2\varphi_R\le\frac4\eps I@@`（常数与截断半径无关）出发，经 Evans–Krylov 与 Schauder 内估计取对角极限，得到全空间上的偶位势 `@@M@@\varphi@@`：梯度映射 `@@M@@x=\nabla\varphi(z)@@` 是把 `@@M@@\mathrm d\nu=e^{-\varphi}\mathrm dz@@` 推为 `@@M@@\mu@@` 的微分同胚，其 Hessian `@@M@@\tau@@` 处处正定且一致有上界；`@@M@@\tau@@` 正是 Fathi 意义下的 Stein 核。由算子 `@@M@@Af=\delta_\mu(\tau\nabla_x f)@@` 生成的测试函数 `@@M@@u=A(A-1)f@@` 是中心化的偶函数，且在 `@@M@@L^2(\mu)@@` 的中心化偶子空间中稠密——仅有的障碍是仿射函数：中心化消去常数，偶性消去线性项。

核心一步是张量估计。加权 Bochner 恒等式（Bochner identity）给出 `@@M@@\E u^2=\E W^THW+\E\tr\bigl((D_xW)^2\bigr)@@`，还需证 `@@M@@\E\tr\bigl((D_xW)^2\bigr)\ge\E\tr(MBHB)@@`：将矩量方程微分两次并与另一展开式比较，把差在 `@@M@@\tau=I@@` 的规范坐标下写成显式平方和 `@@M@@2\|S+\operatorname{Sym}J\|^2+\frac16\|J-J^{(12)}\|^2\ge0@@`。

最后用齐次性（homogeneity）收网：`@@M@@x\cdot\nabla\psi_i=q\psi_i@@`，两次 Cauchy–Schwarz 分别给出 `@@M@@d_i^2\le m_i\,\E\tr(MBH_iB)@@` 与 `@@M@@\E W^TH_iW\ge(q-1)d_i^2/m_i@@`，相加恰得 `@@M@@\sum_i d_i^2/a_i\le\E u^2@@`——逐项控制每个齐次和项是本方法的独有之处。稠密性把该估计延拓到一切中心化偶函数，取 `@@M@@u=\sum_i b_i\psi_i-\E@@` 再用一次 Cauchy–Schwarz 即得方差界。极限过渡分三层：`@@M@@q\to\infty@@` 时积分收敛到 Gauss 权重限制在 `@@M@@P(t)@@` 上（例外集仅限有限个超平面），`@@M@@\eps\downarrow0@@` 时由单调收敛得多面体体积不等式，方向族加密取交得到一般 Wulff 体（测度自上连续）；一维情形直接是等式。

## 可信度与备注

任务元数据标注主结果已完成 Lean 形式化（家族文档 lean/docs/091.md），本文亦给出完整自足的数学论证。定理、`@@M@@L_p@@` 推论与 `@@M@@(B)@@`-猜想出自同一证明链并与 Saroglou 转移定理严格衔接，互相支撑；作者说明方差估计只需矩量 Hessian 的全局上界与逐点正定性，不需全局下界。按 OpenAI 官方声明，未经形式化的结果可能有问题；本文主结果属已形式化之列，外围组合论断仍建议以社区核验为准。

{% endraw %}
