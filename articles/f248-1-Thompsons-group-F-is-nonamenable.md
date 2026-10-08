---
layout: default
title: "Thompson's group F is nonamenable"
family: "248"
discipline: "Group theory"
formalized: true
source: null
pdfname: ""
---

{% raw %}
# 解读 | Thompson's group F is nonamenable

> 结果族 248：Thompson's group <i>F</i> is nonamenable　·　学科：Group theory　·　验证状态：主结果已 Lean 形式化

## 入门导读 🐣

想象一家搬家公司，每种"搬法"都会重新排列棋盘上的棋子。温和的公司允许你圈出一大块地盘：无论用公司里哪几种标准搬法，地盘边界都几乎不动；暴躁的公司则任你圈哪块地盘，总有搬法把它搅得面目全非。这篇论文证明：几何群论的明星对象 Thompson 群 `@@M@@F@@` 属于暴躁的一类——它不是顺从群，Geoghegan 1979 年提出、悬置四十多年的难题就此定案。

**关键词卡片**

- Thompson 群 F（Thompson's group F）：区间 `@@M@@[0,1]@@` 上所有"断点取二进分数、斜率取 2 的幂"的分段线性变形组成的群
- 顺从群（amenable group）：能找到"边界几乎不被搬动"的大地盘的群，等价于群上存在不变平均
- Følner 准则（Følner criterion）：顺从当且仅当对任何有限搬法集，边界比 `@@M@@|hA\triangle A|/|A|@@` 可以任意小
- 对称差（symmetric difference）：`@@M@@A\triangle B@@` 是只属于 `@@M@@A@@`、`@@M@@B@@` 之一的元素全体，用来量"搬动前后差了多少"
- 非顺从（nonamenable）：无论选哪块有限地盘，总有一种搬法让边界占相当大的比例

**看个具体例子**

先看温和的例子：整数群 `@@M@@\mathbb{Z}@@` 中取地盘 `@@M@@A=\{1,2,\dots,100\}@@`，搬法 `@@M@@h@@` 是"右移一格"，`@@M@@hA@@` 与 `@@M@@A@@` 只在两端各差一个数，边界比 `@@M@@=2/100=0.02@@`；地盘越大比值越小，故 `@@M@@\mathbb{Z}@@` 顺从。论文证明 `@@M@@F@@` 中存在一组固定搬法 `@@M@@S@@` 与正常数 `@@M@@c@@`，使任何有限地盘 `@@M@@A@@` 都被某个 `@@M@@h\in S@@` 搅动到边界比不小于 `@@M@@c@@`——"右移一步几乎不动"的好事在 `@@M@@F@@` 里永远不会发生。

<div>

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 560 280">
  <text x="20" y="28" font-size="16" fill="#333333">温和的 Z：大地盘右移一格，几乎不漏边</text>
  <rect x="30" y="50" width="240" height="24" fill="#bbdefb" stroke="#1565c0"/>
  <rect x="33" y="84" width="240" height="24" fill="none" stroke="#c62828" stroke-dasharray="5 4"/>
  <text x="30" y="134" font-size="13" fill="#555555">A = {1,…,100} 与右移后的 A：重合 98 格，边界比 2/100</text>
  <text x="20" y="172" font-size="16" fill="#333333">暴躁的 F：任何地盘都被大幅搅动</text>
  <rect x="40" y="192" width="46" height="22" fill="#c8e6c9" stroke="#2e7d32"/>
  <rect x="100" y="192" width="84" height="22" fill="#c8e6c9" stroke="#2e7d32"/>
  <rect x="196" y="192" width="28" height="22" fill="#c8e6c9" stroke="#2e7d32"/>
  <rect x="70" y="224" width="24" height="22" fill="#ffcdd2" stroke="#c62828"/>
  <rect x="140" y="224" width="64" height="22" fill="#ffcdd2" stroke="#c62828"/>
  <rect x="226" y="224" width="56" height="22" fill="#ffcdd2" stroke="#c62828"/>
  <text x="310" y="205" font-size="13" fill="#555555">绿块 = 地盘 A，红块 = 搬后 hA：</text>
  <text x="310" y="225" font-size="13" fill="#555555">重叠零散，边界比至少为某个固定正数 c</text>
