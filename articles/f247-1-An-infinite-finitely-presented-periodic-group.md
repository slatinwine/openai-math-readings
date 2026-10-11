---
layout: default
title: "An infinite finitely presented periodic group"
family: "247"
discipline: "Group theory"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | An infinite finitely presented periodic group

> 结果族 247：An infinite finitely presented residually finite 2-group and a finitely presented nil algebra　·　学科：Group theory　·　验证状态：暂无形式化证明，请以社区核验为准

## 入门导读 🐣

群就像一本"乘法说明书"：写清所有元素如何相乘。若这本说明书只有有限页（有限个生成元加有限条关系式），就称有限呈现。Burnside 在 1902 年问：如果说明书还保证每个元素转有限圈就回到原点（周期群），世界是否必然只有有限多个元素？本文造出反例：元素无穷多，说明书却只有有限页。

**关键词卡片**

- 周期群（periodic group）：每个元素的阶都有限的群；Burnside 问题问有限生成的它是否必有限。
- 有限呈现（finitely presented）：有限个生成元＋有限条关系式完整刻画。
- Steinberg 群（Steinberg group）：由环搭建的一类群，本文主角是 `@@M@@\mathrm{St}_{12}(R)@@`。
- 幂零代数（nil algebra）：每个元素各自幂零、但整体未必幂零的结合代数。

**看个具体例子**

主角是一个按"自相似规则层级"造出的 `@@M@@\mathbb F_2@@` 上的代数 `@@M@@R@@`；其 Steinberg 群 `@@M@@\mathrm{St}_{12}(R)@@` 无限、有限呈现且周期（见图）。同一个 `@@M@@R@@` 还顺带否定三条代数问题：它给出有限呈现、逐元素幂零却不幂零的代数，以及有限呈现、代数的却无穷维的代数。

<div>

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 560 280"><rect x="45" y="90" width="190" height="110" fill="none" stroke="#2c7fb8" stroke-width="2.5"/><text x="140" y="120" font-size="14" fill="#2c7fb8" text-anchor="middle">有限说明书</text><text x="140" y="145" font-size="13" fill="#333" text-anchor="middle">有限个生成元</text><text x="140" y="168" font-size="13" fill="#333" text-anchor="middle">＋有限条关系式</text><text x="140" y="225" font-size="13" fill="#666" text-anchor="middle">（有限呈现）</text><circle cx="370" cy="60" r="14" fill="none" stroke="#c0392b" stroke-width="2"/><text x="370" y="65" font-size="11" fill="#c0392b" text-anchor="middle">阶3</text><circle cx="455" cy="105" r="14" fill="none" stroke="#c0392b" stroke-width="2"/><text x="455" y="110" font-size="11" fill="#c0392b" text-anchor="middle">阶5</text><circle cx="480" cy="175" r="14" fill="none" stroke="#c0392b" stroke-width="2"/><text x="480" y="180" font-size="11" fill="#c0392b" text-anchor="middle">阶7</text><circle cx="430" cy="238" r="14" fill="none" stroke="#c0392b" stroke-width="2"/><text x="430" y="243" font-size="11" fill="#c0392b" text-anchor="middle">阶n</text><text x="350" y="272" font-size="13" fill="#c0392b" text-anchor="middle">……无穷多个元素，阶都有限</text><line x1="236" y1="115" x2="356" y2="66" stroke="#666" stroke-width="1.8"/><line x1="236" y1="130" x2="441" y2="102" stroke="#666" stroke-width="1.8"/><line x1="236" y1="160" x2="466" y2="170" stroke="#666" stroke-width="1.8"/><line x1="236" y1="180" x2="417" y2="230" stroke="#666" stroke-width="1.8"/></svg>

</div>

**为什么值得关心**

这否定回答了 Ol'shanskii–Sapir 2003 年明确列出的公开问题；该群还具有 Kazhdan 性质 (T)、从而非顺从，代数侧三问也一并关闭。

> 暂无形式化证明（AI 结果待核验）

## 由浅入深：从类比走向定理

**第一级台阶**

