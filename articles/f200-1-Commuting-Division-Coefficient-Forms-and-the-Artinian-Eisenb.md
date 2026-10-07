---
layout: default
title: "Commuting Division-Coefficient Forms and the Artinian Eisenbud--Green--Harris Conjecture"
family: "200"
discipline: "Algebra"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | Commuting Division-Coefficient Forms and the Artinian Eisenbud--Green--Harris Conjecture

> 结果族 200：Eisenbud–Green–Harris and lex-plus-powers　·　学科：Algebra　·　验证状态：暂无形式化证明，请以社区核验为准

## 一句话结论

在 \(\C\) 上构造性地证明了 Artinian 情形的 Eisenbud–Green–Harris 猜想：任何包含正则序列（次数 \(\ge2\)、任意长度）的齐次理想，都与某个含相应纯幂的单项式理想有相同的 Hilbert 函数，并经归约推广到全部特征零域。

## 问题背景

EGH 猜想源自 Eisenbud–Green–Harris 在 1990 年代对高维 Castelnuovo 理论与 Cayley–Bacharach 问题的研究：若齐次理想 \(I\) 包含次数为 \(a_1,\ldots,a_c\ge 2\) 的正则序列（regular sequence），则应存在包含纯幂 \(x_i^{a_i}\) 的单项式理想与 \(S/I\) 有相同的 Hilbert 函数——纯幂模型把几何约束化为"指数有界单项式"的计数问题。此前最好的一般结果均附加条件：Caviglia–Maclagan 与 Caviglia–De Stefani 要求次数满足增长不等式（如 \(a_i\ge\sum_{j<i}(a_j-1)\)）；Abedelfatah 要求型分裂为线性因子；Chen 与 Caviglia–De Stefani–Sbarra 只覆盖少量变量的二次型；Cooper、Chong 借 liaison 处理特殊理想类。任意次数、任意型的完整陈述一直悬而未决。本文的突破口是一个看似无关的工具：有限维中心除代数（central division algebra）。

## 主要结果

定理 1.1（交换型构造）：设 \(f_1,\ldots,f_n\) 是 \(\C[x_1,\ldots,x_n]\) 中次数 \(2\le a_1\le\cdots\le a_n\) 的齐次正则序列。则存在有限生成域扩张 \(k/\C\)、有限维中心除代数 \(\Delta\)，以及由有限多个两两交换的线性型生成的交换分次 \(k\)-子代数 \(k[x]\subseteq A\subseteq\Delta[x]\)，其中有线性型 \(t_1,\ldots,t_n\) 满足三角幂恒等式
\[t_i^{a_i}=c_if_i+\sum_{l<i}B_{il}f_l+\sum_{d>i}C_{id}t_d\qquad(c_i\in k^\times),\]
且有序单项式 \(\{t_1^{\alpha_1}\cdots t_n^{\alpha_n}\}\) 构成整个多项式代数 \(\Delta[x]\) 的左 \(\Delta\)-基——基覆盖全代数而非仅完全交商。推论 1.2（Artinian EGH）：包含该序列的任何齐次理想 \(I\) 都与某个含全部 \(x_i^{a_i}\) 的单项式理想有相同的 Hilbert 函数；借助 Clements–Lindström 压缩还可取 lex-plus-powers 理想。推论 1.3 经 Artinian 归约与系数域下降，推广到特征零任意域、长度 \(c\le n\) 的情形。第九节另给出两个应用：同一 lex-plus-powers 理想的局部上同调（local cohomology）逐层不等式，以及二次 Cayley–Bacharach 界——\(r\) 个二次超曲面的完全交 \(\Omega\) 若不含于 \(k\) 次超面 \(X\)，则 \(\deg(\Omega\cap X)\le 2^r-2^{r-k}\)。

## 证明思路

代数归约先行（第二节）：三角恒等式使 \(t_i\) 成为有限模 \(\Delta[x]\) 上的正则参数系，Hilbert 级数逐度计数给出全代数的有序基；再对扩张理想中元素取 \(t\)-展开的最小指数（按 \(\alpha_n,\ldots,\alpha_1\) 的字典序），所有最小指数构成向上封闭集 \(E\)，因而定义一个单项式理想 \(J\)；三角形状保证 \(a_i\mathbf e_i\in E\)，互补指数计数便给出 Hilbert 函数等式。于是全部困难集中于构造恒等式本身。构造按行自 \(i=n\) 递降到 \(1\)：在某步次数 \(b=a_i\)，先把适当的右端写成已有型的 \(b\) 次幂之和 \(\ell_1^b+\cdots+\ell_M^b\)，再用"二元加法矩阵"两两合并，直至得到单个 \(t_i^b\)。两个难点主导设计：加法矩阵的系数必须落在包含旧系数的除代数中；当下一个次数更小时，早先更高次的幂恒等式必须仍然可用。为此引入形式线性型空间 \(U\) 与一、二次生成的理想 \(Q\subseteq\Sym U\)：消没 \(\mathfrak j_b=(Q,f_1,\ldots,f_i,t_{i+1},\ldots,t_n)_b\) 的线性泛函 \(\lambda\) 给出多项式 \(w_\lambda(\ell)=\lambda(\ell^b)\)，其公共零集的射影化 \(X\) 是约束空间。几何保障在于：\(Q\) 的射影零集不含低度数的曲线，每个非零 \(w\in W\) 都带单重不可约因子，从而取足够多块后 \(X\) 是整完全交（complete intersection），且其光滑轨迹上的锥任意高连通。二元加法矩阵来自一条带三截面 \(z^b=u^b+v^b\) 的曲线：取一般的零度线丛，使这三个截面的乘法矩阵线性地依赖 \(u,v\)——此即 van den Bergh 与 Kulkarni 的广义 Clifford/矩阵束对应。曲线的两个 Picard 簇分工明确：零度部分参数化矩阵，一度部分提供自由有限群作用与携带指定特征的映射。等变下降先得中心单代数；为证它确是除代数，文章证明每个有限右模的维数都被代数维数整除——非平凡右理想会与此矛盾。该可整除性经 Knudsen–Mumford 的上同调行列式修正与 Riemann–Roch 化为 Picard 簇乘积上族的欧拉特征之比较，再由特征映射、连通性与整拓扑 K 理论完成（方法上承 Godeaux–Serre 逼近与 Antieau–Williams 的指标限制）。最后的装配环节验证特征不变性、经有限扩张保留新行，闭合归纳。

## 可信度与备注

本文是家族的代数引擎：姊妹篇《The Artinian Lex-Plus-Powers Betti Theorem》直接引用本文 Theorem 1.1 作为全部构造输入，并在其上新增分辨转移，得到更强的 graded Betti 数不等式；两篇合起来给出特征零上 EGH 与 lex-plus-powers 猜想的完整解决。两篇均无 Lean 形式化证明，OpenAI 官方声明"未经形式化的结果可能有问题"，请以社区核验为准。

{% endraw %}
