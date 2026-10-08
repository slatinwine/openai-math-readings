---
layout: default
title: "Gaussian free-field limits of weighted integer Lipschitz heights"
family: "232"
discipline: "Probability and statistical mechanics"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | Gaussian free-field limits of weighted integer Lipschitz heights

> 结果族 232：Gaussian fields and interfaces for triangular-lattice Lipschitz heights　·　学科：Probability and statistical mechanics　·　验证状态：暂无形式化证明，请以社区核验为准

## 入门导读 🐣

在一张三角格网上给每个小格子填整数高度，规矩只有一条：相邻格子的高度至多差 1。按一定权重随机地填满整张网，这片"随机地形"放大后会是什么模样？答案：高斯自由场——二维世界最普适的随机涨落模板，地位好比一维世界里的布朗运动。

**关键词卡片**

- Lipschitz 高度函数（integer Lipschitz height function）：相邻面高度差至多 1 的整值随机曲面，最简单的"硬约束"地形。
- 权重 x（weight）：每条高度发生跳变的边乘上因子 x；x = 1 是均匀模型，x = 1/√2 是理论预言的临界端点。
- 高斯自由场（Gaussian free field, GFF）：可以想象成"铺满整个平面的布朗运动"，随机场世界的万能模板。
- 随机分布收敛（convergence as random distribution）：场在单点上的值发散，但与检验函数加权平均后，一切联合矩都收敛。
- 零 Dirichlet 边界（zero boundary）：区域边界上的高度被钉死为 0。

**看个具体例子**

下图是地形的一条剖面：台阶高度依次为 0, 1, 2, 2, 1, 0, −1, −1, 0，相邻差不超过 1，每个"台阶边"带权重 x。定理说：对每个固定 `@@M@@x\in[1/\sqrt2,\,1]@@`（含临界端点 `@@M@@x=1/\sqrt2\approx 0.707@@` 与均匀模型 `@@M@@x=1@@`），存在与区域无关的正常数 `@@M@@\sigma(x)@@`，使得 `@@M@@\dfrac{h_\delta}{\sigma(x)}@@` 收敛到零边值 GFF。注意不需要再除以任何对数——涨落天然有限，这与许多别的随机曲面很不一样。

<div>

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 560 280">
  <text x="280" y="26" text-anchor="middle" font-size="15">随机地形的一条剖面：整数台阶，相邻差 ≤ 1</text>
  <text x="280" y="52" text-anchor="middle" font-size="13" fill="#c62828">每个台阶边乘权重 x；格子加密后 ⇒ GFF / σ(x)</text>
  <line x1="60" y1="230" x2="525" y2="230" stroke="#555" stroke-width="1.5"/>
  <line x1="60" y1="80" x2="60" y2="230" stroke="#555" stroke-width="1.5"/>
  <line x1="60" y1="170" x2="511" y2="170" stroke="#ddd" stroke-dasharray="4 4"/>
  <line x1="60" y1="200" x2="511" y2="200" stroke="#ddd" stroke-dasharray="4 4"/>
  <line x1="60" y1="260" x2="511" y2="260" stroke="#ddd" stroke-dasharray="4 4"/>
  <path d="M70 230 L119 230 L119 200 L168 200 L168 170 L266 170 L266 200 L315 200 L315 230 L364 230 L364 260 L462 260 L462 230 L511 230" fill="none" stroke="#1565c0" stroke-width="3"/>
  <g font-size="12" fill="#333">
    <text x="94" y="224">0</text>
    <text x="143" y="194">1</text>
    <text x="215" y="164">2</text>
    <text x="290" y="194">1</text>
    <text x="339" y="224">0</text>
    <text x="410" y="256">−1</text>
    <text x="486" y="224">0</text>
  </g>
  <text x="30" y="150" font-size="12">高度</text>
  <text x="200" y="250" font-size="12">格点位置</text>
</svg>

</div>

**为什么值得关心**

此前学界只掌握"方差按对数增长"这类一阶证据，GFF 极限长期停留在猜想；本文把它变成定理，同时覆盖均匀模型与临界端点，是随机曲面普适性纲领的关键一步。

> 暂无形式化证明（AI 结果待核验）

## 一句话结论
证明了三角格点上零边界、按"高度改变的边数"加权的整数 Lipschitz 高度场，对每个固定权重 `@@M@@x\in[1/\sqrt2,1]@@`，除以正常数 `@@M@@\sigma(x)@@` 后收敛到零 Dirichlet 高斯自由场，覆盖均匀模型与预测临界端点，把长期停留于对数方差层面的粗化证据推进为完整的极限定理。

