---
layout: default
title: "Compatibility entropy and the spectrum of a Thorp sweep"
family: "238"
discipline: "Probability and statistical mechanics"
formalized: true
source: null
pdfname: ""
---

{% raw %}
# 解读 | Compatibility entropy and the spectrum of a Thorp sweep

> 结果族 238：Optimal logarithmic mixing of the Thorp shuffle　·　学科：Probability and statistical mechanics　·　验证状态：主结果已 Lean 形式化

## 入门导读 🐣

让两批人换座位：先每排内部换一轮，再每列内部换一轮。什么时候"先排后列"和"先列后排"结果一样？这个排座位式的小问题，恰好卡住了 Thorp 洗牌的速度上限；论文用"相容性＋熵"把这本账算清，还顺带给一次扫掠开出了完整的"体检单"。

**关键词卡片**

- 相容（compatible）：行置换与列置换满足"先行后列＝先列后行"，等价于每个原列送出的牌两两不同
- 熵亏（entropy deficit）：一组随机量的混乱度离完全均匀还差多少（信息论里以奈特计）
- 奇异值（singular value）：算子拉伸能力的排行榜；榜单衰减越快，说明洗牌收缩越狠
- 正则表示（regular representation）：全部置换打包的大空间，每种成分按维数复制出现
- 混合时间（mixing time）：洗到与均匀分布无法区分的步数，本文证明为 `@@M@@\Theta(\log n)@@`

**看个具体例子**

把 `@@M@@n=2^d@@` 个位置对半分成近 `@@M@@\sqrt n\times\sqrt n@@` 的棋盘后，一次扫掠＝行扫乘列扫。核心不等式说：限制在相容事件上的任何联合律，相对熵至少有 `@@M@@n-O(n^{0.54})@@`——几乎"满熵"，行列两半因此近乎独立。数字版结论：存在绝对常数 `@@M@@p_*@@`，使 `@@M@@M\ge p_*@@` 次独立扫掠后最坏起点的全变差 `@@M@@\le 1/8@@`；而且正则奇异值谱满足 `@@M@@s_j\le j^{-1/(2p_*)}@@`，幂律衰减（下图）。

<div>

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 560 280">
  <text x="280" y="24" text-anchor="middle" font-size="15">一次扫掠的"体检单"：奇异值谱</text>
  <line x1="75" y1="45" x2="75" y2="235" stroke="#333" stroke-width="1.5"/>
  <line x1="75" y1="235" x2="515" y2="235" stroke="#333" stroke-width="1.5"/>
  <rect x="95" y="65" width="30" height="170" fill="#cfe3ff" stroke="#333"/>
  <rect x="139" y="115" width="30" height="120" fill="#cfe3ff" stroke="#333"/>
  <rect x="183" y="137" width="30" height="98" fill="#cfe3ff" stroke="#333"/>
  <rect x="227" y="150" width="30" height="85" fill="#cfe3ff" stroke="#333"/>
  <rect x="271" y="159" width="30" height="76" fill="#cfe3ff" stroke="#333"/>
  <rect x="315" y="166" width="30" height="69" fill="#cfe3ff" stroke="#333"/>
  <rect x="359" y="171" width="30" height="64" fill="#cfe3ff" stroke="#333"/>
  <rect x="403" y="175" width="30" height="60" fill="#cfe3ff" stroke="#333"/>
  <polyline points="110,65 154,115 198,137 242,150 286,159 330,166 374,171 418,175" fill="none" stroke="#d62728" stroke-width="2" stroke-dasharray="7 5"/>
  <text x="95" y="38" font-size="13">奇异值大小</text>
  <text x="330" y="105" text-anchor="middle" font-size="14" fill="#d62728">幂律衰减：s_j ≤ j^(−1/(2p_*))</text>
  <text x="110" y="254" text-anchor="middle" font-size="12">s₁</text>
  <text x="154" y="254" text-anchor="middle" font-size="12">s₂</text>
  <text x="198" y="254" text-anchor="middle" font-size="12">s₃</text>
  <text x="242" y="254" text-anchor="middle" font-size="12">s₄</text>
  <text x="286" y="254" text-anchor="middle" font-size="12">s₅</text>
  <text x="330" y="254" text-anchor="middle" font-size="12">s₆</text>
  <text x="374" y="254" text-anchor="middle" font-size="12">s₇</text>
  <text x="418" y="254" text-anchor="middle" font-size="12">s₈</text>
  <text x="295" y="273" text-anchor="middle" font-size="13">第 j 个奇异值（按从大到小排序）</text>
