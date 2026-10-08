---
layout: default
title: "The Euclidean Steinitz–Bergström theorem"
family: "097"
discipline: "Convex and metric geometry"
formalized: true
source: null
pdfname: ""
---

{% raw %}
# 解读 | The Euclidean Steinitz–Bergström theorem

> 结果族 097：The Euclidean Steinitz–Bergström bound　·　学科：Convex and metric geometry　·　验证状态：主结果已 Lean 形式化

## 入门导读 🐣

一场定向越野：教练按固定顺序喊出一串指令，每条指令是一段长度至多 1 的小步，但你可以自选"照走"或"反着走"。问：能否始终不远离起点？论文证明：在 `@@M@@d@@` 维空间里，无论指令有多少条，都存在一种选法，让你一直待在半径 `@@M@@C\sqrt d@@` 的球内——常数 `@@M@@C@@` 与指令条数完全无关。

**关键词卡片**

- 前缀和（prefix sum）：从第一条指令累加到当前的净位移。
- 符号选择（signing）：给每条指令配 `@@M@@\pm1@@` 的自由度。
- Steinitz 常数 `@@M@@S_2(d)@@`：`@@M@@d@@` 维欧氏空间里，最优重排下最坏部分和的最小可能上界。
- 正则单纯形（regular simplex）：`@@M@@d+1@@` 个两两等距的点，用来证明 `@@M@@\sqrt d@@` 的量级压不下去。

**看个具体例子**

**数字版定理**：`@@M@@\max_k\lVert\sum_{i\le k}\varepsilon_iv_i\rVert\le C\sqrt d@@`。它有多紧？取正则单纯形的顶点，任意 `@@M@@k@@` 个之和的平方范数为 `@@M@@k(d+1-k)/d@@`；取 `@@M@@k=\lfloor(d+1)/2\rfloor@@` 得至少 `@@M@@d/4@@`，即任何策略都免不了 `@@M@@\tfrac12\sqrt d@@` 的漂移。两面夹住：`@@M@@S_2(d)=\Theta(\sqrt d)@@`。排序版随之而来：若向量总和为零，还存在重排使不带符号的部分和也守在同一个 `@@M@@C\sqrt d@@` 圈内。

<div>

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 560 280">
  <circle cx="280" cy="140" r="95" fill="none" stroke="#e08030" stroke-width="2" stroke-dasharray="7 6"/>
  <polyline points="280,140 315,115 260,95 300,160 235,150 270,185 330,170 295,135 335,120 300,105" fill="none" stroke="#345" stroke-width="2.5"/>
  <circle cx="280" cy="140" r="3.5" fill="#222"/>
  <text x="230" y="34" font-size="14" fill="#123">安全圈半径 C√d</text>
  <text x="20" y="115" font-size="14" fill="#123">每步 ≤1，顺序固定，</text>
  <text x="20" y="137" font-size="14" fill="#123">任选 +vᵢ 或 −vᵢ</text>
  <text x="392" y="225" font-size="14" fill="#123">步数任意多</text>
  <text x="392" y="247" font-size="14" fill="#123">圈只随维度 d 变大</text>
</svg>

</div>

**为什么值得关心**

条件收敛级数重排问题的有限版本在欧氏空间就此闭环，`@@M@@\sqrt d@@` 这一量级早在 1954 年就被猜测；对偶的"规定次序选符号"问题也顺带去掉了界对序列长度的依赖——此前 Banaszczyk 的经典界还含 `@@M@@\sqrt{\log N}@@` 项。构造是存在性的：符号可以依赖整条序列来选，并非在线规则。

> 已 Lean 形式化

## 一句话结论

证明了欧氏单位球内任意有限向量列都存在一组符号，使全部带符号前缀和的范数不超过 `@@M@@C\sqrt d@@`（绝对常数 `@@M@@C@@` 与序列长度无关），进而解决 Steinitz–Bergström 猜想，将欧氏 Steinitz 常数确定为 `@@M@@S_2(d)=\Theta(\sqrt d)@@`。

## 问题背景

