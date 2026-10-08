---
layout: default
title: "A Complete Local Domain without a Small Cohen–Macaulay Module"
family: "195"
discipline: "Algebra"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | A Complete Local Domain without a Small Cohen–Macaulay Module

> 结果族 195：A counterexample to the small Cohen–Macaulay module conjecture　·　学科：Algebra　·　验证状态：暂无形式化证明，请以社区核验为准

## 入门导读 🐣

把一个环想成一栋三层小楼，"Cohen–Macaulay 模"就是能把三层楼完整走通的住户（模）。Hochster 在 1970 年代问：每一栋"完备正规整环"大楼，是否总有一位有限生成的住户能层层走通？维数不超过 2 时答案本是肯定的，反例必须活在三维。本文盖出一栋三维大楼：任何有限生成的住户都必然缺一层。

**关键词卡片**

- Cohen–Macaulay 模：深度达到环的维数的非零有限生成模——层层走通的好住户。
- 深度（depth）：正则序列的长度，相当于模能完整走通的楼层数。
- 完备局部整环：聚焦一点并补全极限运算的整环，"大楼"的正式名字。
- 陈数 `@@M@@c_2@@`（second Chern class）：曲面自带的拓扑不变量，在这里充当"验楼报告"的关键数字。

**看个具体例子**

公式卡（数值障碍的数字版）：若大楼有小 Cohen–Macaulay 住户，配套曲面必须通过体检

`@@M@@DK_X^2-2c_2(X)\le 6H^2,\qquad H^2=5\cdot 7^3=1715,@@`

而取 `@@M@@n=7@@` 的 Hirzebruch–Kummer 曲面给出 `@@M@@K_X^2-2c_2(X)=7^3(7^2-10)=13377>10290=6H^2@@`，体检不合格，故对应的完备局部整环没有小 Cohen–Macaulay 模。这座反例曲面由"完全四角形"构造而来：一般位置四点的六条连线经爆破，再取五重覆盖即得。

**为什么值得关心**

它否定了 Hochster 悬置五十余年的小 Cohen–Macaulay 模猜想的整环形式，而且是在最一般的类别——含 `@@M@@\mathbb C@@` 的三维完备正规局部整环——中给出否定答案，恰好回应了 2026 年综述中仍列为开放的情形。值得一提的是，不要求有限生成的"大"Cohen–Macaulay 模早已被证明总存在，倒下的只是"小"字。

> 暂无形式化证明（AI 结果待核验）

## 一句话结论

本文构造了一个含 `@@M@@\mathbb{C}@@`、剩余域为 `@@M@@\mathbb{C}@@` 的三维完备诺特正规局部整环，其上任何非零有限生成模的深度都达不到 3，即不存在小 Cohen–Macaulay 模，从而否定 Hochster 悬置五十余年的整环形式猜想。

## 问题背景

小 Cohen–Macaulay 模（small Cohen–Macaulay module）指诺特局部环 `@@M@@(R,\mathfrak m)@@` 上满足 `@@M@@\depth_R M=\dim R@@` 的非零有限生成模，又称极大 Cohen–Macaulay 模（maximal Cohen–Macaulay module）。Hochster 在 1970 年代研究同调猜想（homological conjectures）时提出：完备诺特局部整环是否都有这样的模？他本人后来也预期存在反例。维数不超过 2 时答案是肯定的（有限正规化环即为 Cohen–Macaulay），正特征分次情形有正面定理（Hartshorne、Peskine–Szpiro、Hochster）；放弃有限生成后，大 Cohen–Macaulay 模（big Cohen–Macaulay module）的存在性已完全解决（Hochster、Hochster–Huneke、André 依次处理特征相等、正特征与混合特征）。但特征零、无分次、任意有限模的情形始终缺少排除工具：Bhatt 2014 年的正特征反例只排除 Cohen–Macaulay 扩张代数，Bhatt–Hochster–Ma 2026 年 8 月版综述仍把"代数闭域上三维仿射整环极大理想处的局部环"列为开放。本文恰在该最一般类别中给出否定答案。

## 主要结果

主定理：存在三维完备诺特正规局部整环 `@@M@@R@@`（含 `@@M@@\mathbb{C}@@`，剩余域 `@@M@@\mathbb{C}@@`），使得没有非零有限生成 `@@M@@R@@`-模具有深度三。核心是数值障碍定理：设 `@@M@@X@@` 为 `@@M@@\mathbb{C}@@` 上光滑整射影曲面，`@@M@@H@@` 为丰富（ample）且整体生成的除子，截面环 `@@M@@T(X,H)=\bigoplus_{j\geq0}H^0(X,\mathcal O_X(jH))@@` 在顶点局部化再完备化记为 `@@M@@R(X,H)@@`。若 `@@M@@R(X,H)@@` 有小 Cohen–Macaulay 模，则
`@@M@@DK_X^2-2c_2(X)\le 6H^2,@@`
其中 `@@M@@K_X@@` 为典范除子，`@@M@@c_2(X)@@` 为第二陈数。论文随后用完全四角形（complete quadrangle）Hirzebruch–Kummer 构造给出违反不等式的曲面：对素数 `@@M@@n\ge3@@` 有 `@@M@@H^2=5n^3@@`、`@@M@@K_X^2-2c_2(X)=n^3(n^2-10)@@`；取 `@@M@@n=7@@` 得 `@@M@@13377>10290=6H^2@@`，故相应完备环无小 Cohen–Macaulay 模。推论：未完备化的局部环 `@@M@@T(X,H)_{T_{>0}}@@` 是 `@@M@@\mathbb{C}@@` 上本质有限型的三维局部整环，同样没有小 Cohen–Macaulay 模（经完备化的忠实平坦性传递），正是上述开放情形的反例。

