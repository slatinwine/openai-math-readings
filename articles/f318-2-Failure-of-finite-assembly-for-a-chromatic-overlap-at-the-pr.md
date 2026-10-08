---
layout: default
title: "Failure of finite assembly for a chromatic overlap at the prime three"
family: "318"
discipline: "Topology"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | Failure of finite assembly for a chromatic overlap at the prime three

> 结果族 318：Chromatic splitting: filtrations and counterexamples　·　学科：Topology　·　验证状态：暂无形式化证明，请以社区核验为准

## 入门导读 🐣

想象你有一盒三种基础积木，规则允许你任意叠加、平移、复制和取"补块"，拼任意有限多步。这篇论文证明：在素数 3 对应的"三楼"，有一个叫色重叠加的关键零件，无论怎么拼都拼不出来——不是难度问题，是原则上拼不出。稳定同伦论里悬置多年的"有限拼装"问题就此得到否定回答。

**关键词卡片**

- 色重叠加（chromatic overlap）：球面同时在相邻两层"放大镜"下观察时留下的粘合数据，是复原整体的关键零件。
- 局部球面（local sphere）：只保留某一层信息看到的球面；低层的 `@@M@@L_0S@@`、`@@M@@L_1S@@`、`@@M@@L_2S@@` 就是三块基础积木。
- 厚子范畴（thick subcategory）：从给定积木出发，经求和、移位、余纤维、收缩四种操作、有限步内能造出的全部对象。
- 色高度（chromatic height）：同伦论按周期复杂度划分的"楼层"；本文出事的位置是素数 3、高度 3。

**看个具体例子**

把主定理代入具体数字 `@@M@@p=3@@`：三块积木加上四种允许操作，步数任意但必须有限；目标是色重叠加 `@@M@@L_2L_{K(3)}S@@`。定理说它"不在厚子范畴里"，画成图就是：

<div>

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 560 280">
<rect x="30" y="212" width="130" height="36" fill="none" stroke="black"/>
<text x="95" y="235" font-size="14" text-anchor="middle">L₀S（有理化）</text>
<rect x="215" y="212" width="130" height="36" fill="none" stroke="black"/>
<text x="280" y="235" font-size="14" text-anchor="middle">L₁S（高度一）</text>
<rect x="400" y="212" width="130" height="36" fill="none" stroke="black"/>
<text x="465" y="235" font-size="14" text-anchor="middle">L₂S（高度二）</text>
<line x1="300" y1="200" x2="378" y2="122" stroke="black" stroke-width="2"/>
<line x1="378" y1="122" x2="364" y2="126" stroke="black" stroke-width="2"/>
<line x1="378" y1="122" x2="372" y2="136" stroke="black" stroke-width="2"/>
<line x1="322" y1="156" x2="342" y2="176" stroke="red" stroke-width="3"/>
<line x1="342" y1="156" x2="322" y2="176" stroke="red" stroke-width="3"/>
<circle cx="424" cy="78" r="44" fill="none" stroke="black" stroke-width="2"/>
<text x="424" y="72" font-size="14" text-anchor="middle">色重叠加</text>
<text x="424" y="92" font-size="13" text-anchor="middle">p=3，高度 3</text>
<text x="140" y="120" font-size="13" text-anchor="middle">任意有限次操作：</text>
<text x="140" y="140" font-size="13" text-anchor="middle">求和·移位·余纤维·收缩</text>
<text x="424" y="150" font-size="14" text-anchor="middle" fill="red">拼不出来</text>
</svg>

</div>

**为什么值得关心**

它给"低层数据能否重建高层粘合信息"这条色理论主线画出了正式界线：至少在 `@@M@@p=3@@`、高度 3 处答案是否定的，今后任何分裂公式都得绕开这个障碍。

> 暂无形式化证明（AI 结果待核验）

## 一句话结论

本文证明在 `@@M@@p=3@@`、高度三处，色重叠加（chromatic overlap）`@@M@@L_2L_{K(3)}S@@` 不属于由 `@@M@@L_0S,L_1S,L_2S@@` 生成的厚子范畴（thick subcategory）：无论多少次求和、移位、取余纤维与收缩，都无法从低高度局部球面拼装出它。这个比任何分裂公式都更弱的"有限拼装"问题就此得到否定回答。

## 问题背景

稳定同伦论的色断裂（chromatic fracture）把谱分解为各高度的局部化片段，再靠相邻高度间的粘合数据复原原对象；对球面 `@@M@@S@@`，携带粘合信息的核心对象是重叠 `@@M@@L_{n-1}L_{K(n)}S@@`，其中 `@@M@@L_i@@` 是 Johnson–Wilson `@@M@@E(i)@@`-局部化（`@@M@@L_0@@` 为有理化），`@@M@@L_{K(n)}@@` 是 Morava `@@M@@K(n)@@`-局部化。Hopkins 的色分裂猜想（由 Hovey 记录）预言该重叠可由低高度局部球面按明确方式分裂。已知结果集中在高度二：`@@M@@p\geq5@@` 的情形建立在 Shimomura–Yabe 计算之上（后经 Behrens 修正），`@@M@@p=3@@` 时 Goerss–Henn–Mahowald 给出了指定分裂；`@@M@@p=2@@` 时 Beaudry 推翻了强和式公式，但 Beaudry–Goerss–Henn 补入 Moore 谱项后典范单位的收缩仍然成立——可见"指定和式列表失败"并不排除有限构造。真正悬而未决的是最弱的有限拼装问题：重叠能否由低高度局部球面经有限步构造？本文在 `@@M@@p=n=3@@` 处给出否定。

