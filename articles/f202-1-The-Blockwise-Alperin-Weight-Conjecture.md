---
layout: default
title: "The Blockwise Alperin Weight Conjecture"
family: "202"
discipline: "Algebra"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | The Blockwise Alperin Weight Conjecture

> 结果族 202：The blockwise Alperin weight conjecture　·　学科：Algebra　·　验证状态：暂无形式化证明，请以社区核验为准

## 一句话结论

论文证明了对任意素数 \(p\) 与任意有限群 \(G\) 的数值形式分块 Alperin 权猜想：每个 \(p\)-块 \(B\) 的不可约 Brauer 特征标个数 \(l(B)\) 恰等于 \(B\) 的权在共轭意义下的类数 \(|W_p(B)|\)。这一 1986 年提出的模表示论核心局部—整体猜想，由此首次在完全一般的情形下获得无条件证明。

## 问题背景

模表示论的局部—整体原理（local–global principle）希望仅凭 \(p\)-子群正规化子的数据恢复有限群表示的整体面貌。Alperin 在 1986 年 Arcata 会议上给出其精确数值形式并于 1987 年发表：特征 \(p\) 的代数闭域 \(k\) 上，群代数 \(kG\) 的简单模可按"权"逐块清点，块（block）即 \(kG\) 的本原中心幂等元所切出的直和分量。一个 \(p\)-权（\(p\)-weight）是二元组 \((Q,\phi)\)：\(Q\leq G\) 为（可平凡的）\(p\)-子群，\(\phi\in\Irr(N_G(Q)/Q)\) 是商群的缺陷零（defect zero）常特征标。分块猜想断言：\(B\) 的不可约 Brauer 特征标（Brauer character）数 \(l(B)\) 等于指派给 \(B\) 的权的共轭类数。此前进展主要沿 Knörr–Robinson 子群链改写与 Navarro–Tiep、Späth 的归纳约化展开——化归为有限单群上的局部条件后逐族验证（对称群、\(\mathrm{GL}_n\)、\(\mathrm{SL}/\mathrm{SU}\)、交换 Sylow 子群等）；一般情形需穷尽全部单群族，长期未决。

## 主要结果

主定理：对每个素数 \(p\)、每个有限群、每个 \(p\)-块 \(B\)，有 \(l(B)=|W_p(B)|\)；权的块指派采用中心特征标（central character）判据 \(\lambda_b\circ s_H=\lambda_B\)（\(s_H\) 为系数限制）。定理不限制亏群（defect group）、素数与群，\(Q=1\) 的权也计入；且证明既不用有限单群分类，也不用任何归纳权条件。由它直接补齐一批既有结果所需的猜想性前提：Alperin 局部不等式 \(l(B)\geq l(b)\) 及交换亏群时的等式 \(l(B)=l(b)\)、整体不等式 \(|\IBr_p(G)|\geq|\IBr_p(N_G(P))|\)、Hung–Sambale–Tiep 的主块下界（如 \(k_p(G)=3\Rightarrow l(B_0)\geq(p-1)/2\)）、\(k(B)-l(B)=1\) 时数据 \((p^d,l(B))\) 的完全数值分类（含七个例外对），以及 Boltje–Bouc–Yılmaz 的函子恒等式——严格 \(p\)-子群链上单函子类的交替和，按缺陷是否为零分别取 \([S_{1,1,F}]\) 或 \(0\)。

## 证明思路

