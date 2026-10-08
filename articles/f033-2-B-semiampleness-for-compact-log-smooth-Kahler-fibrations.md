---
layout: default
title: "B-semiampleness for compact log-smooth Kähler fibrations"
family: "033"
discipline: "Algebraic and complex geometry"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | B-semiampleness for compact log-smooth Kähler fibrations

> 结果族 033：Iitaka subadditivity, variation, and logarithmic additivity　·　学科：Algebraic and complex geometry　·　验证状态：暂无形式化证明，请以社区核验为准

## 入门导读 🐣

想象一本"变形图鉴"：每翻一页，图形就变一点。数学家研究这样一族变形对象时，总账能拆成两笔：一笔记录"哪些页面上图形变坏了"，另一笔记录"形状变化的幅度"。这篇论文证明：后一笔账——模部分——在换一个更干净的账本后，可以被放大若干倍"打印"成一张真正可用的地图（由整体截面生成），而且是在没有全局坐标系的凯勒世界里完成的。

**关键词卡片**

- 纤维化（fibration）：一族几何对象随底参数空间连续变化而形成的总空间。
- 典范丛公式（canonical bundle formula）：把总空间的"弯曲量"拆成判别式与模部分的记账公式。
- 判别式（discriminant）：记录退化、奇异纤维贡献的那部分。
- 模部分（moduli part）：记录纤维形状随参数如何变化的那部分。
- b-半丰富（b-semiample）：在某个修正模型上，某个正倍数能被整体截面生成，从而定义一个映射。

**看个具体例子**

以椭圆纤维化 `@@M@@f:Y\to X@@` 为例：坏纤维记入判别式，纤维形状（`@@M@@j@@`-不变量）的变化记入模部分 `@@M@@M_X@@`。定理说：存在光滑修改 `@@M@@S\to X@@`，使得对一切更高的修改 `@@M@@\nu:S_1\to S@@` 都有 `@@M@@M_{S_1}=\nu^*M_S@@`，且某个倍数 `@@M@@mM_S@@` 的整体截面给出真正的全纯映射——"变形的幅度"变成了实实在在的地图。

<div>

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 560 280"><line x1="70" y1="225" x2="480" y2="225" stroke="#333" stroke-width="2"/><text x="400" y="252" font-size="14" fill="#333">底空间 X</text><path d="M85 205 C 95 155 125 155 135 205" fill="none" stroke="#666" stroke-width="1.6"/><path d="M185 205 C 195 90 225 90 235 205" fill="none" stroke="#666" stroke-width="1.6"/><path d="M285 205 C 295 20 325 20 335 205" fill="none" stroke="#666" stroke-width="1.6"/><path d="M385 205 C 395 155 425 155 435 205" fill="none" stroke="#666" stroke-width="1.6"/><line x1="110" y1="205" x2="110" y2="225" stroke="#aaa" stroke-dasharray="3 3"/><line x1="210" y1="205" x2="210" y2="225" stroke="#aaa" stroke-dasharray="3 3"/><line x1="310" y1="205" x2="310" y2="225" stroke="#aaa" stroke-dasharray="3 3"/><line x1="410" y1="205" x2="410" y2="225" stroke="#aaa" stroke-dasharray="3 3"/><text x="120" y="42" font-size="14" fill="#666">纤维形状随参数变化</text><ellipse cx="500" cy="105" rx="34" ry="20" fill="none" stroke="#555" stroke-width="1.6"/><text x="478" y="110" font-size="13" fill="#555">参数空间</text><line x1="450" y1="200" x2="488" y2="130" stroke="#555" stroke-width="1.6"/><polygon points="490,127 487,141 480,136" fill="#555"/><text x="440" y="75" font-size="13" fill="#555">截面给出映射</text></svg>

</div>

**为什么值得关心**

模部分的半丰富性是极小模型纲领中把"正性"兑换成"映射"的关键齿轮；本文把此前只在代数（射影）范畴成立的结果推进到解析范畴，还啃下了边界系数为 1 的最难情形。

> 暂无形式化证明（AI 结果待核验）

## 一句话结论

论文证明了 b-半丰富性猜想（b-semiampleness conjecture）的紧 Kähler、log 光滑情形：即使底与全空间均非射影、边界含系数 1 的分量，moduli 有理 b-线丛仍可在某个修改模型上被整体全纯截面生成，补上了代数范畴已知结论与解析范畴之间明确遗留的缺口。

## 问题背景

典范丛公式（canonical bundle formula）把纤维化的典范几何拆成判别式（discriminant，度量奇异纤维贡献）与 moduli 部分（度量族的变化）。b-半丰富性猜想预测 moduli 部分的某个倍数在底的双有理模型上定义一个态射，是极小模型纲领中连接正性与丰富性的关键一环。Kawamata 的 Hodge 半正性是其源头；Ambro 建立了 moduli 部分的双有理稳定与一般 klt 情形的正性；Fujino–Gongyo 证明射影 lc-平凡纤维化的 b-nef 性；Bakker–Filipazzi–Mauri–Tsimerman（BFMT）在代数范畴证明了该猜想，但其讨论保留映射的射影性，Kähler（解析）情形在其论文 Remarks 6.31 与 7.5 中被明确指出并未随之解决。难点有三：非射影 Kähler 流形缺少丰富线丛作锚点；边界系数可为 1，使 Hodge 结构从纯变分（pure variation）变为混合变分（mixed variation）；数值半正性不足以产生实际全纯线丛的整体生成。

