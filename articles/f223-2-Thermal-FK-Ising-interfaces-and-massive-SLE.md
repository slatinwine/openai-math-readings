---
layout: default
title: "Thermal FK–Ising interfaces and massive SLE"
family: "223"
discipline: "Probability and statistical mechanics"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | Thermal FK–Ising interfaces and massive SLE

> 结果族 223：Random-cluster interfaces: critical, disordered, thermal, and natural-time scaling　·　学科：Probability and statistical mechanics　·　验证状态：暂无形式化证明，请以社区核验为准

## 入门导读 🐣

把磁铁的温度从临界点调开一点点：分界线不再是无偏的随机漫步，更像在起风的天气里飘的丝带——布朗式的随机抖动还在，但多了一股"风"推着它偏。这篇论文严格证明：这股风的强度和方向由一个确定的方程给出，极限曲线唯一存在，而且不依赖你用哪种格子、怎样逼近区域。

**关键词卡片**

- 质量 m（mass）：偏离临界温度的度量，正负对应往哪个方向偏。
- 等半径格点（isoradial lattice）：一大类"菱形拼出来的"格点，方格只是特例。
- massive SLE（massive Schramm–Loewner evolution）：带漂移的 SLE——布朗驾驶外加风力修正。
- 边值问题（boundary value problem）：方程 `@@M@@\Delta h=-4m|\nabla h|@@` 定出风场 `@@M@@h@@`，漂移由它算出。
- 有限能量（finite energy）：漂移满足 `@@M@@\int_0^T C_t^2dt<\infty@@`，保证理论不出"无穷风"。

**看个具体例子**

极限的驾驶方程是 `@@M@@\dd W_t=\sqrt{16/3}\,\dd B_t+\tfrac{2\pi}{3}C_t\,\dd t@@`：前一项是纯布朗随机性，后一项是风。代入特例 `@@M@@m=0@@`（恰在临界点），风场退化、`@@M@@C_t\equiv0@@`，方程还原成纯 `@@M@@\mathrm{SLE}_{16/3}@@` 的驾驶方程——临界情形被严丝合缝地包含在内。

<div>

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 560 280">
  <text x="20" y="24" font-size="15" fill="#333">临界（m=0）与偏离临界（m≠0）的界面形状对比</text>
  <rect x="60" y="50" width="180" height="180" fill="#f7f7f7" stroke="#333" stroke-width="2"/>
  <text x="95" y="40" font-size="14" fill="#333">m=0：SLE₁₆/₃</text>
  <path d="M60,230 C85,200 120,190 110,155 C100,120 150,120 150,95 C150,75 200,80 240,50" fill="none" stroke="#c33" stroke-width="3"/>
  <rect x="320" y="50" width="180" height="180" fill="#f7f7f7" stroke="#333" stroke-width="2"/>
  <text x="345" y="40" font-size="14" fill="#333">m＞0：massive SLE</text>
  <path d="M320,230 C350,205 365,175 375,150 C385,125 405,105 430,85 C450,70 475,60 500,50" fill="none" stroke="#c33" stroke-width="3"/>
  <line x1="480" y1="70" x2="512" y2="46" stroke="#36c" stroke-width="2.5"/>
  <polygon points="516,43 505,42 510,53" fill="#36c"/>
  <text x="470" y="105" font-size="13" fill="#36c">漂移＝风</text>
  <text x="20" y="262" font-size="14" fill="#333">风由质量边值问题确定；m&lt;0 时经对偶与反向行走得到</text>
</svg>

</div>

**为什么值得关心**

"Makarov–Smirnov 非临界纲领"此前只有零散观测输入，本文补上唯一性与收敛的完整随机分析，是 FK-Ising 非临界几何的第一块完整基石。

> 暂无形式化证明（AI 结果待核验）

## 一句话结论
本文证明偏离临界温度的 FK–Ising 界面在极一般的区域与格点逼近下沿全序列收敛到唯一的"热质量 SLE`@@M@@_{16/3}@@`"：漂移由一个质量边值问题给出的有限能量泛函确定，负质量经对偶与反转得到，从而把 Makarov–Smirnov 非临界界面纲领在 FK–Ising 情形完整实现。

## 问题背景
临界 FK–Ising 模型（cluster weight `@@M@@q=2@@` 的随机簇模型）的 Dobrushin 界面收敛到弦 `@@M@@\mathrm{SLE}_{16/3}@@`，这是 Smirnov 费米观测量方法的标志性成果，后续由 Chelkak–Smirnov 推广到等半径（isoradial）格点、由 CDCHKS 等完成界面收敛。自然的问题是：把温度在网格尺度上移离临界点，界面极限变成什么？Makarov 与 Smirnov 为此提出了非临界纲领：求观测量的标度极限、导出驱动方程、再证界面的唯一性与收敛。术语"massive SLE"虽描述了预期形变，却并未给出具体的连续过程；Park 建立了质量两点费米观测量与近临界矩形穿越估计，提供了输入，但"唯一的界面定律是否存在、等于什么"仍缺随机分析。难点在于漂移系数依赖于整条曲线的历史，其可测性、绝对连续性与能量控制都不能先验假定。

