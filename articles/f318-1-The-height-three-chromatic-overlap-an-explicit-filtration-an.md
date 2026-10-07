---
layout: default
title: "The height-three chromatic overlap: an explicit filtration and its attachments"
family: "318"
discipline: "Topology"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | The height-three chromatic overlap: an explicit filtration and its attachments

> 结果族 318：Chromatic splitting: filtrations and counterexamples　·　学科：Topology　·　验证状态：暂无形式化证明，请以社区核验为准

## 一句话结论

对每个素数 \(p\geq5\)，论文把高度三重叠 \(L_2L_{K(3)}\mathbb S_p^\wedge\) 显式滤过为八个阶段，逐层余纤维正是强分裂猜想的八块局部球面层；两条带符号的断裂公式识别全部黏合映射，且第一条高度一黏合映射非零——碎片清单正确，楔和分裂确已失效。

## 问题背景

按 Hopkins 色谱分裂猜想（Hovey 记录、Barthel–Beaudry 修订），高度三的重叠 \(X=L_2L_{K(3)}\mathbb S_p^\wedge\) 应分裂为八块：两块 \(E(2)\)-局部、两块 \(E(1)\)-局部、四块有理的球面局部化。低高度的历史早已表明公式对素数敏感：高度二在 \(p\gt3\) 由 Hopkins 依 Shimomura–Yabe 的计算给出、\(p=3\) 由 Goerss–Henn–Mahowald 证明、\(p=2\) 被 Beaudry 推翻并由 Beaudry–Goerss–Henn 修正。色谱断裂方块（chromatic fracture square）只给出拉回，黏合映射本身就是额外数据，不能由两个角独自动出；而已知的有理计算（BSSW 外代数，生成元次数 \(0,-1,-3,-4,-5,-6,-8,-9\)）只定维数、不定映射。本族的有理障碍篇又证明高度三强分裂在 \(p\geq5\) 为假。于是核心问题转为：\(X\) 能否仍按这八块有序搭建，且各块之间的黏合映射可被显式识别？本文给出肯定回答。

## 主要结果

记 \(S=\mathbb S_p^\wedge\)（导出 \(p\)-完备化）、\(T=L_{K(3)}S\)、\(X=L_2T\)、\(Q=L_0S\simeq H\Qp\)。主定理：对每个 \(p\geq5\)，存在 \(E(2)\)-局部 \(S\)-模的映射链 \(0=F_0\to F_1\to\cdots\to F_8\xrightarrow{\ \simeq\ }X\)，其逐次余纤维依次为 \(L_2S\)、\(\Sigma^{-1}L_2S\)、\(\Sigma^{-3}L_1S\)、\(\Sigma^{-4}L_1S\)、\(\Sigma^{-5}Q\)、\(\Sigma^{-6}Q\)、\(\Sigma^{-8}Q\)、\(\Sigma^{-9}Q\)；在 \(F_1\simeq L_2S\) 下，复合 \(F_1\to X\) 是典范映射 \(L_2(S\to L_{K(3)}S)\)。附件识别定理（attachment identification）进一步对固定的一组选择（局部映射与相容同伦、局部化逆的凝聚数据）写出全部八条连接映射：\(\partial_1=\partial_2=0\)；中间两条由 \(d=\partial_wh\) 的分量控制；末四条由 \(g=\partial_at\) 的分量控制；\(d\) 与 \(g\) 各是一条穿过低高度局部化纤维、带固定旋转负号的"屋顶"公式。推论：借助姊妹篇的典范映射定理，第一条高度一连接映射 \(d_3:\Sigma^{-3}L_1S\to\Sigma(L_2S\vee\Sigma^{-1}L_2S)\) 作为底层谱的映射非零。定理不断言强楔和，也不分裂首个单位。

## 证明思路

装配分三大块：\(W=L_2S\vee\Sigma^{-1}L_2S\)、\(U_{\mathrm{mid}}=\Sigma^{-3}L_1S\vee\Sigma^{-4}L_1S\)、四个有理位移之并 \(V\)。先由单位与整行列式类 \(\zeta\) 给出实际映射 \(w=(1,\zeta):W\to X\)，并证明其 \(K(2)\)-局部化为等价——这一步依赖 coheight-one 层上的几何：把有限标记塔与 Fargues–Fontaine 曲线上的向量丛扩张联系起来（Scholze–Weinstein 框架、Anschütz–Le Bras 的截面全忠实性），先在完备层上算紧支撑上同调，再去完备化、经下降回到普通 Morava 合作运算。于是余纤维 \(Y\) 是 \(E(1)\)-局部的，中间块的插入靠两个描述的对接：高度一层面有实际基 \((1,\zeta,\delta,\zeta\delta)\)，把 \(L_{K(1)}T\) 完全分裂（\(\delta\) 为整定向类）；有理层面用迹类沿秩二 Tate 框架的输运证明 \(\alpha_3\mapsto c\delta\)、\(\zeta\alpha_3\mapsto c\zeta\delta\)（\(c\in\Qp^\times\)），重标 \(\beta_3=c^{-1}\alpha_3\) 后两种描述在有理化搭接处吻合；高度一断裂方块随即造出 \(h:U_{\mathrm{mid}}\to Y\)——起作用的是指定的相容同伦（compatibility homotopy），而非维数清点。拉回给出 \(F_3,F_4\)；其商是有理的，四个外积类 \(\alpha_5,\zeta\alpha_5,\beta_3\alpha_5,\zeta\beta_3\alpha_5\) 给出到该商的实际等价，有序部分和再拉回得 \(F_5,\dots,F_8\)。连接映射的识别依赖一条"局部化比较的边界引理"：固定余纤维旋转符号后，\(\partial_w\) 与 \(\partial_a\) 都可写成经由局部化逆与纤维含入的带符号屋顶。最后是非零性：有理化后八层次数严格递减迫使一切有理边界为零，但谱层面的边界可以非零。条件判据说：若典范映射 \(u_X:L_0X\to L_0L_{K(2)}X\) 不杀死 \(\beta_3\)，则 \(d_3\neq0\)——否则 \(h|_{U_3}\) 可提升到 \(X\)，而 \(U_3\) 的 \(E(1)\)-局部性使其与 \(K(2)\)-单位的复合必为零，有理化后与假设矛盾。姊妹篇定理恰给出该非零性，经完备化与局部化两个自然性方块以及 \(\pi_{-3}L_0X=\Qp\alpha_3\) 的一维性即完成。

## 可信度与备注

本文与一般素数范围的滤过存在性篇相互独立又彼此印证：那篇的定理在 \(n=3\)（即 \(p\geq5\)）给出同样结论，本文不依赖它，而是自行构造全部映射，并额外给出附件识别与首条黏合的非零性。主结果暂无形式化证明，请以社区核验为准；按 OpenAI 官方声明，未经形式化的结果可能有问题，宜以社区核验为最终标准。

{% endraw %}
