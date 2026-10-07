---
layout: default
title: "Algebraicity of Weil classes on split abelian eightfolds"
family: "032"
discipline: "Algebraic and complex geometry"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | Algebraicity of Weil classes on split abelian eightfolds

> 结果族 032：Hodge and Kuga–Satake results for all projective K3 surfaces　·　学科：Algebraic and complex geometry　·　验证状态：暂无形式化证明，请以社区核验为准

## 一句话结论

论文证明了：每个"分裂"（split）Weil 型复阿贝尔八重簇上的全体有理 Weil 类皆为代数闭链类，对一切虚二次域、一切相容极化及带额外自同态的成员成立，从而在该族中彻底解决这一 Hodge 猜想的经典检验问题。

## 问题背景

有理 Hodge 猜想（rational Hodge conjecture）断言射影簇上的有理 Hodge 类皆由代数闭链（algebraic cycle）给出，Weil 类是它最具体的试验田之一：虚二次域的作用天然切出一个二维有理空间，其代数代表元一般不可能由除子类乘积拼出。Weil 于 1977 年引入这些"例外行列式类"；Markman 随后证明了所有 Weil 型阿贝尔四重簇与分裂 Weil 型六重簇上 Weil 类的代数性，并由此得到维数不超五的阿贝尔簇的有理 Hodge 猜想。分裂八重簇是下一站：Markman 2026 年综述的构造设想依赖较弱的半正则性条件，其验证与形变定理的充分性均为公开问题。本文攻克之。

## 主要结果

设 \(K=\Q(\sqrt{-d})\) 为虚二次域，\(A\) 为八维复阿贝尔簇（abelian variety），带嵌入 \(\iota:K\hookrightarrow\End(A)\otimes_\Z\Q\) 与极化 \(\lambda\)，Rosati 对合在 \(\iota(K)\) 上为复共轭，且 Weil 型条件（Weil-type condition）\(\dim_\C H^{1,0}(A)_\sigma=\dim_\C H^{1,0}(A)_{\bar\sigma}=4\) 成立。有理 Weil 空间 \(W_K(A)=\bigwedge\nolimits_K^8 H^1(A,\Q)\subset H^8(A,\Q)\) 是二维的，恰好落在 \(H^{4,4}(A)\) 中。分裂（split）指 \(V=H_1(A,\Q)\) 含四维 \(K\)-子空间，使 Hermitian 型 \(h(x,y)=\psi(Jx,y)+\sqrt{-d}\,\psi(x,y)\) 在其上恒为零。主定理：对每个分裂 Weil 型四元组 \((K,A,\iota,\lambda)\)，

\[W_K(A)\subset \operatorname{im}\bigl(\CH^4(A)\otimes_\Z\Q \xrightarrow{\ \mathrm{cl}\ } H^8(A,\Q)\bigr),\]

即二维 Weil 空间由余维四代数闭链类张成；结论对一切虚二次域、一切相容极化类型及带额外自同态的特殊成员成立，但不涉及一般八重簇上的全部 Hodge 类。

## 证明思路

证明分四个阶段。先把所有分裂 Weil 型八重簇装进统一模型：它们都 \(K\)-相容地同构（isogeny）于标记族 \(A_\Pi=\C^8/(\Z^8+\Pi\Z^8)\)，代数性沿同构传递；再用 Hodge 群的表示论算出，在余可数个例外集外，一般周期点的有理 Hodge 类恰为 \(\Q\theta^j\) 加上 \(j=4\) 时的 \(W_K\)。再在实辛十六环面 \(T\) 上构造中间维数同调类 \(\alpha=\alpha_{\mathrm{ex}}+g_1+g_2+g_3\)：三个标量图拉格朗日与例外分量 \(\alpha_{\mathrm{ex}}\) 配对为零，另一图 \(C\) 则探测它；关键引理断言与 \(\alpha\) 缩并为零的二形式恰是十六维混合空间 \(\Omega\)。

再把 \(\alpha\) 几何化：其正倍数实现为嵌入的自旋拉格朗日（spin Lagrangian）\(L\)，\(H_2\)、\(H_6\) 到环境的映射均为单射，指定的二形式族在上同调水平限制为零，正是这两个单射迫使后续障碍消失。加权 Floer 操作以有限能量与元数截断构造，经超积（ultraproduct）剩余域化为 \(R=\kappa[[t]]\) 上的精确代数恒等式；定向图代数被算成 theta 截面环 \(\mathscr S\)，\(\mathscr X=\Proj\mathscr S\) 在 \(R\) 上光滑射影。特殊纤维 \(t=0\) 处对无障碍图膜应用通常的镜像对称（mirror symmetry），恢复出周期四分次的完美对象，其交错陈特征（Chern character）逸出极化幂的张成。

最后是提升与扩散：\(t\)-挠在导出限制的交错和中相消，光滑真基变换把非退化性搬到几何泛纤维；用 Baire 定理避开可数个解析例外集选复周期，得代数全闭链类，其余维四分量 \([Z]=a\theta^4+w\)，\(0\ne w\in W_K\)。其希尔伯特参数空间（Hilbert scheme）连通分支必满射整个周期域，且 \(\mathrm{ch}_4(\mathcal O_{Z_b})\) 沿分支常值，故同一 \(w\) 在每根纤维上代数；再取整数 \(m>\sqrt d\,\cot(\pi/8)\)，自同态 \(m1_8+D\) 的拉回在两条行列式线上特征值 \((m\pm i\sqrt d)^8\) 为非实共轭，与 \(w\) 线性无关，二者张成 \(W_K\)。同构归约覆盖一切极化类型与特殊成员。

## 可信度与备注

本篇主结果暂无 Lean 形式化证明；证明横跨辛几何、Floer 理论与代数几何，环节繁多，此处仅给出逻辑骨架，须以社区核验为准。作者也划清边界：仅对无障碍图膜使用通常镜像定理，不假设变形范畴的镜像等价。它与本族姊妹篇（CM 阿贝尔簇有理 Hodge 猜想、K3 曲面 Kuga–Satake 代数性）共享"统一周期模型 + Baire 避例外 + 希尔伯特扩散"框架，互相印证。按 OpenAI 官方声明，未经形式化的结果可能存在问题。

{% endraw %}
