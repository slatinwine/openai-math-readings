---
layout: default
title: "Conditional coordinate sweeps and analytic transfer"
family: "238"
discipline: "Probability and statistical mechanics"
formalized: true
source: null
pdfname: ""
---

{% raw %}
# 解读 | Conditional coordinate sweeps and analytic transfer

> 结果族 238：Optimal logarithmic mixing of the Thorp shuffle　·　学科：Probability and statistical mechanics　·　验证状态：主结果已 Lean 形式化

## 入门导读 🐣

证明洗牌快，有种套路是"先剧透再看"：先亮出几张牌各自怎么走，再检查剩下的随机安排像不像均匀。麻烦在于剧透会改变剩余部分的概率——这篇论文把这笔"剧透税"精确入账，再用复分析的最大值原理，把好估计从一个人造模型"搬运"到真正的 Thorp 洗牌。

**关键词卡片**

- 条件扫掠（conditional sweep）：先固定部分牌的行走路线（剧透），再估计剩下的随机对应表
- 无放回修正（falling-factorial correction）：不许重复地指定 `@@M@@u@@` 个座位的组合账单 `@@M@@(m)_u=m(m-1)\cdots@@`，剧透越多账越贵
- Schatten 矩（Schatten moment）：算子幂的迹，统一度量洗牌算子的收缩强度
- 次调和最大值原理（subharmonic maximum principle）：复变工具——边界上不超标，内部就处处不超标
- 解析转移（analytic transfer）：沿复平面把"掺混模型"上的好估计搬到目标模型

**看个具体例子**

剧透税有多便宜？在一条 `@@M@@m=64@@` 的线上指定 `@@M@@u=3@@` 张牌的落点，代价 `@@M@@C=\ln\frac{64^3}{64\cdot63\cdot62}\approx0.047@@`——只多付约 5%。再看搬运：把扫掠掺进参数 `@@M@@z@@`（`@@M@@z=0@@` 是均匀线律、好证，`@@M@@z=1@@` 是二进制真扫掠、要证的目标），矩阵系数 `@@M@@f(z)@@` 在 `@@M@@z=0@@` 附近有维数节省、在某个圆周上范数 `@@M@@\le1@@`；在挖去实轴一线段的圆盘上对 `@@M@@\log|f|@@` 用最大值原理，节省便搬到 `@@M@@z=1@@`。结论：`@@M@@\|K_\lambda\|_{\rm op}\le D_\lambda^{-g}@@`，固定次数扫掠后全变差趋于零，`@@M@@t_{\rm mix}=\Theta(d)@@`。

<div>

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 560 280">
  <text x="280" y="26" text-anchor="middle" font-size="15">挖去一线段的圆盘：用最大值原理搬运估计</text>
  <line x1="55" y1="150" x2="505" y2="150" stroke="#bbb" stroke-width="1"/>
  <line x1="280" y1="35" x2="280" y2="265" stroke="#bbb" stroke-width="1"/>
  <circle cx="280" cy="150" r="95" fill="none" stroke="#333" stroke-width="2"/>
  <line x1="240" y1="150" x2="330" y2="150" stroke="#d62728" stroke-width="6" stroke-linecap="round"/>
  <circle cx="240" cy="150" r="4" fill="#d62728"/>
  <circle cx="330" cy="150" r="4" fill="#d62728"/>
  <text x="233" y="170" text-anchor="middle" font-size="13">u</text>
  <text x="326" y="170" text-anchor="middle" font-size="13">v</text>
  <text x="250" y="140" text-anchor="middle" font-size="12" fill="#555">0</text>
  <text x="318" y="140" text-anchor="middle" font-size="12" fill="#555">1</text>
  <text x="120" y="95" font-size="13" fill="#1f77b4">z=0：掺均匀，好证</text>
  <text x="360" y="210" font-size="13" fill="#d62728">z=1：真洗牌</text>
  <text x="280" y="110" text-anchor="middle" font-size="12" fill="#555">边界不超标 ⇒ 内部处处不超标</text>
</svg>

</div>

**为什么值得关心**

"条件矩＋复分析搬运"的组合拳是本族被机器验证的骨干路线，也成为伙伴论文反复借用的证明模板。

> 已 Lean 形式化

## 一句话结论

本文先对"给定了部分牌轨迹"的条件坐标扫掠证明一个普适的 Schatten 矩估计，再用次调和最大值原理（subharmonic maximum principle）把近均匀线律下的收缩解析转移到二进制扫掠，证明固定次数扫掠即可混合 `@@M@@2^d@@` 张牌的 Thorp 洗牌，混合时间 `@@M@@O(d)@@` 与支撑下界同阶。

## 问题背景

Thorp 洗牌把 `@@M@@N=2^d@@` 张牌按二进制位置配对、独立掷币交换；剥离确定性坐标旋转后，一次坐标扫掠（coordinate sweep）恰是 `@@M@@d@@` 次物理洗牌。混合时间问题此前卡在 Morris 的 `@@M@@O(d^3)@@` 物理洗牌（更早有 `@@M@@O(d^{44})@@`、`@@M@@O(d^{29})@@`、`@@M@@O((\log N)^4)@@`），而硬币串计数只给出下界 `@@M@@2d-O(1)@@`。以往的分析——Morris 的变色龙过程与熵收缩、Morris–Rogaway–Stegers 与 Czumaj–Vöcking 对部分牌的研究——都靠"揭示牌的运动信息"来组织证明，但揭示路径会改变剩余选择的概率律。本文的关键是控制揭示路径之后剩下的整个随机双射（bijection），并精确支付"无放回地指定位置"的费用，使估计在证明过程中反复揭示更多路径时保持稳定。