## 主要结果

主定理：取 `@@M@@S=S_3^\wedge@@` 为导出 `@@M@@3@@`-完备球面，则在 `@@M@@E(2)@@`-局部 `@@M@@S@@`-模范畴中有
`@@M@@DL_2L_{K(3)}S\notin\operatorname{Thick}\{L_0S,L_1S,L_2S\}.@@`
这里 `@@M@@\operatorname{Thick}@@` 表示最小厚子范畴：对有限和、整数移位、同伦余纤维（cofiber）与收缩（retract）封闭，所有映射均为 `@@M@@S@@`-线性。这一表述刻意宽松——允许非分裂扩张与 Moore 修正（乘 `@@M@@p@@` 的幂的余纤维是允许的操作），不指定映射、不限制操作次数——因此否定它严格强于否定任何具体的分裂公式。结论只针对 `@@M@@p=n=3@@` 这一情形，且其障碍不依赖任何候选和式列表或构造步数上限。

## 证明思路

证明分两条主线：先造一个对有限构造稳定的"检测器"，再实际算出重叠的一个表示论不变量，最后让二者迎头相撞。

先造检测器。取含 `@@M@@\mathbb F_{3^6}@@` 的有限域 `@@M@@k@@` 与高度二 Morava `@@M@@E@@`-理论 `@@M@@E_2@@`（`@@M@@\pi_0E_2=W(k)[[x]]@@`），令 `@@M@@Q_x=k((x))@@`，`@@M@@\omega=\pi_2E_2@@` 为周期线。对谱 `@@M@@X@@` 施加精确测试 `@@M@@\mathcal T(X)=L_{K(2)}(E_2\wedge X)/3@@` 并局部化系数得 `@@M@@\mathcal V_d(X)@@`；单位群 `@@M@@G_F=\mathcal O_F^\times@@`（`@@M@@\mathbb Q_3@@` 的非分歧二次扩域 `@@M@@F@@` 的单位群，嵌入高度二自同构代数）半线性地作用其上。关键观察：经 `@@M@@K(2)@@`-局部化，三个候选生成元变为 `@@M@@0,0,\mathbf 1_2@@`，而 `@@M@@\mathbf 1_2@@` 的检测在每个偶数度恰为一条周期线 `@@M@@\overline\omega^{\otimes j}@@`；由 Serre 子范畴论证，凡从 `@@M@@\mathbf 1_2@@` 经允许的有限操作得到的对象，其一切 `@@M@@\mathcal V_d@@` 都有限维，且单成分只能是周期线之幂。

再算系数。在高度三形变的高度二层上，代数 `@@M@@p@@`-可除群分为连通高度二部分与平展高度一商；对后者构造行列式规范化的整标记塔，先在完备化完美（completed perfection）系数上算上同调，再用 Cartier 算子的残数伴随（它是 Frobenius）控制有限阶段的有限性，经一个分配算子（distribution operator）在驯顺符号平均后去除根，最后沿剩余的范数商下降：得到 `@@M@@L@@` 的普通 `@@M@@P@@`-上同调恰四条线，位于度 `@@M@@0,1,3,4@@`，上面两条带范数特征标 `@@M@@\delta@@`。

最后搬进实际同伦。取有限平展常量扩张 `@@M@@S_k@@` 与 `@@M@@Z_k=L_{K(3)}S_k@@`，Morava 下降谱序列配合可下降性（descendability）给出收敛塔的有限滤过；再用平方零形变挠子与泛 Kodaira–Spencer 同构，把连通–平展分裂提升穿过一切 `@@M@@R[x]/(x^m)@@`，使 `@@M@@J@@`-作用穿过所有 jet 存活。反转 `@@M@@x@@` 后谱序列只剩四行，唯一可能的高阶微分会把范数线 `@@M@@Q_x(\delta)@@` 等同于某条周期线幂——而这被排除：`@@M@@G_F@@` 在 `@@M@@Q_x@@` 上的作用像无限且固定域恰为 `@@M@@k@@`，结合第一个 Hasse 不变量的赋值与 `@@M@@k@@` 在 `@@M@@k((x))@@` 中相对代数封闭，得 `@@M@@Q_x(\delta)@@` 不同构于任何 `@@M@@\overline\omega^{\otimes b}@@`。于是谱序列坍缩，实际同伦在对角常量域和项上给出短正合列 `@@M@@0\to Q_x(\delta)\to\mathcal V_{-3}^\Delta(Z_k)\to\overline\omega^{\otimes(-1)}\to0@@`，故 `@@M@@Q_x(\delta)@@` 也是整个 `@@M@@\mathcal V_{-3}(Z_k)@@` 的一个单成分。若有限拼装成立，则因 `@@M@@S_k@@` 是 `@@M@@S@@` 上有限自由模，检测器要求 `@@M@@\mathcal V_{-3}(Z_k)@@` 只含周期线成分——与范数线的存在矛盾，定理得证。

## 可信度与备注

主结果暂无 Lean 形式化证明，且证明链条长（标记塔、完备上同调、jet 比较、表示论排除环环相扣），请以社区核验为准。同族 318 的姊妹篇勾出完整图景：在 `@@M@@n\geq1@@`、`@@M@@p\gt n+1@@` 的泛素数范围，重叠确有由局部球面片段组成的 `@@M@@2^n@@` 步滤过；`@@M@@p\geq5@@` 高度三的强楔形公式亦被推翻。但按原文说明，这些姊妹结果均未为本文的 `@@M@@p=3@@` 证明提供步骤。OpenAI 官方声明：未经形式化的结果可能有问题。

{% endraw %}
