---
layout: default
title: "Counterexamples to the Hahn-Wilson conjecture at height two"
family: "319"
discipline: "Topology"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | Counterexamples to the Hahn-Wilson conjecture at height two

> 结果族 319：Counterexamples to finite generation at chromatic height two　·　学科：Topology　·　验证状态：暂无形式化证明，请以社区核验为准

## 入门导读 🐣

俱乐部有条入会捷径：只要通过一门"有限性考试"，就自动获得会员资格——Hahn–Wilson 猜想就是这样一条承诺。本文在"高度二"这层楼造出一个考试全过、却无论如何进不了门的考生，捷径被证明是假的。

**关键词卡片**

- fp-型（fp-type）：谱的有限性"考试成绩"，不超过 n 意味着同调在 Steenrod 代数上可以有限呈现。
- 截断 Brown–Peterson 谱（truncated Brown–Peterson spectrum）：每一色层的"标准发电机"`@@M@@\mathrm{BP}\langle n\rangle@@`。
- 厚子范畴（thick subcategory）：从发电机出发，经求和、移位、上纤维、收缩有限步能造出的一切对象。
- 望远镜猜想（telescope conjecture）：比较两种局部化的著名难题；本文的反例反而同时满足这两种比较。

**看个具体例子**

对每个充分大的素数 p，构造出的谱 X 有一份"体检报告"：

<div>

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 560 280">
<text x="280" y="32" font-size="15" text-anchor="middle" font-weight="bold">反例 X 的体检报告（大素数 p）</text>
<rect x="55" y="55" width="450" height="185" fill="none" stroke="black" stroke-width="2"/>
<text x="85" y="100" font-size="15" fill="green">✓</text>
<text x="115" y="100" font-size="14">fp-型恰为 2（考试通过，但不是 1）</text>
<text x="85" y="145" font-size="15" fill="green">✓</text>
<text x="115" y="145" font-size="14">两种望远镜式局部化比较都成立</text>
<text x="85" y="190" font-size="15" fill="red">✗</text>
<text x="115" y="190" font-size="14">不属于 Thick(BP⟨2⟩)：无法由发电机有限步造出</text>
</svg>

</div>

猜想说"fp-型 ≤ 2"与"会员资格"是一回事，第三行把它击碎：考试通过了，门却进不去。

**为什么值得关心**

高度 0 和 1 时猜想成立，高度 2 首次崩塌；它还示范了"局部表现良好"不保证"整体可有限生成"。

> 暂无形式化证明（AI 结果待核验）

## 由浅入深：从类比走向定理

**第一级台阶**

导读把 Hahn–Wilson 猜想说成"通过一门有限性考试就自动入会"。换成半数学的语言：研究对象是一类无穷谱；"考试"是同调层面的有限性——把谱与某个有限对象相撞后，得到的同伦群总体有限；"会员资格"是构造层面的有限性——从每一层的标准发电机出发，经有限步组装得到。猜想说两种有限性等价；本文造出一个考过了试却入不了会的谱，捷径是假的。

**第二级台阶**

用本科术语精确化。谱 `@@M@@X@@` 称为 fp-谱，若其模 `@@M@@p@@` 同调 `@@M@@H^*(X;\mathbb F_p)@@` 在 Steenrod 代数上有限呈现；Mahowald–Rezk 定理说这等价于存在非零有限谱 `@@M@@V@@` 使 `@@M@@\pi_*(V\wedge X)@@` 总体有限。fp-型至多 `@@M@@n@@` 意味着该测试对型为 `@@M@@n+1@@` 的 `@@M@@V@@` 成立。截断 Brown–Peterson 谱 `@@M@@\mathrm{BP}\langle n\rangle@@` 的系数环是 `@@M@@\mathbb Z_p[v_1,\dots,v_n]@@`；`@@M@@\Thick(B)@@` 表示对有限和、移位、上纤维与收缩封闭的最小子范畴，即"从 `@@M@@B@@` 出发有限步可造"的严格化。

**第三级台阶**

