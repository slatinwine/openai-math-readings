---
layout: default
title: "Perfect completeness for 2-to-1 games"
family: "105"
discipline: "Theoretical computer science"
formalized: true
source: null
pdfname: ""
---

{% raw %}
# 解读 | Perfect completeness for 2-to-1 games

> 结果族 105：Perfect completeness for 2-to-1 games　·　学科：Theoretical computer science　·　验证状态：主结果已 Lean 形式化

## 一句话结论

证明了 Khot 的 2-to-1 博弈猜想（2-to-1 Games Conjecture）的完美完备性（perfect completeness）版本：对任意固定有理数 \(\delta\in(0,1)\)，区分"完全可满足"与"值至多 \(\delta\)"的 2-to-1 博弈是 NP 难的。这是逼近难度理论的基石结果。

## 问题背景

2-to-1 博弈是一类投影博弈（projection game）：二部图每条边带约束映射 \(\pi_e\)，左、右字母表为 \([2q]\) 和 \([q]\)，每个右答案恰有两个原像。Khot 于 2002 年研究逼近难度（hardness of approximation）时提出该猜想，它蕴含大量图着色与约束满足问题的最优不可逼近性。Grassmann 纲领（Khot–Minzer–Safra 等）此前已证完备性 \(1-\eps\)、可靠性任意小的近完美版本，但"完美完备性"端点——YES 实例须被全部满足——悬而未决：对恰二投影做普通并行重复会把二元素纤维膨胀成 \(2^k\) 个，破坏 2-to-1 结构。Austrin–O'Donnell–Tan–Wright 的完美完备性结果可靠性停在 \(23/24+\eps\)；Fei–Minzer–Wang 只解决了 4-to-1 情形。

## 主要结果

主定理：对每个固定有理数 \(\delta\in(0,1)\)，存在只依赖 \(\delta\) 的整数 \(q\ge2\) 与确定性多项式时间归约，把 3-SAT 映到字母表为 \([2q]\)、\([q]\) 的 2-to-1 博弈，使可满足公式产生值为 \(1\) 的博弈，不可满足公式产生的博弈值至多 \(\delta\)；输出是显式列出的无权边多重集和显式投影表，每张表的每个右答案恰有两个原像。推论：最大 \(k\)-可着色子图（maximum \(k\)-colorable subgraph）在 \(1-1/k+C\log k/k^2\) 处 NP 难；并恢复 Håstad 关于可满足 Not-Two 谓词与三查询 PCP（可靠性 \(5/8+\eps\)）的定理。

## 证明思路

先用 Dinur 的完美完备性 PCP 与 Dinur–Steurer 并行重复，得到完备性为 \(1\)、值任意小的子句—变量源博弈。再把其独立副本放到一棵有限树的叶上：叶上是答案域上全部 \(\mathbb F_2\) 值函数，内部节点取各子空间两两乘积张成的空间并展示数组（若干行函数）；全体数组的联合取值把定义域剖分成块，合法答案即一块，也就是能同时实现全部还原输出的赋值。测试时随机选一层与非零方向 \(a\) 取商：商核恰为 \(\{0,a\}\)，每个右标签至多合并两块，天然得到"至多二"纤维；满足的源赋值满足全部约束，此即完美完备性。

若标记以 \(\eps\) 比例接受，配对计数给出同时成功的两层 \(i<j\)。上层用逆 shortcode 定理（源于 Grassmann 图扩张），从秩一步游走下的表值相等中提取仿射切片（affine slice）上稠密的响应，联合折叠恒等式把它化为线性泛函 \(z\)（\(z(1)=1\)），其乘积型 \(F(x,y)=z(xy)\) 在展示行上的 Gram 矩阵秩至多 \(1\)；右侧解码器靠 Fourier 重字符列表解码，两侧以正概率相等。难点是左形式的秩只在其依赖的被测行上检验：在纤维内重采样并借稀疏投影后验估计，把限制相等提升为完整相等，再用逆定理取出固定形式；固定的高秩形式在仿射切片上几乎不可能通过秩 \(1\) 检验，故正份额协议只能来自秩至多 \(s\) 的形式。最后"干净重复"论证让低秩形式在源叶诱导短奇列表、重建输入，与源博弈值 \(<1/(2s^2)\) 矛盾。组装时按依赖顺序选参数，把"至多二"补成"恰为二"，再把有理权重舍入为显式无权多重集，总可靠性不超过 \(\delta\)。

## 可信度与备注

主结果已由 OpenAI 完成 Lean 形式化证明（结果族 105 配套文档 lean/docs/105.md）。三个外部输入（Dinur PCP、Dinur–Steurer 重复、KMS Grassmann 扩张）均为社区已证定理；论文自证的采样比较、逆定理推广与干净重复引理是核验重点。本定理恰好补上 Guruswami–Sinop 与 O'Donnell–Wu 归约所需的"恰二纤维加完美完备性"前提，使上述推论无条件成立；同纲领姊妹篇另证得三着色图独立集的更强可靠性。按 OpenAI 官方声明，未经形式化的结果可能有问题，而本文主结果已形式化，可信度较高。

{% endraw %}
