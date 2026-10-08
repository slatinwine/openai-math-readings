---
layout: default
title: "A finitely generated counterexample to the Eilenberg–Ganea conjecture"
family: "249"
discipline: "Group theory"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | A finitely generated counterexample to the Eilenberg–Ganea conjecture

> 结果族 249：A finitely generated Eilenberg–Ganea counterexample　·　学科：Group theory　·　验证状态：暂无形式化证明，请以社区核验为准

## 入门导读 🐣

给同一件家具量"占几维空间"有两把尺子：一把纯代数的，一把纯几何的。1957 年以来人们知道，3 维及以上两把尺子读数必然相同，1 维也相同，于是自然猜想 2 维也该相同——这就是 Eilenberg–Ganea 猜想。这篇论文造出一件"怪家具"：一个群，代数尺量出 2，几何尺量出 3，悬置近七十年的猜想被推翻。

**关键词卡片**

- 上同调维数 cd_Z（integral cohomological dimension）：纯代数的尺子，量"用代数消解的办法处理这个群最少要几步"
- 几何维数 gd（geometric dimension）：几何的尺子，量"给这个群搭一栋可缩骨架建筑最少要几维"
- 分类空间（classifying space）：万有覆盖可缩、基本群恰为该群的胞腔"骨架建筑" `@@M@@K(G,1)@@`
- Bestvina–Brady 群（Bestvina–Brady group）：右角 Artin 群在"高度"同态下的核，反例取自这一家族
- 剩余有限（residually finite）：每个非单位元都能在某个有限商里"现形"的良好性质

**看个具体例子**

反例群 `@@M@@G@@` 来自一个只有两条关系的展示：`@@M@@x^2=y^5@@` 与 `@@M@@x^2=(xy^{-1})^3@@`。先取这个展示复形的无环 flag 三角剖分 `@@M@@L@@`，再取右角 Artin 群 `@@M@@A_L@@` 里"把每个生成元都映到 1"的高度同态的核。论文证明：`@@M@@G@@` 有限生成、剩余有限，且数字版定理为 `@@M@@\cd_{\mathbb Z}G=2@@` 而 `@@M@@\mathrm{gd}\,G=3@@`——哪怕允许使用无穷多个胞腔，`@@M@@G@@` 也搭不出二维的分类空间。

<div>

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 560 280">
  <text x="30" y="30" font-size="15" fill="#333333">纵轴：几何维数 gd；横轴：代数维数 cd</text>
  <line x1="50" y1="240" x2="520" y2="240" stroke="#888888" stroke-width="2"/>
  <text x="70" y="264" font-size="14" fill="#333333">cd = 1</text>
  <text x="230" y="264" font-size="14" fill="#c62828">cd = 2</text>
  <text x="400" y="264" font-size="14" fill="#333333">cd 至少 3</text>
  <rect x="80" y="190" width="50" height="50" fill="#c8e6c9" stroke="#2e7d32"/>
  <text x="70" y="168" font-size="13" fill="#2e7d32">gd = 1，相等</text>
  <text x="58" y="184" font-size="12" fill="#666666">Stallings–Swan</text>
  <rect x="240" y="190" width="50" height="50" fill="none" stroke="#999999" stroke-dasharray="5 4"/>
  <text x="226" y="174" font-size="12" fill="#888888">猜想的期望</text>
  <rect x="240" y="140" width="50" height="100" fill="#ffcdd2" stroke="#c62828" stroke-width="2"/>
  <text x="216" y="118" font-size="13" fill="#c62828">本文反例 gd = 3</text>
  <rect x="420" y="140" width="50" height="100" fill="#c8e6c9" stroke="#2e7d32"/>
  <text x="404" y="118" font-size="13" fill="#2e7d32">gd = cd，相等</text>
  <text x="386" y="134" font-size="12" fill="#666666">Eilenberg–Ganea 定理</text>
</svg>

</div>

**为什么值得关心**

它宣告"代数维数与几何维数总相等"的美梦在 2 维破灭，而且反例群相当"规矩"（有限生成、剩余有限），连"补加条件拯救猜想"的退路也被堵死。

> 暂无形式化证明（AI 结果待核验）

## 一句话结论

