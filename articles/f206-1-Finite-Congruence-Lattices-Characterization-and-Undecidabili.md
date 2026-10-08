---
layout: default
title: "Finite congruence lattices: characterization and undecidability"
family: "206"
discipline: "Algebra"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | Finite congruence lattices: characterization and undecidability

> 结果族 206：Finite lattice representation and undecidability　·　学科：Algebra　·　验证状态：暂无形式化证明，请以社区核验为准

## 入门导读 🐣

把一个代数系统"强行粘贴"的各种方式按粗细排成一张层次图，就得到同余格。自然的问题：随手画一张有限层次图，能不能找到某个有限代数恰好粘出它？本文的回答是双重的"不"：有些图注定找不到，而且"判断找不找得到"这件事本身没有算法——不是难算，是原理上不可判定。

**关键词卡片**

- 格（lattice）：带"交""并"两种运算的层次结构，像一张组织架构图。
- 同余格（congruence lattice）：一个代数的全部粘贴方式按粗细排成的格。
- 染色图判据（colored-graph criterion）：给完全图的每条边涂上格的元素，用三条有限可查的条件判定可表示性。
- 不可判定（undecidable）：不存在任何总能停机并给出正确答案的算法。

**看个具体例子**

<div>

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 560 280">
  <text x="40" y="40" font-size="15" fill="#333">格 L（示例：三元链）</text>
  <circle cx="110" cy="80" r="16" fill="#fff" stroke="#555" stroke-width="2"/>
  <text x="110" y="86" font-size="14" fill="#333" text-anchor="middle">1</text>
  <circle cx="110" cy="150" r="16" fill="#fff" stroke="#555" stroke-width="2"/>
  <text x="110" y="156" font-size="14" fill="#333" text-anchor="middle">a</text>
  <circle cx="110" cy="220" r="16" fill="#fff" stroke="#555" stroke-width="2"/>
  <text x="110" y="226" font-size="14" fill="#333" text-anchor="middle">0</text>
  <line x1="110" y1="96" x2="110" y2="134" stroke="#555" stroke-width="2"/>
  <line x1="110" y1="166" x2="110" y2="204" stroke="#555" stroke-width="2"/>
  <text x="250" y="40" font-size="15" fill="#333">L-染色的完全图（判据的证据图）</text>
  <circle cx="330" cy="90" r="5" fill="#333"/>
  <circle cx="480" cy="90" r="5" fill="#333"/>
  <circle cx="405" cy="220" r="5" fill="#333"/>
  <line x1="335" y1="90" x2="475" y2="90" stroke="#555" stroke-width="2"/>
  <line x1="333" y1="95" x2="402" y2="215" stroke="#555" stroke-width="2"/>
  <line x1="477" y1="95" x2="408" y2="215" stroke="#555" stroke-width="2"/>
  <text x="330" y="76" font-size="14" fill="#333">p</text>
  <text x="487" y="76" font-size="14" fill="#333">q</text>
  <text x="405" y="243" font-size="14" fill="#333" text-anchor="middle">u</text>
  <text x="405" y="80" font-size="13" fill="#a33" text-anchor="middle">d(p,q)=a</text>
  <text x="330" y="165" font-size="13" fill="#a33" text-anchor="middle">d(p,u)=a</text>
  <text x="482" y="165" font-size="13" fill="#a33" text-anchor="middle">d(u,q)=1</text>
  <text x="30" y="266" font-size="13" fill="#555">三角不等式：d(p,q) ≤ d(p,u) ∨ d(u,q)，此处 a ≤ a ∨ 1 成立</text>
</svg>

</div>

判据里最直观的一条就是三角不等式：绕路的开销不得小于直连。三条条件本身有限可查，但"存在满足条件的染色图"却没有算法可判；论文还顺带证明识别有限群的全子群区间同样不可判定。

**为什么值得关心**

Pálfy–Pudlák 1980 年公开问题得到否定解，且连判定算法都不存在——这是比"存在反例"更强的负面信息。

> 暂无形式化证明（AI 结果待核验）

## 一句话结论
本文给出有限格可作为有限代数全同余格（congruence lattice）的显式染色图判据，并证明这一表示性质算法不可判定；由此彻底否定有限格表示问题，且识别有限群的全子群区间同样不可判定。

## 问题背景
Grätzer–Schmidt 表示定理（1963）断言每个代数格（algebraic lattice）都同构于某个代数的同余格，但表示所用的代数可能是无限的；当给定的格有限时能否找到有限代数，是 Pálfy 与 Pudlák 1980 年以来悬置的公开问题。他们证明了两条全局断言等价："每个有限格都是有限代数的同余格"与"每个有限格都是某有限群子群格的区间"。此前的正面结果都差一口气：Pudlák–Tůma 只能把有限格嵌入有限集合的分拆格（保交并的嵌入而非全格实现），Repnitskiĭ–Tůma 则在可数局部有限群中实现区间，有限性始终无法保证。与存在性问题并列的判定问题——从有限格的运算表出发判定可表示性——同样没有答案。本文把存在、判定两个问题一并解决，答案是双重否定。

