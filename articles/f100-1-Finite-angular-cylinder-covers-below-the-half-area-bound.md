---
layout: default
title: "Finite angular cylinder covers below the half-area bound"
family: "100"
discipline: "Convex and metric geometry"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | Finite angular cylinder covers below the half-area bound

> 结果族 100：Cylinder coverings below the half-area bound　·　学科：Convex and metric geometry　·　验证状态：暂无形式化证明，请以社区核验为准

## 入门导读 🐣

用木板盖住一件家具，木板总宽度至少得是家具的"最小宽度"——这是 Tarski 木板问题。三维换成无限长的圆柱管盖凸体，对应的猜想是：管子横截面的总面积至少是物体最薄影子面积的一半；正四面体上的两管方案恰好取等，看起来天衣无缝。本文说：不对——把管子掰得微微倾斜、再细分成一大把窄管，总面积能严格小于一半。

**关键词卡片**

- 圆柱覆盖（cylinder covering）：形如 `@@M@@B+\mathbb{R} u@@` 的无限长管子，底面 `@@M@@B@@` 位于与轴垂直的平面内。
- 最小正交投影面积（minimal orthogonal projection area）：凸体在所有方向的影子中最小的一块。
- 角度扇区（angular sector）：把三角底面细分的窄扇形，每个配自己的微倾轴线。
- 仿射不变性（affine invariance）：方向化成本比在线性变换下不变，反例自动推广到一切四面体。

**看个具体例子**

棱长 2 的正四面体：`@@M@@A_{\min}=\sqrt2\approx1.414@@`，半面积猜想要求总面积 `@@M@@\ge0.707@@`。本文构造 `@@M@@m=2\lceil2/\varepsilon^2\rceil@@` 个三角形底圆柱，总面积满足 `@@M@@\frac{1}{\sqrt2}\sum_i|B_i|=\frac12-\frac{13}{6000}\varepsilon^2+O(\varepsilon^4)@@`。取 `@@M@@\varepsilon=0.1@@`：约 400 根圆柱，节省约五万分之二——极小，但严格为正。

<div>

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 560 280">
  <path d="M 280 50 L 110 220 L 450 220 Z" fill="#f3f0e8" stroke="#345" stroke-width="2"/>
  <circle cx="280" cy="160" r="4" fill="#222"/>
  <line x1="280" y1="160" x2="172" y2="220" stroke="#89a" stroke-width="1"/>
  <line x1="280" y1="160" x2="226" y2="220" stroke="#89a" stroke-width="1"/>
  <line x1="280" y1="160" x2="280" y2="220" stroke="#89a" stroke-width="1"/>
  <line x1="280" y1="160" x2="334" y2="220" stroke="#89a" stroke-width="1"/>
  <line x1="280" y1="160" x2="388" y2="220" stroke="#89a" stroke-width="1"/>
  <line x1="222" y1="130" x2="262" y2="118" stroke="#c00" stroke-width="2"/>
  <line x1="262" y1="140" x2="300" y2="140" stroke="#c00" stroke-width="2"/>
  <line x1="308" y1="152" x2="344" y2="162" stroke="#c00" stroke-width="2"/>
  <line x1="238" y1="172" x2="268" y2="186" stroke="#c00" stroke-width="2"/>
  <line x1="300" y1="178" x2="322" y2="196" stroke="#c00" stroke-width="2"/>
  <text x="18" y="48" font-size="14" fill="#123">圆柱的三角形底面切成窄扇区</text>
  <text x="18" y="70" font-size="14" fill="#123">每个扇区配一根微倾的轴（红线）</text>
  <text x="18" y="248" font-size="14" fill="#123">相邻扇区在公共边界共面＝防缝</text>
  <text x="18" y="270" font-size="14" fill="#123">交界处用二阶小量外扩兜底</text>
</svg>

</div>

**为什么值得关心**

只需"严格小于"就足以推翻归于 Bang 的半面积猜想与更强的方向归一化版本；这也是该问题第一个完全显式的反例。

> 暂无形式化证明（AI 结果待核验）

## 一句话结论

本文为正四面体构造出有限个圆柱组成的覆盖，其垂直底面（均为紧三角形）的总面积严格小于该四面体最小正交投影面积（minimal orthogonal projection area）的一半，从而推翻归于 Bang 的半面积圆柱覆盖猜想，并经仿射不变性否定更强的方向归一化半界猜想。

## 问题背景

这个问题是 Tarski 木板问题（plank problem）的圆柱类比。Bang 在 1951 年证明凸体的有限木板覆盖的总宽度不小于其最小宽度，Ball 又对中心对称体给出按方向归一化的精化。在三维中把木板换成圆柱 `@@M@@C=B+\mathbb{R} u@@`（底面 `@@M@@B@@` 位于与轴垂直的平面内），Bezdek 与 Bezdek–Litvak 记录了归于 Bang 的问题：任何有限圆柱覆盖是否总有 `@@M@@\sum_i|B_i|\ge\tfrac12 A_{\min}(K)@@`？正四面体的两圆柱覆盖（两轴平行于一对对棱）恰好取等，暗示 `@@M@@\tfrac12@@` 可能是最优常数。Bezdek–Litvak 证明了方向化下界 `@@M@@\mathcal R\ge\tfrac13@@`（椭球体则 `@@M@@\ge1@@`），Bezdek–Khan 进一步提出 `@@M@@\mathcal R\ge\tfrac12@@` 的"1-余维圆柱覆盖猜想"（1-Codimensional Cylinder Covering Conjecture）；Verreault 的 2026 年综述仍把半面积问题列为未决。卡点在于：取等的例子看似刚性，没人知道能否扰动它以压低成本而不留缝隙。

## 主要结果

