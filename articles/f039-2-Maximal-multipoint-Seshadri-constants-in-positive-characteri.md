---
layout: default
title: "Maximal multipoint Seshadri constants in positive characteristic"
family: "039"
discipline: "Algebraic and complex geometry"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | Maximal multipoint Seshadri constants in positive characteristic

> 结果族 039：Nagata's conjecture and maximal Seshadri constants　·　学科：Algebraic and complex geometry　·　验证状态：暂无形式化证明，请以社区核验为准

## 入门导读 🐣

前面这套"能量均分"定理的证明大量使用复数世界专属的量尺——解析极限、无穷小退化。这篇把同样的结论搬到"特征 `@@M@@p@@` 世界"：那里数字像时钟，加到 `@@M@@p@@` 就归零，老量尺全部失灵。作者改用纯代数工具（插值、形式幂级数、Hensel 提升）把整座房子在新地基上重盖一遍。

**关键词卡片**

- 特征 `@@M@@p@@`（positive characteristic）：运算按模 `@@M@@p@@` 归零的算术世界。
- 几何一般点组（geometric generic tuple）："绝对一般位置"的代数化精确说法。
- 中国剩余定理（Chinese remainder theorem）：在多个点独立下指令的插值引擎，任意特征可用。
- 结点（node）：曲线上两支交叉的最简奇点；特征 2 下经典样本退化，作者换了新样本。
- Hensel 提升（Hensel lifting）：从近似解提炼出精确形式分支的方法。

**看个具体例子**

结论同形：特征 `@@M@@p@@` 的代数闭域上，阈值之后每个点数 `@@M@@r@@` 都有 `@@M@@\varepsilon=(L^n/r)^{1/n}@@`，二维也一并覆盖。技术上最妙的一步是特征 2 的结点：经典样本在特征 2 会两支粘死，作者改用 `@@M@@y^2+xy-x^3=\xi\eta@@`——两支是否分开取决于 `@@M@@Z^2+Z-x@@` 的根，而 `@@M@@0@@` 与 `@@M@@1@@` 在特征 2 里依然不同，两支保住了，整套几何机制得以继续运转。

<div>

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 560 280">
  <text x="280" y="30" text-anchor="middle" font-size="15" fill="#334455">特征 2 的结点：两支不塌缩</text>
  <line x1="280" y1="50" x2="280" y2="235" stroke="#cccccc" stroke-width="1"/>
  <line x1="70" y1="145" x2="490" y2="145" stroke="#cccccc" stroke-width="1"/>
  <path d="M110 60 Q 280 145 450 230" fill="none" stroke="#c0504d" stroke-width="3"/>
  <path d="M110 230 Q 280 145 450 60" fill="none" stroke="#4a90c4" stroke-width="3"/>
  <circle cx="280" cy="145" r="6" fill="#333333"/>
  <text x="130" y="55" font-size="13" fill="#c0504d">支 1</text>
  <text x="130" y="248" font-size="13" fill="#4a90c4">支 2</text>
  <text x="280" y="272" text-anchor="middle" font-size="13" fill="#666666">两根 0 与 1 在特征 2 下仍不同，结点不退化</text>
</svg>

</div>

**为什么值得关心**

特征 `@@M@@p@@` 是数论与算术几何的主场；定理在那里成立，说明"正性均分"不是复分析的幻影，而是代数本质。

> 暂无形式化证明（AI 结果待核验）

## 一句话结论

在特征 `@@M@@p>0@@` 代数闭域上，光滑射影簇配丰富线丛存在阈值 `@@M@@r_0@@`：`@@M@@r\ge r_0@@` 时几何一般点组的多点 Seshadri 常数恰为体积上界 `@@M@@(L^n/r)^{1/n}@@`，Nagata–Biran–Szemberg 断言在正特征成立。

## 问题背景

多点 Seshadri 常数 (multipoint Seshadri constant) 度量一个丰富线丛 (ample line bundle) 在同时指定若干点后还保留多少正性 (positivity)。它有一个只依赖顶级自交 `@@M@@L^n@@` 与点数 `@@M@@r@@` 的"体积上界" `@@M@@(L^n/r)^{1/n}@@`；问题是：当点足够多且处于一般位置时，是否真有曲线能把这个界压得更低。这一问题谱系源自 Nagata 对希尔伯特第十四问题的研究及他的著名猜想——过 `@@M@@r@@` 个一般点、带任意重数 `@@M@@m_i@@` 的平面曲线满足 `@@M@@\sum_i m_i < d\sqrt r@@`，Nagata 本人在点数为平方数且至少 16 时给出了证明。Biran 与 Szemberg 把"点数足够多时常数取到最大值"的定性版本推广到极化簇 (polarized varieties)，Roé–Ross 在不可数代数闭域上给出了任意维数的精确表述。此前的方法大量依赖复解析工具（解析极限、微分退化论证），无法直接搬到特征 `@@M@@p>0@@` 的域上——这正是本文要填补的缺口。

## 主要结果

设 `@@M@@k@@` 为特征 `@@M@@p>0@@` 的代数闭域，`@@M@@X/k@@` 为 `@@M@@n@@` 维（`@@M@@n\ge3@@`）光滑整射影簇，`@@M@@L@@` 为丰富线丛。令 `@@M@@U_r@@` 为 `@@M@@r@@` 个有序互异点的构型空间，`@@M@@K_r=\overline{k(U_r)}@@`，由其几何一般点 (geometric generic point) 给出 `@@M@@p_1,\dots,p_r\in X(K_r)@@`，即几何一般点组。定义普通（曲线式）Seshadri 常数

`@@M@@D\varepsilon_r(X,L)=\inf_C\frac{L_{K_r}\cdot C}{\sum_{i=1}^r\mult_{p_i}C}，@@`