Steinitz 早年在研究条件收敛向量级数 (conditionally convergent series) 的重排时提出了有限重排问题：总和为零的单位球向量族，能否通过重排使所有部分和保持有界？对任意范数，Grinberg 与 Sevast'yanov 在 1980 年就证明了维度线性界 `@@M@@d@@`；而在欧氏空间，正确量级长期被预期为 `@@M@@\sqrt d@@`（Behrend 1954 年已讨论过这一增长），该猜想归于 Bergström，2026 年由 Ambrus 与 Heck 整理成现代表述。对偶的"规定次序选符号"问题上，Banaszczyk 的经典界 `@@M@@O(\sqrt d+\sqrt{\log N})@@` 依赖序列长度 `@@M@@N@@`；Dutta–Jha–Jiang（2026）改进为 `@@M@@O(\sqrt d+d^{1/4}\log^{7/4}N)@@`，长度项始终无法去掉。本文给出纯 `@@M@@C\sqrt d@@` 界，与长度彻底无关，两个问题同时闭环。

## 主要结果

**定理 1（规定次序的带符号前缀）**：存在绝对常数 `@@M@@C@@`，对任意 `@@M@@d,N\ge1@@` 及单位球中序列 `@@M@@v_1,\ldots,v_N\in\R^d@@`（`@@M@@\lVert v_i\rVert_2\le1@@`），可选符号 `@@M@@\varepsilon_i\in\{-1,1\}@@`，使
`@@M@@D\max_{0\le k\le N}\Bigl\lVert\sum_{i=1}^k\varepsilon_i v_i\Bigr\rVert_2\le C\sqrt d .@@`

**定理 2（欧氏 Steinitz–Bergström 界）**：若再设 `@@M@@\sum_{i=1}^N v_i=0@@`，则存在置换 `@@M@@\pi@@`，使全部不带符号的部分和满足同一个界：`@@M@@\max_{0\le k\le N}\lVert\sum_{i=1}^k v_{\pi(i)}\rVert_2\le C\sqrt d@@`。按最优重排定义的欧氏 Steinitz 常数 `@@M@@S_2(d)@@` 由此受控：`@@M@@S_2(d)\le C\sqrt d@@`。

量级无法改进：正则单纯形 (regular simplex) 顶点 `@@M@@u_i=\sqrt{\tfrac{d+1}{d}}\,(e_i-\tfrac{\mathbf 1}{d+1})@@` 两两内积为 `@@M@@-1/d@@`，任意 `@@M@@k@@` 个不同顶点之和的平方范数为 `@@M@@k(d+1-k)/d@@`，取 `@@M@@k=\lfloor(d+1)/2\rfloor@@` 时已至少 `@@M@@d/4@@`，故 `@@M@@\tfrac12\sqrt d\le S_2(d)@@`。推论还给出有限维 `@@M@@\ell_p@@` 情形的界 `@@M@@Cd^{\max\{1/p,\,1-1/p\}}@@`（当 `@@M@@1\le p\le2@@` 时阶 `@@M@@d^{1/p}@@` 最优），以及彩色行置换 (colorful row-permutation) 版本：多行数组各自置换行内元素，同步聚合的前缀和不超过 `@@M@@2C\sqrt d@@`。

## 证明思路

全文枢纽是把"带符号的随机游走"编码为高维系数空间 `@@M@@\R^{d+n}@@` 中一个凸体里的单个点，证明该凸体的 Dirichlet 能量 (Dirichlet energy) 一致地小，再援引"低能量凸体允许自适应选符号"的原理完成构造。

先建滤波 (filter)：取小绝对常数 `@@M@@\sigma@@`，令 `@@M@@b_i=\sigma v_i@@`，`@@M@@C_i=(I-b_ib_i^{\top})^{1/2}@@` 是满足 `@@M@@C_i^2+b_ib_i^{\top}=I@@` 的对称收缩，在系数空间上递推 `@@M@@R_tx=C_tR_{t-1}x+b_tx_{d+t}@@`。凸体 `@@M@@\mathcal D=\{x:\ |x_j|<B_0,\ \lVert R_tx\rVert_2<A_0\sqrt d\ \forall t\}@@` 就是"所有滤波状态受控"的点集。

