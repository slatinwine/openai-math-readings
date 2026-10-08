---
layout: default
title: "The cotype–cotype conjecture under the approximation property"
family: "326"
discipline: "Functional analysis"
formalized: true
source: null
pdfname: ""
---

{% raw %}
# 解读 | The cotype–cotype conjecture under the approximation property

> 结果族 326：The cotype–cotype conjecture under the approximation property　·　学科：Functional analysis　·　验证状态：主结果已 Lean 形式化

## 入门导读 🐣

想知道一块地形平不平整，可以扔弹珠听回声。研究无穷维空间也一样：把一组向量按抛硬币的正负随机加起来，听"随机和"的回声。这篇论文解决了一个 1981 年遗留的猜想：只要空间和它的对偶在抛硬币测试下都不"塌缩"（有余型），且空间可被有限维逼近，那么空间一定是"圆润"的（K-凸）——两枚硬币的正反面信息合在一起，恰好补齐了缺失的那一半。

**关键词卡片**

- 余型（cotype）：随机求和洗不掉向量的性质：随机和的平均长度不小于逐个长度的 `@@M@@\ell^q@@` 范数（差常数倍）。
- 型（type）：对偶概念：随机性能帮忙"消化"向量组，随机和的长度不超过 `@@M@@\ell^p@@` 范数。
- K-凸（K-convexity）：空间几何足够圆润、有不平凡型的等价说法；反面例子是越来越尖的"八面体"。
- 逼近性质（approximation property, AP）：恒等映射可以被有限维算子逐点逼近，空间"看得清自己"。
- 对偶空间（dual space）：原空间上全体连续线性函数组成的新空间，像原空间的"影子"。

**看个具体例子**

在平面 `@@M@@\mathbb{R}^2@@` 里取正交单位向量 `@@M@@y_1,y_2@@`，抛两枚硬币得到四个随机和 `@@M@@\pm y_1\pm y_2@@`，长度全是 `@@M@@\sqrt2@@`。余型 2 不等式在此取具体数字：

`@@M@@D(\|y_1\|^2+\|y_2\|^2)^{1/2}=\sqrt2=\big(\mathbb{E}\|\varepsilon_1y_1+\varepsilon_2y_2\|^2\big)^{1/2}@@`

两边严格相等——最圆润的空间（Hilbert 空间）里随机和不塌缩。定理说：只要 `@@M@@X@@` 与影子 `@@M@@X^*@@` 都通过这类测试（指数还可以一个用 2、一个用 3），`@@M@@X@@` 就必然 K-凸。

<div>

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 560 280">
  <text x="20" y="28" font-size="15" fill="#222">抛两枚硬币：四个随机和 ±y₁±y₂ 落在同一半径的圆上</text>
  <line x1="40" y1="165" x2="400" y2="165" stroke="#999" stroke-width="1"/>
  <line x1="220" y1="50" x2="220" y2="268" stroke="#999" stroke-width="1"/>
  <circle cx="220" cy="165" r="95" fill="none" stroke="#bbb" stroke-width="1.5" stroke-dasharray="5 5"/>
  <line x1="220" y1="165" x2="287" y2="98" stroke="#2f8f4e" stroke-width="2.5"/>
  <line x1="220" y1="165" x2="153" y2="98" stroke="#2f8f4e" stroke-width="2.5"/>
  <line x1="220" y1="165" x2="153" y2="232" stroke="#2f8f4e" stroke-width="2.5"/>
  <line x1="220" y1="165" x2="287" y2="232" stroke="#2f8f4e" stroke-width="2.5"/>
  <circle cx="287" cy="98" r="4" fill="#2f8f4e"/>
  <circle cx="153" cy="98" r="4" fill="#2f8f4e"/>
  <circle cx="153" cy="232" r="4" fill="#2f8f4e"/>
  <circle cx="287" cy="232" r="4" fill="#2f8f4e"/>
  <text x="295" y="92" font-size="13" fill="#2f8f4e">y₁+y₂</text>
  <text x="90" y="92" font-size="13" fill="#2f8f4e">−y₁+y₂</text>
  <text x="90" y="250" font-size="13" fill="#2f8f4e">−y₁−y₂</text>
  <text x="295" y="250" font-size="13" fill="#2f8f4e">y₁−y₂</text>
  <text x="228" y="60" font-size="13" fill="#888">半径 √2 的圆</text>
  <text x="412" y="110" font-size="14" fill="#222">四个和长度</text>
  <text x="412" y="132" font-size="14" fill="#222">全是 √2</text>
  <text x="412" y="168" font-size="14" fill="#b0348f" font-weight="bold">不塌缩！</text>
  <text x="412" y="204" font-size="13" fill="#666">定理：X 与影子 X*</text>
  <text x="412" y="224" font-size="13" fill="#666">都这样不塌缩，</text>
  <text x="412" y="244" font-size="13" fill="#666">则 X 必是 K-凸</text>
</svg>

</div>

**为什么值得关心**