</svg>

</div>

**为什么值得关心**

它不只算出最优混合时间，还完整刻画了一次扫掠的奇异值谱——相当于给洗牌算子做了全谱"体检"，且主结果已被机器验证。

> 已 Lean 形式化

## 一句话结论

本文证明：`@@M@@n=2^d@@` 张牌的 Thorp 洗牌（Thorp shuffle）在 `@@M@@\Theta(d)@@`（即 `@@M@@\Theta(\log n)@@`）次物理洗牌内完成整副排列的全变差（total variation）混合，匹配支集计数下界 `@@M@@2d-O(1)@@`；更强地，它完全刻画了一次扫掠的奇异值谱：正则表示中第 `@@M@@j@@` 个奇异值不超过 `@@M@@j^{-1/(2p_*)}@@`。

## 问题背景

Thorp 1973 年研究 Faro 纸牌的非完美洗牌时提出该模型：位置编号为 `@@M@@\{0,1\}^d@@`，一次坐标扫掠（coordinate sweep）依次访问各坐标方向，独立地以概率 `@@M@@1/2@@` 交换该方向每条边上的两张牌，恰等于 `@@M@@d@@` 次物理洗牌。一次扫掠用 `@@M@@nd/2@@` 个随机比特，已足以让每张牌的边缘分布均匀，但与均匀排列的熵 `@@M@@\log_2(n!)@@` 相比远远不够，`@@M@@t@@` 次物理洗牌支集至多 `@@M@@2^{tn/2}@@`，给出下界 `@@M@@2d-O(1)@@`——单牌均匀与整副混合之间横亘着"共用开关"带来的强相关。全牌混合的前沿记录依次是 Morris 的 `@@M@@O(d^{44})@@`、Montenegro–Tetali 的 `@@M@@O(d^{29})@@`、Morris 熵收缩的 `@@M@@O(\log^4 n)@@` 与 `@@M@@O(d^3)@@`；Czumaj–Vöcking 的 `@@M@@O(\log^2 n)@@` 只针对固定比例的牌。本文以"一次扫掠的整个奇异值谱"为对象给出 `@@M@@\Theta(d)@@` 的最优答案。

## 主要结果

把坐标对半 split 成 `@@M@@A\times D@@` 棋盘（`@@M@@AD=n@@`，两边均近 `@@M@@\sqrt n@@`），行、列子群 `@@M@@R,C@@` 的元素对 `@@M@@(r,c)@@` 称为**相容**（compatible），如果"先行后列"复合也能写成"先列后行"——等价于每个原始列中的输出两两不同。第一主定理（加权相容性）：对任意非负权 `@@M@@w_i,v_k@@`，在 `@@M@@\theta=1-L/\log m@@` 下
`@@M@@D\frac{n!}{|R||C|}\,\mathbb E_U\Big[\mathbf 1_{\mathcal I}\prod_iw_i(r_i)\prod_kv_k(c_k)\Big]\le e^{C_0n^{.54}}\prod_i(\mathbb E w_i^{1/\theta})^\theta\prod_k(\mathbb E v_k^{1/\theta})^\theta .@@`
第二主定理（有界正则矩）：存在绝对 `@@M@@p_*@@` 使每个二的幂次 `@@M@@n@@` 均有 `@@M@@Z_n(p_*)=\operatorname{Tr}_{\rm reg}(T_n^*T_n)^{p_*}\le 1+\tfrac1{16}@@`；从而任取整数 `@@M@@M\ge p_*@@`，`@@M@@M@@` 次独立扫掠后最坏起点全变差 `@@M@@\le 1/8@@`。推论给出奇值秩界 `@@M@@s_r(T_{n,\lambda})\le(16D_\lambda r)^{-1/(2p_*)}@@`、正则奇值列表 `@@M@@s_j(T_n)\le j^{-1/(2p_*)}@@`，以及混合时间 `@@M@@\Theta(d)@@`、下界 `@@M@@2d-O(1)@@`；且对每个固定 `@@M@@M>p_*@@`，`@@M@@Md@@` 次物理洗牌后的误差随 `@@M@@d\to\infty@@` 趋于零。

