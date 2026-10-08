---
layout: default
title: "Invariant anticanonical indices and conversion of twisted differentials"
family: "068"
discipline: "Algebraic and complex geometry"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | Invariant anticanonical indices and conversion of twisted differentials

> 结果族 068：Anticanonical nonvanishing in every dimension　·　学科：Algebraic and complex geometry　·　验证状态：暂无形式化证明，请以社区核验为准

## 入门导读 🐣

想象你在数一栋大楼每层楼的窗户：楼层越高窗户越多，而且增长严格有规律，像能写出公式的那种。这篇论文就是在数"对称图形"——在高维复空间上数"转完之后保持不变"的几何对象，证明这个数目随尺寸严格按多项式增长，而且把尺寸缩到零时，公式给出的恰好是真实起点值，不是硬外推出来的。

**关键词卡片**

- 反典范丛（anticanonical bundle）：由"全纯体积形式的倒数"打包成的线丛；它有非零截面，粗略说就是空间上存在一个全局的"体积公式"。
- 环面作用（torus action）：一族可交换的连续对称操作，像圆桌可以转到任意角度。
- 不变截面（invariant section）：对称操作之后保持原样的对象，"转完了看起来没变"的那一个。
- 不变 Euler 特征（invariant Euler characteristic）：对不变对象做"生成的减去消失的"净计数。
- 伪有效（pseudoeffective）：数值上"平均不亏"的除子类，是有效除子的极限位置。

**看个具体例子**

主定理说：计数函数 `@@M@@I_T(m)@@` 在某个等差数列的指数上等于一个多项式 `@@M@@P(m)@@`，且 `@@M@@P(0)@@` 是真实计数。取最小的情形——环面完全不动的黎曼球面 `@@M@@\mathbb P^1@@`：反典范幂的 Euler 特征 `@@M@@\chi(\mathcal O(2m))=2m+1@@`，落在一条直线上。

<div>

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 560 280">
  <line x1="60" y1="235" x2="500" y2="235" stroke="#555" stroke-width="2"/>
  <line x1="60" y1="235" x2="60" y2="40" stroke="#555" stroke-width="2"/>
  <line x1="60" y1="214" x2="440" y2="54" stroke="#9dbfdd" stroke-width="2"/>
  <circle cx="60" cy="214" r="7" fill="#e05a4e"/>
  <circle cx="130" cy="182" r="6" fill="#4a7dbd"/>
  <circle cx="200" cy="150" r="6" fill="#4a7dbd"/>
  <circle cx="270" cy="118" r="6" fill="#4a7dbd"/>
  <circle cx="340" cy="86" r="6" fill="#4a7dbd"/>
  <circle cx="410" cy="54" r="6" fill="#4a7dbd"/>
  <text x="46" y="252" font-size="14" fill="#333">0</text>
  <text x="126" y="252" font-size="14" fill="#333">1</text>
  <text x="196" y="252" font-size="14" fill="#333">2</text>
  <text x="266" y="252" font-size="14" fill="#333">3</text>
  <text x="336" y="252" font-size="14" fill="#333">4</text>
  <text x="406" y="252" font-size="14" fill="#333">5</text>
  <text x="432" y="252" font-size="14" fill="#333">指数 m</text>
  <text x="28" y="42" font-size="14" fill="#333">计数</text>
  <text x="74" y="207" font-size="13" fill="#a33">真实计数 1</text>
  <text x="300" y="34" font-size="15" fill="#1d3c5c">P(m) = 2m + 1</text>
</svg>

</div>

妙处在"零点取真值"：只看远处像多项式，排除不了它恒为零；`@@M@@P(0)=1\neq0@@` 说明多项式活着，于是某些大指数处计数非零。配上第二条定理——从无界增长的有效扭曲中消去固定的伪有效误差——两块拼图合成对丘成桐 Problem 75 的完整回答：`@@M@@-K_X@@` 光滑半正时 `@@M@@H^0(X,-mK_X)\neq0@@`。

**为什么值得关心**

反典范非消没是双有理几何悬置多年的核心缺口，本文与姊妹篇给出任意维数的第一条无条件证明链，"零点取真值"是全新的技术武器。

> 验证状态：暂无形式化证明（AI 结果待核验）

## 一句话结论

证明两条独立定理——紧环面作用下反典范幂的不变 Euler 特征（invariant Euler characteristic）在可除等差数列上为多项式且在零点取真值；光滑半正反典范簇上可从无界有效扭曲中消去固定伪有效误差——再经"先下降后转换"组合成丘成桐反典范非消没问题的完整证明。

## 问题背景

本文围绕两个动机问题展开。其一：紧环面 `@@M@@T@@` 在紧复流形 `@@M@@F@@` 上全纯作用时，指数 `@@M@@m=0@@` 处的不变 Euler 特征 `@@M@@I_T(0)@@` 能否 forcing 大指数处的上同调？其二：光滑射影簇上，固定的伪有效（pseudoeffective）误差能否从一列无界增长的有效扭曲中消去？两者汇合于丘成桐 Problem 75 的反典范非消没问题：`@@M@@-K_X@@` 光滑半正时 `@@M@@H^0(X,-mK_X)@@` 是否非零。此前障碍在于剩余单值作用（monodromy）以紧环面作用在万有覆盖的紧因子上，截面未必能下降；而已知方法（Müller 2025）需要半放大假设。本文的关键新意是"在零点取值"：单纯的多项式渐进无法区分多项式是否恒为零，端点信息才是排除零多项式的武器。