</svg>

</div>

**为什么值得关心**

`@@M@@F@@` 早在 1985 年就被证明不含非交换自由子群，也不属于初等顺从类，两条判断非顺从的经典路径全部失效，使它成为该领域最著名的悬案之一；本文以"无穷维球面上一个没有近似不动点的映射"加一次有限平均论证将其攻克。

> 已 Lean 形式化

## 一句话结论

论文证明了 Thompson 群 `@@M@@F@@`——区间 `@@M@@[0,1]@@` 上二进分段线性同胚构成的群——不是顺从群（nonamenable），确认了 Geoghegan 1979 年猜想，为这个悬置四十余年的几何群论难题画上句号。

## 问题背景

Thompson 群 `@@M@@F@@` 由 `@@M@@[0,1]@@` 上所有保定向分段线性同胚构成，要求分段有限、断点均为二进有理数（dyadic rational）、斜率均为 2 的整数幂；它由 Thompson 于 1965 年引入（早期构造见 McKenzie–Thompson 1973），是几何群论的核心对象。顺从性（amenability）源自 von Neumann 与 Day 的经典理论：群顺从当其上有正的、归一的左不变平均（invariant mean）；由 Følner 准则可知，顺从群对任何有限平移集都能找到相对边界 `@@M@@|hA\triangle A|/|A|@@` 同时任意小的有限集。Cannon–Floyd–Parry 讲义记载了 Geoghegan 1979 年的猜想：`@@M@@F@@` 非顺从。问题之难在于两条经典判据全部失效：Brin–Squier（1985）证明 `@@M@@F@@` 不含非交换自由子群，自由群障碍用不上；`@@M@@F@@` 又不属于初等顺从类（elementary amenable）。此前不乏两个方向的证明断言——Akhmedov 2021 宣称非顺从，Shavgulidze 2009 宣称顺从（被 Moore 指出错误，Moore 亦撤回过自己一篇顺从证明）——均未成为定论。Moore 还证明了 Følner 集大小的塔式下界与 Ramsey 刻画，Haagerup–Olesen 证明 Thompson 群 `@@M@@T@@` 的约化 C*-代数单性蕴含 `@@M@@F@@` 非顺从，但都不能直接定夺。

## 主要结果

主定理：Thompson 群 `@@M@@F@@` 不是顺从群。论文实际证明的是定量版本（finite-proof.tex，命题 avg:boundary）：存在与待测集无关的有限集 `@@M@@S\subset F@@` 及正常数
`@@M@@Dc=\frac{\delta^2/L^2-4/D}{4(1-1/D)}>0,@@`
使得对一切非空有限集 `@@M@@A\subset F@@` 均有 `@@M@@\max_{h\in S}|hA\triangle A|/|A|\ge c@@`，与 Følner 准则直接矛盾。推论有两条（consequences.tex，均援引配套定理）：其一，对每个 `@@M@@\varepsilon>0@@`，存在表示 `@@M@@\pi:F\to\mathrm{GL}(H)@@` 满足 `@@M@@\sup_g\|\pi(g)\|\le1+\varepsilon@@`，却不能被任何有界可逆算子整体酉化（nonunitarizable，不可酉化）；其二，对任意有限对称生成集给出的 Cayley 图，Bernoulli 边渗流（bond percolation）满足 `@@M@@\|T_{p_c}\|_{2\to2}<\infty@@`、`@@M@@p_c<p_{2\to2}\le p_u@@`，且对每个 `@@M@@p\in(p_c,p_u)@@` 几乎必然出现无穷多个无穷开簇（open cluster），并存在确定性窗口 `@@M@@[p_1,p_2]@@` 使之同时发生。

## 证明思路

