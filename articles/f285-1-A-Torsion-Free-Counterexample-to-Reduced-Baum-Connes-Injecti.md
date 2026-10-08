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

## 入门导读 🐣

每个群都有两份档案：一份记它的"形状"（拓扑），一份记它生成的算子代数（分析）。两者之间有一座标准桥梁，叫装配映射；著名的 Baum–Connes 猜想断言这座桥不丢信息。本文造出一个有限生成、无挠的群：一块拓扑侧的无限阶"石块"过桥后竟消失得无影无踪——桥确实会丢东西。

**关键词卡片**

- 装配映射（assembly map）：从拓扑侧 K-同调通往算子代数 K-理论的桥
- 约化群 C*-代数（reduced group C*-algebra）：群左正则表示打包成的算子代数
- K-理论（K-theory）：给空间或代数记"账"的不变量
- 无挠群（torsion-free）：没有有限阶元素的群
- Bott 生成元（Bott generator）：环面 K-理论里的基本"计量块"

**看个具体例子**

石块来自大家熟悉的环面 `@@M@@T^2@@`：其自旋 Dirac 类 `@@M@@[D_{T^2}]@@` 经嵌入映射推入大群 `@@M@@G_{\mathrm{inj}}@@` 的拓扑侧，记作 `@@M@@h@@`。

公式卡（数字版定理）：`@@M@@\langle(Bi)^*c,[T^2]\rangle=1@@`（配对等于 1，保证 `@@M@@h@@` 是无限阶元素），但 `@@M@@\mu^r_{G_{\mathrm{inj}}}(h)=0@@`——同一块石块，拓扑侧非零无限阶，过桥后归零。

<div>

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 560 280">
  <line x1="20" y1="185" x2="170" y2="185" stroke="#000" stroke-width="4"/>
  <line x1="390" y1="185" x2="540" y2="185" stroke="#000" stroke-width="4"/>
  <path d="M170 178 Q 280 70 390 178" fill="none" stroke="#333" stroke-width="2"/>
  <rect x="72" y="147" width="34" height="34" fill="none" stroke="#000" stroke-width="2"/>
  <text x="40" y="136" font-size="13" fill="#000">h：无限阶</text>
  <rect x="452" y="147" width="34" height="34" fill="none" stroke="#c00" stroke-width="2" stroke-dasharray="5,4"/>
  <text x="432" y="136" font-size="13" fill="#c00">μ(h) = 0</text>
  <text x="238" y="88" font-size="13" fill="#333">装配映射 μ</text>
  <text x="52" y="212" font-size="13" fill="#000">拓扑侧 K(BG)</text>
  <text x="420" y="212" font-size="13" fill="#000">分析侧 K(C_r^*(G))</text>
  <text x="103" y="252" font-size="13" fill="#000">同一块石块 h：过桥前无限阶，过桥后归零</text>
</svg>

</div>

**为什么值得关心**

这是首个"无系数、无挠群"情形的反例，动摇了 Baum–Connes 猜想最核心的版本；但注意经典 Novikov 猜想与最大装配版本并未被推翻。

> 暂无形式化证明（AI 结果待核验）

## 一句话结论

本文构造了一个有限生成无挠群 `@@M@@G_{\mathrm{inj}}@@`：环面 Dirac 类 `@@M@@(Bi)_*[D_{T^2}]@@` 在拓扑侧是无限阶元素，经约化 Baum–Connes 装配映射（assembly map）后却变成零。这个无限阶核类推翻了无挠群、无系数情形约化 Baum–Connes 猜想的有理单射性。

## 问题背景

对离散群 `@@M@@G@@`，约化 Baum–Connes 装配映射 `@@M@@\mu_G^r\colon K_*(BG)\to K_*(C_r^*(G))@@` 从分类空间（classifying space）`@@M@@BG@@` 的紧支撑 `@@M@@K@@`-同调指向约化群 `@@M@@C^*@@`-代数（reduced group `@@M@@C^*@@`-algebra）的 `@@M@@K@@`-理论；猜想断言它是同构。它由 Baum 与 Connes 于 1982 年提出（2000 年正式发表），是 Novikov 猜想与椭圆指标理论的算子代数化身。正结果丰厚：Higson–Kasparov 处理了在 Hilbert 空间上有真仿射等距作用的群（含可数顺群），Mineyev–Yu 与 Lafforgue 处理了双曲群。反例一侧，Higson–Lafforgue–Skandalis 2002 年给出的是带交换系数与 groupoid 情形，且只涉满射；系数恰为 `@@M@@\mathbb C@@` 的离散群情形，单射性从未被否定。本文补上的正是这块最核心的空白。

## 主要结果