定理的语境是：素数取充分大者——这一假设挡住了两件事：高度二的"色代数性"比较需要 `@@M@@p>8@@`，核心算子的组合构造还需要更大的素数；生成元取指定标准形式的 `@@M@@\mathrm{BP}\langle2\rangle_p^\wedge@@`（在大奇素数处其底层谱不依赖商的选取）。定理断言：存在连通 `@@M@@p@@`-完备谱 `@@M@@X@@`，fp-型恰为二，却 `@@M@@X\notin\Thick(\mathrm{BP}\langle2\rangle_p^\wedge)@@`——同调有限性推不出有限构造。同一 `@@M@@X@@` 还满足 `@@M@@L_2^fX\simeq L_2X@@` 与 `@@M@@L_{T(2)}X\simeq L_{K(2)}X@@`，即局部化层面行为规整；障碍全在局部片段的粘合方式上。

## 一句话结论

对每个充分大的素数 `@@M@@p@@`，本文构造出 fp-型恰为 2 的连通 `@@M@@p@@`-完备谱 `@@M@@X@@`，它不能由 `@@M@@\mathrm{BP}\langle2\rangle_p^\wedge@@` 经有限次求和、移位、上纤维与收缩得到，从而在色高度 2 否定 Hahn–Wilson 猜想；同一个 `@@M@@X@@` 却仍满足两种望远镜式局部化比较。

## 问题背景

稳定同调论的一个基本问题：哪些无穷谱（infinite spectrum）能从截断 Brown–Peterson 谱（truncated Brown–Peterson spectrum）`@@M@@\mathrm{BP}\langle n\rangle@@` 出发，经有限次求和、移位、上纤维序列（cofiber sequence）与收缩（retract）构造出来？Mahowald–Rezk 的 fp-谱理论给出了自然的有限性刻画：`@@M@@H^*(X;\F_p)@@` 在模 `@@M@@p@@` Steenrod 代数上有限呈现，等价于对某个非零有限谱 `@@M@@V@@` 有 `@@M@@\pi_*(V\wedge X)@@` 总体有限。Hahn–Wilson 猜想（书面形式见于 Lee–Pstrągowski 2026，作者自述 2021 年闻于 Dylan Wilson）断言：fp-型至多 `@@M@@n@@` 的谱恰好构成 `@@M@@\Thick(\mathrm{BP}\langle n\rangle_p^\wedge)@@` 这个 thick 子范畴（thick subcategory）。高度 0 与 1 的情形已知成立，高度 `@@M@@\ge2@@` 长期未决。另一侧，Burklund–Hahn–Levy–Schlank 已在每个素数的每个高度 `@@M@@\ge2@@` 否定了望远镜猜想（telescope conjecture），但其反例与有限谱 smash 后的同伦群只是逐次有界而非总体有限，不满足 fp 条件，无法回答此问题。

## 主要结果

主定理：对每个充分大的素数 `@@M@@p@@`，存在连通 `@@M@@p@@`-完备谱 `@@M@@X@@`，其 fp-型恰为二（exact fp-type two，即至多为 2 而非 1），且对指定标准形式的 `@@M@@\mathrm{BP}\langle2\rangle_p^\wedge@@` 有 `@@M@@X\notin\Thick(\mathrm{BP}\langle2\rangle_p^\wedge)@@`——也就是说 `@@M@@X@@` 没有任何来自该生成元的有限构造。同一个谱还满足两个局部化比较：`@@M@@L_2^fX\simeq L_2X@@`（有限色局部化与 Johnson–Wilson 局部化一致）与 `@@M@@L_{T(2)}X\simeq L_{K(2)}X@@`（`@@M@@T(2)@@`-望远镜局部化与 Morava `@@M@@K(2)@@`-局部化一致）。局部行为反而是正面的：`@@M@@L_{K(2)}X@@` 在 `@@M@@K(2)@@`-局部范畴中属于 `@@M@@\Thick(E_2)@@`，其 Morava `@@M@@E@@`-上同调在运算环上有限生成且自反（reflexive）。论文还给出一个独立障碍：`@@M@@\tau_{\geq0}E_2\notin\Thick(b_p^\wedge)@@`，因为 `@@M@@\pi_0((\tau_{\geq0}E_2)/p)\cong\F_{p^2}[[u_1]]@@` 无限，而"除以 `@@M@@p@@` 后逐次有限"是 thick 性质。

## 证明思路

