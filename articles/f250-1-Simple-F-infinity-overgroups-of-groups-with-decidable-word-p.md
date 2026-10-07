---
layout: default
title: "Simple $F_\\infty$ overgroups of groups with decidable word problem"
family: "250"
discipline: "Group theory"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | Simple \(F_\infty\) overgroups of groups with decidable word problem

> 结果族 250：Boone–Higman embeddings with higher finiteness　·　学科：Group theory　·　验证状态：暂无形式化证明，请以社区核验为准

## 一句话结论
证明了 Boone–Higman 猜想的高阶有限性强化：每个字问题（word problem）可判定的有限生成群，都嵌入一个 \(F_\infty\) 型的非平凡单群——即拥有每维只含有限多个胞腔的分类空间。由于 \(F_\infty\) 蕴涵有限呈现，这同时给出了原猜想的另一条证明，并把单超群的有限性推到同伦的每一维。

## 问题背景
1974 年 Boone 与 Higman 证明：有限生成群字问题可判定当且仅当 \(G\leq H\leq K\)，\(H\) 单、\(K\) 有限呈现，并问 \(H\) 能否取有限呈现——即 Boone–Higman 猜想。一个更强的自然问题是要求 \(H\) 具有类型 \(F_\infty\)（type \(F_\infty\)）：拥有一个在每个维数只含有限多个胞腔的类分类空间（classifying space）\(K(H,1)\)（\(F_1\) 即有限生成、\(F_2\) 即有限呈现）。该问题出现在 BBMZ 综述 Question 5.6 之后的讨论中。此前只知一些局部结果：Brown 证明 Thompson–Higman 群族是 \(F_\infty\)；Belk–Zaremsky 造出含一切右角 Artin 群的 \(F_\infty\) 单群、Belk–Hyde–Matucci 造出含一切可数交换群的 \(F_\infty\) 单群，但都没有从字问题算法出发的一般构造。障碍也是具体的：FFKLZ 定理表明，有限虚上同调维数群或可数线性群的寡态作用必有某个有限子集稳定子不是 \(F_\infty\)——所以作用群与稳定子必须一并从头建造。

## 主要结果
主定理：每个字问题可判定的有限生成群 \(G\) 都可单射同态入某个非平凡单群 \(H\)，且 \(H\) 具有类型 \(F_\infty\)。输入群不必有限呈现，判定算法运行时间任意。结合 Kuznetsov 方向的经典论证（非平凡有限呈现单群字问题可判定且遗传给有限生成子群），这类群恰好就是 \(F_\infty\) 单群的有限生成子群。附加结论：同一超群 \(H\) 还可由两个有限阶元素生成。论文的核心中间定理是一个高传递作用：存在含 \(G\) 的群 \(\Lambda\)，在可数无限集上忠实作用，且对每个固定长度的互异有序点组传递（highly transitive），同时 \(\Lambda\) 与每个有限点组的逐点稳定子都是 \(F_\infty\)——这恰好凑齐 Belk–Zaremsky 扭曲 Brin–Thompson 定理的全部输入。

