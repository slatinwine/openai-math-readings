---
layout: default
title: "A power saving for planar unit distances"
family: "167"
discipline: "Combinatorics"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | A power saving for planar unit distances

> 结果族 167：Planar distinct distances and unit-distance bounds　·　学科：Combinatorics　·　验证状态：暂无形式化证明，请以社区核验为准

## 入门导读 🐣

在广场上撒下 `@@M@@n@@` 个点，数一数"恰好相距 1"的点对最多能有多少对。这是 Erdős 1946 年提出的单位距离问题。四十多年来最好的围墙一直是 `@@M@@n^{4/3}@@`，无论怎么修修补补，指数都纹丝不动；这篇论文终于把指数真正砸下去了一块。

**关键词卡片**

- 单位距离（unit distance）：两点间距离恰好等于 1
- 幂改进（power saving）：存在固定 `@@M@@\delta>0@@` 使上界变成 `@@M@@Cn^{4/3-\delta}@@`，而不只是改良常数
- 点—圆关联（incidence）：把"两点相距 1"改看成"点落在另一个点画出的单位圆上"来计数
- 乘积公式（product formula）：数论工具，迫使坐标在所有"大小度量"之间互相制衡
- 实闭域转移（real closed field transfer）：把任意点集换成实代数数坐标，一切距离关系原样保留

**看个具体例子**

哪类点集最"高产"？三角格点：

<div>

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 560 280">
  <text x="280" y="28" text-anchor="middle" font-size="16" fill="#333">三角格点：单位距离的"高产农场"</text>
  <line x1="160" y1="90" x2="240" y2="90" stroke="#999" stroke-width="1"/>
  <line x1="240" y1="90" x2="320" y2="90" stroke="#999" stroke-width="1"/>
  <line x1="320" y1="90" x2="400" y2="90" stroke="#999" stroke-width="1"/>
  <line x1="200" y1="160" x2="280" y2="160" stroke="#999" stroke-width="1"/>
  <line x1="280" y1="160" x2="360" y2="160" stroke="#999" stroke-width="1"/>
  <line x1="360" y1="160" x2="440" y2="160" stroke="#999" stroke-width="1"/>
  <line x1="160" y1="230" x2="240" y2="230" stroke="#999" stroke-width="1"/>
  <line x1="240" y1="230" x2="320" y2="230" stroke="#999" stroke-width="1"/>
  <line x1="320" y1="230" x2="400" y2="230" stroke="#999" stroke-width="1"/>
  <line x1="160" y1="90" x2="200" y2="160" stroke="#999" stroke-width="1"/>
  <line x1="240" y1="90" x2="200" y2="160" stroke="#999" stroke-width="1"/>
  <line x1="240" y1="90" x2="280" y2="160" stroke="#999" stroke-width="1"/>
  <line x1="320" y1="90" x2="280" y2="160" stroke="#999" stroke-width="1"/>
  <line x1="320" y1="90" x2="360" y2="160" stroke="#999" stroke-width="1"/>
  <line x1="400" y1="90" x2="360" y2="160" stroke="#999" stroke-width="1"/>
  <line x1="400" y1="90" x2="440" y2="160" stroke="#999" stroke-width="1"/>
  <line x1="200" y1="160" x2="160" y2="230" stroke="#999" stroke-width="1"/>
  <line x1="200" y1="160" x2="240" y2="230" stroke="#999" stroke-width="1"/>
  <line x1="280" y1="160" x2="240" y2="230" stroke="#999" stroke-width="1"/>
  <line x1="280" y1="160" x2="320" y2="230" stroke="#999" stroke-width="1"/>
  <line x1="360" y1="160" x2="320" y2="230" stroke="#999" stroke-width="1"/>
  <line x1="360" y1="160" x2="400" y2="230" stroke="#999" stroke-width="1"/>
  <line x1="440" y1="160" x2="400" y2="230" stroke="#999" stroke-width="1"/>
  <line x1="280" y1="160" x2="200" y2="160" stroke="#c0392b" stroke-width="2.5"/>
  <line x1="280" y1="160" x2="360" y2="160" stroke="#c0392b" stroke-width="2.5"/>
  <line x1="280" y1="160" x2="240" y2="90" stroke="#c0392b" stroke-width="2.5"/>
  <line x1="280" y1="160" x2="320" y2="90" stroke="#c0392b" stroke-width="2.5"/>
  <line x1="280" y1="160" x2="240" y2="230" stroke="#c0392b" stroke-width="2.5"/>
  <line x1="280" y1="160" x2="320" y2="230" stroke="#c0392b" stroke-width="2.5"/>
  <circle cx="160" cy="90" r="4" fill="#333"/>
  <circle cx="240" cy="90" r="4" fill="#333"/>
  <circle cx="320" cy="90" r="4" fill="#333"/>
  <circle cx="400" cy="90" r="4" fill="#333"/>
  <circle cx="200" cy="160" r="4" fill="#333"/>
  <circle cx="360" cy="160" r="4" fill="#333"/>
  <circle cx="440" cy="160" r="4" fill="#333"/>
  <circle cx="160" cy="230" r="4" fill="#333"/>
  <circle cx="240" cy="230" r="4" fill="#333"/>
  <circle cx="320" cy="230" r="4" fill="#333"/>
  <circle cx="400" cy="230" r="4" fill="#333"/>
  <circle cx="280" cy="160" r="6" fill="#c0392b"/>
  <text x="280" y="266" text-anchor="middle" font-size="14" fill="#555">红点有 6 个恰好相距 1 的邻居（红边），灰色网格的边也全是单位长</text>