## 证明思路

首个完整证明分四步。先用"稀疏路径二阶矩"处理第一行极长的表示（`@@M@@1\le h=n-\lambda_1\le n^{.60}@@`，此时 `@@M@@\|T_{n,\lambda}\|\le n^{-bh}@@`）：在有序 `@@M@@h@@` 元组表示上做容斥 `@@M@@F=\sum_I(-1)^{h-|I|}D_I@@`，孤立牌的路径组消后归零，存活构形必含一棵相互作用森林；每条森林边的碰撞概率为 `@@M@@2l/n@@`，而蝴蝶接触引理（`@@M@@s@@` 条路径共享开关数 `@@M@@\le\tfrac s2\log_2s@@`，文中亦给熵证明）钉死剩余密度因子，得 `@@M@@n^{-h/50}@@` 级二阶矩。第二步是核心的相容熵不等式：在支集含于相容事件 `@@M@@\mathcal I@@` 的任意联合律 `@@M@@Q@@` 下，`@@M@@\mathcal D(Q\|U_{R\times C})\ge n-O(n^{.54})+(1-\tfrac L{\log m})\sum(\text{行、列边缘熵亏})@@`。证明用随机顺序暴露：先亮出行数组，再按随机优先级逐列、逐位暴露列置换；轻的、未结块的表项因先前暴露的列已禁止取值而各付近一奈特（对 `@@M@@-\log(1-x+x\alpha)@@` 积分加 Jensen），重原子与结块表项的损失计入相应边缘相对熵。第三步，经 Carlen–Cordero-Erausquin 的有限熵–Brascamp–Lieb 对偶把熵不等式变成上述加权乘积不等式，其 `@@M@@-n@@` 主项恰与换序归一化 `@@M@@n!/|R||C|\approx e^n@@` 对消。最后是谱转换：`@@M@@T_n=K_CK_R@@`，Araki–Lieb–Thirring 型正幂比较把 `@@M@@\operatorname{Tr}(T_n^*T_n)^t@@` 化为四个行、列因子的交替迹，代数引理（四因子迹恒等式加对合的 Cauchy–Schwarz）把它精确写成带权的相容概率，再由逆 Hausdorff–Young 不等式用子扫掠的矩 `@@M@@Z_A,Z_D@@` 控制行、线权，得到递归 `@@M@@Z_n(t)\le\exp(O(n^{.54}))@@`（`@@M@@t=p(1+L'/\log m)@@`）。收尾时把表示分两类：小层由森林估计吸收（`@@M@@D_\lambda\le n^{2h}@@`）；大维块 `@@M@@D_\lambda\ge e^{n^{.58}}@@` 在正则表示中带 `@@M@@D_\lambda@@` 重复副本，指数再升 `@@M@@\delta=1/\log m@@` 即被乘性放大消灭；有限小尺寸用严格谱隙（立方体边对换生成整个 `@@M@@S_n@@`）作基，指数增量沿二分递归求积有界，得一致 `@@M@@p_*@@`。混合结论由矩–秩转换与 Schatten–Hölder 给出，全程不需算子正规性。第 4 节之后给出多种替代证明与细化（条件秩、反色可用性、倾斜数组、分数可积、非对称棋盘、水平递归、奇异带、逐点平滑等）。

## 可信度与备注

本篇主结果已有 Lean 形式化证明（见结果族 238 的 Lean 文档），是该数学事实目前最强的机器验证背书；同族另两篇（加权路线与随机子平面路线）以独立技术得到同一 `@@M@@\Theta(d)@@` 结论，与本文的熵–对偶路线交叉印证，且本文的稀疏估计与姊妹篇《Routing densities》的确定性接触引理互相衔接。按 OpenAI 官方声明，未经形式化的结果可能有问题；本篇形式化部分除外，其余细化估计仍请以社区核验为准。

{% endraw %}
