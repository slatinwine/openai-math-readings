---
layout: default
title: "Maximal Seshadri Constants on Arbitrary Polarized Surfaces"
family: "039"
discipline: "Algebraic and complex geometry"
formalized: true
source: null
pdfname: ""
---

{% raw %}
# 解读 | Maximal Seshadri Constants on Arbitrary Polarized Surfaces

> 结果族 039：Nagata's conjecture and maximal Seshadri constants　·　学科：Algebraic and complex geometry　·　验证状态：主结果已 Lean 形式化

## 入门导读 🐣

把曲面想成一匹总能量为 `@@M@@L^2@@` 的布料：往上戳 `@@M@@r@@` 个点，每个点都会消耗布料的强度。定理说，只要点数够多、位置一般，每点恰好分到平均的能量份额，谁也占不到便宜——衡量剩余强度的 Seshadri 常数，不多不少正是 `@@M@@\sqrt{L^2/r}@@`。

**关键词卡片**

- Seshadri 常数（Seshadri constant）：曲线穿过这组点时，单位重数至少要付的"过路费"。
- 丰富线丛（ample line bundle）：能量随倍数增长的强光源系统。
- 体积上界（volume bound）：能量守恒给出的天花板 `@@M@@\sqrt{L^2/r}@@`。
- 爆开（blow-up）：在每个点架一座"收费站"（例外除子）的改造手术。
- 非常一般点组（very general points）：位于可数个特殊闭集之外的点组。

**看个具体例子**

取 `@@M@@S=\mathbb P^2@@`、`@@M@@L=\mathcal O(2)@@`：总能量 `@@M@@L^2=4@@`。戳 `@@M@@r=16@@` 个一般点，每点分到 `@@M@@4/16=1/4@@`，这块"小份额"的边长 `@@M@@\sqrt{1/4}=1/2@@` 正是 Seshadri 常数。即使点数不是平方数、各点重数参差不齐，均分规则照样成立。定理保证：存在只依赖 `@@M@@(S,L)@@` 的阈值 `@@M@@r_0@@`，此后每个整数点数都精确取到平均值——曲面上的定性 Nagata–Biran 猜想就此落定。此前的路各有缺口：辛几何的堆满稳定性不固定复结构，转移方法又要借助平面常数的极大性，本文绕开了这些依赖，对任意丰富极化直接证明。

<div>

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 560 280">
  <text x="280" y="30" text-anchor="middle" font-size="15" fill="#334455">布料均分图：P² 上 L = O(2)，r = 16 个点</text>
  <rect x="90" y="50" width="200" height="200" fill="#eef4fa" stroke="#4a90c4" stroke-width="2"/>
  <rect x="240" y="50" width="50" height="50" fill="#fde9d9" stroke="#d08030" stroke-width="1.5"/>
  <line x1="140" y1="50" x2="140" y2="250" stroke="#9db8d2" stroke-width="1"/>
  <line x1="190" y1="50" x2="190" y2="250" stroke="#9db8d2" stroke-width="1"/>
  <line x1="240" y1="50" x2="240" y2="250" stroke="#9db8d2" stroke-width="1"/>
  <line x1="90" y1="100" x2="290" y2="100" stroke="#9db8d2" stroke-width="1"/>
  <line x1="90" y1="150" x2="290" y2="150" stroke="#9db8d2" stroke-width="1"/>
  <line x1="90" y1="200" x2="290" y2="200" stroke="#9db8d2" stroke-width="1"/>
  <circle cx="265" cy="75" r="4" fill="#c0504d"/>
  <line x1="295" y1="75" x2="350" y2="75" stroke="#d08030" stroke-width="1.5"/>
  <text x="358" y="80" font-size="13" fill="#d08030">每格 = 1/4</text>
  <text x="358" y="105" font-size="13" fill="#d08030">边长 = 1/2 = ε</text>
  <text x="358" y="140" font-size="13" fill="#666666">总能量 L² = 4</text>
  <text x="358" y="165" font-size="13" fill="#666666">16 点各占一格</text>
  <text x="280" y="272" text-anchor="middle" font-size="13" fill="#666666">r ≥ r₀ 后，ε = √(L²/r) 精确成立</text>
</svg>

</div>

**为什么值得关心**

"多点正性"是研究截面、辛堆满与插值的基础量；取到最大值意味着这些曲面上不存在任何更刁钻的"抄近路"曲线。

> 已 Lean 形式化

## 一句话结论
对任意光滑整复射影曲面 `@@M@@S@@` 与丰富线丛 `@@M@@L@@`，本文证明当点数 `@@M@@r@@` 超过仅依赖 `@@M@@(S,L)@@` 的阈值后，`@@M@@r@@` 个非常一般点处的多点 Seshadri 常数恰等于体积上界 `@@M@@\sqrt{L^2/r}@@`，正面解决曲面上的定性 Nagata–Biran 猜想。

## 问题背景
多点 Seshadri 常数（multipoint Seshadri constant）`@@M@@\varepsilon(S,L;\mathbf p)=\inf_C L\cdot C/\sum_i \mathrm{mult}_{p_i}C@@` 度量丰富线丛（ample line bundle）在一组点处的局部正性；等价地，它是使爆炸曲面上 `@@M@@\pi^*L-\lambda\sum_i E_i@@` 为 nef（与每条积分曲线交非负）的最大 `@@M@@\lambda@@`。jet 计数给出万有上界 `@@M@@\sqrt{L^2/r}@@`，定性 Nagata–Biran(-Szemberg) 猜想断言：`@@M@@r@@` 充分大时等式在非常一般点组处成立。此前进展各有缺口：Biran 的辛堆满稳定性（symplectic packing stability，1999）不固定复结构，不是代数陈述；Harbourne 的极大性限于 `@@M@@rL^2@@` 为平方数（且需很丰富性假设）；Roé 的转移方法与 Biran–Roé–Ross 乘积不等式均须借助相应平面常数的极大性。本文对任意丰富极化与阈值之后的全部整数 `@@M@@r@@` 直接给出证明。