其中 `@@M@@C@@` 取遍 `@@M@@X_{K_r}@@` 中至少经过一个 `@@M@@p_i@@` 的整曲线 (integral curve)。

**主定理**：存在整数 `@@M@@r_0=r_0(X,L)@@`，使得对每个整数 `@@M@@r\ge r_0@@` 都有 `@@M@@\varepsilon_r(X,L)=\left(L^n/r\right)^{1/n}@@`；文末备注指出 `@@M@@n=2@@`（曲面情形）由同一证明覆盖。用爆开 (blow-up) 的语言，这等价于 `@@M@@\pi^*L_{K_r}-(L^n/r)^{1/n}\sum_i E_i@@` 是 nef 实除子类且顶级自交为零。作者强调：等式对每个足够大的点数 `@@M@@r@@` 精确成立，且"一般位置"由几何一般点组给出精确含义，不需要在无穷个开集的交里挑点。

## 证明思路

整体框架是把截面环编码为"分级指数集"：有限集 `@@M@@S_N\subset\mathbb Z^n@@` 满足 `@@M@@S_N+S_M\subseteq S_{N+N'}@@`，其单项式空间 `@@M@@M(S_N)@@` 一旦在环面点处分离 jet (jet separation)，就可"反向传递"回原来的截面。由于 `@@M@@H^0(X,L^{\otimes N})@@` 分离阶数 `@@M@@\le m=\lfloor N\theta\rfloor@@` 的 jet 就推出曲线不等式 `@@M@@NL\cdot C\ge m\sum_i\mult_{p_i}C@@`，故只需对每个固定的 `@@M@@\theta<w=(L^n/r)^{1/n}@@` 和所有大 `@@M@@N@@` 实现 jet 分离。

先由旗构造起步：Bertini 定理（任意特征可用）给出完全交旗，在旗底光滑点处把截面展开成形式幂级数，取字典序最小指数 (least exponents)，得到分级族 `@@M@@S_N\subset N\Delta(1/D,\dots,1/D,D^{n-1}V)@@`（`@@M@@DL@@` 极丰富），其基数 `@@M@@\#S_N=h^0(X,NL)=\frac{V}{n!}N^n+o(N^n)@@` 恰为单纯形体积的领先项。

再反复做"双截距重塑"：把单纯形相邻两个截距 `@@M@@A,B@@` 换成 `@@M@@w,AB/w@@`，保持乘积、每阶基数与反向传递。其代数核心是结点曲线 (node) `@@M@@y^2+xy-x^3=\xi\eta@@` 的两支界：即使在特征 2，方程 `@@M@@Z^2+Z-x@@` 的根 `@@M@@0@@` 与 `@@M@@-1=1@@` 仍不同，Hensel 提升给出的两个形式分支不塌缩，于是带权最小指数被一个与原四边形等面积的四边形 `@@M@@Q@@` 控制。此后经剪切、坐标压缩（用 `@@M@@z=1@@` 处的消没阶替换行空间——特征 `@@M@@p@@` 下行可以不连续，如 `@@M@@\mathrm{Span}\{1,z^p\}@@` 只有阶 `@@M@@0,p@@`，但区间界够用）与本原格方向 `@@M@@u@@` 的选取（使三角形顶点高度差恰为 `@@M@@H/w@@`），最终落进 `@@M@@\Delta(w,H/w)@@`。依次重塑 `@@M@@n-1@@` 次后得到 `@@M@@F_N\subset NP_*@@`，`@@M@@P_*=\Delta(w,\dots,w,rw)@@`，且满渐近密度。

然后是两个纯代数引理。内部填充：满密度的分级族在大度数包含固定紧集 `@@M@@K\subset\operatorname{int}(P_*)@@` 的全部格点——每个点有约 `@@M@@cN^n@@` 种近等度二分解，而缺失点只排除 `@@M@@o(N^n)@@` 种。插值：末端被拉长的截距 `@@M@@rw@@` 容许在仅最后一个坐标不同的 `@@M@@r@@` 个环面点上做一元多项式插值，所用工具是中国剩余定理，对任意特征有效。

正特征的两个关键替代值得强调：用 `@@M@@k[[s]]@@` 上的形式替换 `@@M@@z_a=s^{\lambda_a}(Q_{i,a}+\delta_a)@@` 在截断环里做秩论证，取代复解析的加权退化（不出现微分与阶乘分母）；用 `@@M@@y^2+xy-x^3@@` 取代特征 2 下会退化的结点。每条 jet 分离陈述都在构型空间 `@@M@@U_r@@` 的非空开集上成立，而 `@@M@@U_r@@` 不可约，故在几何一般点处成立。

最后由正性收尾：jet 分离经 Hilbert–Samuel 重数 (Hilbert–Samuel multiplicity) 的局部长度估计（同时覆盖奇异曲线）给出 `@@M@@\varepsilon_r\ge\theta@@`，令 `@@M@@\theta\to w@@` 得下界；上界则在爆开上考察 `@@M@@\pi^*A-s\sum E_i@@` 的 nef 性与顶级自交 `@@M@@0\le A^n-rs^n@@`。两侧夹逼即得定理。

## 可信度与备注

本文属于结果族 039，主结果暂无形式化证明。其分级支撑骨架承自同族两篇姊妹篇——复数域高维版与曲面版（文中分别以 [OpenAI2026Higher]、[OpenAI2026Surfaces] 引用），但作者声明所有需要的陈述都在本文完整重证；族内三篇互相支撑，共同覆盖了复数域很一般点与任意正特征几何一般点两大情形。按 OpenAI 官方声明，未经形式化的结果可能存在问题，请以社区核验为准。

{% endraw %}