论文取棱长 `@@M@@2@@` 的正四面体 `@@M@@K@@`（顶点 `@@M@@(\pm1,0,0)@@`、`@@M@@(0,\pm1,H)@@`，`@@M@@H=\sqrt2@@`）。主定理断言：`@@M@@A_{\min}(K)=\sqrt2@@`，且对每个 `@@M@@0<\eps\le1/2000@@`，闭四面体 `@@M@@K@@` 容许由 `@@M@@m=2\lceil2/\eps^2\rceil@@` 个具紧三角形垂直底的圆柱覆盖，其总面积满足 `@@M@@\frac{1}{\sqrt2}\sum_i|B_i|=\frac12-\frac{13}{6000}\eps^2+O(\eps^4)@@`（余项绝对值至多 `@@M@@2\eps^4@@`），故严格小于 `@@M@@A_{\min}(K)/2@@`。推论：任何非退化四面体 `@@M@@T@@` 都容许有限覆盖使 `@@M@@\sum_i|B_i|/|\pi_{u_i^\perp}T|<\tfrac12@@`，即 1-余维圆柱覆盖猜想不成立；其证明是验证方向化比值在可逆仿射映射下不变（分子分母同乘 `@@M@@|\det L|@@`）。扩展章节还允许径向余量随倾角趋于零，得到规范化成本 `@@M@@\tfrac12-\tau^2/240+(25/2)\tau^3+O(\tau^4)@@`，覆盖对 `@@M@@0<\tau\le1@@` 成立，严格节省对 `@@M@@0<\tau\le1/4000@@` 成立。

## 证明思路

构造从 Bang 的等式覆盖出发：下半段 `@@M@@t\le1/2@@` 由平行 `@@M@@x@@` 轴的圆柱覆盖，上半段 `@@M@@t\ge1/2@@` 由平行 `@@M@@y@@` 轴的圆柱覆盖，两个底三角形面积各为 `@@M@@H/4@@`，总成本恰为 `@@M@@A_{\min}/2@@`。核心想法是把两个三角形底面按斜率参数 `@@M@@q@@` 细分成 `@@M@@n@@` 个窄的角度扇区（angular sector），给每个扇区配一条自己的微倾轴线 `@@M@@(1,\eps\alpha_j,H\eps\beta_j)@@`：倾斜使垂直底面乘上小于 `@@M@@1@@` 的投影因子 `@@M@@[1+\eps^2(\alpha_j^2+2\beta_j^2)]^{-1/2}@@`，从而省面积；但相邻扇区之间、两族之间可能开缝。防缝有两套机制。其一是共享边界匹配：规定边界位移 `@@M@@\phi(q)=(1-q^2)/4@@`，解端点方程 `@@M@@\alpha_j-q\beta_j=\phi(q)@@` 得 `@@M@@\alpha_j=(1+q_jq_{j+1})/4@@`、`@@M@@\beta_j=(q_j+q_{j+1})/4@@`，使相邻扇区的轴在公共侧边处张成同一平面。角度方向的覆盖用"首次跨越"论证：序列 `@@M@@F_i@@` 的首尾为 `@@M@@-t\le y\le t@@`，取第一个 `@@M@@F_i\ge y@@` 的指标即把 `@@M@@y@@` 夹住——全程不要求 `@@M@@F_i@@` 单调。其二是径向预算：在两族交界 `@@M@@t\approx1/2@@` 处，两个选定截面的径向高度一阶变化恰好相反（`@@M@@-\eps xy@@` 与 `@@M@@+\eps xy@@`，正源于 `@@M@@\beta_j\simeq q/2@@` 的选择），相加后只剩二阶项。于是把每个扇区径向外扩 `@@M@@\eps^2M_j@@`（`@@M@@M_j=\eta+\max d@@`，`@@M@@d(q)=q^2(1+q^2)/16@@`，`@@M@@\eta=1/1000@@`），再证两个选定圆柱不可能同时失效：否则径向预算恒等式导出 `@@M@@0>2\eta-(2+2\eta)\eps-\eps^2/4>0@@` 的矛盾，覆盖对闭四面体的每一点（含面、棱、顶点）成立。最后算账：对精确面积公式 `@@M@@S/H=\sum_j\Delta T_j^2[1+\eps^2(\alpha_j^2+2\beta_j^2)]^{-1/2}@@` 关于 `@@M@@z=\eps^2@@` 做一致 Taylor 展开（二阶导一致有界 `@@M@@59/64@@`），再把 Riemann 和换成积分——网格 `@@M@@\Delta\le\eps^2@@` 保证圆柱数目增长不侵蚀误差，总误差 `@@M@@O(\eps^4)@@`。积分值 `@@M@@\int d=1/15@@`、`@@M@@\int A=17/30@@` 给出 `@@M@@S/\sqrt2=\tfrac12+(2\eta-\tfrac1{240})\eps^2+O(\eps^4)@@`；代入 `@@M@@\eta=1/1000@@` 得负系数 `@@M@@-13/6000@@`，即外扩的面积代价小于倾斜的收益。最小投影面积本身由 Cauchy 投影公式的面积向量形式逐面验证。

## 可信度与备注

本文未形式化，主结果应以社区核验为准。它在结果族 100 中给出最直接、完全自足的显式构造：姊妹篇《Finite cylinder approximation of ruled sets》提供"连续线段族到有限圆柱"的抽象机器，《Slope-field perturbations of the two-cylinder covering》用斜率场给出独立的流场构造；本文零余量极限的二次系数 `@@M@@-1/240@@` 与后者平方零构造的系数一致，三篇互相印证同一否定结论。按 OpenAI 官方声明，未经形式化的结果可能有问题。

{% endraw %}