## 主要结果
主定理：对每对 `@@M@@(S,L)@@` 存在整数 `@@M@@r_0=r_0(S,L)@@`，使得对每个 `@@M@@r\ge r_0@@`，在非常一般点组（即可数个真 Zariski 闭子集之外、余集非空）处，实除子类 `@@M@@\pi^*L-\sqrt{L^2/r}\sum_i E_i@@` 在爆炸曲面上是 nef 的，从而 `@@M@@\varepsilon(S,L;\mathbf p)=\sqrt{L^2/r}@@`。推论将结论推广到不可数、特征为零的代数闭域。由于结论落在自交为零的 nef 边界类上，它排除了一切"次数与总重数之比低于该数值界"的曲线，包括重数不等的情形。

## 证明思路
全文把问题转化为代数环面 `@@M@@\mathbb T=(\mathbb C^*)^2@@` 上的有限插值：目标是证明对所有满足 `@@M@@m\gt k\sqrt{H/r}@@`（`@@M@@H=L^2@@`）的正整数 `@@M@@k,m@@`，`@@M@@kL@@` 的截面在某组 `@@M@@r@@` 个不同点处通过 `@@M@@m@@` 阶单射 jet 测试——即只有零截面能在全部测试点消失到阶 `@@M@@\ge m@@`。与 Alexander–Hirschowitz 渐近后置化定理不同，这里的阈值 `@@M@@r_0@@` 必须对任意大的 jet 阶统一生效，这是新的困难点。

先建立传递机制：满秩的初始 Taylor 单项式 jet 矩阵在充分小的解析重标度下保持满秩；取一个带普通结点（node）的除子 `@@M@@V\in|dL|@@`，其两分支局部即坐标轴，在权 `@@M@@(1,t)@@` 下截面的最小 Taylor 指数落入四边形 `@@M@@kQ_t@@` 内；再作环面坐标替换并沿 `@@M@@(1,1)@@` 方向压缩切片，得到面积 `@@M@@k^2H/2@@` 的三角形 `@@M@@kP_t@@`。两级传递依次作用，便把三角形上的环面测试送回曲面截面。

核心是三角形的连续变形与有限子群测试：`@@M@@P_t@@` 的面积恒为 `@@M@@H/2@@`，令 `@@M@@t@@` 连续变动，可为每个充分大的 `@@M@@r@@` 调整形状，使某个本原格向量（primitive lattice vector）`@@M@@u@@` 上行列式投影的长度恰为 `@@M@@\sqrt{rH}@@`；取指标为 `@@M@@r@@` 的子格，其特征子群 `@@M@@G\subset\mathbb T@@` 恰有 `@@M@@r@@` 个点（在坐标下即 `@@M@@X=1,Y^r=1@@`，不必是方格）。若非零 Laurent 多项式在 `@@M@@G@@` 上处处消失到阶 `@@M@@\ge m@@`，对 `@@M@@G@@` 取平均将其分解为陪集分量，每个分量的支撑落在面积 `@@M@@(kw)^2/2@@`、竖直范围 `@@M@@kw@@`（`@@M@@w=\sqrt{H/r}@@`）的三角形内；三角形重数引理——按水平切片长度论证并提取 `@@M@@(U-1)^e@@` 因子——给出它在单位元处的阶 `@@M@@\le kw\lt m@@`，矛盾。故环面测试单射，且 `@@M@@t@@` 与 `@@M@@G@@` 在选定 `@@M@@k,m@@` 之前固定。

最后组装：单射性是 Zariski 开条件，可数多个测试由 Baire 纲论证在某非常一般点组同时成立。再从齐次 jet 过渡到 nef：若 `@@M@@D_0=\pi^*L-w\sum_i E_i@@` 非 nef，则有曲线 `@@M@@C@@` 使 `@@M@@D_0\cdot C\lt 0@@`；减去小 `@@M@@\delta C@@`、并把 `@@M@@w@@` 微扰为略大的有理数 `@@M@@s@@`，得 `@@M@@D^2\gt 0@@` 且 `@@M@@\pi^*L\cdot D\gt 0@@`，由 Riemann–Roch 与 Serre 对偶使 `@@M@@kD@@` 的倍数有效，加回 `@@M@@k\delta C@@` 便得到 `@@M@@kL@@` 的截面在所有点消失到阶 `@@M@@m=ks\gt kw@@`，与测试矛盾。反向的上界 `@@M@@\sqrt{H/r}@@` 由初等 jet 计数给出，两界合并即得定理。

## 可信度与备注
本文主结果已由 Lean 形式化证明。族内姊妹篇互相支撑：平面篇把阈值精确到 `@@M@@r\ge 10@@` 并处理任意非齐次重数，本文引言将其引用为独立的精细化；高维篇沿用本文的"结点指数界 + 本原方向"机制推广到 `@@M@@n\ge 3@@` 维（改用满射 jet 评估，且不以本文定理为输入）；据族概述，该族还包含正特征版本的对应结果。按 OpenAI 官方声明，未经形式化的结果可能有问题；本文已形式化。

{% endraw %}