它以比已知更弱的条件（AP 弱于 BAP）关闭了 Pisier 的公开问题，还顺带给出一大类凸体的无维数依赖熵对偶。

> 主结果已 Lean 形式化

## 一句话结论

在仅假设普通逼近性质（AP）的条件下证明了 cotype–cotype 猜想：非零实 Banach 空间是 `@@M@@K@@`-凸的，当且仅当它及其对偶都具有有限 Rademacher 余型，且两个指数可以不同。这解决了 Pisier 1981 年公开遗留的问题，条件还比已知的有界逼近性质（BAP）更弱。

## 问题背景

Banach 空间的几何可用随机符号和的尺度刻画：`@@M@@Y@@` 有 Rademacher 余型（cotype）`@@M@@q@@`，指对任意有限组 `@@M@@(\sum_i\|y_i\|^q)^{1/q}\le C_q(Y)(\E\|\sum_i\varepsilon_i y_i\|^2)^{1/2}@@` 成立；对偶地有型（type）。Maurey 与 Pisier 在 1976 年建立这套理论时引入了 `@@M@@K@@`-凸性（`@@M@@K@@`-convexity）：符号立方上 `@@M@@X@@`-值函数的一阶 Rademacher 投影（Rademacher projection）一致有界。Pisier 随后的全纯半群定理证明 `@@M@@K@@`-凸等价于有非平凡型（某个 `@@M@@p>1@@`），也等价于不一致包含 `@@M@@\ell_1^s@@`。对偶手续能把型传成对偶空间上的余型，但反方向——从 `@@M@@X@@` 与 `@@M@@X^*@@` 双侧有限余型恢复型——需要额外信息，这正是 cotype–cotype 问题。Pisier 1980 年证明双侧余型 2 加逼近性质（approximation property, AP）蕴含同构于 Hilbert 空间；1981 年在限制余型指数的条件下对具有基或 BAP 的空间证得 `@@M@@K@@`-凸，并追问指数限制能否去掉；Szarek–Tomczak-Jaegermann 后来把它称作 cotype–cotype 猜想。无逼近假设时命题为假：Pisier 1983 年的构造把 `@@M@@\ell_1@@` 这类余型 2 空间嵌入一个双侧余型 2 却非 `@@M@@K@@`-凸的空间，这类反例都破坏 AP。又因 Figiel–Johnson 已把 AP 与 BAP 分离，AP 框架下的证明必须容纳范数毫无一致界的逼近算子——这正是难点所在。

## 主要结果

主定理：设 `@@M@@X@@` 为非零实 Banach 空间且具有普通 AP，则 `@@M@@X@@` 是 `@@M@@K@@`-凸的当且仅当存在可以不同的 `@@M@@q,r\in[2,\infty)@@` 使 `@@M@@C_q(X)<\infty@@` 且 `@@M@@C_r(X^*)<\infty@@`；其中正向蕴含对一切实 Banach 空间成立，不需要 AP。定理还是一致的：固定 `@@M@@q,r@@` 与余型常数 `@@M@@C,D@@` 后，`@@M@@K(X)@@` 有仅依赖这组数据的上界 `@@M@@\kappa(q,r,C,D)@@`。由此推出两个应用。其一（度量熵对偶，metric entropy duality）：若 `@@M@@\mathbb{R}^n@@` 中原点对称凸体 `@@M@@K@@`、`@@M@@L@@` 之一所定的赋范空间满足上述双侧余型界，则覆盖数（covering number）满足 `@@M@@\frac1b\log N(L^\circ,atK^\circ)\le\log N(K,tL)\le b\log N(L^\circ,a^{-1}tK^\circ)@@`，常数 `@@M@@a,b@@` 与维数无关——这给出一大类凸体上常数无维数依赖的熵对偶。其二（Grothendieck 对，Grothendieck pair）：若对每个 `@@M@@A:E_m\to E_n^*@@`，张量积 `@@M@@A\otimes\Id_F@@` 从单射张量范数到射影张量范数的范数一致不超过 `@@M@@C\|A\|@@`，且 `@@M@@F@@` 无限维并具有 AP，则同一估计对 `@@M@@\ell_2@@` 代替 `@@M@@F@@` 也成立，即 Pisier 猜想在 AP 下成立。

## 证明思路