**定理**：存在有限生成无挠离散群 `@@M@@G_{\mathrm{inj}}@@`、单同态 `@@M@@i\colon\mathbb Z^2\to G_{\mathrm{inj}}@@` 与上同调类 `@@M@@c\in H^2(BG_{\mathrm{inj}};\mathbb Z)@@`，使得
`@@M@@D\langle(Bi)^*c,[T^2]\rangle=1,\qquad i_*(\beta)=0\ \text{in}\ K_0(C_r^*G_{\mathrm{inj}}),@@`
其中 `@@M@@\beta@@` 是 `@@M@@K_0(C_r^*\mathbb Z^2)\cong K_0(C(\mathbb T^2))@@` 的秩零 Bott 生成元（Bott generator），`@@M@@[D_{T^2}]@@` 是环面的自旋 Dirac `@@M@@K@@`-同调类。于是 `@@M@@h=(Bi)_*[D_{T^2}]@@` 在 `@@M@@K_0(BG_{\mathrm{inj}})@@` 中有无限阶，而 `@@M@@\mu^r_{G_{\mathrm{inj}}}(h)=0@@`：核里有无限阶整元素，有理单射性随之失效。两点精细限定：群有限生成，但有限呈现不在结论之列；改用最大装配映射（maximal assembly）时同一类 `@@M@@h@@` 的像非零（由 Hanke–Schick 的低度非零定理），故最大形式的强 Novikov 猜想与经典 Novikov 猜想（高阶符号的同伦不变性）均未被推翻。

## 证明思路

全证分三块：造群、建检测子、做 Bott 消没。

先造群。把一个分层图塔用交错有限流标记（沿 Osajda 的图形小消去路线），随机标记以一致概率具有扩张隙（expansion gap），剪枝剔除会干扰重叠估计的短回流；随后给每条边赋整 Heisenberg 群 `@@M@@\mathsf H=\langle x,y,z\mid[x,y]=z\rangle@@` 中的电压（voltage），作电压覆盖。`@@M@@\mathsf H@@` 无挠且含交换对 `@@M@@(z,x)@@`，为最终环面埋下伏笔，而围长控制保证幸存的短路不是 `@@M@@\mathsf H@@` 中的关系。几何实现把 `@@M@@\mathsf H@@` 嵌入群 `@@M@@\Gamma_\nu@@`，借由"叶"（sheet，嵌入覆盖的平移）拼成的复形中的整闭链分解，既证无挠，又把嵌入环面的定向类延拓为整个群上的积分检测子 `@@M@@c@@`。

核心的解析步骤是 Bott 消没。模型空间按高度 `@@M@@i\ge0@@` 分层，每层放一个环面上紧支撑的 Bott 差 `@@M@@a_i@@`。念头是 Eilenberg swindle 式的高度平移：在不相交对 `@@M@@(0,1),(2,3),\dots@@` 上用"旋转＋再尺度化"的投影同伦把偶族移成奇族，再用 `@@M@@(1,2),(3,4),\dots@@` 把奇族移成正偶族；两条同伦结合有限可加性，迫使高度零那一项的 `@@M@@K_0@@` 类为零。难点在于这些族必须是真实有界算子、同伦须落在约化代数的范数序列商 `@@M@@\mathcal Q_r=\prod_\nu A_\nu/\bigoplus_\nu A_\nu@@` 内：论文用扩散算子与载体投影（迹 `@@M@@\le C2^{-700H_i}@@`）、剪裁估计、森林范数估计，把每个指定轮廓以有限 Cayley 公式在完全正则算子范数下一致逼近；精度序列 `@@M@@\nu@@` 取商后，近似化为精确等式。最后经"逐坐标相等"引理取充分晚的坐标，再用多项式逼近该等式的有限见证所涉的群元素，连同 `@@M@@\mathsf H@@` 的生成元一起生成 `@@M@@G_{\mathrm{inj}}@@`——有限生成性由此获得，而非一开始就具备。

收尾把两条线缝合：由 Atiyah–Singer 指标定理，`@@M@@h@@` 与线丛类 `@@M@@[L]-[1]@@` 的指标配对等于 `@@M@@1@@`，故 `@@M@@h@@` 无限阶；而装配像经子群自然性化为 `@@M@@j_*\mu^r_{\mathbb Z^2}([D_{T^2}])=i_*(\beta)=0@@`。

## 可信度与备注

本文暂无形式化证明。结果族 285 三篇互补：本篇（无挠群）破单射，无理迹姊妹篇破满射，投影姊妹篇推翻 Kadison–Kaplansky 猜想，合起来宣告无系数约化 Baum–Connes 猜想对可数离散群不成立。按 OpenAI 官方声明，未经形式化的结果可能有问题，请以社区核验为准。

{% endraw %}
