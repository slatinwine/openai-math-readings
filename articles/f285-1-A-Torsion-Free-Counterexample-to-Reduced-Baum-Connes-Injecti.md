---
layout: default
title: "A torsion-free counterexample to reduced Baum–Connes injectivity"
family: "285"
discipline: "Operator algebras"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | A torsion-free counterexample to reduced Baum–Connes injectivity

> 结果族 285：Counterexamples to Baum–Connes and Kadison–Kaplansky　·　学科：Operator algebras　·　验证状态：暂无形式化证明，请以社区核验为准

## 一句话结论

本文构造了一个有限生成无挠群 \(G_{\mathrm{inj}}\)：环面 Dirac 类 \((Bi)_*[D_{T^2}]\) 在拓扑侧是无限阶元素，经约化 Baum–Connes 装配映射（assembly map）后却变成零。这个无限阶核类推翻了无挠群、无系数情形约化 Baum–Connes 猜想的有理单射性。

## 问题背景

对离散群 \(G\)，约化 Baum–Connes 装配映射 \(\mu_G^r\colon K_*(BG)\to K_*(C_r^*(G))\) 从分类空间（classifying space）\(BG\) 的紧支撑 \(K\)-同调指向约化群 \(C^*\)-代数（reduced group \(C^*\)-algebra）的 \(K\)-理论；猜想断言它是同构。它由 Baum 与 Connes 于 1982 年提出（2000 年正式发表），是 Novikov 猜想与椭圆指标理论的算子代数化身。正结果丰厚：Higson–Kasparov 处理了在 Hilbert 空间上有真仿射等距作用的群（含可数顺群），Mineyev–Yu 与 Lafforgue 处理了双曲群。反例一侧，Higson–Lafforgue–Skandalis 2002 年给出的是带交换系数与 groupoid 情形，且只涉满射；系数恰为 \(\mathbb C\) 的离散群情形，单射性从未被否定。本文补上的正是这块最核心的空白。

## 主要结果

**定理**：存在有限生成无挠离散群 \(G_{\mathrm{inj}}\)、单同态 \(i\colon\mathbb Z^2\to G_{\mathrm{inj}}\) 与上同调类 \(c\in H^2(BG_{\mathrm{inj}};\mathbb Z)\)，使得
\[\langle(Bi)^*c,[T^2]\rangle=1,\qquad i_*(\beta)=0\ \text{in}\ K_0(C_r^*G_{\mathrm{inj}}),\]
其中 \(\beta\) 是 \(K_0(C_r^*\mathbb Z^2)\cong K_0(C(\mathbb T^2))\) 的秩零 Bott 生成元（Bott generator），\([D_{T^2}]\) 是环面的自旋 Dirac \(K\)-同调类。于是 \(h=(Bi)_*[D_{T^2}]\) 在 \(K_0(BG_{\mathrm{inj}})\) 中有无限阶，而 \(\mu^r_{G_{\mathrm{inj}}}(h)=0\)：核里有无限阶整元素，有理单射性随之失效。两点精细限定：群有限生成，但有限呈现不在结论之列；改用最大装配映射（maximal assembly）时同一类 \(h\) 的像非零（由 Hanke–Schick 的低度非零定理），故最大形式的强 Novikov 猜想与经典 Novikov 猜想（高阶符号的同伦不变性）均未被推翻。

## 证明思路

全证分三块：造群、建检测子、做 Bott 消没。

先造群。把一个分层图塔用交错有限流标记（沿 Osajda 的图形小消去路线），随机标记以一致概率具有扩张隙（expansion gap），剪枝剔除会干扰重叠估计的短回流；随后给每条边赋整 Heisenberg 群 \(\mathsf H=\langle x,y,z\mid[x,y]=z\rangle\) 中的电压（voltage），作电压覆盖。\(\mathsf H\) 无挠且含交换对 \((z,x)\)，为最终环面埋下伏笔，而围长控制保证幸存的短路不是 \(\mathsf H\) 中的关系。几何实现把 \(\mathsf H\) 嵌入群 \(\Gamma_\nu\)，借由"叶"（sheet，嵌入覆盖的平移）拼成的复形中的整闭链分解，既证无挠，又把嵌入环面的定向类延拓为整个群上的积分检测子 \(c\)。

核心的解析步骤是 Bott 消没。模型空间按高度 \(i\ge0\) 分层，每层放一个环面上紧支撑的 Bott 差 \(a_i\)。念头是 Eilenberg swindle 式的高度平移：在不相交对 \((0,1),(2,3),\dots\) 上用"旋转＋再尺度化"的投影同伦把偶族移成奇族，再用 \((1,2),(3,4),\dots\) 把奇族移成正偶族；两条同伦结合有限可加性，迫使高度零那一项的 \(K_0\) 类为零。难点在于这些族必须是真实有界算子、同伦须落在约化代数的范数序列商 \(\mathcal Q_r=\prod_\nu A_\nu/\bigoplus_\nu A_\nu\) 内：论文用扩散算子与载体投影（迹 \(\le C2^{-700H_i}\)）、剪裁估计、森林范数估计，把每个指定轮廓以有限 Cayley 公式在完全正则算子范数下一致逼近；精度序列 \(\nu\) 取商后，近似化为精确等式。最后经"逐坐标相等"引理取充分晚的坐标，再用多项式逼近该等式的有限见证所涉的群元素，连同 \(\mathsf H\) 的生成元一起生成 \(G_{\mathrm{inj}}\)——有限生成性由此获得，而非一开始就具备。

收尾把两条线缝合：由 Atiyah–Singer 指标定理，\(h\) 与线丛类 \([L]-[1]\) 的指标配对等于 \(1\)，故 \(h\) 无限阶；而装配像经子群自然性化为 \(j_*\mu^r_{\mathbb Z^2}([D_{T^2}])=i_*(\beta)=0\)。

## 可信度与备注

本文暂无形式化证明。结果族 285 三篇互补：本篇（无挠群）破单射，无理迹姊妹篇破满射，投影姊妹篇推翻 Kadison–Kaplansky 猜想，合起来宣告无系数约化 Baum–Connes 猜想对可数离散群不成立。按 OpenAI 官方声明，未经形式化的结果可能有问题，请以社区核验为准。

{% endraw %}
