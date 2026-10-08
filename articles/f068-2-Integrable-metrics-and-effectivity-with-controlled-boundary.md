---
layout: default
title: "Integrable metrics and effectivity with controlled boundary"
family: "068"
discipline: "Algebraic and complex geometry"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | Integrable metrics and effectivity with controlled boundary

> 结果族 068：Anticanonical nonvanishing in every dimension　·　学科：Algebraic and complex geometry　·　验证状态：暂无形式化证明，请以社区核验为准

## 入门导读 🐣

有人手里攥着"账面上值钱却花不出去"的资产（伪有效除子）。这篇论文给出一条兑现规则：只要空间的"体积尺度"弯曲方向有严格底线（曲率下界），而且边界欠条温和到平方可积，那么在任何账面资产上补贴一小笔（支集落在边界内的有效修正），它就能变成真金白银（有理有效）。

**关键词卡片**

- 伪有效（pseudoeffective）：数值落在有效锥闭包里，"极限不亏"，但未必有有效代表。
- 有理有效（rationally effective）：有理线性等价于一个货真价实的有效除子，"资产可变现"。
- 乘子理想（multiplier ideal）：收集"相对于度量不可积"的函数，是度量尖峰有多尖的账本。
- 曲率下界（curvature lower bound）：度量的弯曲不塌过某条底线，严格支配某个 Kähler 形式。
- 边界除子（boundary divisor C）：预先指定的"欠条"载体，其典范截面范数平方局部可积。

**看个具体例子**

可积与不可积一线之隔，用一维积分就能摸到：`@@M@@\int_0^1 x^{-1/2}dx=2@@` 有限，而 `@@M@@\int_0^1 x^{-3/2}dx=\infty@@`——指数一旦过 `@@M@@1@@` 就翻脸。定理的条件 `@@M@@\mathcal J(h)\supset\mathcal O_Y(-C)@@` 正是"边界处尖峰指数小于 `@@M@@1@@`"的几何版：

<div>

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 560 280">
  <text x="66" y="28" font-size="15" fill="#1d3c5c">密度 ~ x^(-1/2)：可积</text>
  <line x1="60" y1="235" x2="300" y2="235" stroke="#555" stroke-width="2"/>
  <line x1="60" y1="235" x2="60" y2="45" stroke="#555" stroke-width="2"/>
  <path d="M 62 48 C 90 150, 130 205, 290 228 L 290 235 L 62 235 Z" fill="#bcd6ee"/>
  <path d="M 62 48 C 90 150, 130 205, 290 228" fill="none" stroke="#4a7dbd" stroke-width="3"/>
  <text x="80" y="258" font-size="13" fill="#333">尖峰下面积 = 2，有限</text>
  <text x="356" y="28" font-size="15" fill="#a33">密度 ~ x^(-3/2)：不可积</text>
  <line x1="340" y1="235" x2="540" y2="235" stroke="#555" stroke-width="2"/>
  <line x1="340" y1="235" x2="340" y2="45" stroke="#888" stroke-width="1" stroke-dasharray="6,5"/>
  <path d="M 342 50 C 352 140, 375 200, 470 226 L 470 235 L 342 235 Z" fill="#f2c4bd"/>
  <path d="M 342 50 C 352 140, 375 200, 470 226" fill="none" stroke="#e05a4e" stroke-width="3"/>
  <text x="415" y="258" font-size="13" fill="#333">面积无穷大</text>
</svg>

</div>

结论链条：伪有效除子 `@@M@@M@@` 经修正 `@@M@@C_0@@`（支集含于 `@@M@@C@@`）后有理有效；对一个 Iitaka 纤维化用这套规则，就把"带固定误差的无界截面"转化为 `@@M@@H^0(X,mL)\neq0@@`，把反典范非消没推进到任意维数。

**为什么值得关心**

它是族内"分析条件换代数兑现"的枢纽：边界修正经拉回后自动消失，实现"借基还簇"。

> 验证状态：暂无形式化证明（AI 结果待核验）

## 一句话结论

本文证明受控边界有效性定理：若 `@@M@@-K_Y+C@@` 的度量有整体严格曲率下界且 `@@M@@C@@` 的典范截断局部平方可积，则任何伪有效有理除子经支集含于 `@@M@@C@@` 的有效修正后即有理有效；据此建立固定误差转化定理，把反典型非消没推进到任意维数。

## 问题背景

伪有效（pseudoeffective）除子未必有任何正倍的有效代表。本文研究一个使其变为有效（至相差有理线性等价）的分析条件：反典型度量的正曲率，加上边界除子典范截断的可积性。其价值在双有理几何：纤维化基上作出的修正，经拉回与推向后可以在原簇上消失，从而"借基还簇"。用乘子理想（multiplier ideal）语言，条件 `@@M@@\mathcal J(h)\supset\mathcal O_Y(-C)@@` 恰好等价于 `@@M@@s_C@@` 的范数平方局部可积。与 LMPTX、Müller 的 nef 框架相比，光滑半正度量给出更强的分析输入，使结论能对一切维数成立。

## 主要结果