## 证明思路
先定路线：Belk–Zaremsky 定理说，若 \(\Lambda\) 忠实、寡态（oligomorphic，即在每个固定基数的有限子集上只有有限多个轨道）地作用于可数集 \(S\)，且 \(\Lambda\) 与每个有限子集的集型稳定子均为 \(F_\infty\)，则扭曲 Brin–Thompson 群 \(SV_\Lambda\) 非平凡、单、\(F_\infty\) 且含 \(\Lambda\)。高传递远强于寡态，故任务化为造作用并证所有稳定子 \(F_\infty\)。再构造作用：取有限呈现环 \(B\)，令 \(Q=\mathrm E_7(B)\) 作用于列集 \(X=B^7\)；用"压缩对角"引理把形如 \(D_1(1+\phi^2(v-1))\) 的单位嵌入初等矩阵群（在 \(\mathrm{GE}_r/\mathrm E_r\) 的交换商里，靠四个两两正交又等价的幂等元把类压成 \(c=c^2\)），得到相容单射 \(\delta:Q\to Q\)、\(\sigma:X\to X\)；取直极限并附加层级平移 \(t\)，得到上升环面（ascending torus）\(\Lambda=N\rtimes\langle t\rangle\)。压缩后每列集中于第一坐标，前缀算子 \(S_xT_x\) 两两正交，使 \(Q\) 能实现 \(\sigma(X)\) 的任意有限支撑置换，于是两组同长有序点组推进一层即可互送，得高传递；忠实性靠非平凡矩阵必动某基列、以及层级严格增长识别出 \(t\)。然后是全文核心的上升环面判据：设单射自同态 \(f:U\to U\) 经过有限呈现群分解（保证 \(T(U,f)=\langle U,t\mid t^{-1}ut=f(u)\rangle\) 有限呈现），且对 \(\ell=2,3\) 各有一组以 \(\{0,1\}^{\mathbb N}\) 前缀算子导出的幂等元为指标的同态 \(h_E\)，正交时像交换且保持乘法分解，则 \(T(U,f)\) 是 \(F_\infty\)。证明走 Bieri–Eckmann 乘积模判据：只需对一切指标集 \(\mathcal I\) 证 \(H_n(J,(\mathbb ZJ)^{\mathcal I})=0\)（\(n\ge2\)）。关键新工具是"单纯形类型"的控制：以有限对称集为界的单纯形在左平移下只有有限多个类型；先用 Alexander–Whitney 对角与 shuffle 映射（mitotic 群对角论证的受控版）建立加性引理，再归纳证明存在统一的幂次 \(k\) 与公共输出界，使 \(f^k\) 把给定界内一切约化 \(n\)-圈链都变为边界——统一的精髓在于控制类型而非链长与系数。继而对同调类 \(z_E=[(h_Ef^k)_*z]\) 套用幂等引理（三份 \(M_3(\mathbb F_\ell)\) 的对角幂等元上的加性关系迫使 \(\ell z_I=0\)），2 与 3 两套系统分别湮灭同一类，故 \(z_I=0\)；最后用陪集 \(jU\) 构成的 \(J\)-树给出上升 HNN 同调正合列，\(F\) 的局部幂零性使 \(1-F\) 可逆，完成消灭。最后组装稳定子：逐点稳定子被识别为上升环面 \(T(U,f)\)，\(f(u)=a\delta(u)a^{-1}\)；其分解经有限呈现的 Steinberg 群 \(\mathrm{St}_6(B)\)——用姊妹篇的 Steinberg 核湮灭定理把 \(B^\times\) 的同态提升到 \(\mathrm{St}_6(B)\)（配合 Krstić–McCool 的有限呈现定理），再用交换矩阵 \(E=e_{12}(d)e_{21}(-d)e_{12}(d)\) 把单位从坐标 1 挪到坐标 2 而不动标记列，使第二个分解因子把整个 Steinberg 群送进稳定子。集型稳定子是逐点稳定子的有限指数扩张，封闭性引理保证仍为 \(F_\infty\)。至于环 \(B\) 本身，其单元既编码 \(G\) 又编码 \(\mathrm E_7(B)\) 作用的指定扩充——这一自指由姊妹篇的有限编译器加长度归纳与 Kleene 递归定理化解。

## 可信度与备注
本篇为 OpenAI 批量预印本，暂无 Lean 形式化证明，请以社区核验为准；OpenAI 官方声明"未经形式化的结果可能有问题"。它是结果族 250 的"高阶有限性篇"：基石篇（有限代数包络证原猜想）向它提供有限编译器、二进角落构造与 Steinberg 核湮灭定理，第三篇万有群又复用本文的判据；三篇链条环环相扣，任何一环有误都会波及全局。同调部分的均匀填充论证技术性较强，此处从略，详见论文第 2 节。

{% endraw %}