导读把群比作"乘法说明书"：有限页即有限个生成元加有限条关系。Burnside 问：若说明书还保证每个元素转有限圈回原点（周期群），元素是否必只有有限多个？本文给出否定反例。制造路线是两步：先用"自相似的局部替换规则"造一个环，再取该环上的 Steinberg 群——由初等矩阵式符号加三条 Steinberg 关系定义的抽象群。

**第二级台阶**

用本科术语精确化：普通有限呈现指自由群模有限个关系词的正规闭包之商；代数 `@@M@@R=\mathbb F_2\oplus I@@` 分次、单结合、有限呈现，其正度理想 `@@M@@I@@` 矩阵幂零（matrix-nil）：任何尺寸、系数取自 `@@M@@I@@` 的矩阵逐个幂零。周期性由此分两段：矩阵像模 `@@M@@I@@` 归约到有限群 `@@M@@\GL_n(\mathbb F_2)@@`，特征 `@@M@@2@@` 下逐次平方；剩下的 Steinberg 核 `@@M@@J_{12}(R)@@` 须是挠群。

**第三级台阶**

定理断言 `@@M@@\mathrm{St}_{12}(R)@@` 无限、具普通有限呈现且周期，否定回答 Ol'shanskii–Sapir 列出的有限呈现 Burnside 问题。同一构造须同时兑现四项义务：有限呈现（Krstić–McCool 方法）、无限性、矩阵像周期、核的挠性（分次嵌入配合循环/截断移位求值，再经标架复理的有理稳定性回到秩 12）。推论顺势落下：该群具 Kazhdan 性质 (T)（据 Ershov–Jaikin-Zapirain 定理）从而非顺从；理想 `@@M@@I@@` 还同时否定 Ufnarovskij、Amitsur 与 Kurosh 三问的有限呈现版本。

## 一句话结论

本文构造了首个具普通有限呈现的无限周期群 `@@M@@\mathop{\mathrm{St}}\nolimits_{12}(R)@@`，并同批造出有限呈现、无穷维、逐元素幂零却不幂零的结合代数，一并否定有限呈现 Burnside 问题、Ufnarovskij 幂零代数问题与 Kurosh 问题的有限呈现版本。

## 问题背景

Burnside（1902）问：每个元素皆有限阶的有限生成群（周期群，periodic group）是否必有限？Golod 与 Novikov–Adian 先后给出无限反例，但都不是有限呈现（finitely presented）；Ol'shanskii–Sapir（2003）明确把"无限周期群可否有普通有限呈现"列为独立公开问题。代数一侧有平行的问题：结合代数逐元素幂零（nil）是否推出整体幂零（nilpotent，即 `@@M@@A^N=0@@`）？Ufnarovskij 问有限呈现的幂零代数是否必幂零，Amitsur 问 Jacobson 根（Jacobson radical）版本，Kurosh 问（域含于中心时）有限生成的代数代数（algebraic algebra）是否必有限维，其有限呈现版本更强且长期未决。难点在于 Golod–Shafarevich 式的无限性论证与"只允许有限条定义关系"几乎天然冲突，而群与代数两侧必须一次解决。

## 主要结果

定理：存在无限周期群具普通有限呈现。具体地，构造无限、有限呈现的单结合 `@@M@@\mathbb F_2@@`-代数 `@@M@@R=\mathbb F_2\oplus I@@`（`@@M@@I@@` 为正度理想），则 Steinberg 群（Steinberg group）`@@M@@\mathop{\mathrm{St}}\nolimits_{12}(R)@@` 无限、有限呈现且周期。

推论：该群具 Kazhdan 性质 (T)（Kazhdan's property (T)，由 Ershov–Jaikin-Zapirain 的定理得出），因而非顺从（nonamenable）。

代数推论：理想 `@@M@@I@@` 是无限维、非幺（nonunital）、有限呈现的幂零代数，同时是 Jacobson 根但非幂零；其单位化（unitization）有限呈现、代数的且无穷维。这三件分别否定 Ufnarovskij 问题、Amitsur 问题与 Kurosh 问题的有限呈现版本。