整个证明是"反证法＋无穷维现象＋一次有限平均"的组合。先固定三样与待测集无关的原料。其一，Benyamini–Sternfeld 定理（1983）供给的映射：无穷维 Hilbert 空间闭单位球 `@@M@@B@@` 上存在 Lipschitz 自映射 `@@M@@f@@` 与 `@@M@@\delta>0@@` 使 `@@M@@\|f(x)-x\|\ge\delta@@` 处处成立（无近似不动点）；附录在 `@@M@@L^2([0,1];\mathbb R^2)@@` 上以 `@@M@@\delta=1/2@@` 显式构造——沿一条带"有界尾部"的螺线曲线取固定半径的管状邻域，再令 `@@M@@f(x)=-G(x)/\|G(x)\|@@`。其二，满足 `@@M@@D>4L^2/\delta^2@@` 的大整数 `@@M@@D@@`。其三，`@@M@@D@@` 个两两分离的内部二进区间 `@@M@@I_1<\cdots<I_D@@`（父区间），并在每个父区间内放入这组区间的仿射拷贝 `@@M@@I_i\cdot I_j@@`（子区间）。随后对每个基本二进划分按胞腔数递归定义颜色 `@@M@@p(T)\in B@@`：当 `@@M@@T@@` 尊重全部父区间时，`@@M@@p(T)=f(\text{诸限制颜色的均值})@@`，否则取 `@@M@@0@@`；取限制会严格减少胞腔数，故归纳良定。对群元 `@@M@@g@@` 取足够细的水平 `@@M@@n@@`，使像划分 `@@M@@gT^{(n)}@@` 基本化并尊重所有相关区间，据此定义颜色函数 `@@M@@X_I(g)@@` 与标量相关（scalar correlation）`@@M@@\varphi_{I,J}(g)=\langle X_I,X_J\rangle@@`。

接着是组合核心"搬运"：`@@M@@F@@` 能把任意分离区间对标仿射地送到任意另一对（在三个余隙中反复二分配平胞腔数即可），据此预先固定有限搬运元集 `@@M@@S@@`。精确的协方差恒等式 `@@M@@((hg)T^{(n)})_{I'}=(gT^{(n)})_I@@` 给出 `@@M@@\varphi_{I,J}(g)=\varphi_{I_1,I_2}(h_{I,J}g)@@`；再配合初等的有限平均比较 `@@M@@|\mathbb E_A\varphi(hg)-\mathbb E_A\varphi(g)|\le|hA\triangle A|/|A|=\eta@@`，可得：凡严格分离的区间对，其平均相关都落在同一公共值 `@@M@@\alpha@@` 的 `@@M@@\eta@@` 邻域中。

最后是方差估计。令 `@@M@@m@@` 为父颜色均值、`@@M@@z_i@@` 为第 `@@M@@i@@` 个父区间诸子颜色的均值，递归定义给出精确恒等式 `@@M@@X_{I_i}=f(z_i)@@`，而 `@@M@@m@@` 又是诸 `@@M@@f(z_i)@@` 的均值。位移下界、平方范数的凸性与 Lipschitz 条件联合给出
`@@M@@D\delta^2\le\|m-f(m)\|^2\le\frac{L^2}{D}\sum_i\|z_i-m\|^2 .@@`
展开 `@@M@@\mathbb E_A\|z_i-m\|^2@@` 时，交叉项中严格分离对的相关被 `@@M@@\alpha\pm\eta@@` 控制，公共值 `@@M@@\alpha@@` 的系数恰好正负相消；对角项与嵌套对只占比例 `@@M@@1/D@@`，由单位球界控制。合并得 `@@M@@\mathbb E_A\|z_i-m\|^2\le4/D+4(1-1/D)\eta@@`，代回上式整理即得一致正下界 `@@M@@c@@`，与 Følner 准则矛盾，故 `@@M@@F@@` 非顺从。

## 可信度与备注

论文标注主结果已获 Lean 形式化证明（结果族 248 附有形式化文档），这对该量级的结论是重要保障。两条推论分别援引同项目关于不可酉化表示与渗流的姊妹定理：它们依赖本文结论而非相反，论文也明确说明二者未参与非顺从性的证明。按 OpenAI 官方声明，未经形式化的结果可能存在问题；本文主结果已形式化，推论所涉配套定理仍请以社区核验为准。

{% endraw %}
