---
layout: default
title: "A counterexample to the nearby Lagrangian conjecture"
family: "340"
discipline: "Differential geometry"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | A counterexample to the nearby Lagrangian conjecture

> 结果族 340：A counterexample to the nearby Lagrangian conjecture　·　学科：Differential geometry　·　验证状态：暂无形式化证明，请以社区核验为准

## 一句话结论

论文证明：存在充分大的偶数 \(N\)，使 \(T^*(S^9\times S^{N-1})\) 中有闭的、精确的、光滑嵌入的拉格朗日子流形，它与底流形微分同胚，却不能由零截面经紧支撑哈密顿同痕得到——推翻了无限制版的邻近拉格朗日猜想。

## 问题背景

设 \(Q\) 为闭光滑流形，其余切丛（cotangent bundle）\(T^*Q\) 带有典范刘维尔形式 \(\lambda\)。阿诺德（Arnold）1986 年讨论"拉格朗日纽结"时提出邻近拉格朗日猜想（nearby Lagrangian conjecture）：\(T^*Q\) 中每个闭的、精确（exact，\(\lambda|_L=df\)）嵌入拉格朗日子流形（Lagrangian submanifold）是否都哈密顿同痕（Hamiltonian isotopy）于零截面？这是辛刚性理论的核心检验问题。此前已知的多是必要条件：Hofer 与 Laudenbach–Sikorav 的相交定理、Abouzaid–Kragh 的单同伦等价定理、法向不变量（normal invariant）为 \(2\)-挠等；低维也有肯定结果，如 Hind 关于 \(T^*S^2\) 中拉格朗日球的定理，但一般情形只约束投影的拓扑。最近 Álvarez-Gavela–Igusa–Sullivan 在射流空间 \(J^1Q=T^*Q\times\R\) 中构造出管挠率（tube torsion）非平凡而底投影同伦于微分同胚的勒让德子流形，但遗忘最后一维会引入双点，不构成余切丛反例。本文补上了从双点到嵌入的最后一步。

## 主要结果

定理 1：存在充分大的偶数 \(N\)，取 \(Q=S^9\times S^{N-1}\)，则 \(T^*Q\) 中存在闭（紧致无边界）、精确、光滑嵌入的拉格朗日子流形 \(L\)，使 \(L\) 微分同胚于 \(Q\)，且没有任何紧支撑哈密顿同痕把零截面 \(Q_0\) 送到 \(L\)。注意 \(Q\) 与 \(L\) 都连通且单连通：障碍不在 \(L\) 的抽象拓扑，而在其嵌入余切丛的方式。构造以生成函数（generating family）语言给出：正则函数 \(F(q,w)\) 的临界点集经 \((q,w)\mapsto(q,d_qF)\) 生成精确拉格朗日浸入，再辅以整体单射性论证即得嵌入。

## 证明思路

证明分四步。先制造"不可见但非平凡"的无穷远数据：二次型 \(q_{k,l}=-\|x\|^2+\|y\|^2\) 在球面上的负区域（同伦型 \(S^{k-1}\times D^l\)）称为光滑管（smooth tube），管函数经双参数稳定化构成稳定管空间 \(\mathbf T\)，其负区域自带由 \(\gamma:\mathbf T\to BG\) 分类的稳定球面纤维化（stable spherical fibration）。Waldhausen 管纤维化给出 \(H^s(*)\to\mathbf T\to BG\)，结合参数化 h-余边缘（h-cobordism）定理 \(H^s(*)\simeq\Omega\mathrm{Wh}^{\mathrm{diff}}(*)\)、Bott 周期律与 Adams 的 J-同态（J-homomorphism）单射性，代入 Rognes 算出的 \(\pi_{10}\mathrm{Wh}^{\mathrm{diff}}(*)\)（二的幂部分阶 \(32\)）与 \(\pi_9^S\)（阶 \(8\)），阶数比较表明连接同态不满，故有非零类 \(a\in\pi_9\mathbf T\) 满足 \(\gamma_*a=0\)：管族非平凡而球面纤维化已平凡。

再证核心障碍命题：\(S^9\) 上齐次无穷远、每根纤维恰有一个非退化临界点、球面类为零的函数族，其稳定管类必为零。先用莫尔斯理论（Morse theory）把临界点处的负特征球与无穷远负区域做成纤维同伦等价，并把局部归一化为固定二次型；再在内、外球之间取正则零水平集，得一族 h-余边缘 \(C_b\)，乘一个区间做稳定化并延拓进固定柱体 \(Y=S^{k+l-1}\)，用带符号流场证明补集为乘积；由 Igusa 稳定性与连通度估计（维数 \(\geq38\) 保证 \(\pi_9\) 层面单射）反推原族为零，末以多重 jet 横截性（multijet transversality）把管核经嵌入同伦缩到固定标准管。

第三步把类 \(a\) 实现为拉格朗日量：取 \(F(b,v,w)=G_b(w)-R(b)\beta(\|w\|/T)\langle v,w\rangle\)，临界方程恰为 \(\nabla g_b(w)=R(b)v\)，由齐次性，临界轨迹由 \(S^9\times S^{N-1}\) 参数化。嵌入性靠两次"动量分离"：球面动量相等迫使重合分支之差落在 \(v\) 张成的直线上；尺度 \(R(b)=\Lambda e^{K\theta(b)}\) 随 \(b\) 变化，条件 \(K\delta_0>C_1/c\) 使底动量分离其余情形，而高度函数临界点附近族已是标准二次型、解唯一。紧致单射浸入即嵌入。

末步反证：若哈密顿同痕把零截面送到 \(L\)，逆向同痕可紧支撑地扩张到 \(T^*\R^d\)，使柱化后的 \(\mathcal L_0\) 在中心板上成为零截面。把同痕细分为小步，每步生成新莫尔斯族并添加分裂型 \((d,d)\) 二次变量，对数截断与磨光引理保证无穷远数据的稳定类不变。最终族在中心板每点恰有一个非退化临界点；限制到固定 \(S^9\) 切片后满足障碍命题全部假设，管类应为零——但仍等于 \(a\neq0\)，矛盾。

## 可信度与备注

本文是 OpenAI 2026 年 9 月的预印本，主结果暂无 Lean 形式化证明，请以社区核验为准；按 OpenAI 官方声明，未经形式化的结果可能有问题。结果族 340 现仅此一篇手稿，论证系统性倚重近年"生成函数—管空间—Waldhausen 代数 K-理论"主线的既有成果（Rognes 的 Whitehead 群计算、Igusa 稳定性、AIS 与 Courte–Porcelli 的技术工具）。全文构造、障碍、传输三部分互相咬合、结构自洽；个别步骤（如多重 jet 横截性的参数化应用）技术性较强，此处从略，宜对照原文核验。

{% endraw %}