## 证明思路

先化模为几何。完备锥 `@@M@@R@@` 有限于正则环 `@@M@@A=\mathbb{C}[[x_0,x_1,x_2]]@@`；若有小 Cohen–Macaulay 模 `@@M@@M@@`，参数 `@@M@@x_0,x_1,x_2@@` 就是 `@@M@@M@@`-正则序列，Auslander–Buchsbaum 公式迫使 `@@M@@M@@` 作为 `@@M@@A@@`-模自由（秩 `@@M@@N@@`），故限制到刺破谱上局部自由。把对应层拉回正则模型 `@@M@@W@@`（线性丛 `@@M@@\Tot(\mathcal O_X(-H))@@` 沿 `@@M@@A@@` 的基变换，在例外曲面 `@@M@@X@@` 之外同构于锥）并取双重对偶，得无挠层 `@@M@@\mathcal E@@`，其限制 `@@M@@P=\mathcal E|_X@@` 无挠且秩 `@@M@@r>0@@`，而 `@@M@@g_*\mathcal E@@` 在例外除子 `@@M@@D\simeq\mathbb{P}^2@@` 之外是平凡丛。

再做斜率平衡。`@@M@@M@@` 可以毫无分次结构，`@@M@@P@@` 未必半稳定。取 `@@M@@P@@` 的 Harder–Narasimhan 过滤最后一个半稳定商 `@@M@@G@@`，把 `@@M@@\mathcal E@@` 换成 `@@M@@\ker(\mathcal E\to i_*G)@@`，Tor 计算给出新限制的正合列 `@@M@@0\to G(H)\to\mathcal E'|_X\to B\to 0@@`；每次修正最大斜率不增而平均斜率至少升 `@@M@@1/r@@`，故有限步后全部因子斜率落入长度至多 1 的区间，且锥外的丛不变。

然后建立下界。对 `@@M@@\mathbb{P}^2@@` 上秩 `@@M@@N@@` 的层 `@@M@@F@@` 定义 `@@M@@v(F)=2\ch_2(F)/N-(c_1(F)/N)^2@@`，当 `@@M@@F=\bigoplus_i\mathcal O(a_i)@@` 时恰是整数 `@@M@@a_i@@` 的方差。关键引理：在 `@@M@@D@@` 外平凡的无挠层限制到 `@@M@@D@@` 后必有 `@@M@@v\ge0@@`；证明把它夹在 `@@M@@\mathcal I^{2b}\mathcal O_V^N@@` 与 `@@M@@\mathcal O_V^N@@` 之间，对商按 `@@M@@\mathcal I@@` 的幂分层并在 Grothendieck 群中比较，最后化为一个初等组合不等式。以 `@@M@@g_*\mathcal E@@` 代入即得 `@@M@@v(f_*P)\ge0@@`。

最后封顶并构造反例。对每个半稳定因子 `@@M@@G@@`，比较 `@@M@@X@@` 与 `@@M@@\mathbb{P}^2@@` 上的 Riemann–Roch，配合 Bogomolov 不等式、Hodge 指标定理与 Noether 公式得 `@@M@@v(f_*G)\le\frac14-\frac{K_X^2-2c_2(X)}{12h}@@`；再由方差分解，斜率区间长度至多 1 使加权方差项至多 `@@M@@\frac14@@`，合并得 `@@M@@K_X^2-2c_2(X)\le6H^2@@`。反例曲面出自 Hirzebruch 线构形：一般位置四点的六条连线经爆破给出分支除子 `@@M@@\Delta\sim-2K_B@@`，再在函数域中添加五个比值 `@@M@@l_a/l_6@@` 的 `@@M@@n@@` 次根得 `@@M@@n^5@@` 次 Galois 覆盖；节点处赋值向量的模 `@@M@@n@@` 独立性保证覆盖光滑，极化 `@@M@@H=3J-E@@` 满足 `@@M@@nH\sim\pi^*(-K_B)@@`，丰富且整体生成。与 Ulrich 层的平凡化判据不同，本文比较的是完备锥上的凝聚扩张，因此对任意非分次有限模同样有效。

## 可信度与备注

本文暂无 Lean 形式化证明；按 OpenAI 官方声明"未经形式化的结果可能有问题"，结论应以社区核验为准。族内姊妹篇互相支撑：Anghel 2026 年 9 月预印本用同一完全四角形构造排除了算术 Cohen–Macaulay 丛与分次极大 Cohen–Macaulay 模，但不涉及完备环上的任意模；Chen 同期预印本在 `@@M@@K_X\equiv4H@@` 假设下给出局部上同调定量界。本文的障碍既不需要分次结构，也不要求 `@@M@@K_X@@` 与 `@@M@@H@@` 成比例（所用极化满足 `@@M@@K_X\equiv5H@@`），且对任意有限模生效，是族内最强的否定结果；脚注披露上述姊妹篇曾使用 ChatGPT/Claude 辅助计算与写作。

{% endraw %}