证明分两大步。第一步为有限秩算子建立一致的 Walsh 衰减。对 `@@M@@T:G\to F@@`，把 `@@M@@T@@` 与 `@@M@@n@@` 元归一化 Walsh 矩阵复合，其 `@@M@@L_2@@` 算子范数记为 `@@M@@w_n(T)@@`。基础观察是：有限秩 `@@M@@T@@` 可经有限维 Hilbert 空间分解，由正交性得 `@@M@@w_n(T)\le D_T2^{-n/2}@@`，但常数 `@@M@@D_T@@` 依赖算子，目标就是去掉这种依赖。先固定一个足够大的组长度 `@@M@@m@@`，使由余型换算出的提升幅度 `@@M@@ma=m^{1/r}/(24LC_Y)@@` 与 `@@M@@mb=m^{1/q}/(2LC_F)@@` 超过系数引理所需的 `@@M@@(\log m)^3@@` 级门槛——`@@M@@m@@` 的正幂最终压倒对数，这也是两个指数允许不同的原因。核心是新的标量系数引理：符号矩阵上的函数 `@@M@@\Psi@@` 若带有足够大的一阶 Fourier 系数和规定的行、列投影矩，其 Fourier 展开中必有指标在 `@@M@@\F_2@@` 上秩至少为 2 的系数不小于 `@@M@@c_*@@`。证明用反证：若支撑全落在秩不超过 1 的矩形指标上，就用带阻尼 `@@M@@2^{-kl}@@` 的多项式 `@@M@@H(s,u)@@` 编码这些矩形，其上确界受控；而规定的混合导数 `@@M@@\partial_s\partial_u H(0,0)=AB/2@@` 很大，在 Chebyshev 基下按两个变量分阶再用 Markov 型导数估计，即得与之矛盾的上界。秩至少 2 的指标经二元换变量后恰能拆出两个独立的 Walsh 因子。接着是增长引理：若 `@@M@@w_n(T)@@` 在某处下降缓慢，先用矩提升（moment lift，基于带显式常数 `@@M@@L=24@@` 的 Kahane 不等式、商对偶与 Hahn–Banach，把向量组表示成有界符号指标族使 `@@M@@\E\varepsilon_iP_\eps=ax_i@@`），再在有限群 `@@M@@\GL(n,\F_2)@@` 上平均使配对只依赖符号模式，然后套用系数引理，得 `@@M@@w_{2(n-2m)}(T)\ge c_1w_n(T)@@`：慢下降迫使近二倍维度处出现可观的范数。最后用伸缩望远镜论证迭代：一个慢下降点会无限繁殖，与该固定算子的 Hilbert 空间界 `@@M@@D_T2^{-n/2}@@` 矛盾——这是全文唯一用到有限秩的地方。于是得到与空间、算子均无关的 `@@M@@\rho_N\to0@@` 使 `@@M@@w_N(T)\le\rho_N\|T\|@@`。

第二步把衰减经 AP 转移到 `@@M@@X@@` 的恒等算子上。困难在于有限维子空间 `@@M@@E\subset X@@` 的对偶 `@@M@@E^*@@` 是 `@@M@@X^*@@` 的商，未必继承 `@@M@@X^*@@` 的余型估计。办法是构造紧因子分解：先做嵌套有限维扩张 `@@M@@E=E_0\subset E_1\subset\cdots@@`，对单位球网逐点提升，使每层 `@@M@@\ell_2^m@@` 向量组都有受控的矩提升；再以递减权 `@@M@@2^{-l}@@` 取 `@@M@@\ell_2@@` 直和得到范数不超过 2 的紧算子 `@@M@@J:G\to X@@`，并由加权移位满足 `@@M@@jR=j@@` 拼装各层提升，证得 `@@M@@c_m(G^*)\le12\Delta@@`。对紧集 `@@M@@\overline{J(B_G)}@@` 使用 AP：存在有限秩 `@@M@@S_j@@` 使 `@@M@@\|S_jJ-J\|<1/j@@`，这里完全不需要 `@@M@@\|S_j\|@@` 的公共上界，故 `@@M@@J@@` 是有限秩映射的算子范数极限，一致衰减先传给 `@@M@@J@@`，再经 `@@M@@J\iota=\Id@@` 传给 `@@M@@X@@` 的每个有限 Walsh 输入，得 `@@M@@w_N(\Id_X)\le2\rho_N@@`。若 `@@M@@K(X)=\infty@@`，前述经典刻画给出一致的 `@@M@@\ell_1^s@@` 拷贝，其每个 Walsh 输出范数都不小于 `@@M@@\lambda^{-1}@@`，与 `@@M@@\rho_N\to0@@` 矛盾，定理得证。

## 可信度与备注

主结果已由 OpenAI 完成 Lean 形式化证明（族文档 lean/docs/326.md 收录），验证等级最高。两个推论是在主定理之上组合外部经典结果得到的：熵对偶引用 Artstein–Milman–Szarek–Tomczak-Jaegermann 的有界 `@@M@@K@@` 熵对偶定理，Grothendieck 对的推导沿用 Gupta–Misra–Ray 的工作与 Figiel–Tomczak-Jaegermann 的可补 Euclid 子空间定理。本结果族仅此一篇手稿，但它同时关闭了三条线索：Pisier 1981 年 Remark 2(iii) 的问题、Szarek–Tomczak-Jaegermann 命名的 cotype–cotype 猜想、Gupta–Misra–Ray 的 BAP 版猜想（并减弱到 AP）。按 OpenAI 官方声明，未经形式化的结果可能存在问题；本文主定理已形式化，可信度高。

{% endraw %}