## 证明思路

一切系于理想 `@@M@@I@@` 的矩阵幂零性（matrix-nil）：任意尺寸、系数取自 `@@M@@I@@` 的矩阵逐个幂零。有了它，`@@M@@\GL_n(R)@@` 中矩阵模 `@@M@@I@@` 归约到有限群 `@@M@@\GL_n(\mathbb F_2)@@`，特征 `@@M@@2@@` 下逐次平方给出矩阵群周期；剩下证 Steinberg 核 `@@M@@J_{12}(R)@@` 是挠群，则任何群元先乘某幂落进核、再乘一幂回到单位元。

环 `@@M@@R@@` 由自相似局部规则层级构造。字母是 `@@M@@ch@@` 比特串（`@@M@@c=10000@@`），"干净块"含 `@@M@@q_h@@` 个核心格、一张调色板（palette）与一个停止格，总长 `@@M@@L_h=2q_h+1@@`；上层字母经代入 `@@M@@E_h@@` 编码为下层规范块串。关系只有等长替换 `@@M@@v=v'@@` 与零声明 `@@M@@v=0@@`，长度至多 `@@M@@k=10@@`。规则表本身是自指地定义的：块内的验证者头（verifier head）用 Cook 计算表（computation tableau）式的三文字局部子句核查"替换证书"，而验证程序由 Kleene 不动点 `@@M@@a=s(t,t)@@` 指定——程序 `@@M@@a@@` 恰好认证以 `@@M@@a@@` 为代码的规则表（先例是 Durand–Romashchenko–Shen 的自模拟瓦片构造）。由此证得：干净编码保持非零词；每个足够长的非零词有唯一的 token 分解，各 token 可孤立地规范化为规范块串。

矩阵幂零性靠消没证明：给每字母指定数值矩阵，词取其有序乘积（Schützenberger 加权自动机）。长词中必含长度 `@@M@@\ge q/100@@` 的可换色段（eligible run），段内颜色互异、相邻字母可任意换位；对该段内的整块做全体置换，特征 `@@M@@2@@` 下交错和 `@@M@@\sum_\sigma X_{\sigma(1)}\cdots X_{\sigma(m)}=0@@`（`@@M@@m>d^2@@`，且证明无须除 `@@M@@m!@@`）。当调色板相对测试维数不够大时，经 token 分解把测试提升一层，再用有限状态矩阵自动机把块测试还原为字母测试（维数增大）；层级指数增长保证若干层后直接消没成立。最后引入中心未定元把"因子个数"与"词长"分开，抽取系数即得每个固定矩阵幂零。

群侧按 Krstić–McCool 方法给出 `@@M@@\mathop{\mathrm{St}}\nolimits_n(R)@@`（`@@M@@n\ge 5@@`）的普通有限呈现：生成元 `@@M@@g_{ij}(w)@@`（`@@M@@|w|\le 2@@`），长词根递归定义为换位子，一条三因子换位子恒等式保证定义与分裂方式无关。核的挠性：经分次嵌入 `@@M@@\gamma:R\to R[t]@@` 把 `@@M@@t@@` 代入 `@@M@@2@@` 幂阶循环移位矩阵 `@@M@@C_N@@`，基变换三角化后得 `@@M@@W=\iota_1(u)^N@@`；再用"环绕消去"证明循环移位与截断移位在 Steinberg 群内相等（误差收集进矩阵映射单射的条带），后者恰为 `@@M@@\mathbb F_2@@` 上核元素之积、为挠，故 `@@M@@u@@` 稳定后为挠；最后由标架复形（frame complex）的有理稳定性（rational stability，`@@M@@n\ge 12@@`）把挠性拉回 `@@M@@J_{12}(R)@@`：一切到 `@@M@@\mathbb Q@@` 的同态都杀死 `@@M@@u@@`，故 `@@M@@u@@` 挠。

## 可信度与备注