## 主要结果

定理 1.1（不变反典范指标）：紧实环面 `@@M@@T@@` 全纯作用于紧复流形 `@@M@@F@@`，`@@M@@-K_F@@` 取微分诱导的自然线性化（natural linearization），则存在 `@@M@@a>0@@` 与 `@@M@@P\in\mathbb Q[t]@@` 使 `@@M@@I_T(m)=P(m)@@` 对 `@@M@@a@@` 的每个正倍数成立，且 `@@M@@P(0)=I_T(0)@@`。无需射影性、Kähler 性或任何正性假设。定理 1.2（伪有效误差转换）：`@@M@@S@@` 光滑连通射影，`@@M@@L=-K_S@@` 有半正曲率光滑度量，`@@M@@D@@` 为伪有效 Cartier 除子；若 `@@M@@H^0(S,\mathcal O_S(m_jL-D))\ne0@@` 对严格递增的 `@@M@@m_j@@` 成立，则存在 `@@M@@k>0@@` 使 `@@M@@H^0(S,\mathcal O_S(kL))\ne0@@`。推论 5.2：光滑连通射影复簇上 `@@M@@-K_X@@` 光滑半正则 `@@M@@H^0(X,-mK_X)\ne0@@` 对某 `@@M@@m>0@@` 成立。

## 证明思路

指标定理走局部化路线：Atiyah–Bott–Segal–Singer 等变 Dolbeault 不动点公式把 `@@M@@I_T(m)@@` 写成平凡特征系数，对固定分量极化分母后成为有理多面体上的多项式加权格点计数；先在闭多面体上用基本平行六面体分解与二项式恒等式（加权 Ehrhart 理论）得到可除指数上的多项式性；删去的坐标面贡献的常数项是 `@@M@@(\chi(D)-\chi(A))W(0,0)@@`，而反典范特征 `@@M@@w=\sum_i\nu_i@@` 恰好使外点 `@@M@@u@@`（在 `@@M@@I@@` 上坐标为 `@@M@@-1@@`、其余为 `@@M@@1@@`）落在多面体的仿射方程空间中，从 `@@M@@u@@` 出发的射线首次进入 `@@M@@D@@` 必经被删面，给出形变收缩（deformation retraction）`@@M@@\chi(A)=\chi(D)=1@@`，删面贡献的常数项相消；幸存常数恰为 `@@M@@m=0@@` 处的真实计数。再配合半正系数的 Hard Lefschetz 定理（DPS 2001）：`@@M@@I_T(0)\ne0@@` 时某固定 `@@M@@p@@` 与无界大 `@@M@@m@@` 给出不变扭曲形式 `@@M@@H^0(F,\Omega_F^p\otimes L_F^{m+1})^T\ne0@@`。转换定理则分四步：先取被 `@@M@@L@@` 支配的极大基，截面比值必落在 `@@M@@\mathbb C(Y)@@` 中，插值恒等式使水平零点阶随指数仿射变化，得 `@@M@@N_2-N_1@@` 水平部分有效；再沿基除子取垂直阶数最小值，规范化出基上线丛 `@@M@@B@@` 与非零映射 `@@M@@\sigma:f^*B\to\ell\pi^*L@@`，并由极大性证出伴随直像秩一；接着用 Berndtsson 直像半正性定理，以 `@@M@@L^{2k}@@` 范数经 Hölder 不等式与 Dini 定理收敛到 `@@M@@\sigma@@` 的逐纤维最大值权，配以规范化提供的边界估计，得 `@@M@@B@@` 上局部有界的半正度量；最后混合度量使曲率 `@@M@@\ge\epsilon f^*\omega_H@@` 且乘子理想子（multiplier ideal）平凡（Skoda/Demailly–Kollár 可积性），Fujino 的 Kollár–Nadel 消没定理对一切 `@@M@@k\ge0@@` 生效，Euler 多项式 `@@M@@Q(k)=h^0@@` 处处成立，例外典则截面使 `@@M@@Q(0)>0@@`，多项式非零故某正指数有截面，乘 `@@M@@\sigma^k@@` 后推到 `@@M@@S@@`。应用环节次序关键：引用姊妹篇的有限覆叠结构定理与 étale 范数引理，把 `@@M@@F@@` 上的不变形式先张上其他因子的不变典则框架、经牌不变性单射下降到有限覆叠 `@@M@@S@@`，转换定理只在下降后使用，无需任何等变强化。

## 可信度与备注

本文暂无形式化证明，请以社区核验为准。其几何骨架（有限覆叠结构、范数引理）直接引用同族第一篇手稿，而第一篇的有限体积归纳路线又与本文的不变指标路线互补，两篇交叉印证同一主结论；第三篇则把结论推广到 klt 对。按 OpenAI 官方声明，未经形式化的结果可能有问题。

{% endraw %}