先在大素数处启用色代数性（chromatic algebraicity）：用 Pstrągowski 的同调相容三角比较（高度 2 需 `@@M@@p>8@@`），把问题搬进"高度至多 2 的 `@@M@@p@@`-典型形式群栈再商去中心自同构 `@@M@@1+p\mathbb{Z}_p@@`"所得栈 `@@M@@\mathcal N@@` 上的周期导出范畴。记 `@@M@@D=2(p-1)@@`，目标化为构造对象 `@@M@@U@@` 同时满足三条：每个 `@@M@@\pi_iU@@` 有限；完备化 `@@M@@\widehat U\in\Thick(\widehat{T'})@@`；但 `@@M@@U\notin\Thick(T')@@`，其中 `@@M@@T'@@` 是图表推进的结构层。

再构造核心算子。完备运算环形如 `@@M@@\Delta=k[[x]][[H]]@@`，取定一个运算 `@@M@@a@@`（模 `@@M@@x@@` 即 `@@M@@\delta_\gamma-\delta_1@@`），它在 Laurent 级数上的作用是无穷下三角矩阵。借助 Bhargava 型 `@@M@@P@@`-排序插值测度（Amice 方法），可按"深度"递增逐层修改矩阵元素而不扰动更浅的层；秩匹配引理（rank matching）说明按深度固定元素时，是否出现新 pivot 由角元素是否避开一个指定标量决定。于是用 `@@M@@p@@`-进制"中心数字"策略设计 `@@M@@a@@`：在中心簇保留 `@@M@@B_0=2\lfloor M/8\rfloor@@` 个数字，使尺度 `@@M@@N@@` 处至少 `@@M@@cN^\beta@@`（`@@M@@\beta=\log_pB_0>1/3@@`）个行与列永不匹配，从而 `@@M@@a@@` 在交叠空间上留下大量独立的核向量与余核类。把永不匹配的正行类与核向量配对、张成离散格，由开范畴实现为 `@@M@@V\to LY@@`，取同伦拉回 `@@M@@U=Y\times_{LY}V@@`，其中 `@@M@@Y@@` 是 `@@M@@a@@` 的锥的 `@@M@@D@@` 个移位之和。联合映射 `@@M@@\pi_iY\oplus\pi_iV\to\pi_iLY@@` 的核与余核皆有限，故 `@@M@@\pi_iU@@` 有限；完备化杀死开对象，故 `@@M@@\widehat U\simeq Y@@`。

最后的排除是全文枢纽。先经微局地化（microlocalization）得到双侧平坦、具主理想性质的区域扩张 `@@M@@S@@`，使 `@@M@@\Psi(U)@@` 的同调成为非零挠模；再建立"有限塔判据"：只要"同调幽灵（ghost）蕴含对偶同调幽灵"对一切全局映射成立，则 `@@M@@U\notin\Thick(T')@@`。关键是增长率对比：满足符号条件的两个积分算子的公共核在精度 `@@M@@N@@` 处维数至多 `@@M@@O(N^{1/3})@@`（轨道插值加有限商上的单项式计数），而配对缺陷提供 `@@M@@\ge cN^\beta@@` 个独立向量，`@@M@@\beta>1/3@@` 造成矛盾，把代表映射逼入左理想，倒向归纳遂排除一切有限塔及其收缩。再经约化三角形与幂零比较把排除回推到整 stack，取 `@@M@@E(2)@@`-局部谱的连通覆盖得 `@@M@@X@@`；exact fp-型 2 由高度 1 正定理加 `@@M@@\mathrm{BP}\langle1\rangle_p^\wedge\in\Thick(b_p^\wedge)@@` 反证，两个望远镜比较则由负 Postnikov 尾巴的 `@@M@@T(j)@@`-消没与 Bousfield 类计算直接给出。

## 可信度与备注

本文属 OpenAI 数学预印本系列，主结果暂无 Lean 形式化证明，请以社区核验为准；按 OpenAI 官方声明，未经形式化的结果可能有问题。证明依赖一串大素数技术前提（`@@M@@p>8@@` 的代数性比较、`@@M@@M\ge81@@`、`@@M@@p>16M^2@@` 等），反例只在充分大的素数处给出，小素数与更高高度仍开放。族内结果互相支撑：本文引用了同系列对 Hovey–Strickland 局部张量理想分类的无条件证明（所有素数、所有高度），为"局部正面、全局反面"的对照提供背景；Lee–Pstrągowski 的高度 1 正定理则内嵌于 exact 型 2 的论证之中。