## 主要结果
**图判据**（Theorem f:criterion）：有限非空格 `@@M@@L@@` 是某有限代数的全同余格，当且仅当存在一个 `@@M@@L@@`-染色的完全图 `@@M@@(A,d)@@`（即对称函数 `@@M@@d:A\times A\to L@@`，`@@M@@d(p,p)=0@@`）同时满足三个有限可验证的条件：三角不等式 `@@M@@d(p,q)\le d(p,u)\vee d(u,q)@@`；反射性——凡 `@@M@@a\not\le b@@` 必有边的颜色 `@@M@@\le a@@` 而 `@@M@@\not\le b@@`；连通性——对任意非空边集 `@@M@@S@@`，凡满足 `@@M@@d(p,q)\le a_S=\bigvee_{\{p,q\}\in S}d(p,q)@@` 的两点在图 `@@M@@\Gamma_S@@` 的同一连通分量中。这沿 Pudlák 1976 年的赋值—路径方法给出，且每个证据图的大小有限可查。
**不可判定性**（Theorem n:undecidable）：不存在算法判定给定有限格的表是否可实现为某有限代数的同余格；等价地，可表示格的最小载体规模不存在以格基数为变量的可计算上界。
**负格存在**：存在有限格不是任何有限代数的同余格，最小负格的基数严格大于 `@@M@@6@@`，并可给出一个具最小基数性质的有限显式描述。
**区间识别不可判定**（Corollary n:interval-undecidable）：不存在总是停机的算法判定有限格是否同构于某有限群的全子群区间 `@@M@@[H,G]@@`。

## 证明思路
证明由互相配合的两大分支构成。第一支构造反例格：先取有限仿射几何 `@@M@@\operatorname{AG}(N,q)@@`（`@@M@@q@@` 为使 `@@M@@q-1@@` 不是素数幂的素数幂，如 `@@M@@7@@` 的幂）的多个拷贝，按树干、私有、叶三类图表递归粘贴成偏序集，再与其反序拷贝水平和，得到"测试格" `@@M@@L@@`——它简单、自对偶、既原子又余原子。若 `@@M@@L@@` 可由某有限代数表示，先用 Pálfy–Pudlák 的最小载体论证把代数约化为一个置换群的不变等价格，再借对角子群构造区间 `@@M@@[\Delta(C)\rtimes J,\ C^A\rtimes J]@@` 把 `@@M@@L@@` 实现为有限群的普通子群区间；随后的单块（monolith）分析把情形压缩到几乎单群（almost simple group）区间或一个"扩张偏序集"两种，后者被一个仿射四维网格矛盾排除——四维空间中两张平面恰交于一点的几何，迫使扩张核既映满单群又同时可解，冲突。剩下的几乎单群情形，再依次通过交替群二重传递作用、高秩经典群逐类稳定子剪枝（子空间、直和分解、张量因子、域代数，靠阶比较与不可约性逐类排除）与有界 Lie 秩（Larsen–Pink 定理）三道关卡，参数足够大时全部矛盾，反例格由此成立，并附带可计算的大小上限。第二支证不可判定性：先把正整数算术电路（加法门、乘法门）编码为"加权模板"——每个变量 `@@M@@v@@` 配上大小为 `@@M@@v@@` 与 `@@M@@16v@@` 的单元群，乘法门 `@@M@@c=ab@@` 由平方读数恒等式 `@@M@@(16(r_a{+}r_b))^2=(16r_a)^2+(16r_b)^2+32\cdot 16r_c@@` 实现；再证若存在判定器，则图判据的可半判定性给出可计算的最小载体界，进而把任何丢番图正解替换为不超过 `@@M@@60^m m!@@` 的有界正解，于是正电路方程的可解性可以能行判定——与 Davis–Putnam–Robinson–Matiyasevich 定理矛盾。子群区间版本沿同一模板，把载体界换成顶群阶界即可。

## 可信度与备注
主结果暂无 Lean 形式化证明，请以社区核验为准。本文与姊妹篇《A negative solution to the finite lattice representation problem》互相支撑：后者以 Boolean 装饰格独立构造出子群区间障碍，经 Pálfy–Pudlák 全局等价同样否定有限格表示问题；本文的仿射测试格则额外给出显式判据与不可判定性。证明重度依赖有限单群分类及其表示论推论，技术密集，独立核验门槛高。OpenAI 官方声明：未经形式化的结果可能有问题。

{% endraw %}
