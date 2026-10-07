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

## 一句话结论

本文推翻了 Gopalan–Servedio 的平方根度猜想，且连常数倍都不留：对任意 \(C>0\) 都存在布尔函数 \(f\) 使 \(\sum_i\widehat f(\{i\})>C\sqrt{\deg(f)}\)，即线性 Fourier 系数之和与多项式度之间不存在任何常数倍的平方根约束。

## 问题背景

在布尔函数分析（analysis of Boolean functions）中，\(f:\{-1,1\}^n\to\{-1,1\}\) 的 Fourier 系数定义为 \(\widehat f(S)=\mathbb E[f(X)\prod_{i\in S}X_i]\)。一阶（单点集）系数之和 \(\sum_i\widehat f(\{i\})=\mathbb E[f(X)\sum_iX_i]\) 度量 \(f\) 与"输入总和"的带符号总相关，Cauchy–Schwarz 给出平凡上界 \(\sqrt n\)。约 2009 年，Gopalan 与 Servedio 猜想（见 O'Donnell 问题清单，亦为 Filmus–Hatami–Keller–Lifshitz 预印本中的猜想 3.17）可将 \(\sqrt n\) 换成 \(\sqrt{\deg(f)}\)，其中 \(\deg(f)\) 是表示 \(f\) 的实多重线性多项式（real multilinear polynomial）的次数。若成立，函数的线性可预测性便与其代数复杂度直接绑定，这对电路下界与学习理论都有意义。此前进展零散：Jha 与 Wang 给出等价形式并验证个别度数，Kudin–Pašalić 证明了 \(d=2,3\) 并在 \(d=4\) 反驳了更强的"多数函数基准"变体。另一方面，Nisan–Szegedy 的总影响力（total influence）不等式给出恒成立的线性界 \(\sum_i|\widehat f(\{i\})|\le\deg(f)\)，争论焦点正是平方根尺度是否真实。

## 主要结果

主定理：对任意实数 \(C>0\)，存在正整数 \(n\) 与非常量布尔函数 \(f:\{-1,1\}^n\to\{-1,1\}\)，满足
\[\sum_{i=1}^n\widehat f(\{i\})>C\sqrt{\deg(f)}.\]
因此比值 \(\sum_i|\widehat f(\{i\})|/\sqrt{\deg(f)}\) 在所有非常量布尔函数上的上确界为无穷——原猜想连"差一个常数倍"的弱化版本也无法幸存。带符号与绝对值两种表述等价：作坐标翻转 \(x_i\mapsto\operatorname{sign}(\widehat f(\{i\}))x_i\)（零处取 \(+1\)）即把所有一阶系数化为非负。作者强调构造中的维数与各步复制数均为有限，但未给出有用的增长界。

## 证明思路

证明分三层：先把布尔问题化成"观测"问题，再设计能逐步放大优势的报道规则，最后做符号读出。第一层不直接构造 \(f\)，而是构造关于比特和 \(H_N=X_1+\cdots+X_N\) 的有限值观测 \(F\)：其得分（score）为 \(T_F=\mathbb E[H_N\mid F]\)，保留方差（retained variance）为 \(v(F)=\mathbb E\,T_F^2\)，而 \(D\) 是胞度界（cell degree bound），即每个输出指示函数 \(\mathbf 1_{\{F=a\}}\) 的次数不超过 \(D\)。对 \(M\) 份独立复制取 \(f=\operatorname{sign}(T_1+\cdots+T_M)\)，条件期望给出 \(\sum_i\widehat f(\{i\})=\mathbb E|T_1+\cdots+T_M|=\sqrt{Mv(F)}\,\mathbb E|Z_M|\)，中心极限定理使 \(\mathbb E|Z_M|\to\sqrt{2/\pi}\)，而 \(\deg(f)\le MD\)。于是只要某个观测满足 \(v(F)/D>4C^2\)，定理即得。第二层是放大（amplification）：从"显示单个符号"（\(v=D=1\)）出发，每步把 \(r\) 组独立复制的标准化得分（近似标准正态）送入固定报道规则 \(\mathcal W\)；若每个输出指示函数都是至多依赖 \(d\) 个坐标的函数的线性组合，且规则能从 \(r\) 个输入之和中保留方差 \(d+\eta\)，则 \(v/D\) 每步至少乘 \(1+\eta/d\)，有限步迭代超过任意预设值。第三层是规则的灵魂。输入 \((u,z_1,\dots,z_m)\)（\(r=m+1\)，\(d=m\)），\(u\) 选出叶子 \(z_{\iota(u)}\)，各配小区间 \(I_j\)。常规报道总留下恰好一个未观察输入，每份报道恰好残留单位误差、共保留方差 \(m\)；唯一例外是事件 \(A\)——恰好被选中的叶子未落入自己的区间——此时只报道一个标签。妙处有二。其一，\(A\) 的指示函数满足逐点相消恒等式 \(\mathbf 1_A=\sum_i\mathbf 1_{\{\iota(u)=i\}}\prod_{j\ne i}\mathbf 1_{I_j}(z_j)-\prod_j\mathbf 1_{I_j}(z_j)\)，每项只用 \(m\) 个坐标：度节省来自相消（cancellation），而非无视某个固定坐标。其二，把区间中心铺成总半宽 \(R=\sqrt{8\log m}\)、单格半宽 \(h=m^{-3/2}\) 的网格，让 \(\iota(t)\) 选最接近 \(1+t\) 的中心，则在 \(A\) 上总和 \(L=u+\sum_jz_j\) 集中于常数 \(b\) 附近；高斯模型下有精确恒等式 \(d_A=p_*(1+S-J)\)，估计可将误差项 \(J\) 压到 \(1/4\) 以下，故 \(A\) 上的预测误差小于 \(1\)，保留方差严格超过 \(m\)。最后用传递引理（借一致四阶矩保证的一致可积性）把高斯增益搬到有限符号立方，各阶段由中心极限定理选定足够大的有限复制数，有限步后符号读出即证定理。论文另给出三条独立备选路线——合并"全通过"报道的粗报道、切换到额外独立输入的规则、只要求保留方差超过平均代价的均值代价放大——从不同侧面印证同一构造原理。

## 可信度与备注

本篇主结果暂无形式化证明，请以社区核验为准；OpenAI 官方亦声明"未经形式化的结果可能有问题"。就内部结构而言，论文第 1、2 节自含完整证明，第 3、4 节及附录又给出粗报道、切换规则、均值代价放大等彼此独立的替代路径，同一放大原理的多重实现互相支撑，降低了单点出错的风险。构造对维数增长无有效界，复核重点宜放在例外事件的度恒等式与高斯区间估计两处。

{% endraw %}
