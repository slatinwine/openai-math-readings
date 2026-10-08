---
layout: default
title: "Unbounded Violations of the Square-Root Degree Bound"
family: "192"
discipline: "Combinatorics"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | Unbounded Violations of the Square-Root Degree Bound

> 结果族 192：Boolean functions violate the square-root degree bound by arbitrary factors　·　学科：Combinatorics　·　验证状态：暂无形式化证明，请以社区核验为准

## 入门导读 🐣

n 位评委各投 +1 或 −1 票，规则 f 把选票汇总成"通过/否决"。每位评委的话语权可以量化成一个数（线性 Fourier 系数）。曾有人猜想：如果规则在代数上很简单（能用低次多项式写出），全体评委带方向的话语权之和至多是"次数的平方根"再乘个常数。本文构造出把任何常数倍都远远甩开的规则。若猜想成立，规则的线性可预测性就与其代数复杂度直接绑定，对电路下界与机器学习理论都有意义——如今这条锁链被证明根本不存在。

**关键词卡片**

- 布尔函数（Boolean function）：把 `@@M@@n@@` 个 `@@M@@\pm1@@` 输入映成 `@@M@@\pm1@@` 输出的规则。
- Fourier 系数 `@@M@@\widehat f(\{i\})@@`：第 `@@M@@i@@` 位输入与输出的平均相关度。
- 度 `@@M@@\deg(f)@@`：写出 `@@M@@f@@` 的多重线性多项式的次数，衡量规则的代数复杂度。
- 放大（amplification）：复制独立样本、送入固定规则再取符号，让优势逐级扩大的技术。

**看个具体例子**

<div>

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 560 280">
<text x="280" y="40" text-anchor="middle" font-size="14">放大流水线：复制 → 报道规则 → 取符号</text>
<rect x="50" y="100" width="120" height="60" fill="none" stroke="#222" stroke-width="1.5"/>
<text x="110" y="125" text-anchor="middle" font-size="13">第 1 步：比值</text>
<text x="110" y="146" text-anchor="middle" font-size="13">v/D = 1</text>
<rect x="225" y="100" width="120" height="60" fill="none" stroke="#222" stroke-width="1.5"/>
<text x="285" y="125" text-anchor="middle" font-size="13">第 2 步：比值</text>
<text x="285" y="146" text-anchor="middle" font-size="13">×(1+η/d)</text>
<rect x="400" y="100" width="120" height="60" fill="none" stroke="#222" stroke-width="1.5"/>
<text x="460" y="125" text-anchor="middle" font-size="13">第 k 步：比值</text>
<text x="460" y="146" text-anchor="middle" font-size="13">&gt; 4C²</text>
<line x1="170" y1="130" x2="216" y2="130" stroke="#222" stroke-width="2"/>
<polygon points="216,125 216,135 228,130" fill="#222"/>
<text x="197" y="120" text-anchor="middle" font-size="12">放大</text>
<line x1="345" y1="130" x2="391" y2="130" stroke="#222" stroke-width="2"/>
<polygon points="391,125 391,135 403,130" fill="#222"/>
<text x="372" y="120" text-anchor="middle" font-size="12">放大</text>
<text x="280" y="205" text-anchor="middle" font-size="13">有限步后，v/D 超过任意预设值</text>
<text x="280" y="245" text-anchor="middle" font-size="13">数字版定理：取 C = 10⁶，存在 f 使 Σ f̂({i}) &gt; 10⁶·√deg(f)</text>
</svg>

</div>

数字版定理：任取 `@@M@@C=10^6@@`，都存在布尔函数 `@@M@@f@@` 使 `@@M@@\sum_i\widehat f(\{i\})>10^6\sqrt{\deg(f)}@@`。构造像滚雪球：从比值 `@@M@@v/D=1@@` 出发，每步把多份独立复制送进固定报道规则再取符号，比值至少乘 `@@M@@1+\eta/d@@`，有限步后超过 `@@M@@4C^2@@`。