---

## 深入探讨：像审稿人一样追问 🔍

**问 1：全文最关键也最脆的一步在哪里？**

（答：增长率对撞。粘合缺陷在精度 `@@M@@N@@` 处至少 `@@M@@cN^\beta@@` 个独立方向，`@@M@@\beta=\log_pB_0>1/3@@`；而有限塔判据要求两个满足符号条件的积分算子的公共核维数至多 `@@M@@O(N^{1/3})@@`。指数之争只赢在严格大于 `@@M@@1/3@@`——若组合构造的 `@@M@@\beta@@` 估计或轨道插值的核上界有一处差个常数因子或漏掉一层深度，排除论证就断裂。）

**问 2："充分大的素数"这个假设为什么去不掉？**

（答：两层原因：把谱论搬进栈上导出范畴的 Pstrągowski 比较在高度二需要 `@@M@@p>8@@`；算子的"中心数字"设计还需 `@@M@@M\geq81@@`、`@@M@@p>16M^2@@` 一类数值前提，下界是天文数字。小素数与高度 `@@M@@\geq3@@` 论文明确留作开放，未给出任何变体论证。）

**问 3：与 Burklund–Hahn–Levy–Schlank 的望远镜反例相比，新意究竟是什么？**

（答：BHLS 的反例与有限谱相撞后的同伦群只是逐次有界、并非总体有限，不满足 fp 条件，答不了这个问题。本文给出首个 fp 反例，而且同一个 `@@M@@X@@` 同时满足两种望远镜比较——这直接堵死 Lee–Pstrągowski 在 Remark 5.1 提议的路线："高度分解+局部定理+望远镜比较"仍不足以推出全局有限生成。）

**问 4：反例依赖"指定标准形式"的 `@@M@@\mathrm{BP}\langle2\rangle@@`，这是不是躲开了命题本意？**

（答：不是躲闪，论文正面处理了：引用 Lee2026 推论 1.9（基于 Angeltveit–Lind 的修正论证），在大奇素数处完备截断谱的底层谱不依赖标准商生成元的选取，所以反例对所有标准形式同时生效。）

**问 5：AI 生成证明最可能在哪里出错？**

（答：接口处的类型偷换。组合数论部分（Bhargava 型 `@@M@@P@@`-排序插值、按深度递增修改无穷下三角矩阵）自洽不等于它实现的是同调相容的运算；把拉回对象 `@@M@@U@@` 经非分裂比较三角形与幂零比较搬回谱、再取连通覆盖保住 fp 测试，这条转移线最容易被"画歪一毫米"。）

**问 6：局部全好、全局全坏，这说明什么、谁在乎？**

（答：`@@M@@L_{K(2)}X\in\Thick(E_2)@@`、Morava `@@M@@E@@`-上同调有限生成且自反，但整体造不出——障碍定位在"局部片段怎么接"，而非局部内容。做 fp-谱、Mahowald–Rezk 对偶、望远镜猜想有限性细化以及红移问题的人都需要这个分界；此外 `@@M@@\tau_{\geq0}E_2\notin\Thick(b_p^\wedge)@@` 给出一条独立的简易障碍。）

**问 7：有限塔判据"幽灵蕴含对偶幽灵"凭什么成立？**

（答：这是论文自证的范畴判据（第 obstruction 节），思路承 Christensen 的幽灵与有限扩张塔：经微局地化把 `@@M@@\Psi(U)@@` 的同调变成非零挠模后，同调消没强迫对偶同调消没，倒向归纳逐级拆除可能的有限塔。该蕴含依赖选定的粘合数据，是全证明最需要逐行核验的引理。）

**总评**

这是对"有限呈现=有限构造"这一纲领在高度二的第一击，且附带望远镜比较成立，使失败模式无处推诿；最大风险在天文素数下的组合构造与转移回谱论的接口，以及 `@@M@@1/3@@` 指数对撞处差之毫厘即崩的脆弱性。

{% endraw %}