</svg>

</div>

三角格点中每个点有 6 个恰好相距 1 的邻居，`@@M@@n@@` 个点能造出约 `@@M@@n^{1+c/\log\log n}@@` 对——比线性还多一点，说明上界不可能压到 `@@M@@n@@` 以下（数域塔构造甚至给出 `@@M@@n^{1.014}@@`）。定理则从上面封顶：存在绝对常数 `@@M@@C@@` 与 `@@M@@\beta<4/3@@`，使任何 `@@M@@n@@` 点集的单位距离对数满足 `@@M@@u(n)\le Cn^{\beta}@@`。

**为什么值得关心**

组合几何最古老问题之一的四十年指数壁垒首次被打破；注意结论是定性的——只证固定缺口存在，不给 `@@M@@\delta@@` 的显式数值。

> 暂无形式化证明（AI 结果待核验）

## 一句话结论

证明了平面单位距离问题的幂改进：存在绝对常数 `@@M@@\beta<4/3@@`，使任何 `@@M@@n@@` 个点的平面点集至多确定 `@@M@@O(n^\beta)@@` 对单位距离——Spencer–Szemerédi–Trotter 保持四十余年的 `@@M@@n^{4/3}@@` 指数壁垒首次被打破。

## 问题背景

单位距离问题（unit-distance problem）是 Erdős 1946 年提出的另一经典：`@@M@@u(n)@@` 定义为 `@@M@@n@@` 点平面点集所能确定的单位距离对数 maximum。格点构形给出 `@@M@@n^{1+c/\log\log n}@@` 的下界；上界方面，Spencer、Szemerédi 与 Trotter 在 1984 年证得 `@@M@@u(n)=O(n^{4/3})@@`，Székely 随后给出交叉数（crossing number）证明。此后四十年人们只改进了前导常数、刻画了接近极值构形的结构，或在刚性猜想前提下得到对数级改进，指数 `@@M@@4/3@@` 始终无人撼动。另一侧，Erdős 曾猜想 `@@M@@u(n)=n^{1+o(1)}@@`，该猜想已被一项 OpenAI 构造否定——借助类群思想与 Golod–Shafarevich 数域塔给出至少 `@@M@@n^{1+\varepsilon}@@` 个单位距离，Sawin 又改进到 `@@M@@n^{1.014114}@@`。上界是否存在固定幂的缺口，遂成悬置核心，本文给出肯定回答。

## 主要结果

定理：存在绝对常数 `@@M@@C<\infty@@` 与 `@@M@@1\le\beta<4/3@@`，使得对一切 `@@M@@n@@` 与一切平面点集 `@@M@@X@@`，其单位距离对数不超过 `@@M@@Cn^\beta@@`；等价地 `@@M@@u(n)=O(n^{4/3-\delta})@@` 对某绝对 `@@M@@\delta>0@@` 成立，常数与构形无关。须强调：证明是存在性的，不给出 `@@M@@\beta@@` 或 `@@M@@\delta@@` 的显式数值，只证明固定缺口存在，与下界 `@@M@@n^{1.014114}@@` 之间仍留未定区间。