**为什么值得关心**

它推翻了 Gopalan–Servedio 的平方根度猜想，连"差个常数倍"的退让版本也不能幸存——布尔函数的线性可预测性与代数复杂度之间，不存在简单的平方根锁链。

> 暂无形式化证明（AI 结果待核验）

## 一句话结论

本文推翻了 Gopalan–Servedio 的平方根度猜想，且连常数倍都不留：对任意 `@@M@@C>0@@` 都存在布尔函数 `@@M@@f@@` 使 `@@M@@\sum_i\widehat f(\{i\})>C\sqrt{\deg(f)}@@`，即线性 Fourier 系数之和与多项式度之间不存在任何常数倍的平方根约束。

## 问题背景

在布尔函数分析（analysis of Boolean functions）中，`@@M@@f:\{-1,1\}^n\to\{-1,1\}@@` 的 Fourier 系数定义为 `@@M@@\widehat f(S)=\mathbb E[f(X)\prod_{i\in S}X_i]@@`。一阶（单点集）系数之和 `@@M@@\sum_i\widehat f(\{i\})=\mathbb E[f(X)\sum_iX_i]@@` 度量 `@@M@@f@@` 与"输入总和"的带符号总相关，Cauchy–Schwarz 给出平凡上界 `@@M@@\sqrt n@@`。约 2009 年，Gopalan 与 Servedio 猜想（见 O'Donnell 问题清单，亦为 Filmus–Hatami–Keller–Lifshitz 预印本中的猜想 3.17）可将 `@@M@@\sqrt n@@` 换成 `@@M@@\sqrt{\deg(f)}@@`，其中 `@@M@@\deg(f)@@` 是表示 `@@M@@f@@` 的实多重线性多项式（real multilinear polynomial）的次数。若成立，函数的线性可预测性便与其代数复杂度直接绑定，这对电路下界与学习理论都有意义。此前进展零散：Jha 与 Wang 给出等价形式并验证个别度数，Kudin–Pašalić 证明了 `@@M@@d=2,3@@` 并在 `@@M@@d=4@@` 反驳了更强的"多数函数基准"变体。另一方面，Nisan–Szegedy 的总影响力（total influence）不等式给出恒成立的线性界 `@@M@@\sum_i|\widehat f(\{i\})|\le\deg(f)@@`，争论焦点正是平方根尺度是否真实。

## 主要结果

主定理：对任意实数 `@@M@@C>0@@`，存在正整数 `@@M@@n@@` 与非常量布尔函数 `@@M@@f:\{-1,1\}^n\to\{-1,1\}@@`，满足
`@@M@@D\sum_{i=1}^n\widehat f(\{i\})>C\sqrt{\deg(f)}.@@`
因此比值 `@@M@@\sum_i|\widehat f(\{i\})|/\sqrt{\deg(f)}@@` 在所有非常量布尔函数上的上确界为无穷——原猜想连"差一个常数倍"的弱化版本也无法幸存。带符号与绝对值两种表述等价：作坐标翻转 `@@M@@x_i\mapsto\operatorname{sign}(\widehat f(\{i\}))x_i@@`（零处取 `@@M@@+1@@`）即把所有一阶系数化为非负。作者强调构造中的维数与各步复制数均为有限，但未给出有用的增长界。

## 证明思路