本文构造了一个有限生成、剩余有限（residually finite）的群 `@@M@@G@@`，其整上同调维数为 `@@M@@2@@` 而几何维数为 `@@M@@3@@`，从而否定 Eilenberg–Ganea 猜想：`@@M@@G@@` 不存在任何二维分类空间，即便允许无穷多个胞腔。这一悬置近七十年的维数问题以否定方式告终。

## 问题背景

对离散群 `@@M@@\Gamma@@`，整上同调维数（integral cohomological dimension）`@@M@@\cd_Z\Gamma@@` 定义为平凡 `@@M@@\mathbb{Z}[\Gamma]@@`-模 `@@M@@\mathbb{Z}@@` 的最短投射消解长度；几何维数（geometric dimension）`@@M@@\mathrm{gd}\,\Gamma@@` 是以 `@@M@@\Gamma@@` 为基本群、万有覆盖可缩的 CW 复形——即分类空间（classifying space）`@@M@@K(\Gamma,1)@@`——的最小维数。可缩万有覆盖的胞腔链给出自由消解，故恒有 `@@M@@\cd_Z\le\mathrm{gd}@@`。1957 年的 Eilenberg–Ganea 定理证得 `@@M@@\cd_Z\ge 3@@` 时两数相等；一维情形由 Stallings 与 Swan 解决（`@@M@@\cd_Z=1@@` 的群必为自由群），唯独二维情形成为遗留猜想。Bestvina–Brady 的高度核（height kernel）例子提供了天然候选：他们证明，对 Poincaré 同调球面脊柱的适当 flag 三角剖分，Eilenberg–Ganea 猜想与 Whitehead 可缩性猜想至少一个不真，却无法判定孰假。症结在于：无环（acyclic，约化整同调消没）不等于可缩，即使证明某个二维无环模型不可缩，也堵不死"另换一个二维分类空间"的可能。

## 主要结果

主定理：存在有限生成、剩余有限的群 `@@M@@G@@`，满足 `@@M@@\cd_Z G=2@@`、`@@M@@\mathrm{gd}\,G=3@@`。具体取法：设 `@@M@@L@@` 是 presentation 复形 `@@M@@\langle x,y\mid x^2=y^5,\ x^2=(xy^{-1})^3\rangle@@` 的有限无环 flag 三角剖分（该群亦以 `@@M@@a^5=b^3=(ab)^2@@` 之形出现于 Hatcher 教材例 2.38），`@@M@@G@@` 是右角 Artin 群（right-angled Artin group）`@@M@@A_L@@` 在高度同态（height homomorphism，把每个标准生成元映为 `@@M@@1@@`）`@@M@@\lambda:A_L\to\mathbb{Z}@@` 下的核，即一个 Bestvina–Brady 群。论文证明 `@@M@@G@@` 没有任何二维分类空间，无论胞腔多少；同时 `@@M@@G@@` 属 type `@@M@@\mathrm{FL}@@`（平凡模有长度二的有限生成自由消解），故为 `@@M@@\mathrm{FP}_\infty@@`，但由 Bestvina–Brady 有限展示判据（`@@M@@\pi_1(L)@@` 非平凡）它不是有限展示群。`@@M@@G@@` 有限生成从而可数，故把猜想限定于可数群也于事无补。

## 证明思路

证明分"造模型—立接口—致矛盾"三段。

先造几何模型。种子复形的胞腔边界矩阵为 `@@M@@\begin{pmatrix}2&-5\\-1&3\end{pmatrix}@@`，行列式为 `@@M@@1@@`，故整无环；又能显式写出非平凡表示 `@@M@@\alpha:\pi_1(L)\to\SU(2)@@`：取 `@@M@@\theta=\pi/5@@`，令 `@@M@@x\mapsto u@@`（虚单位四元数）、`@@M@@y\mapsto\cos\theta+v\sin\theta@@`，其中 `@@M@@u\cdot v=1/(2\sin\theta)@@`，则两个关系的像均为 `@@M@@-1@@`。经顺序复形手续得 flag 三角剖分 `@@M@@L@@`。在 `@@M@@A_L@@` 的立方模型中，万有覆盖 `@@M@@E@@` 三维可缩，水平集 `@@M@@X=\lambda^{-1}(0)@@` 是以 `@@M@@G@@` 为顶点集的二维单纯复形；其上升链与下降链（ascending/descending link）皆为 `@@M@@L@@` 的重心重分，配合半空间形变收缩与 Mayer–Vietoris 序列证得 `@@M@@X@@` 无环。于是 `@@M@@X@@` 的胞腔链给出长度二的自由消解，`@@M@@\cd_Z G\le 2@@`；而 `@@M@@L@@` 含二维单形使 `@@M@@G@@` 容纳子群 `@@M@@\mathbb{Z}^2@@`，反向逼出 `@@M@@\cd_Z G\ge 2@@`；`@@M@@E/G@@` 则是现成的三维分类空间。剩余有限性由图群的顶点归纳证得。

