---
layout: default
title: "Monochromatic finite sums and products in the positive integers"
family: "164"
discipline: "Combinatorics"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | Monochromatic finite sums and products in the positive integers

> 结果族 164：Hindman's finite sums and products conjecture　·　学科：Combinatorics　·　验证状态：暂无形式化证明，请以社区核验为准

## 一句话结论

证明了 Hindman 有限和积猜想：对正整数的任意有限染色与任意 \(k\)，都存在 \(k\) 元集合，使其全部非空子集和与非空子集积落在同一颜色中。加性与乘性 Ramsey 性质的同时实现这一 1979 年提出的问题首次得到肯定回答。

## 问题背景

Ramsey 理论的经典线索是：Schur 定理保证任意有限染色的 \(\mathbb N\) 中有单色三元组 \(\{x,y,x+y\}\)；Folkman–Rado–Sanders 有限和定理与 Hindman 无穷有限和定理把它推广到任意大有限集的全部非空子集和。染色经 \(n\mapsto\chi(2^n)\) 转移即得纯乘法版本。但"和与积同时同色"是另一层次的问题：Hindman 在 1980 年构造了一个有限染色，使任何无穷集的元素、两两和与两两积都不同色，无穷版本由此失败；他在 1979 年提出有限猜想——任意有限染色下是否总有任意大的有限集 \(A\) 使 \(\FS(A)\cup\FP(A)\) 单色（Hindman–Strauss 著作 Question 17.18）。此前只在很小规模有结果：Moreira 证明任意有限染色含单色 \(\{x,x+y,xy\}\)，Alweiss 给出多项式证明并在有理数域 \(\mathbb Q\) 上证明完整的有限和积定理，Alweiss–Bowen–Sabok 处理两色的 \(\{x,y,xy,x+iy\}\)。从有理数到整数的过渡是本质障碍：通分后的公共伸缩因子把和放大一次幂、把 \(j\) 元积放大 \(j\) 次幂，任意染色不必尊重这种不一致的缩放。

## 主要结果

主定理（Theorem 1.1）：设 \(r,m\ge1\) 为整数，\(R\ge2\)、\(D\ge1\) 为实数。对任意染色 \(\chi:\mathbb N\to[r]\)，存在互异正整数 \(a_1<\cdots<a_m\) 与颜色 \(c\)，使对每个非空 \(J\subseteq[m]\) 有
\[\chi\Big(\sum_{j\in J}a_j\Big)=\chi\Big(\prod_{j\in J}a_j\Big)=c,\]
即 \(m\) 元集 \(A\) 的非空子集和集 \(\FS(A)\) 与子集积集 \(\FP(A)\) 之并单色；且可要求元素极度分离：\(a_1>R\)，\(a_d>R\big(\sum_{k<d}a_k+\prod_{k<d}a_k\big)^D\)。推论 1.2 由此得出：可使 \(|\FS(A)|=|\FP(A)|=2^m-1\) 且 \(\FS(A)\cap\FP(A)=A\)，即除单例外所有子集和与子集积两两互异。另一推论给出有限区间形式：存在 \(N\)，使 \([N]\) 的任意 \(r\) 染色都含此类配置，甚至可要求全部元素落在指定倍数集 \(q\mathbb N\) 中。证明纯定性：参数的有限性与选取顺序是本质的，但不给最小配置任何数值界。

## 证明思路

证明先组合、后解析，拆成两个独立原理，最后合并。

第一步先做组合选择：把原始变量排成"块"\(B=T\cup\{i\}\)（尾巴 \(T\) 加主元 \(i\)），链满足 \(T_1<\cdots<T_m<i_1<\cdots<i_m\)，使每个较早的块恰是较晚块的"可加块"。对整数列 \(x_i=h_ib_it_i\)，先用有限 Ramsey 定理按 \(A\mapsto\chi(x_A)\) 染色子集得到齐次集，再用 Folkman–Rado–Sanders 有限和定理选出一条链，使全部非空块积已同色；剩余任务只是让各子集和也进入同一颜色。

第二步再建立预测原理（Prediction Principle）：为颜色示性函数构造有界的分段 nilsequence 模型 \(S_{B,a,c}\)（Lipschitz 函数沿幂零李群轨道 \(F(g^kx)\) 取值，分区间与剩余类定义）。要点有三：其一，块积是多个调和 \(W\)-单位变量之积，分布异于单变量，作者用除子权 \(\nu_B(y)=\mathbb E_\sigma\,\sigma\mathbf 1_{\sigma\mid y}\) 编码可除性，配合素数插入与保持乘积不变的"倒数伸缩"\(z_u\mapsto z_u/p,\ z_v\mapsto pz\)，经带权 Cauchy–Schwarz 逐个剥去乘法掩码，把计数误差化归为单变量的加性立方检验；其二，计数需细尺度模型而对齐需粗尺度模型，对嵌套子空间的投影能量做 Ramsey 选择使两个要求兼容，幂零步数 \(s\) 只依赖 \(m\)；其三，用 Green–Tao–Ziegler 逆定理与 Tao–Ziegler 子群 Bessel 不等式把"细投影小"转为"立方均值小"，阈值与主索引个数无关。校准条款还保证颜色在中心真实出现时其模型值大概率不小于 \(2\tau\)。

第三步建立对齐原理（Alignment Principle）：从固定有限的有理尺度表 \(\mathcal B\) 中选出向量 \(b\)，使每个中心的正预测经全部所需加性平移后仍为正，且成功概率有与模型复杂度无关的下界 \(\delta>0\)——正是这一一致性允许校准容差最后才选定。难点是加性平移可能要求主变量作非整数改变：先做整数剩余校正 \(t_C(p+mr_e)+mM\Delta_e=t_Cp+mq_e\)，再把剩余位移实现为 nilsequence 状态的变换；这些变换生成步数不超过 \(s\) 的幂零群，在其上用幂零多项式递归（nilpotent polynomial recurrence）配合"逆向保护"式有限词计划选取尺度更新，使先前已确保的比较不被破坏。

最后合并：对齐与校准事件同时发生的概率至少 \(\delta/2\)；在其上链选择给出乘积掩码全为 1、各中心模型值超过 \(2\tau\)，对齐推论又给出每处和的模型值超过 \(\tau\)，于是某加权计数沿超滤（ultrafilter）极限为正。取出使所有因子为正的具体元组即得配置；元素分离性由"每个尺度支配前序量的一切固定幂"直接保证。

## 可信度与备注

该主结果暂无 Lean 形式化证明，且论文自述所有参数均为定性、无显式数值界。论文明确声明所借用的外部深结果——Green–Tao–Ziegler 逆定理（含勘误）、Tao–Ziegler 拼接定理、Green–Tao 多项式等分布、Zorin–Kranich 幂零多项式递归——所需的特殊形式，其余传递、进度比较与提升论证均给出完整证明；但其中间步骤技术性很强，宣告解决一个悬置 47 年的猜想仍需社区逐行核验。本批次中结果族 164 仅此一篇手稿，未读到可交叉印证的姊妹篇。依据 OpenAI 官方声明，"未经形式化的结果可能有问题"，请以社区核验为准。

{% endraw %}