先做代数归约。权等式被改写为算子方程 \(l=(1+T)z\)：\(z\) 计缺陷零常特征标，\(T\) 沿非平凡 \(p\)-子群的正规化子商移动并因群阶 \(p\)-部分严格下降而幂零，取有限逆得 Knörr–Robinson 型正规链（normal chain）交替和；再在余中心（cocenter）上用 Frobenius 型算子 \(\overline a\mapsto\overline{a^p}\) 与 Brauer 子段（subsection）公式，配两个"插入/删除"对合，把交替的简单模计数换成交替的常特征标计数。随后构造 Tsushima 式中心元 \(v=E(1-c_X)\)（\(c_X\) 为全体 \(p\)-元之和），其支集为 \(p\)-奇异元、中心剩余数恰为 0 或 1；把它提升到特征零并限制到各链正规化子，交替迹 \(\Phi_{p^s}\) 在赋值拓扑下收敛于"交替常计数减缺陷零计数"。由 Frobenius 换位子计数公式，迹展开为满足 \([x,y]u_1\cdots u_n=1\)（\(n=p^s\)）的元组加权和，\(O_p(J)\neq1\) 的项再被对合消去。于是只剩纯计数命题：对 \(O_p(J)=1\) 的有限群 \(J\) 与任意 \(p\)-奇异共轭类多重集 \(\mathcal M\)，生成 \(J\) 的该类元组数 \(N_{J,s}(\mathcal M)\) 在 \(s\) 充分大时被 \(p^h\) 整除，阈值不依赖 \(\mathcal M\)——正是这条一致性使随 \(s\) 增长的多重集求和仍趋于零。

几何部分构造带标点的高指标亏格一曲线：用 \(\sigma(t_i)=t_{i+1}-P\)（\(P\) 的阶恰为 \(n\)）的平移循环扭转（translated cyclic twist）下降出 \(E/F_0\)，凭群律和关系 \(\sigma(v)+[b]P=v\) 与"常量加自同态"分解比较，证明 \(E\) 的一切除子次数都被 \(n=p^s\) 整除；分裂后各 \(t_i^*\eta\) 是绝对微分的基，经 \(p\)-部分至多 \(p^h\) 的扩张，指标（index）仍被 \(p^{s-h}\) 整除、微分独立性至多损失 \(h\) 维。对 \(E_F\) 的纯不可分（purely inseparable）覆盖，沿 Frobenius 塔逐层用高度一恒等式 \(\det\mathcal Q\simeq(\det\mathcal F)^{\otimes p}\) 与标记点处的切向消没，得带误差 \(h+\log_p d\) 的亏格估计；两端乘 \(d\) 后都是 \(F\) 上的除子次数、被 \(p^{s-h}\) 整除，而误差界小于该模，差被迫非负——这一"取整"步骤给出精确不等式 \(\nu(Z)/d\geq\sum_i(1-1/r_i)\)。最后把曲线提升到剩余域为 \(F_0\) 的球完备（spherically complete）赋值域：生成元组恰是刺孔亏格一曲线上连通 \(J\)-覆盖的单值群（monodromy）数据；Galois 群作用于固定 \(\mathcal M\) 的覆盖集，小于 \(p^h\) 的轨道因下降障碍的核 \(Z(J)\) 与 \(p\) 互素而可经 Sylow 论证带 \(J\)-作用下延，而对已下降的覆盖取赋值延拓与正规化，用特征零 Riemann–Hurwitz 加上述亏格估计得 \(\chi(Y)=\sum_w\chi(C_w)\)，作平坦模型后由连通性迫使惯性群（inertia group）是 \(J\) 的非平凡正规 \(p\)-子群，与 \(O_p(J)=1\) 矛盾。故每个 Sylow 轨道都不小于 \(p^h\)，元组数被 \(p^h\) 整除，回代即得块等式。

## 可信度与备注

本文暂无 Lean 形式化证明，其中繁重的几何构造——扭转下降、不可分亏格估计、球完备赋值域上的特殊化——均待社区逐条核验；按 OpenAI 官方声明，未经形式化的结果可能存在问题。结果族 202 目前仅收录本篇手稿，无姊妹篇互相支撑；若干推论还将正确性部分托付给 Hung–Sambale–Tiep、Boltje–Bouc–Yılmaz 等外部文献。论文自述不依赖单群分类、不以任何权计数猜想为输入，代数与几何两部分接口清晰，若核心引理成立则整体结构自洽。

{% endraw %}