本文主结果暂无形式化证明（任务元数据 formalized=false），请以社区核验为准。姊妹篇"An infinite finitely presented residually finite 2-group"（2026-10-05）显式引用本文的代数与层级命题，把结论加强为剩余有限 `@@M@@2@@`-群，两文互相支撑。按 OpenAI 官方声明，未经形式化的结果可能有问题；本文最复杂、最值得核验的是自指规则表（Kleene 不动点与计算表子句）及逐层消没的组合细节。

---

## 深入探讨：像审稿人一样追问 🔍

**问 1：证明中最关键、最脆弱的一步是什么？**

答：自指规则表。关系规则由 Kleene 不动点 `@@M@@a=s(t,t)@@` 指定——程序 `@@M@@a@@` 恰好认证以 `@@M@@a@@` 为代码的规则表，验证者头用 Cook 计算表式三文字子句局部核查替换证书。论文自己强调：必须控制"关系允许的每一个有限词"，包括未完成或伪造验证状态的词。这一自模拟构造（先例是 Durand–Romashchenko–Shen 的不动点瓦片）是全文的地基，也是最可能藏错的地方。

**问 2：为什么必须"四项义务"在同一个环上同时成立，拼装已有反例不行吗？**

答：不行。Ivanov–Pogodaev–Kanel-Belov 的有限呈现零半群满足 `@@M@@x^9=0@@`，但不保证词像的任意和或矩阵的幂零；Ol'shanskii–Sapir 的有限呈现挠群带无限循环商、不周期；Golod 路线与有限呈现天然冲突。有限呈现、无限、矩阵像周期、核挠性必须由同一个 `@@M@@R@@` 同一批关系兑现。

**问 3：核 `@@M@@J_{12}(R)@@` 的挠性是怎么证的，为何需要秩 12？**

答：三段接力：先用根条带（矩阵映射在其上单射）证中心性；再比较 `@@M@@t@@` 代入循环移位与截断移位两种求值，环绕边界的根收进条带后证明两者在 Steinberg 群内相等，从而稳定化副本的某幂等于基域核元素之积（已挠）；最后用标架复理的有理同调稳定性把挠性拉回低秩——同态 `@@M@@J_n\to\mathbb Q@@` 可扩张要求 `@@M@@n\ge 12@@`，秩 12 由此而来。

**问 4：矩阵消没为什么偏要在特征 2 里做？**

答：因为关键恒等式是对可换色段全体置换的交错和 `@@M@@\sum_\sigma X_{\sigma(1)}\cdots X_{\sigma(m)}=0@@`（`@@M@@m>d^2@@`），特征 2 使证明无须除以 `@@M@@m!@@`。调色板不够大时经 token 分解与 Schützenberger 加权自动机把块测试还原为字母测试、逐层放大维数，层级指数增长保证有限层后直接消没；中心未定元再分离因子个数与词长。

**问 5：这类构造最可能出错的模式是什么？**

答：自模拟与逐层消没的组合记账——"伪造验证状态也要被规则拒绝"这类封闭性断言，以及层间提升时维数、色数、长度参数的耦合选择，都是 AI 生成证明易在细节处滑跤的位置。姊妹篇（剩余有限 2-群）完全依赖本文的代数与层级命题，错误会双向传导；两文均无形式化。

**问 6：与已有工作相比真正的新意是什么？**

答：首个具普通有限呈现的无限周期群，且自带性质 (T)（此前 Ershov 的周期 (T) 群非有限呈现）；代数侧一次性关掉 Ufnarovskij、Amitsur 与 Kurosh 有限呈现版三问。自指规则表 + 矩阵消没的组合是此前未有的机制。

**问 7：谁会用这个结果？**

答：几何群论（周期群、非顺从群、Burnside 型问题的基准反例）、环论与 K-理论（幂零代数与代数代数的有限呈现反例）；姊妹篇在其上得到剩余有限 2-群，使整个家族成为后续构造的起点。

**总评**

这是有限呈现 Burnside 问题与三条代数问题的同时否定回答，构造野心与技术密度都极高；最大风险集中于自指规则表的封闭性与逐层消没的组合细节，无形式化背书，须按最长反例的标准逐行核验。

{% endraw %}