证明分三层：先把布尔问题化成"观测"问题，再设计能逐步放大优势的报道规则，最后做符号读出。第一层不直接构造 `@@M@@f@@`，而是构造关于比特和 `@@M@@H_N=X_1+\cdots+X_N@@` 的有限值观测 `@@M@@F@@`：其得分（score）为 `@@M@@T_F=\mathbb E[H_N\mid F]@@`，保留方差（retained variance）为 `@@M@@v(F)=\mathbb E\,T_F^2@@`，而 `@@M@@D@@` 是胞度界（cell degree bound），即每个输出指示函数 `@@M@@\mathbf 1_{\{F=a\}}@@` 的次数不超过 `@@M@@D@@`。对 `@@M@@M@@` 份独立复制取 `@@M@@f=\operatorname{sign}(T_1+\cdots+T_M)@@`，条件期望给出 `@@M@@\sum_i\widehat f(\{i\})=\mathbb E|T_1+\cdots+T_M|=\sqrt{Mv(F)}\,\mathbb E|Z_M|@@`，中心极限定理使 `@@M@@\mathbb E|Z_M|\to\sqrt{2/\pi}@@`，而 `@@M@@\deg(f)\le MD@@`。于是只要某个观测满足 `@@M@@v(F)/D>4C^2@@`，定理即得。第二层是放大（amplification）：从"显示单个符号"（`@@M@@v=D=1@@`）出发，每步把 `@@M@@r@@` 组独立复制的标准化得分（近似标准正态）送入固定报道规则 `@@M@@\mathcal W@@`；若每个输出指示函数都是至多依赖 `@@M@@d@@` 个坐标的函数的线性组合，且规则能从 `@@M@@r@@` 个输入之和中保留方差 `@@M@@d+\eta@@`，则 `@@M@@v/D@@` 每步至少乘 `@@M@@1+\eta/d@@`，有限步迭代超过任意预设值。第三层是规则的灵魂。输入 `@@M@@(u,z_1,\dots,z_m)@@`（`@@M@@r=m+1@@`，`@@M@@d=m@@`），`@@M@@u@@` 选出叶子 `@@M@@z_{\iota(u)}@@`，各配小区间 `@@M@@I_j@@`。常规报道总留下恰好一个未观察输入，每份报道恰好残留单位误差、共保留方差 `@@M@@m@@`；唯一例外是事件 `@@M@@A@@`——恰好被选中的叶子未落入自己的区间——此时只报道一个标签。妙处有二。其一，`@@M@@A@@` 的指示函数满足逐点相消恒等式 `@@M@@\mathbf 1_A=\sum_i\mathbf 1_{\{\iota(u)=i\}}\prod_{j\ne i}\mathbf 1_{I_j}(z_j)-\prod_j\mathbf 1_{I_j}(z_j)@@`，每项只用 `@@M@@m@@` 个坐标：度节省来自相消（cancellation），而非无视某个固定坐标。其二，把区间中心铺成总半宽 `@@M@@R=\sqrt{8\log m}@@`、单格半宽 `@@M@@h=m^{-3/2}@@` 的网格，让 `@@M@@\iota(t)@@` 选最接近 `@@M@@1+t@@` 的中心，则在 `@@M@@A@@` 上总和 `@@M@@L=u+\sum_jz_j@@` 集中于常数 `@@M@@b@@` 附近；高斯模型下有精确恒等式 `@@M@@d_A=p_*(1+S-J)@@`，估计可将误差项 `@@M@@J@@` 压到 `@@M@@1/4@@` 以下，故 `@@M@@A@@` 上的预测误差小于 `@@M@@1@@`，保留方差严格超过 `@@M@@m@@`。最后用传递引理（借一致四阶矩保证的一致可积性）把高斯增益搬到有限符号立方，各阶段由中心极限定理选定足够大的有限复制数，有限步后符号读出即证定理。论文另给出三条独立备选路线——合并"全通过"报道的粗报道、切换到额外独立输入的规则、只要求保留方差超过平均代价的均值代价放大——从不同侧面印证同一构造原理。

## 可信度与备注

本篇主结果暂无形式化证明，请以社区核验为准；OpenAI 官方亦声明"未经形式化的结果可能有问题"。就内部结构而言，论文第 1、2 节自含完整证明，第 3、4 节及附录又给出粗报道、切换规则、均值代价放大等彼此独立的替代路径，同一放大原理的多重实现互相支撑，降低了单点出错的风险。构造对维数增长无有效界，复核重点宜放在例外事件的度恒等式与高斯区间估计两处。

{% endraw %}
