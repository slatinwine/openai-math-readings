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

> 结果族 091：Logarithmic and \(L_p\) Brunn–Minkowski inequalities and the B-conjecture　·　学科：Convex and metric geometry　·　验证状态：主结果已 Lean 形式化

## 一句话结论

本文证明了任意维数中原点对称凸体的对数 Brunn–Minkowski 不等式：以支撑函数几何平均定义的 Wulff 体，其体积不小于两端体积的几何加权；并连带得到 \(0<p<1\) 的加性 \(L_p\) 不等式与 \((B)\)-猜想。

## 问题背景

经典 Brunn–Minkowski 不等式断言 Minkowski 和 \((1-\lambda)K+\lambda L\) 的体积满足超强可加性，是凸几何的基石。Firey 的 \(p\)-平均（1962）与 Lutwak 的 \(L_p\) 混合体积理论（1993）以支撑函数（support function）的幂平均插值代替求和；当 \(p\downarrow 0\) 幂平均退化为几何平均，Böröczky–Lutwak–Yang–Zhao 于 2012 年将相应体积不等式列为公开问题（Problem 1.1），即对数 Brunn–Minkowski 猜想，它与锥体积测度（cone-volume measure）及对数 Minkowski 问题关系密切。此前仅平面（BLYZ 2012）、同一正交基下无条件（unconditional，Saroglou 2015）、共享反射对称（Böröczky–Kalantzopoulos 2022）、复范数球（Rotem）等特例得证；一般情形的障碍在于两体没有公共法扇（normal fan），局部二阶变分与谱方法难以闭合为全局不等式。Stancu（2018）曾宣布全维数结果，但流渐近分析细节被搁置。

## 主要结果

记 \(h_K(u)=\max_{x\in K}\langle x,u\rangle\) 为支撑函数；对球面上的正连续函数 \(f\)，其 Wulff 体（Wulff body）为 \(\mathcal W[f]=\bigcap_{u\in S^{n-1}}\{x\in\mathbb R^n:\langle x,u\rangle\le f(u)\}\)。

**定理（偶对数 Brunn–Minkowski 不等式）**：设 \(n\ge1\)，\(K=-K\)、\(L=-L\) 为 \(\mathbb R^n\) 中的凸体，则对一切 \(0\le\lambda\le1\)，
\[\bigl|\mathcal W[h_K^{1-\lambda}h_L^\lambda]\bigr|\ \ge\ |K|^{1-\lambda}|L|^\lambda .\]
由算术–几何平均不等式 \(\mathcal W[h_K^{1-\lambda}h_L^\lambda]\subset(1-\lambda)K+\lambda L\)，故该定理在对称框架下严格强于经典乘法形式；而 \(h_K^{1-\lambda}h_L^\lambda\) 一般并不是支撑函数，Wulff 交必不可少。

**推论（对称 \(L_p\) Brunn–Minkowski 不等式）**：对全维原点对称凸体与 \(0<p<1\)，
\[\Bigl|\mathcal W\bigl[\bigl((1-\lambda)h_K^p+\lambda h_L^p\bigr)^{1/p}\bigr]\Bigr|^{p/n}\ \ge\ (1-\lambda)|K|^{p/n}+\lambda|L|^{p/n}.\]
对数端点经 BLYZ 记录的单调蕴含给出中间范围，再归一化与重加权即得加性形式。

**测度论推论**：由 Saroglou 的转移定理，Lebesgue 情形的定理自动迁移到一切偶对数凹（log-concave）Radon 测度 \(\mathrm d\mu=e^{-V(x)}\mathrm dx\)；取单个对称凸体的两个标量伸缩 \(e^tK\)，即得 \((B)\)-猜想：\(t\mapsto\mu(e^tK)\) 在 \(\mathbb R\) 上对数凹。论文还处理支撑在真子空间上的此类测度。

## 证明思路

整体是"光滑化—方差界—取极限"的三段式。