## 主要结果

论文的二元结论是：存在绝对常数 `@@M@@g>0@@` 与 `@@M@@d_0@@`，使对一切 `@@M@@d\ge d_0@@` 与 `@@M@@\lambda\vdash 2^d@@`，扫掠算子在不可约表示（irreducible representation）中的 Fourier 系数满足 `@@M@@\|K_\lambda\|_{\op}\le D_\lambda^{-g}@@`，且 sign 表示被完全消灭；于是存在绝对正整数 `@@M@@w@@`，使 `@@M@@w@@` 次独立扫掠后与均匀律的全变差距离对一切确定性初始牌序一致趋于零。配合支撑障碍 `@@M@@\|q_d^{*t}-U_N\|_{\TV}\ge1-2^{tN/2}/N!@@`（`@@M@@t@@` 次物理洗牌只有 `@@M@@2^{tN/2}@@` 个硬币串），得 `@@M@@t_{\rm mix}(d)=\Theta(d)@@`。核心输入是条件定理：对线尺寸取自固定区间 `@@M@@[R,R^2]@@` 内 2 的幂、线律为混合 `@@M@@(1-z)U_m+zB_m@@` 的有序扫掠网格，对任何可行的指定轨迹族 `@@M@@\mathcal H@@`，剩余随机双射在每个不可约表示中的 Schatten 矩都有一致界，界含三项：正比于 `@@M@@\log D_\lambda@@` 的负项、指定牌数的容许项，以及无放回修正 `@@M@@C(\mathcal H)=\sum\log\bigl(m^u/(m)_u\bigr)@@`，其中 `@@M@@(m)_u@@` 是下降阶乘（falling factorial）。

## 证明思路

证明分四大步。第一步证条件定理的稀疏层：对只在跟踪少数牌时才首次出现的表示类型，把放置概率对其子集交错求和，使任何与其余轨迹不共享阶段线的被跟踪路径相消；坐标很多时用有根森林计数说明"所有被跟踪路径都共享某条线"概率很小；坐标数有界时线更长、此计数失效，改在 `@@M@@z=0@@` 处用逆伽马矩恒等式把下降阶乘比写成期望，把共享同一条线的粒子分组后再取矩；固定 `@@M@@R@@` 后只剩有限多个网格，用连续性把估计延拓到一个共同的小实区间。第二步处理大维数的钩型：把坐标分成两块、把网格看成矩形，第一块在行内扫、第二块在列内扫；在带号张量表示中，每个行或列同型投影（isotypic projection）被"迹为一的正定矩阵的张量幂的概率混合"的受控倍数控制；对所选行矩阵取平均得到一个迹一参考矩阵，用以界定行、列投影在自由格上的重叠；子矩估计恰好抵消该重叠中子群维数的成本，给出全钩型的更强估计。第三步是"增广路径"：当附加放置把 `@@M@@\mathcal H@@` 增广为 `@@M@@\mathcal H^+@@` 时，用差值 `@@M@@C(\mathcal H^+)-C(\mathcal H)@@` 控制其转移概率；分支法则把杨图（Young diagram）去框的实现记录为这种放置，循环迹展开与 Hölder 不等式把原始的 `@@M@@-C(\mathcal H)@@` 收回来，因此归纳必须对所有条件律同时成立。最后是解析转移：令 `@@M@@\mathcal H=\varnothing@@`，无条件扫掠算子是 `@@M@@z@@` 的矩阵多项式，在实区间 `@@M@@[0,z_*]@@` 上有维数节省 `@@M@@D_\lambda^{-a_0}@@`；另一方面，二进制线平均在非平凡不可约表示中有严格小于一的谱隙（立方体的边对换生成整个对称群），故在半径 `@@M@@r>1@@` 的圆盘上算子范数不超过一。在去掉实线段 `@@M@@[u,v]@@` 的圆盘上构造对数位势型的调和障碍 `@@M@@G@@`，对每个矩阵系数 `@@M@@f(z)@@` 使用 `@@M@@\log|f|@@` 的次调和性与边界最大值原理，把维数节省搬到 `@@M@@z=1@@`，即二进制扫掠本身。收尾用 Diaconis–Shahshahani 有限群 Fourier 分析，按 `@@M@@k(\lambda)=\min(N-\lambda_1,N-\lambda'_1)@@` 分层、配合维数下界与划分计数控制求和，得到全变差收敛。

## 可信度与备注

本篇在任务元数据中被标注为主结果已有 Lean 形式化证明，是结果族 238 中可信度最高的一条路线。两篇姊妹篇分别用带号张量熵预算与四行 permanent 不等式独立导出同一 `@@M@@\Theta(d)@@` 混合阶，三种机制互相印证。即便如此，完整证明中的条件矩估计与解析转移细节，仍建议对照 Lean 形式化文档与社区核验来阅读。

{% endraw %}