## 主要结果
定理（main.tex 的 Theorem 2.1）：设有界单连通域 `@@M@@\Omega@@`、边界素端（prime end）`@@M@@a,b@@` 与非零实质量 `@@M@@m@@`。对任何满足一致角度约束的等半径格点域序列、满足标记 Carathéodory 收敛（区域的物理直径可以发散）的区域逼近、以及 nome 比值 `@@M@@r_\delta/\delta\to|m|/2@@` 的温度扰动，归一化界面 `@@M@@\chi_\delta\circ\gamma_\delta@@` 的 law 沿全序列收敛，且极限 `@@M@@\mu_{\Omega,a,b,m}@@` 不依赖格点、逼近与 nome 序列的选取。`@@M@@m>0@@` 时它是唯一的 massive `@@M@@\mathrm{SLE}_{16/3}@@` 律：驱动函数满足
`@@M@@D\dd W_t=\sqrt{16/3}\,\dd B_t+\tfrac{2\pi}{3}C_t\,\dd t,\qquad C_t=\tfrac4\pi\int_{\mathbb H}\Im\tfrac{-1}{v}\,\mu_t(v)|\nabla(h_t\circ\psi_t)(v)|\,\dd A(v),@@`
其中 `@@M@@h_t@@` 是活动域上质量边值问题 `@@M@@\Delta h=-4m|\nabla h|@@`（原侧取 `@@M@@1@@`、对偶侧取 `@@M@@0@@`）的有界解，`@@M@@\psi_t@@` 是尖端处的逆共形映射，`@@M@@\mu_t=m|\psi_t'|@@`；且漂移满足有限能量条件 `@@M@@\int_0^T C_t^2\,\dd t<\infty@@`。方差、漂移的绝对连续性与有限能量都是证明的结论而非假设；负质量由对偶与时间反转得到。

## 证明思路
证明先经 Kemppainen–Smirnov 的穿越—Loewner 紧性理论取出子序列极限曲线与驱动，再分三步完成识别。第一步是"动点能量估计"：在尚不知道驱动是否为半鞅时，跟踪一个物理点在以其到驱动距离定义的 Loewner 时钟（point clock）下的角坐标 `@@M@@X@@`。先由条件穿越界（条件 G3 与 FK 正相联给出的环形阻挡电路）得到重启后 `@@M@@X@@` 的上确界幂尾与共形半径下降控制；再对避开的边界球做 Schwarz 反射，用 Koebe 偏差与对空间变量（而非驱动）求导的确定性 Loewner 恒等式，得到反弹界；最后取小幂 `@@M@@p<1/4@@` 构造指数收缩，经二进壳分解、带 `@@M@@\sin^p@@` 权的 Cauchy–Schwarz 与对物理面积的 Tonelli 定理，得到 `@@M@@\E\int_0^\infty J_t^2\,\dd t\le K m^2\,\mathrm{area}(\Omega)@@`。第二步做随机 Green 势演算：高度截断使容量、漂移变差与空间鞅括号在同一时钟下同时有密度，近尖展开识别出驱动方程中的密度，即二次变差为 `@@M@@16/3@@`、变差测度密度为 `@@M@@\tfrac{2\pi}{3}C_t@@`。第三步证唯一性：把 `@@M@@C_t@@` 延拓为非预期可测泛函，对有限能量弱解用能量停时 `@@M@@\sigma_n@@` 与停时 Girsanov 变换证明任何两个候选解的停止律都由同一个 Wiener 泛函表示，从而定律唯一；存在性由方形网格上的一个有界逼近经紧性给出，于是全序列收敛。最后用边界簇探索、受限长度—面积估计与"强制闸门"层级把可能发散的远程区域局部化成有界 Dobrushin 问题，保证圆盘曲线拓扑不被破坏；负质量情形由对偶与反转归结为正质量。

## 可信度与备注
本文主结果暂无形式化证明，属于 OpenAI 数学成果批量发布的一部分，官方声明"未经形式化的结果可能有问题"，请以社区核验为准。文章依赖并引用了 Park 的质量观测量与近临界穿越估计等前置输入，这些同样待核。它与本结果族中临界情形的姊妹篇（临界方形格点随机簇界面收敛到 `@@M@@\mathrm{SLE}_\kappa@@` 及其自然占据测度）互为支撑：临界理论提供紧性与穿越界的模板，本文则补上非临界漂移识别与唯一性这一缺失环节。

{% endraw %}