再立两个互不相容的接口。比较定理说：若 `@@M@@G@@` 有二维 `@@M@@K(G,1)@@`，则存在 `@@M@@\eta>0@@`，凡是与 `@@M@@1@@` 距离小于 `@@M@@\eta@@` 的 `@@M@@\SU(2)@@` 边标号，只要在三角形边界字集 `@@M@@\mathcal D@@` 的所有平移上乘积为 `@@M@@1@@`，就在一切闭路上乘积为 `@@M@@1@@`。小标号命题说：对任意 `@@M@@\epsilon>0@@`，存在与 `@@M@@1@@` 距离小于 `@@M@@\epsilon@@`、逐三角形平坦、却使某闭路乘积非 `@@M@@1@@` 的标号；而 `@@M@@\mathcal D@@` 中的字恰是三角形边界，平坦性自动满足前一接口的前提。取 `@@M@@\epsilon<\eta@@` 即矛盾。

比较定理是核心难点：边界链只记带符号计数、忘记顺序，须借助真实的 aspherical 展示。对可能无穷乃至不可数的生成元与 relator，先经剪切变换把 `@@M@@\mathcal D@@` 的边界链精确排成特选 relator 的边界；边界同构的单射性随之给出精确的平移计数恒等式。四元数交换子估计 `@@M@@|ab-ba|\le 2|a-1|\,|b-1|@@` 使线性误差全部相消，只剩二次误差 `@@M@@h\le C(h+\epsilon)h@@`，自举地排除 `@@M@@h@@` 越过阈值 `@@M@@\delta@@`。有限商上解剩余 relator 方程组，用的是 Gerstenhaber–Rothaus 式词映射（word map）度方法：局部化度引理按模素数 `@@M@@p@@` 计数共轭轨道上的不动点，证得共轭不变区域上映射度非零；再让已给标号沿短弧自 `@@M@@1@@` 连续滑向目标值，度在变形中保持不变，解随之存在。最后，剩余有限性把任一有限组约束复制进有限商求解，Tychonoff 紧性把全部约束一次满足，二次估计逼出 `@@M@@h=0@@`：一切 relator 平凡，闭路乘积只能为 `@@M@@1@@`。

反驳一端靠传输（transport）：迹（trace）理论给出的方向映射 `@@M@@b(g)@@` 每个生成元步至多变动约 `@@M@@2/n@@`；把水平图平移至远离单位处，得映射 `@@M@@f_N:X\to L@@`，一切边像直径 `@@M@@\le 4/N@@`、三角形边界像 `@@M@@\le 8/N@@`，而交换幂路径 `@@M@@d\,a_q^{-(N-j)}a_r^{-j}@@` 恰好精确描出 `@@M@@L@@` 的指定棱。把 `@@M@@\alpha@@` 的等变提升（developing map）沿 `@@M@@f_N@@` 拉回便得小标号：小像迫使逐三角形平坦，被精确追踪的闭路则保有非平凡和乐（holonomy）。矛盾完成证明。

## 可信度与备注

本文主结果暂无形式化证明，请以社区核验为准；OpenAI 官方声明"未经形式化的结果可能有问题"。该结果族目前仅此一篇手稿，无姊妹篇交叉支撑，但论证自足：种子复形的无环性与 `@@M@@\SU(2)@@` 表示是行列式为 `@@M@@1@@` 的显式计算，四个模块（几何模型、展示比较、局部化度引理、传输构造）均给出完整证明，依赖的经典结果（Bestvina–Brady、Gerstenhaber–Rothaus、Dicks–Leary、Howie 等）一一注明。鉴于结论推翻了近七十年的公开猜想，严格的专家核验尤为必要。

{% endraw %}
