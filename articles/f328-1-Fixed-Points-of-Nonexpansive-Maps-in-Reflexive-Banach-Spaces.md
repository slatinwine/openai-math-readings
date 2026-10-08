---
layout: default
title: "Fixed Points of Nonexpansive Maps in Reflexive Banach Spaces"
family: "328"
discipline: "Functional analysis"
formalized: true
source: null
pdfname: ""
---

{% raw %}
# 解读 | Fixed Points of Nonexpansive Maps in Reflexive Banach Spaces

> 结果族 328：Nonexpansive fixed points in reflexive Banach spaces　·　学科：Functional analysis（泛函分析）　·　验证状态：主结果已 Lean 形式化

## 入门导读 🐣

把一张地图揉一揉再盖回原区域，规则只有一条：不许把任何两点的距离拉长。问：总有某个点原地不动吗？这就是非扩张映射的不动点问题。这篇论文给出肯定回答的最终版：在"自反"的无穷维空间里，任何闭、有界、凸的块上，这样的揉图操作必有不动点——不需要此前六十年来一直添的各种额外几何条件。

**关键词卡片**

- 非扩张映射（nonexpansive map）：任何两点映后距离 ≤ 原距离；"揉地图但不许拉伸"。
- 不动点（fixed point）：满足 `@@M@@F(x)=x@@` 的点，被映射送回自己原位。
- 自反空间（reflexive Banach space）：与自己的二次对偶自然重合的空间，如 `@@M@@\ell^p@@`、`@@M@@L^p@@`（`@@M@@1<p<\infty@@`）；其闭有界凸集有弱紧性。
- 一致凸（uniformly convex）：球面没有平直边的强几何条件；1965 年以来的老定理都需要它，本文证明可以不要。
- 凸集（convex set）：包含任意两点连线段的集合，"没有洞、没有凹陷"。

**看个具体例子**

平面圆盘绕中心转 30°：任何两点的距离都没变（非扩张），中心点原地不动。但把圆盘挖成圆环再转：每个点都挪了位置，没有不动点——差别只在"凸不凸"。再如区间 `@@M@@[0,1]@@` 上的 `@@M@@F(x)=1-x@@`（距离不变），不动点是 `@@M@@x=\frac12@@`。本文定理：在自反空间（如 `@@M@@\ell^p@@`，`@@M@@1<p<\infty@@`）的任何闭有界凸集上，非扩张自映射必定有不动点，凸性之外不再要任何条件。

<div>

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 560 280">
  <text x="20" y="28" font-size="15" fill="#222">同样转 30°：圆盘（凸）有不动点，圆环（非凸）没有</text>
  <circle cx="150" cy="160" r="78" fill="#dce8fb" stroke="#2f5fd0" stroke-width="2"/>
  <path d="M 95 120 A 70 70 0 0 1 205 120" fill="none" stroke="#333" stroke-width="2"/>
  <polygon points="205,120 193,113 197,126" fill="#333"/>
  <circle cx="150" cy="160" r="6" fill="#d64545"/>
  <text x="60" y="262" font-size="14" fill="#222">圆盘：中心不动 ✓</text>
  <circle cx="420" cy="160" r="78" fill="#dce8fb" stroke="#2f5fd0" stroke-width="2"/>
  <circle cx="420" cy="160" r="34" fill="#f6f6f6" stroke="#2f5fd0" stroke-width="2"/>
  <path d="M 370 130 A 58 58 0 0 1 470 130" fill="none" stroke="#333" stroke-width="2"/>
  <polygon points="470,130 459,124 462,136" fill="#333"/>
  <text x="398" y="166" font-size="13" fill="#888">洞</text>
  <text x="330" y="262" font-size="14" fill="#b0348f">圆环：转起来无不动点 ✗</text>
</svg>

</div>

**为什么值得关心**

Kirk 1965 年开启的问题在原有范数下彻底关闭；优化算法里的不动点迭代从此有了最大适用范围。

> 主结果已 Lean 形式化

## 一句话结论

证明了任意实自反 Banach 空间 (reflexive Banach space) 中，非空闭有界凸子集上的每个非扩张自映射 (nonexpansive selfmap) 都有不动点——Kirk 的自反空间不动点问题在原有范数下获得肯定回答，不再需要一致凸性等任何附加几何条件。

## 问题背景

非扩张映射指满足 `@@M@@\norm{F(a)-F(b)}\le\norm{a-b}@@` 的映射；"闭有界凸集上的非扩张自映射是否必有不动点"是非线性泛函分析的核心问题。1965 年 Browder 与 Göhde 对一致凸 (uniformly convex) 空间给出肯定答案，Kirk 对正规结构 (normal structure) 凸集给出证明，其极小不变集约化正是本文起点。此后虽推广到 `@@M@@L^1@@` 的自反子空间（Maurey）、`@@M@@1@@`-无条件基（Lin）、一致非方空间等，但均为充分条件：Karlovitz 例子表明正规结构非必要；Alspach 在 `@@M@@L_1[0,1]@@` 造出弱紧凸集上无不动点的非扩张自映射，说明仅有弱紧性不够；Benavides 证明每个自反空间可重赋范使结论成立，但换范数会改变哪些映射非扩张。于是"原有范数下自反空间是否总有不动点性质"悬置至今，2026 年的综述仍将其列为未解决。