先把几何问题化为分析问题。对有限组约束 \(|\langle p_i,x\rangle|\le h_i(t)\) 定义的对称多面体 \(P(t)\)，令宽度按几何方式变化 \(h_i(t)=(h_i^0)^{1-t}(h_i^1)^t\)，并用光滑权重 \(\exp\bigl(-\frac\eps2|x|^2-\sum_i(\langle p_i,x\rangle/h_i)^q\bigr)\)（\(q\ge2\) 偶，\(\eps>0\)）替代指示函数。其积分 \(Z_{q,\eps}(t)\) 满足 \(\frac{d^2}{dt^2}\log Z_{q,\eps}=\mathrm{Var}_\mu(\dot V)-\E_\mu\ddot V\)，其中 \(\psi_i=(\langle p_i,x\rangle/h_i)^q\)，\(\dot V=\sum_i b_i\psi_i\)，\(\ddot V=\sum_i b_i^2\psi_i\)。于是体积不等式归结为方差估计 \(\mathrm{Var}_\mu(\sum_i b_i\psi_i)\le\sum_i b_i^2\E_\mu\psi_i\)。

再构造矩量坐标（moment coordinates）。从 Berman–Berndtsson 的紧矩量定理（截断到球）与 Klartag 的 Hessian 估计 \(0<D^2\varphi_R\le\frac4\eps I\)（常数与截断半径无关）出发，经 Evans–Krylov 与 Schauder 内估计取对角极限，得到全空间上的偶位势 \(\varphi\)：梯度映射 \(x=\nabla\varphi(z)\) 是把 \(\mathrm d\nu=e^{-\varphi}\mathrm dz\) 推为 \(\mu\) 的微分同胚，其 Hessian \(\tau\) 处处正定且一致有上界；\(\tau\) 正是 Fathi 意义下的 Stein 核。由算子 \(Af=\delta_\mu(\tau\nabla_x f)\) 生成的测试函数 \(u=A(A-1)f\) 是中心化的偶函数，且在 \(L^2(\mu)\) 的中心化偶子空间中稠密——仅有的障碍是仿射函数：中心化消去常数，偶性消去线性项。

核心一步是张量估计。加权 Bochner 恒等式（Bochner identity）给出 \(\E u^2=\E W^THW+\E\tr\bigl((D_xW)^2\bigr)\)，还需证 \(\E\tr\bigl((D_xW)^2\bigr)\ge\E\tr(MBHB)\)：将矩量方程微分两次并与另一展开式比较，把差在 \(\tau=I\) 的规范坐标下写成显式平方和 \(2\|S+\operatorname{Sym}J\|^2+\frac16\|J-J^{(12)}\|^2\ge0\)。

最后用齐次性（homogeneity）收网：\(x\cdot\nabla\psi_i=q\psi_i\)，两次 Cauchy–Schwarz 分别给出 \(d_i^2\le m_i\,\E\tr(MBH_iB)\) 与 \(\E W^TH_iW\ge(q-1)d_i^2/m_i\)，相加恰得 \(\sum_i d_i^2/a_i\le\E u^2\)——逐项控制每个齐次和项是本方法的独有之处。稠密性把该估计延拓到一切中心化偶函数，取 \(u=\sum_i b_i\psi_i-\E\) 再用一次 Cauchy–Schwarz 即得方差界。极限过渡分三层：\(q\to\infty\) 时积分收敛到 Gauss 权重限制在 \(P(t)\) 上（例外集仅限有限个超平面），\(\eps\downarrow0\) 时由单调收敛得多面体体积不等式，方向族加密取交得到一般 Wulff 体（测度自上连续）；一维情形直接是等式。

## 可信度与备注

任务元数据标注主结果已完成 Lean 形式化（家族文档 lean/docs/091.md），本文亦给出完整自足的数学论证。定理、\(L_p\) 推论与 \((B)\)-猜想出自同一证明链并与 Saroglou 转移定理严格衔接，互相支撑；作者说明方差估计只需矩量 Hessian 的全局上界与逐点正定性，不需全局下界。按 OpenAI 官方声明，未经形式化的结果可能有问题；本文主结果属已形式化之列，外围组合论断仍建议以社区核验为准。

{% endraw %}