定理一（受控边界有效性，Effectivity modulo a controlled boundary）：设 `@@M@@Y@@` 光滑射影、`@@M@@C\ge0@@` 为整除子，`@@M@@-K_Y+C@@` 有曲率支配某 Kähler 形式的奇性 Hermitian 度量 `@@M@@h@@`，且 `@@M@@\mathcal J(h)\supset\mathcal O_Y(-C)@@`。则对每个伪有效有理除子 `@@M@@M@@`，存在支集含于 `@@M@@C@@` 的有效有理除子 `@@M@@C_0@@`，使 `@@M@@M+C_0@@` 有理有效（rationally effective，即有理线性等价于有效有理除子）。定理二（固定误差转化）：设 `@@M@@X@@` 光滑连通射影、`@@M@@L=-K_X@@` 光滑半正、`@@M@@P@@` 为任意伪有效 Cartier 除子；若存在无界正整数 `@@M@@m_j@@` 及有效整除子 `@@M@@N_j\sim m_jL-P@@`，则 `@@M@@H^0(X,mL)\ne0@@`。推论：固定 `@@M@@p\ge0@@`，若 `@@M@@H^0(X,(\Omega_X^1)^{\otimes p}\otimes mL)@@` 沿无界 `@@M@@m@@` 非零，则 `@@M@@L@@` 的某正倍有截断。文中还给出修正环的多分次有限生成、辅助基的 Fano 型（Fano type）模型，以及 `@@M@@\chi(X,\mathcal O_X)\ne0@@` 时的不变截断版本。

## 证明思路

定理一走"BCHM 大边界非消没"路线。先用 Demailly 加权 Bergman 逼近（Ohsawa–Takegoshi 点延拓，配合 Nadel 消没给出的整体生成性）在消解 `@@M@@\sigma:Y'\to Y@@` 上造出符号除子 `@@M@@\Psi=\Psi^+-\Psi^-@@`：其系数严格小于一，负部只落在 `@@M@@C@@` 与例外轨迹之上。留一个小丰富（ample）除子 `@@M@@A@@` 作缓冲；对给定 `@@M@@M@@` 取小 `@@M@@t>0@@` 使 `@@M@@A+tM@@` 丰富，用一般自由与丰富代表把正部充实成有效、大且 klt（Kawamata log terminal）的边界 `@@M@@\Delta_t@@`，满足 `@@M@@K_{Y'}+\Delta_t\sim_{\mathbb Q}\Psi^-+t\sigma^*M@@`，右端伪有效。BCHM 定理 D 给出实线性等价的有效代表；"有理恢复"引理（系数非负性是有限组有理线性不等式，非空有理多面体必有有理点）把结论升级为有理等价；推前后除以 `@@M@@t@@`，修正 `@@M@@\sigma_*\Psi^-/t@@` 的支集恰落在 `@@M@@C@@` 上。另有度量层面的扰动路线：Guan–Zhou 强开性加 Skoda 小指数可积性加 Hölder 不等式，允许对度量作小伪有效扰动而保持 `@@M@@s_C@@` 可积与严格下界。

定理二只用单个 Iitaka 纤维化（Iitaka fibration）。取 `@@M@@N_1@@` 的截断比值域，一切 `@@M@@N_j@@` 的除子沿一般纤维仿射变化（精确恒等式 `@@M@@\pi^*N_j=\pi^*N_0+(m_j-m_0)(\pi^*R+f^*Q_j)@@`），垂直最小值定义出基上除子 `@@M@@M@@`，由有效性取极限知其伪有效。反证法证伴随直像秩一：若秩更大，两个一般纤维无关的截断经扭曲后的比值既是基函数又不是，矛盾。极化等式给出 `@@M@@\pi^*L@@` 上支配 `@@M@@f^*\omega_Y@@` 的正电流度量，与光滑拉回度量小比例混合后，Skoda 定理保证全空间乘子理想平凡；Păun–Takayama 奇性直像正性在秩一壳 `@@M@@\mathcal O_Y(-K_Y+C)@@` 上给出整体严格曲率度量，且 `@@M@@\mathcal J\supset\mathcal O_Y(-C)@@`、`@@M@@f^*C@@` 例外。套定理一得 `@@M@@M+C_0\sim_{\mathbb Q}G\ge0@@`，返回引理把截断送回 `@@M@@X@@` 而不引入极点。张量版由行列式法与余切子丛伪有效性衔接。另一路线调用姊妹篇《Metric descent》的环面体积度量（文中引作 CompanionG）得到无权可积版本；光滑 coarea 路线则给出整除子修正与 `@@M@@L^{1+\eta}@@` 增强可积性。

## 可信度与备注

本文处于本族的分析—代数枢纽：它消费《Metric descent and rank-preserving contractions》的环面体积度量构造，其固定误差转化机制与《Cohomological transfer》的转移定理互为呼应；不变版本则依赖族内姊妹篇的不变指标定理与有限覆盖结构。全部结果暂无 Lean 形式化证明；按 OpenAI 官方声明，未经形式化的结果可能存在问题，结论请以社区核验为准。

{% endraw %}