## 问题背景
整数 Lipschitz 高度函数（integer Lipschitz height function）是最简单的带硬约束随机曲面：相邻面上高度差至多为 `@@M@@1@@`。给每条高度改变的边乘权重 `@@M@@x@@` 后，其等价的回路描述恰是六角格点上的 loop `@@M@@O(2)@@` 模型，权重为 `@@M@@2^{\#\text{loops}}x^{\#\text{occupied edges}}@@`，这一联系可追溯到 Nienhuis 1982 年的工作。Schramm 在其问题集中提出此类模型的高斯场与界面预测；Glazman–Manolescu 证明了均匀整数模型的对数涨落与两自旋表示，Glazman–Lammers 在更大参数区间建立离域化（delocalization）并把 GFF 极限明确列为猜想，Duminil-Copin–Glazman–Peled–Spinka 在 `@@M@@x=1/\sqrt2@@` 处证实了宏观回路。此前卡壳之处在于：对数方差只是粗化的一阶证据，既未识别协方差结构，也无法控制边界条件与高阶矩，GFF 极限本身始终悬而未决。

## 主要结果
设 `@@M@@D\subset\mathbb{R}^2@@` 是有界 `@@M@@C^2@@` Jordan 区域，`@@M@@\{D_\delta\}@@` 是其内部格点逼近且边界参数化一致收敛。主定理断言：对每个固定 `@@M@@x\in[1/\sqrt2,1]@@`，存在常数 `@@M@@\sigma(x)\in(0,\infty)@@`，不依赖区域 `@@M@@D@@` 及其格点逼近方式，使得 `@@M@@\frac{h_\delta}{\sigma(x)}\Rightarrow\Phi_D@@` 在 `@@M@@\mathcal D'(D)@@` 中成立，其中 `@@M@@\Phi_D@@` 是协方差核为 Dirichlet Green 函数 `@@M@@G_D=(-\Delta_D)^{-1}@@` 的零边值高斯自由场（Gaussian free field, GFF）。收敛作为随机分布（random distribution）成立，任意有限组检验函数的联合矩都收敛；场不需要对数重标度——点方差的发散与光滑平均后的有限涨落相容。参数区间同时包含均匀模型 `@@M@@x=1@@` 与预测临界端点（predicted critical endpoint）`@@M@@x=1/\sqrt2@@`。论文不给出 `@@M@@\sigma(x)@@` 的显式公式，也不断言该常数与 `@@M@@x@@` 无关。

## 证明思路
证明分四步推进。先建立精确的加权切割与条件序：把高度模 `@@M@@4@@` 编码为一对 `@@M@@\pm1@@` 自旋（spin），并为每个上三角胞附加一个状态变量；一条开回路可固定第一个自旋而释放第二个，由此得到胞因子化与精确条件切割（cut）。正相联（positive association）意义下的序不等式必须对记录了观测胞内全部第一自旋位点的历史成立——仅条件于状态本身并不保序，这一限制是本质性的。随后用 Klartag–Lehec 离散中点不等式（Prékopa–Leindler 形式）把中心概率界放大为磨光高度（smeared height）所有矩的一致界。再进入平面分析：关于三角格点三个方向之一格点行的反射正性（reflection positivity）产生法向正转移算子，其协方差可表示为法向频率上 Cauchy 核的正混合；关键的角向恒等式同时调用三个镜面方向，迫使谱测度的每个标度极限都形如 `@@M@@c\,\mathrm dp/|p|^2@@`，一个带符号的截断恒等式证明常数 `@@M@@c@@` 唯一，双盘方差界证明 `@@M@@c>0@@`，最终 `@@M@@v=(2\pi)^2c@@`、`@@M@@\sigma(x)=\sqrt v@@`。接着处理销钉（pin）与真实边界：将场与上、下钉扎括号比较，利用一致矩界在三个格向解析地移动分离销钉，先取相位平均、再闭合缺口，把反射零化的 Laplace 插入从平面转移到这些括号；边界附着（boundary attachment）估计以合成边界律给出有利的水平线路径，并在管中迭代形成边界拱，使括号均值消失。最后识别极限场：紧性与一致可积先行，括号极限与真实场等同后，每个极限矩分布在碰撞点之外调和，对数矩界排除集中于对角线的奇异分布，与平面律的局部比较固定每个碰撞奇性的系数，减去相应的 Green 函数即得 Wick 递推，从而一切子列极限必为高斯。

## 可信度与备注
本结果暂无形式化证明，属 OpenAI 研究手稿；按其官方声明"未经形式化的结果可能有问题"，请以社区核验为准。族内三篇互为姊妹：两弧边界姊妹篇解决 Schramm 问题 2.2 的场部分，与本文共享"反射正性—销钉移动—矩方法"的骨架，但两文的模型特定输入与结论各自独立证明、互不作为前提；实值模型篇则以凸几何与反射 Brown 运动技术攻克问题 2.3。

{% endraw %}
