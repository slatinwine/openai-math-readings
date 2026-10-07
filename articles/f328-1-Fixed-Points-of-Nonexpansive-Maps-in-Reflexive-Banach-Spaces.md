---
layout: default
title: "Fixed Points of Nonexpansive Maps in Reflexive Banach Spaces"
family: "328"
discipline: "Functional analysis"
formalized: true
source: null
pdfname: ""
---

{% raw %}
# 解读 | Fixed Points of Nonexpansive Maps in Reflexive Banach Spaces

> 结果族 328：Nonexpansive fixed points in reflexive Banach spaces　·　学科：Functional analysis（泛函分析）　·　验证状态：主结果已 Lean 形式化

## 一句话结论

证明了任意实自反 Banach 空间 (reflexive Banach space) 中，非空闭有界凸子集上的每个非扩张自映射 (nonexpansive selfmap) 都有不动点——Kirk 的自反空间不动点问题在原有范数下获得肯定回答，不再需要一致凸性等任何附加几何条件。

## 问题背景

非扩张映射指满足 \(\norm{F(a)-F(b)}\le\norm{a-b}\) 的映射；"闭有界凸集上的非扩张自映射是否必有不动点"是非线性泛函分析的核心问题。1965 年 Browder 与 Göhde 对一致凸 (uniformly convex) 空间给出肯定答案，Kirk 对正规结构 (normal structure) 凸集给出证明，其极小不变集约化正是本文起点。此后虽推广到 \(L^1\) 的自反子空间（Maurey）、\(1\)-无条件基（Lin）、一致非方空间等，但均为充分条件：Karlovitz 例子表明正规结构非必要；Alspach 在 \(L_1[0,1]\) 造出弱紧凸集上无不动点的非扩张自映射，说明仅有弱紧性不够；Benavides 证明每个自反空间可重赋范使结论成立，但换范数会改变哪些映射非扩张。于是"原有范数下自反空间是否总有不动点性质"悬置至今，2026 年的综述仍将其列为未解决。

## 主要结果

**主定理**：设 \(X\) 是实自反 Banach 空间，\(C\subseteq X\) 非空、范数闭、有界、凸。若 \(F:C\to C\) 满足 \(\norm{F(a)-F(b)}\le\norm{a-b}\)，则 \(F\) 必有不动点。非扩张性按原有范数衡量，不需一致凸性、正规结构等附加条件。

**推论（交换族）**：对 \(C\) 上两两交换的非扩张映射族 \(\mathcal S\)，公共不动点集 \(\operatorname{Fix}(\mathcal S)\) 非空，且是 \(C\) 的非扩张收缩 (nonexpansive retract)——存在非扩张映射 \(R:C\to\operatorname{Fix}(\mathcal S)\) 在该集上为恒等。推论由主定理结合 Bruck (1974) 的定理直接导出。

## 证明思路

证明用反证法，先做极小不变集 (minimal invariant set) 约化：由反例可得可分、弱紧、凸、直径归一为 \(1\) 的集合 \(K\)，其上无不动点的非扩张映射 \(T\)，且 \(K\) 无真的闭凸不变子集。Goebel–Karlovitz 直径引理断言：近似不动点序列（\(\norm{Tu_j-u_j}\to0\)）到 \(K\) 中每个定点的距离都趋于 \(1\)。

第一步构造**锚点**。定义预解映射 (resolvent) \(R_n\)（\(R_n(a)=a/n+(1-1/n)TR_n(a)\)，\(\norm{TR_n(a)-R_n(a)}\le1/n\)），以其生成非扩张映射半群；在逐点弱收敛拓扑下对尾部族取闭凸包之交得紧半群，用 Ellis 引理取出幂等元 \(P\)，锚点 \(x\) 满足 \(P(x)=x\) 且在尾部图像集 \(D_x\) 的闭凸包中。由此得"自适应选择"引理：每步精度门槛可依赖此前全部历史，仍能依次选出映射并有限终止，使所选图像的凸组合按范数回到 \(x\) 附近。

第二步构造**无穷有序树**：节点带映射、权重 \(\alpha_v\)（兄弟和为 \(1\)）、可和误差预算 \(e_v\)（总和 \(\le1/128\)）与泛函 \(f_v\)，输出按 \(H_u=G_u(\sum\alpha_vH_v)\) 自叶向根传递。"预测"机制尤为关键：\(Q_v(b;\theta)\) 刻画"\(v\) 左侧叶子保留标签、\(v\) 及其右侧换成公共点 \(b\)"的理想截断根输出，\(\theta\) 取值于紧集，用自由超滤子 (ultrafilter) 取弱极限得 \(Z_v(\theta)\)，在选定映射前便备好比较极限；\(f_v\) 由紧检测器引理选出，满足 \(f_v(y_v-z)\ge1-e_v\)。

第三步**换叶**：取充分晚的 \(b_j\)，把截断树的叶输出从右到左逐个换成 \(b\)。整块换前后根输出之差满足 \(f_v(U_v-V_v)\ge W_v-5e_v\)，其中偏离路径的权重经伸缩求和恰好归并为 \(1-W_v\)。归一化差 \(d_s=(U_s-V_s)/W_s\) 落在弱紧球 \(B_Y\) 中；加权亏缺总量 \(\le5/128\)，故必有叶子使路径上全部 \(f_v(d_s)>1/2\)。可行节点构成有限分支、任意深的树，逐层选取得无穷枝 \(v_k\)；弱紧性给出公共向量 \(d\) 使 \(f_{v_k}(d)\ge1/2\)。但预算可和给出 \(|f_{v_k}(z_i-z_j)|\le e_{v_k}\to0\)，差 \(z_i-z_j\) 张成的子空间在 \(Y\) 稠密，故 \(f_{v_k}\) 逐点趋于零——矛盾。

## 可信度与备注

本篇主结果已由 OpenAI 团队用 Lean 形式化验证（结果族资料附有 Lean 文档），区别于此前 Hanebaly 等宣布而未获核验的证明；锚点、预测树、换叶估计对凸性、非扩张性与紧性的依赖在文中明确分离，便于核验。按 OpenAI 官方声明，未经形式化的结果可能有问题；本篇已形式化，可信度较高，读者仍应以社区核验与 Lean 细节为准。

{% endraw %}