## 主要结果

设 `@@M@@f:Y\to X@@` 是紧 Kähler 流形间具连通纤维的满射全纯映射，`@@M@@\Delta@@` 是有效有理除子，支撑单正规交叉（simple normal crossing）、系数落在 `@@M@@[0,1]@@`，且 `@@M@@K_Y+\Delta\sim_{\mathbb{Q}}f^*L@@`（`@@M@@L\in\Pic(X)_{\mathbb{Q}}@@`）。对每个修改 `@@M@@\mu:X'\to X@@`，用 log 常规阈值（log canonical threshold）`@@M@@t_P@@` 定义判别式 `@@M@@B_{X'}=\sum_P(1-t_P)P@@` 与 moduli 部分 `@@M@@M_{X'}=\mu^*L-K_{X'}-B_{X'}@@`。主定理：moduli 有理 b-线丛 `@@M@@\mathbf M=(M_{X'})@@` 是 b-半丰富的——存在光滑紧 Kähler 修改 `@@M@@S\to X@@`，使得 (a) 对每个进一步的修改 `@@M@@\nu:S_1\to S@@` 都有 `@@M@@M_{S_1}=\nu^*M_S@@`（在 `@@M@@\Pic(S_1)_{\mathbb{Q}}@@` 中）；(b) 某个正整数倍 `@@M@@mM_S@@` 由其整体全纯截面生成。水平系数 1 分量被允许，点底与相对维数零亦然；不假设 `@@M@@f@@`、`@@M@@X@@`、`@@M@@Y@@` 的射影性，也不假设 Campana 轨道 Iitaka 假设。论文特别指出该判别式是阈值型而非轨道底的重数下确界除子，故把多重形式分解产生的 Hodge 线与它等同是证明的主要步骤之一。

## 证明思路

先取边界单正规交叉的紧 Kähler 修改 `@@M@@S@@`，局部取相对 log 多重体积线的 `@@M@@m@@` 次根覆盖：其最高 Hodge 特征空间一维，根形式 `@@M@@\tau@@` 在好开集上只有沿系数 1 分量的对数极点。系数 1 部分天然产生混合变分结构；通过迭代留数（iterated residue），把这条线经由单一纯权等级（pure weight grade）与最深边界层的体积线等同——此步依赖 Fujino–Fujisawa 的混合 Hodge 延拓定理，保证该约化在圆盘上与延拓相容。随后是全文最精细的局部计算：在分辨后的横向圆盘上做幂替换 `@@M@@t=u^N@@`，用变量替换恒等式（含基雅可比）逐除子追踪阶数，证明根体积的规范化 Hodge 阶恰为 `@@M@@\operatorname{ord}_P^{\mathrm{Hodge}}(\tau)=t_P-1@@`。由此得到两个关键推论：典范 Hodge 延拓就是实际的 moduli 线；该等同在每个更高光滑模型上拉回，即定理的 (a)。再向最深的边界层伴随，得到 log 典范丛平凡的紧 Kähler klt 纤维；Matsumura–Wang–Wu–Zhang 的定理给出其有限乘积覆盖。逐点的乘积分解不足以推出半丰富性，作者转而构造带截面的标记族（marked family），在有限基变换后实现有限纤维覆盖，并把乘积图嵌入固定的紧 Kähler 环境中参数化；紧 Douady 分量与正常可构造性论证给出紧的正常满射 `@@M@@P\to S@@`，在稠密开集上承载乘积族（辅助基 `@@M@@P@@` 不必射影、也不必在 `@@M@@S@@` 上一般有限）。乘积因子分类处理：射影 log Calabi–Yau 因子借助射影比较基上的代数 b-半丰富性定理；最高形式由权一、权二周期控制的因子，则通过 Hodge 滤波的平坦变换把实极化换成有理极化而不改变积分单值，再用 BFMT 的算术周期紧致化在辅助基上解析地提供半丰富延拓。最后，以留数积分作为延拓范数，体积范数的乘积恒等式与双侧对数增长界把开集上的线丛同构穿过边界延拓（排除隐藏的平坦扭曲）；半丰富性经 Stein 因子分解与有限解析范数从 `@@M@@P@@` 下降到 `@@M@@S@@`，得到在每一点整体生成且指数单一的结论。

## 可信度与备注

主结果暂无形式化证明，请以社区核验为准。本篇是结果族 033 的解析分支，与射影 Iitaka 子可加性、反向对数 Kodaira 不等式等姊妹篇共享典范丛公式与 BFMT Hodge 理论框架；值得注意的是本篇明确不使用 Campana 轨道 Iitaka 定理，从而在族内独立供给 b-半丰富性这一输入。按 OpenAI 官方声明，未经形式化的结果可能存在问题，宜以社区核验为准。

{% endraw %}
