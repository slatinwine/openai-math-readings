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

## 入门导读 🐣

想象一场巨型配对考试：左边一排答题人、右边一排审题人，每张考卷规定"审题人 a 的答案只能配答题人 1 或 2，审题人 b 只能配 3 或 4"——每个右侧答案恰好有两个候选。问：全对到什么程度？论文证明，判断"能否人人配对成功"还是"怎么做都至少九成配错"，与最难的 NP 问题一样难。

**关键词卡片**

- 2-to-1 博弈（2-to-1 game）：约束都是投影映射、每个右答案恰有两个原像的配对问题
- 完美完备性（perfect completeness）："全对"情形要求百分之百满足，一条不许欠
- 值（value）：任何答题方案能同时满足的约束比例之上确界
- NP 难（NP-hard）：与 3-SAT 同级；若有多项式算法则 P=NP
- 逼近难度（hardness of approximation）：不只求最优难，连"近似到 99%"也难

**看个具体例子**

<div>

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 560 280">
<text x="280" y="34" text-anchor="middle" font-size="14">每个右答案恰有 2 个原像——“2-to-1”的由来</text>
<line x1="180" y1="88" x2="112" y2="204" stroke="#843" stroke-width="2"/>
<line x1="180" y1="88" x2="248" y2="204" stroke="#843" stroke-width="2"/>
<line x1="390" y1="88" x2="322" y2="204" stroke="#843" stroke-width="2"/>
<line x1="390" y1="88" x2="458" y2="204" stroke="#843" stroke-width="2"/>
<circle cx="180" cy="88" r="24" fill="#e8eef8" stroke="#345" stroke-width="2"/>
<text x="180" y="94" text-anchor="middle" font-size="15">a</text>
<circle cx="390" cy="88" r="24" fill="#e8eef8" stroke="#345" stroke-width="2"/>
<text x="390" y="94" text-anchor="middle" font-size="15">b</text>
<text x="180" y="46" text-anchor="middle" font-size="12" fill="#345">右答案</text>
<text x="390" y="46" text-anchor="middle" font-size="12" fill="#345">右答案</text>
<circle cx="112" cy="204" r="22" fill="#f8e8e8" stroke="#843" stroke-width="2"/>
<text x="112" y="210" text-anchor="middle" font-size="14">1</text>
<circle cx="248" cy="204" r="22" fill="#f8e8e8" stroke="#843" stroke-width="2"/>
<text x="248" y="210" text-anchor="middle" font-size="14">2</text>
<circle cx="322" cy="204" r="22" fill="#f8e8e8" stroke="#843" stroke-width="2"/>
<text x="322" y="210" text-anchor="middle" font-size="14">3</text>
<circle cx="458" cy="204" r="22" fill="#f8e8e8" stroke="#843" stroke-width="2"/>
<text x="458" y="210" text-anchor="middle" font-size="14">4</text>
<text x="280" y="240" text-anchor="middle" font-size="13">π(a) = {1, 2}，π(b) = {3, 4}：一条约束就是一张投影表</text>
<text x="280" y="264" text-anchor="middle" font-size="13">目标：左右各选标签，让所有约束同时被满足</text>
</svg>

</div>

定理的数字版：取 `@@M@@\delta=1\%@@`——存在多项式时间变换，把可满足的 3-SAT 变成值为 `@@M@@1@@`（全部约束满足）的 2-to-1 博弈，把不可满足的变成值至多 `@@M@@0.01@@` 的博弈，且区分二者是 NP-难的。注意"每个右答案恰有两个候选"的刚性：多一个少一个都会破坏证明结构，这正是它名字里"2-to-1"的含义。

**为什么值得关心**

这是 Khot 2002 年提出的 2-to-1 猜想的完美完备性版本，长期缺口被补上，而它正是图着色等一大片"近似也难"结论的钥匙。

> 已 Lean 形式化

## 一句话结论

证明了 Khot 的 2-to-1 博弈猜想（2-to-1 Games Conjecture）的完美完备性（perfect completeness）版本：对任意固定有理数 `@@M@@\delta\in(0,1)@@`，区分"完全可满足"与"值至多 `@@M@@\delta@@`"的 2-to-1 博弈是 NP 难的。这是逼近难度理论的基石结果。

## 问题背景