## 证明思路

反设无幂改进，沿反例序列令 `@@M@@t=n^{1/3}@@`，有序单位对数达 `@@M@@t^{4-o(1)}@@`，分六步导出矛盾。

先做关联归约。把点集复制为"点"与"单位圆心"两侧，有序单位对恰为点—圆关联（incidence）边；实闭域转移原理把坐标代数化。Clarkson 式随机切割（random cuttings）抽出度数受控、小顶点集抓不住多少边的关联图；再按度数边际选中心、取其两个独立邻居构成"楔"（wedge），并证楔两端点的互信息（相对熵）仅 `@@M@@o(\log t)@@`。

再做预测引理（prediction lemma）。给点编码的测试序列配"短历史"，从同历史点中重采样预测点，它保持原点边际；信息预算 `@@M@@o(\log t)@@` 保证可固定一个历史，使预测点在与整个实验独立的新测试（可依赖采样中心）上足够准确——Katz–Tardos 条件拷贝原理的新形态。

接着定义算术尺度。复坐标 `@@M@@z=x+\mathrm{i}y@@`、`@@M@@w=x-\mathrm{i}y@@` 下单位边跳变为 `@@M@@d@@` 与 `@@M@@d^{-1}@@`；在每个绝对值与阈值处记录比特，尺度 `@@M@@S@@` 度量对数跳变剖面随边变化的程度。若 `@@M@@S@@` 有界，乘积公式把控制转移到坐标高度（height）上：新的复嵌入中，量化测试给出与原点分离、却近似满足三个邻居单位方程的预测点，被一段行列式计算排除；故只剩 `@@M@@S\to\infty@@`。

然后把层级分为公共层（common levels）与稀有层（rare levels）。除 `@@M@@O(1)@@` 积分误差外，每条边恰有一个坐标标签一致且比特指明是哪个。对共享点或共享中心的两条边设得分，乘积公式给出积分预算；预测引理与初等几何给出公共层下界，稀有层项在两取向相加时抵消。结论：公共层对中心楔变化贡献可忽略，稀有层上残留正量的点例外质量。

再做高度加权提取。剩余质量提供大量楔端点对 `@@M@@(p,r)@@` 与中心 `@@M@@q@@`，其比率 `@@M@@\lambda_{pr}=(z_p-z_q)/(z_r-z_q)@@` 的对数近似为两端剖面之差，故完整矩形上交错乘积 `@@M@@\lambda_{pr}\lambda_{p'r'}/(\lambda_{pr'}\lambda_{p'r})@@` 高度可忽略。据此提取稠密图：单边比率高度 `@@M@@\ge J/3@@`（`@@M@@J\to\infty@@`）而矩形乘积高度 `@@M@@o(J)@@`；提取须按公共高度带进行，并删去同落热门单位圆（含 `@@M@@\ge t^{9/10}@@` 点）的对。

最后是代数障碍。用超积（ultraproduct）构造域，高度 `@@M@@o(J)@@` 的元素构成相对代数闭子域 `@@M@@k_0@@`：矩形乘积落入 `@@M@@k_0@@`，单个比率却在 `@@M@@k_0@@` 上超越。在平面或低次曲线上选位置 generic 的完整二部模式，对 `@@M@@k_0@@` 微分矩形关系，得到由 `@@M@@(z_p-z_r)(w_p-w_r)=2-\lambda-\lambda^{-1}@@` 派生的含根式方程组；对每个根式构造只在其上取奇值的赋值，使各平方根可独立变号，一个未用变号与微分方程矛盾；热门圆的排除补上平方类独立性失效的情形。

## 可信度与备注

本文主结果暂无形式化证明，按 OpenAI 官方声明"未经形式化的结果可能有问题"，请以社区核验为准。姊妹篇《The weak pinned planar distance theorem》主结果已 Lean 形式化，且与本文共享复坐标分解、乘积公式与实闭域转移的同一技术骨架，为本文路线提供旁证。另请注意结论是定性的：只证固定缺口存在，不给显式指数。

{% endraw %}
