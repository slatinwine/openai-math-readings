---
layout: default
title: "Choiceless polynomial time with counting does not capture polynomial time"
family: "243"
discipline: "Mathematical logic"
formalized: true
source: null
pdfname: ""
---

{% raw %}
# 解读 | Choiceless polynomial time with counting does not capture polynomial time

> 结果族 243：Separating choiceless counting from polynomial time and witnessed choice　·　学科：Mathematical logic　·　验证状态：主结果已 Lean 形式化

## 一句话结论

本文证明了带计数的无选择多项式时间（choiceless polynomial time with counting, CPT）不能捕获无序有限结构上的多项式时间：在 \(\mathbb F_3\) 上的一个线性方程组相容性查询属于 P，却无法被 CPT 定义，从而确认了 Blass–Gurevich–Shelah 近三十年前提出的非捕获猜想。

## 问题背景

描述复杂性（descriptive complexity）的核心问题之一是：哪种逻辑能表达全部多项式时间可判定的性质？Immerman–Vardi 定理（1982）给出有序情形的完满答案——最小不动点逻辑恰好捕获有序结构上的 P。但数据库等场景中的输入是无序结构（unordered structures），Gurevich 在 1988 年猜想不存在捕获无序 P 的逻辑。Blass、Gurevich、Shelah 于 1999 年提出 CPT：在由输入元素生成的遗传有限集（hereditarily finite sets）上对称地计算，所有运算与输入自同构交换，从而不做任意选择；他们猜想即使加上计数操作 \(\mathsf{Card}\)，该形式化仍是 P 的真片段。此前所有下界都卡在限制条件上：Dawar–Richerby–Rossman 的著名结果表明集合秩限制在 \(o(\log n/\log\log n)\) 时计数也不够，但秩固定的下界无法直接推出对允许任意有限秩的完整形式化的分离；Rossman 与 Pago 的结果则是功能性障碍而非布尔查询的不可定义性。

## 主要结果

论文固定一个含八个二元关系符号的词汇表 \(\tau=\{\mathsf{Ed},\mathsf{Cf},\mathsf{EB},\mathsf{VB},\mathsf I,\mathsf Z_0,\mathsf Z_1,\mathsf Z_2\}\)，定义查询 \(Q\) 如下：由 \(\mathsf{Ed},\mathsf{Cf}\) 区分边原子集 \(Y\) 与构形原子集 \(X\)，由 \(\mathsf{VB}\) 分块；对每块引入归一化方程 \(\sum_{a\in X_t}\lambda_a=1\)，并通过关联测试对满足条件的对 \((t,y)\) 引入相容方程 \(\mu_y=\sum_{a\in X_t}\lambda_a C(y,a)\)，其中系数 \(C(y,a)\) 由关系 \(\mathsf Z_\delta\) 直接给出。\(Q(A)\) 定义为该线性方程组（linear system）在 \(\mathbb F_3\) 上是否相容。定理 1 断言：\(Q\) 是同构不变的、确定性多项式时间可判定的（高斯消元即可），但不可被完整带计数的 CPT 定义。推论还指出 \(Q\) 在线性代数逻辑 \(\mathrm{FPS}_3\) 与 \(\mathrm{FPR}_3\)（FPC 加上 \(\mathbb F_3\) 上的可解性算子/秩算子）中可定义，因此这两个逻辑都不包含于 CPT。

## 证明思路

先构造答案相反的结构对。以边长 \(L\) 的三维盒网格为基础，每条边挂一个 Heisenberg 型有限群（finite Heisenberg group），其元素成为边原子；每个顶点处满足共享面坐标条件与发散方程 \(\sum_{e\ni v}\epsilon_{ve}z_e=b_v\) 的相邻边状态组成为构形原子。取电荷向量 \(b^0=0\) 与 \(b^1=\mathbf 1_{v_*}\)，得到大小同为 \(N=\Theta(L^3)\) 的结构 \(A_{b^0},A_{b^1}\)。把查询方程逐顶点加权求和，每条有向边一进一出而相互抵消，于是相容性迫使总电荷 \(\sum_v b_v=0\)；全零构形给出 \(A_{b^0}\) 的解，故 \(Q\) 在两结构上答案相反。关键在于该求和论证允许任意域值权重，不要求解"选出"每顶点唯一构形。

再证任何固定 CPT 程序在两结构上答案相同，分三步。第一步是秩无关的支撑定理（support theorem）：结构的自同构群 \(H\) 是面平移与其交换子生成的中心流的非交换中心扩张，含中心子群 \(K=\ker\partial\)（无发散边流）。利用交错形式（alternating form）的秩论证与稀疏上链引理——减去显式构造的梯度，把检测稳定子的线性泛函集中到至多 \(2Lt\) 条边上——证明凡 \(H\)-轨道大小至多 \(N^q\) 的遗传有限对象都有长度 \(O_q(L(1+\log L)^2)\) 的 \(K\)-支撑，且界与对象的秩无关；这正是绕过以往秩限制下界的关键，非交换群的作用在此本质，仅有中心流不够。第二步是计数等价：仅作分析之用，给两结构附加区分原子类与比较标量差的扩张关系，证明两个扩张在至多 \(M=\lfloor L^{7/4}\rfloor\) 个变量名的一阶计数句子上不可区分；再对"自身及每个递归成员都有长度 \(\le s\) 支撑"的全体对象组成的域，沿用 BGS 的分子表示法（以在支撑元组处求值的有限形式表示对象）证明等式、隶属与精确计数均可转移，宽度代价 \(O_{q,m}(L^{3/2}(1+\log L)^3)=o(M)\)。第三步把整个计算纳入比较：借助 Grohe–Schweitzer–Wiebking 的解释程序刻画（interpretation characterization），把程序完整运行轨迹用带序数标签的 Kuratowski 编码打包为 \(H\)-不变、成员传递、大小至多 \(9B^3\le N^q\) 的族，从而整体落入被比较的支撑域，且不设秩上限；再由避免捕获的替换引理证明每个状态、停机测试与输出测试都有精确的计数公式定义，所需变量名个数 \(m\) 只依赖程序本身。先固定程序与 \(q,m\)，再取 \(L\) 充分大：计数等价迫使两侧同阶段停机、输出相同，与查询答案相反矛盾。

## 可信度与备注

本篇主结果已由 OpenAI 完成 Lean 形式化验证（族文档 lean/docs/243.md）。姊妹篇证明加入见证对称选择后表达能力严格增强，两文共享同一套网格构造与支撑—转移架构，互为印证。另需注意 OpenAI 官方声明：未经形式化的结果可能存在问题，故同族未形式化的姊妹篇宜以社区核验为准。

{% endraw %}