再证能量命题：对一切正定对角矩阵 `@@M@@Q@@` 有 `@@M@@\lambda_Q(\mathcal D)\le H_0\operatorname{tr}Q@@`，常数与滤波步数 `@@M@@n@@` 无关。做法是让平稳 Ornstein–Uhlenbeck 过程在系数空间游走，把协方差矩阵 `@@M@@L_t=R_tQR_t^{\top}@@` 按二进谱尺度 `@@M@@\theta@@` 局部化。矩阵一节建立增量估计：把每步收缩的迹损失与增益记成可加能量 `@@M@@E_\theta(s,t)@@`，当 `@@M@@E\le e_0@@` 时滤波矩阵的 Hilbert–Schmidt 变差不超过 `@@M@@C(1+k_t)E^{2/3}@@`；难点是增益要穿过一串互不交换的收缩，文中用相对矩阵 `@@M@@S^{-1/2}V_*S^{-1/2}@@` 的 `@@M@@3/2@@` 次幂迹作势函数——收缩不增它、增益期间的导数由势 `@@M@@p_1@@` 支付——而两项总预算 `@@M@@\sum\ell_t,\sum g_t\le\operatorname{tr}Q@@` 均与序列长度无关。概率一节在每个尺度上按能量分组，用双参数（能量坐标＋OU 时间坐标）链法配合 Borell 集中不等式，证得"一个尺度、一段能量区间、长度 `@@M@@1/\theta@@` 时间内所有约束同时成立"的概率至少 `@@M@@1/2@@`；再用高斯相关不等式 (Gaussian correlation inequality) 把全部尺度、区间与坐标事件相乘，谱重构给出 `@@M@@\lVert R_tU\rVert\le c_1\sqrt{Cd}@@`，存活率随时间的指数不超过 `@@M@@C'\operatorname{tr}Q@@`，令 `@@M@@T\to\infty@@` 即得能量界。

最后选符号：核心命题断言，谱界 `@@M@@\lambda_Q(K)\le\kappa^2\operatorname{tr}Q@@` 的对称凸体允许带自适应移位（`@@M@@|q_i|\le\delta@@`，可依赖已选坐标）的符号选择。证明先以凸集分离取出各坐标能量都小的公共密度，再做提升的 Steiner 对称化 (Steiner symmetrization) 取切片：切片借 Minkowski 平均下 `@@M@@\lambda_Q@@` 的凸性与 Jensen 不等式保持谱界，且其每点竖直纤维长超过 2，故 `@@M@@q+1@@` 与 `@@M@@q-1@@` 必有一个落回 `@@M@@K@@`；于是倒向构造嵌套域、正向依次选符号。应用时在 `@@M@@2D_*\mathcal D@@` 上叠加"预测器"约束 `@@M@@|m_ix|<\delta@@`（`@@M@@m_ix=\eta_ib_i^{\top}R_{i-1}x@@`），精确的望远镜恒等式保证其每列范数平方不超过 `@@M@@\sigma^2@@`，附加能量被薄板 (slab) 引理吸收。取移位 `@@M@@q_i=m_ix^{(i-1)}@@`，终点落入 `@@M@@K@@` 说明截断从未激活，递推中预测项与收缩项精确相消：`@@M@@R_tx=\sigma\sum_{i\le t}\varepsilon_iv_i@@`——滤波状态恰是带符号部分和本身，除以 `@@M@@\sigma@@` 得常数 `@@M@@C=2D_*A_0/\sigma@@`。排序版再由 Chobanyan 传递原理 (transference principle) 一步导出：正号项按原序、负号项逆序拼接，新前缀和形如 `@@M@@(A_j+B_j)/2@@` 或 `@@M@@-(A_j-B_j)/2@@`，由 `@@M@@\beta@@` 的最优性立得 `@@M@@\beta\le C\sqrt d@@`。

## 可信度与备注

本文主结果已有 Lean 形式化证明，这是最硬的核验层；本批次结果族 097 仅此一篇手稿，其传递环节（Chobanyan 传递原理、Bárány 矩阵传递）衔接的均是已发表的经典结果，链条互相支撑。按 OpenAI 官方声明，未经形式化的结果可能有问题，定理 1、2 已有形式化背书，其余推论建议以社区核验为准。另有两点值得注意：构造是存在性的，符号选择可依赖整个输入序列，不提供在线规则或高效算法；符号选择方法改编自 Guo–Fang–Lu 2026，而后者在脚注中将证明归功于 Odin 自动 AI 研究代理。

{% endraw %}
