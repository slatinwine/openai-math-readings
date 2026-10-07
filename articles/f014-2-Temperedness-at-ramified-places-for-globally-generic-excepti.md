---
layout: default
title: "Temperedness at ramified places for globally generic exceptional groups"
family: "014"
discipline: "Number theory"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | Temperedness at ramified places for globally generic exceptional groups

> 结果族 014：Restricted geometric Langlands, global Arthur enhancements, and generic Ramanujan　·　学科：Number theory　·　验证状态：暂无形式化证明，请以社区核验为准

## 一句话结论

对函数域上 \(G_2,F_4,E_6,E_7,E_8\) 型分裂伴随例外单群，论文证明广义拉马努金猜想：整体泛型（globally generic）尖点自守表示的每个局部分量都温和（tempered），无任何特征与分歧深度限制，把姊妹篇的非分歧定理推进到全部分歧位。

## 问题背景

拉马努金猜想断言：尖点自守表示（cuspidal automorphic representation）的每个局部分量都温和，即酉且弱包含于正则表示。函数域上 Drinfeld 证明了 \(\GL_2\)，Laurent Lafforgue 证明了 \(\GL_n\)，Lomelí 处理了分裂典型群与拟分裂酉群，例外群此前只有带附加假设的部分结果。难点在分歧位：非分歧参数由 Satake 类决定，而分歧位的 Weil–Deligne 参数还含幺幂单项算子（monodromy operator）\(N\)；Vincent Lafforgue 的 excursion 理论与 Genestier–Lafforgue 的相容性只给出半单 Weil 参数，不携带 \(N\)。本文补上缺失的单项算子比较。

## 主要结果

主定理：设 \(F=\mathbb F_q(X)\) 为函数域，\(G/F\) 是 \(G_2,F_4,E_6,E_7,E_8\) 型分裂连通伴随绝对单群。若 \(\pi=\bigotimes'_v\pi_v\) 是 \(G(\mathbb A_F)\) 上整体泛型的复尖点自守表示——某向量的 Whittaker 系数对每个单根坐标均非平凡——则每个 \(\pi_v\) 都温和，对特征、分歧深度、表示类型均无限制；经典类型已由 Lomelí 覆盖。

技术核心是局部判别法（纯完备判别法）：设 \(\tau\) 是局部函数域上分裂伴随单群的不可约泛型光滑表示，若其半单 Weil 参数 \(\rho_\tau\) 容许伴随表示权零纯（pure of weight zero）的 Weil–Deligne 完备 \((\rho_\tau,N_*)\)——Frobenius 在单项滤波（monodromy filtration）第 \(j\) 层分块上的特征值绝对值均为 \(Q^{j/2}\)——则 \(\tau\) 温和。权零纯允许 Weil 部分特征值偏离单位圆，只要求沿 Jordan 链对称分布；判别法不预设局部 Langlands 对应。

## 证明思路

"先全局取纯性，再局部判别"。全局输入是姊妹篇的非分歧定理：有一个泛型非分歧分量，则全部非分歧分量温和。全局 Whittaker 泛函的加性特征处处非平凡，故每个 \(\pi_v\) 都泛型且几乎处处非分歧；于是伴随局部系统 \(\Ad\circ\Sigma\)（\(\Sigma\) 为 excursion 参数）在非分歧位点态权零纯。任意位处，Deligne 的 Weil II 局部单项定理再给出权零纯的局部 Weil–Deligne 表示，Genestier–Lafforgue 相容性保证其 Weil 部分恰为 \(\rho_{\pi_v}\)，判别法即得温和。

判别法用反证法：若 \(\tau\) 非温和，Langlands 分类把它写成 \(I_P^G(\sigma_\nu)\) 的 Langlands 商，\(P=MR\) 真包含，\(\sigma\) 温和，\(\nu\) 在正腔。先由 Gan–Harris–Sawin 温和完备定理给 \(\sigma\) 配 \((\rho_\sigma,N_M)\)，\(\nu\)-扭转后嵌入对偶群得 \((r,N_M)\)，Weil 部分即 \(\rho_\tau\)。再证伴随 \(L\)-因子在 \(s=1\) 正则：长交缠算子的像为泛型 Langlands 商，故局部系数 \(C_G(\nu,\sigma)\) 非零；比较定理把 \(C_G(z,\sigma)\) 表为 \(\prod_b L(1-b(z),r_b^\vee)/L(b(z),r_b)\)，因 \(b(\nu)>0\)，分母正则、分子被迫无极点，由 \(\Lie(\widehat G)=\Lie(\widehat M)\oplus\widehat{\mathfrak n}\oplus\widehat{\mathfrak n}^-\) 三分解得正则。所设纯完备 \((r,N_*)\) 同样正则；由轨道命题，伴随正则迫使单项算子落入唯一开轨道，故二者共轭，纯性传给 \((r,N_M)\)。而 \(\widehat{\mathfrak n}\) 是直和项，纯性使其 Frobenius 行列式绝对值为 \(1\)；但扭转前该值为 \(1\)，\(\nu\)-扭转把它乘成 \(Q^{-\sum_b b(\nu)\dim V_b}\)，严格小于 \(1\)，矛盾。

比较定理分三步：先证诱导族的 Whittaker 余不变量线自由秩一且与特化交换；再用 Weyl 元初等分解与乘法性化到秩一情形（Tate \(\gamma\) 因子）；最后对超尖点数据，用 Gan–Lomelí 整体化定理造出仅在指定位等于 \(\sigma\)、他处为主序列的整体泛型尖点表示，比对自守与几何两侧的函数方程，他处因子相消。关键引理——同一 Weil 部分的两个 Weil–Deligne 表示的 \(L\)-因子比值只差一个单位——使比较无需识别单项算子，绕开"半单参数不含 \(N\)"之障碍。

## 可信度与备注

本文是 OpenAI 2026 年 10 月 5 日的预印本，主结果暂无形式化证明，请以社区核验为准。姊妹篇的非分歧拉马努金定理是本文唯一的全局输入，两者合并即族概述中"每个位都拉马努金、无特征与分歧深度限制"的结论；局部判别法适用于任意分裂伴随单群，可独立复用。按 OpenAI 官方声明，未经形式化的结果可能有问题。

{% endraw %}