## 主要结果

**主定理**：设 `@@M@@X@@` 是实自反 Banach 空间，`@@M@@C\subseteq X@@` 非空、范数闭、有界、凸。若 `@@M@@F:C\to C@@` 满足 `@@M@@\norm{F(a)-F(b)}\le\norm{a-b}@@`，则 `@@M@@F@@` 必有不动点。非扩张性按原有范数衡量，不需一致凸性、正规结构等附加条件。

**推论（交换族）**：对 `@@M@@C@@` 上两两交换的非扩张映射族 `@@M@@\mathcal S@@`，公共不动点集 `@@M@@\operatorname{Fix}(\mathcal S)@@` 非空，且是 `@@M@@C@@` 的非扩张收缩 (nonexpansive retract)——存在非扩张映射 `@@M@@R:C\to\operatorname{Fix}(\mathcal S)@@` 在该集上为恒等。推论由主定理结合 Bruck (1974) 的定理直接导出。

## 证明思路

证明用反证法，先做极小不变集 (minimal invariant set) 约化：由反例可得可分、弱紧、凸、直径归一为 `@@M@@1@@` 的集合 `@@M@@K@@`，其上无不动点的非扩张映射 `@@M@@T@@`，且 `@@M@@K@@` 无真的闭凸不变子集。Goebel–Karlovitz 直径引理断言：近似不动点序列（`@@M@@\norm{Tu_j-u_j}\to0@@`）到 `@@M@@K@@` 中每个定点的距离都趋于 `@@M@@1@@`。

第一步构造**锚点**。定义预解映射 (resolvent) `@@M@@R_n@@`（`@@M@@R_n(a)=a/n+(1-1/n)TR_n(a)@@`，`@@M@@\norm{TR_n(a)-R_n(a)}\le1/n@@`），以其生成非扩张映射半群；在逐点弱收敛拓扑下对尾部族取闭凸包之交得紧半群，用 Ellis 引理取出幂等元 `@@M@@P@@`，锚点 `@@M@@x@@` 满足 `@@M@@P(x)=x@@` 且在尾部图像集 `@@M@@D_x@@` 的闭凸包中。由此得"自适应选择"引理：每步精度门槛可依赖此前全部历史，仍能依次选出映射并有限终止，使所选图像的凸组合按范数回到 `@@M@@x@@` 附近。

第二步构造**无穷有序树**：节点带映射、权重 `@@M@@\alpha_v@@`（兄弟和为 `@@M@@1@@`）、可和误差预算 `@@M@@e_v@@`（总和 `@@M@@\le1/128@@`）与泛函 `@@M@@f_v@@`，输出按 `@@M@@H_u=G_u(\sum\alpha_vH_v)@@` 自叶向根传递。"预测"机制尤为关键：`@@M@@Q_v(b;\theta)@@` 刻画"`@@M@@v@@` 左侧叶子保留标签、`@@M@@v@@` 及其右侧换成公共点 `@@M@@b@@`"的理想截断根输出，`@@M@@\theta@@` 取值于紧集，用自由超滤子 (ultrafilter) 取弱极限得 `@@M@@Z_v(\theta)@@`，在选定映射前便备好比较极限；`@@M@@f_v@@` 由紧检测器引理选出，满足 `@@M@@f_v(y_v-z)\ge1-e_v@@`。

第三步**换叶**：取充分晚的 `@@M@@b_j@@`，把截断树的叶输出从右到左逐个换成 `@@M@@b@@`。整块换前后根输出之差满足 `@@M@@f_v(U_v-V_v)\ge W_v-5e_v@@`，其中偏离路径的权重经伸缩求和恰好归并为 `@@M@@1-W_v@@`。归一化差 `@@M@@d_s=(U_s-V_s)/W_s@@` 落在弱紧球 `@@M@@B_Y@@` 中；加权亏缺总量 `@@M@@\le5/128@@`，故必有叶子使路径上全部 `@@M@@f_v(d_s)>1/2@@`。可行节点构成有限分支、任意深的树，逐层选取得无穷枝 `@@M@@v_k@@`；弱紧性给出公共向量 `@@M@@d@@` 使 `@@M@@f_{v_k}(d)\ge1/2@@`。但预算可和给出 `@@M@@|f_{v_k}(z_i-z_j)|\le e_{v_k}\to0@@`，差 `@@M@@z_i-z_j@@` 张成的子空间在 `@@M@@Y@@` 稠密，故 `@@M@@f_{v_k}@@` 逐点趋于零——矛盾。

## 可信度与备注

本篇主结果已由 OpenAI 团队用 Lean 形式化验证（结果族资料附有 Lean 文档），区别于此前 Hanebaly 等宣布而未获核验的证明；锚点、预测树、换叶估计对凸性、非扩张性与紧性的依赖在文中明确分离，便于核验。按 OpenAI 官方声明，未经形式化的结果可能有问题；本篇已形式化，可信度较高，读者仍应以社区核验与 Lean 细节为准。

{% endraw %}