2-to-1 博弈是一类投影博弈（projection game）：二部图每条边带约束映射 `@@M@@\pi_e@@`，左、右字母表为 `@@M@@[2q]@@` 和 `@@M@@[q]@@`，每个右答案恰有两个原像。Khot 于 2002 年研究逼近难度（hardness of approximation）时提出该猜想，它蕴含大量图着色与约束满足问题的最优不可逼近性。Grassmann 纲领（Khot–Minzer–Safra 等）此前已证完备性 `@@M@@1-\eps@@`、可靠性任意小的近完美版本，但"完美完备性"端点——YES 实例须被全部满足——悬而未决：对恰二投影做普通并行重复会把二元素纤维膨胀成 `@@M@@2^k@@` 个，破坏 2-to-1 结构。Austrin–O'Donnell–Tan–Wright 的完美完备性结果可靠性停在 `@@M@@23/24+\eps@@`；Fei–Minzer–Wang 只解决了 4-to-1 情形。

## 主要结果

主定理：对每个固定有理数 `@@M@@\delta\in(0,1)@@`，存在只依赖 `@@M@@\delta@@` 的整数 `@@M@@q\ge2@@` 与确定性多项式时间归约，把 3-SAT 映到字母表为 `@@M@@[2q]@@`、`@@M@@[q]@@` 的 2-to-1 博弈，使可满足公式产生值为 `@@M@@1@@` 的博弈，不可满足公式产生的博弈值至多 `@@M@@\delta@@`；输出是显式列出的无权边多重集和显式投影表，每张表的每个右答案恰有两个原像。推论：最大 `@@M@@k@@`-可着色子图（maximum `@@M@@k@@`-colorable subgraph）在 `@@M@@1-1/k+C\log k/k^2@@` 处 NP 难；并恢复 Håstad 关于可满足 Not-Two 谓词与三查询 PCP（可靠性 `@@M@@5/8+\eps@@`）的定理。

## 证明思路

先用 Dinur 的完美完备性 PCP 与 Dinur–Steurer 并行重复，得到完备性为 `@@M@@1@@`、值任意小的子句—变量源博弈。再把其独立副本放到一棵有限树的叶上：叶上是答案域上全部 `@@M@@\mathbb F_2@@` 值函数，内部节点取各子空间两两乘积张成的空间并展示数组（若干行函数）；全体数组的联合取值把定义域剖分成块，合法答案即一块，也就是能同时实现全部还原输出的赋值。测试时随机选一层与非零方向 `@@M@@a@@` 取商：商核恰为 `@@M@@\{0,a\}@@`，每个右标签至多合并两块，天然得到"至多二"纤维；满足的源赋值满足全部约束，此即完美完备性。

若标记以 `@@M@@\eps@@` 比例接受，配对计数给出同时成功的两层 `@@M@@i<j@@`。上层用逆 shortcode 定理（源于 Grassmann 图扩张），从秩一步游走下的表值相等中提取仿射切片（affine slice）上稠密的响应，联合折叠恒等式把它化为线性泛函 `@@M@@z@@`（`@@M@@z(1)=1@@`），其乘积型 `@@M@@F(x,y)=z(xy)@@` 在展示行上的 Gram 矩阵秩至多 `@@M@@1@@`；右侧解码器靠 Fourier 重字符列表解码，两侧以正概率相等。难点是左形式的秩只在其依赖的被测行上检验：在纤维内重采样并借稀疏投影后验估计，把限制相等提升为完整相等，再用逆定理取出固定形式；固定的高秩形式在仿射切片上几乎不可能通过秩 `@@M@@1@@` 检验，故正份额协议只能来自秩至多 `@@M@@s@@` 的形式。最后"干净重复"论证让低秩形式在源叶诱导短奇列表、重建输入，与源博弈值 `@@M@@<1/(2s^2)@@` 矛盾。组装时按依赖顺序选参数，把"至多二"补成"恰为二"，再把有理权重舍入为显式无权多重集，总可靠性不超过 `@@M@@\delta@@`。

## 可信度与备注

主结果已由 OpenAI 完成 Lean 形式化证明（结果族 105 配套文档 lean/docs/105.md）。三个外部输入（Dinur PCP、Dinur–Steurer 重复、KMS Grassmann 扩张）均为社区已证定理；论文自证的采样比较、逆定理推广与干净重复引理是核验重点。本定理恰好补上 Guruswami–Sinop 与 O'Donnell–Wu 归约所需的"恰二纤维加完美完备性"前提，使上述推论无条件成立；同纲领姊妹篇另证得三着色图独立集的更强可靠性。按 OpenAI 官方声明，未经形式化的结果可能有问题，而本文主结果已形式化，可信度较高。

{% endraw %}
