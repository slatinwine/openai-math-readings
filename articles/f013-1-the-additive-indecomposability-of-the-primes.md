---
layout: default
title: "The additive indecomposability of the primes"
family: "013"
discipline: "Number theory"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | The additive indecomposability of the primes

> 结果族 013：Ostmann's inverse Goldbach conjecture　·　学科：Number theory　·　验证状态：暂无形式化证明，请以社区核验为准

## 入门导读 🐣

Goldbach 猜想说每个大偶数都能写成两个素数之和；Ostmann 在 1956 年反过来问：素数集合本身能否"开膛破肚"——找两个集合 `@@M@@A@@`、`@@M@@B@@`，让两两求和的结果不多不少恰好是全体素数？就像声称俱乐部的完整名单能由两个分组名单两两相加复制出来。本文证明：办不到，素数在加法世界里是不可再分的"原子"。

**关键词卡片**

- 和集（sumset `@@M@@A+B@@`）：从 `@@M@@A@@` 和 `@@M@@B@@` 各取一个数相加，所有可能结果组成的集合。
- 逆 Goldbach 问题（inverse Goldbach problem）：Ostmann 提出的反问题——素数集是否等于某两个集合之和。
- 有限改动（finite modification）：允许增添或删去有限个元素后再比较，比严格相等宽松。
- 大筛法（large sieve）：利用模素数的剩余类信息给集合规模设限的经典工具。
- 渐近不可分解（additively indecomposable）：无法写成两个真子集之和，本文对素数集确立了这一性质。

**看个具体例子**

玩一个最小规模的尝试：`@@M@@A=\{0,1,2\}@@`，`@@M@@B=\{3,4\}@@`，则 `@@M@@A+B=\{3,4,5,6\}@@`——既混进了合数 4 和 6，又漏掉了 7、11……定理说这种"顾此失彼"无法修补：只要 `@@M@@|A|,|B|\ge2@@`，`@@M@@A+B@@` 要么漏掉某个大素数，要么含无穷多个合数；哪怕允许对素数集做有限改动也不行。

<div>

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 560 280">
  <text x="280" y="34" font-size="15" text-anchor="middle">和集 A+B 网格（例：A={0,1,2}，B={3,4}）</text>
  <text x="178" y="64" font-size="14" text-anchor="middle">+3</text>
  <text x="236" y="64" font-size="14" text-anchor="middle">+4</text>
  <text x="125" y="96" font-size="14" text-anchor="middle">0</text>
  <text x="125" y="138" font-size="14" text-anchor="middle">1</text>
  <text x="125" y="180" font-size="14" text-anchor="middle">2</text>
  <rect x="150" y="72" width="56" height="40" fill="#e2f0dd" stroke="#345"/>
  <text x="178" y="97" font-size="15" text-anchor="middle">3</text>
  <rect x="208" y="72" width="56" height="40" fill="#f7dada" stroke="#a55"/>
  <text x="236" y="97" font-size="15" text-anchor="middle">4</text>
  <rect x="150" y="114" width="56" height="40" fill="#f7dada" stroke="#a55"/>
  <text x="178" y="139" font-size="15" text-anchor="middle">4</text>
  <rect x="208" y="114" width="56" height="40" fill="#e2f0dd" stroke="#345"/>
  <text x="236" y="139" font-size="15" text-anchor="middle">5</text>
  <rect x="150" y="156" width="56" height="40" fill="#e2f0dd" stroke="#345"/>
  <text x="178" y="181" font-size="15" text-anchor="middle">5</text>
  <rect x="208" y="156" width="56" height="40" fill="#f7dada" stroke="#a55"/>
  <text x="236" y="181" font-size="15" text-anchor="middle">6</text>
  <rect x="320" y="76" width="20" height="20" fill="#f7dada" stroke="#a55"/>
  <text x="350" y="92" font-size="13">合数：素数集里不该有</text>
  <rect x="320" y="112" width="20" height="20" fill="#e2f0dd" stroke="#345"/>
  <text x="350" y="128" font-size="13">素数</text>
  <text x="320" y="164" font-size="13">A+B={3,4,5,6}：混入合数，</text>
  <text x="320" y="184" font-size="13">又漏掉 7、11……</text>
  <text x="280" y="262" font-size="14" text-anchor="middle">定理：只要 |A|,|B|≥2，任何有限修补都无法让 A+B 恰好等于素数集</text>
</svg>

</div>

**为什么值得关心**

这是 1956 年提出、悬置近七十年的 Ostmann 逆 Goldbach 猜想的完整证明，且不依赖任何未经证实的逆筛猜想。

> 暂无形式化证明（AI 结果待核验）

# 过渡桥 | The additive indecomposability of the primes

## 由浅入深：从类比走向定理

**第一级台阶**

入门导读的比喻是"俱乐部完整名单能否由两个分组名单两两相加复制"：对象从人换成了非负整数，操作从"相加"看结果——两个集合各取一员、求和，收集所有可能的和。导读里"顾此失彼、无法修补"的直觉，精确化就是：任何这种两两求和的复制，要么漏掉无穷多个素数，要么混进无穷多个非素数，而且有限次增删名单也救不回来。

**第二级台阶**

用本科术语定形：对非负整数集 A、B，和集 A+B 定义为 {a+b : a∈A, b∈B}；两个集合称为渐近相等，若其对称差（属于一者不属于另一者的元素全体）有限。素数集记作 P；"有限改动"即做有限增删。这样，命题变成：P 不与任何 A+B 渐近相等，除非某个加数是单点集——平移这种平凡情形被"各含至少两个元素"的要求挡住。

**第三级台阶**

定理（Ostmann 猜想，1956）的陈述是：若 A、B 都至少含两个元素，则 (A+B) 与 P 的对称差是无限集。语境上，Laffer–Mann 把假想分解约化为两个无穷加数；Elsholtz–Harper 用大筛法把加数的计数函数压到平方根尺度（√x/log x loglog x ≪ A(x),B(x) ≪ √x loglog x），但平方根尺度本身与覆盖需求相容、不产生矛盾；Green–Harper 证明一个逆筛分类猜想足以推出结论，Croot–Mao–Pohoata–Yip 的熵论证给出二次像大交集的必要条件，却仍达不到所需的近包含。本文绕开分类路线，直接联用两条假设——每个足够大的素数都被表示（覆盖）、足够大的和都是素数（排除）——这两条都不能放松为密度条件。结论的等价读法：任何至少二元的 A+B 只要覆盖全部大素数，就必含无穷多个合数；素数在加法世界里确是"原子"。

## 一句话结论

本文完整证明了 Ostmann 逆 Goldbach 猜想：素数集经任意有限改动后，都不可能写成两个各含至少两个元素的非负整数集之和 `@@M@@A+B@@`——素数在加法意义下不可分解。

## 问题背景

Goldbach 猜想问每个大偶数是否为两素数之和，Ostmann 则在 1956 年专著中提出反方向的逆 Goldbach 问题（inverse Goldbach problem）：素数集 `@@M@@\mathcal P@@` 本身能否写成两个非负整数集之和？精确地说，`@@M@@\mathcal P@@` 是否渐近加法不可分解（asymptotically additively indecomposable），即不存在 `@@M@@|A|,|B|\ge 2@@` 使 `@@M@@A+B@@` 与 `@@M@@\mathcal P@@` 只差有限个元素。Laffer 与 Mann 在 1964 年证明假想的分解必有两个无限 summand；Elsholtz、Elsholtz–Harper 等随后用大筛法（large sieve）与更大筛把假想分解的计数函数压缩到平方根尺度 `@@M@@\sqrt{x}/(\log x\log\log x)\ll A(x),B(x)\ll\sqrt{x}\log\log x@@`；Green 与 Harper 证明一个合适的逆筛猜想足以推出 Ostmann 猜想；Croot–Mao–Pohoata–Yip 又用加权熵论证给出"两 summand 必与整系数二次像有大交集"的必要条件。这些限制不断收紧，却都不足以导出矛盾——本文绕开任何分类定理，直接联用逐素数的剩余约束与"每个足够大的素数都被表示"这一覆盖条件完成证明。

## 主要结果

**定理（Ostmann 猜想）**：若 `@@M@@A,B\subseteq\mathbb N_0@@` 满足 `@@M@@|A|,|B|\ge 2@@`，则 `@@M@@(A+B)\mathbin{\triangle}\mathcal P@@` 是无限集。等价地，对素数集做任何有限修改（finite modification）所得的集合都不能分解为两个至少二元的集合之和。

证明分两步。第一步是"有限 summand"引理：若 `@@M@@A+B@@` 与 `@@M@@\mathcal P@@` 渐近相等且 `@@M@@|A|,|B|\ge 2@@`，则 `@@M@@A,B@@` 都是无限集——这重述并简证了 Laffer–Mann 定理。第二步是技术核心"两个无限 summand"定理：不存在无限集 `@@M@@A,B\subseteq\mathbb N_0@@` 使 `@@M@@(A+B)\mathbin{\triangle}\mathcal P@@` 有限。

值得注意的是定理结论的双重性：既要最终覆盖所有大素数，又要最终排除所有合数，二者都不能换成密度条件。特别地，若 `@@M@@|A|,|B|\ge 2@@` 且 `@@M@@A+B@@` 含每个足够大的素数，则 `@@M@@A+B@@` 必含无穷多个合数。

## 证明思路

反证法：设无限集 `@@M@@A,B@@` 满足 `@@M@@\mathcal P\cap(N,\infty)\subseteq A+B@@`（素数覆盖）且 `@@M@@(A+B)\cap(N,\infty)\subseteq\mathcal P@@`（排除合数），记 `@@M@@D=-B@@`。先建立两个基础事实：其一，Elsholtz 的平方根界 `@@M@@\sqrt{Y}/(\log Y)^3\ll A(Y),B(Y)\ll\sqrt{Y}(\log Y)^2@@`；其二，对每个素数 `@@M@@p@@`，`@@M@@A@@` 与 `@@M@@D@@` 的远尾部模 `@@M@@p@@` 剩余互不相交——否则 `@@M@@a-d=a+b@@` 是超过 `@@M@@N@@` 的 `@@M@@p@@` 的倍数，与素性矛盾。据此把 `@@M@@\mathbb F_p@@` 划分为互补剩余集 `@@M@@S_p,S_p^c@@`；碰撞稳定性（collision stability）引理作为 Gallagher 更大筛的加权形式表明，按 `@@M@@\log p/p@@` 加权平均，两个 summand 在各自剩余部分上近似均匀，且两边规模近似减半。

再排除与平移乘法特征（multiplicative character）的持续相关：二次特征情形用矩估计与 Poisson 求和迫使一个公共有理中心，再用二次大筛法把尾部囚禁进一小族二次核，以碰撞矛盾收场；高阶特征情形用反复 Cauchy–Schwarz 转移处理，锚变量区分被复制的项并供给控制对角项所需的特征抵消。两者合成混合特征去相关（mixed-character decorrelation）。

素数覆盖单独进场。供应（supply）命题断言：在某段 `@@M@@\log\log p@@` 窗口内，剩余密度满足 `@@M@@1/3\le\sigma_p\le 2/3@@` 且归一化加性变换 `@@M@@g_p@@` 的 `@@M@@L^1@@` 质量有下界的素数，其调和质量不可忽略。证明从稀疏 Fourier 谱构造收缩的张量核 `@@M@@W(n)\ge 0@@`：大筛法给出 `@@M@@W@@` 在 `@@M@@A\times D@@` 上的平均的上界，Landau–Page 定理与 Montgomery 零点密度定理经显式公式算出其素数平均，而覆盖迫使每个大素数都有 `@@M@@A\times D@@` 中的表示从而给出下界，两端矛盾。

最后构造正统计量并做二叉树转移：按对数胞腔先验独立抽取素数（一个来自"有利"块的巨型素数、`@@M@@m/2@@` 个 bulk 素数、`@@M@@m/2@@` 个旁观素数及若干顶部、补偿位置），Poisson 求和把它化为有下界的振幅 `@@M@@\eta_0@@`，再逐层转移。有限域树比较引理只假设概率 `@@M@@L^2@@` 界与混合特征小相关，允许高度非均匀的点值，恰好适配残差指示函数的精确 Fourier 变换，从而控制非对角项；重复素数标签、互素条件与可能的例外实特征在第 8 节的算术分离中处理。终局对 bulk 变量做置换对称化：坏排列对（重叠分量多于 `@@M@@3r/4@@` 者）占比仅 `@@M@@\exp(-\tfrac34 rm\log r)@@`，其总量连同中国剩余定理与素数等差数列估计给出的公共正则变换范数界，使 `@@M@@|\eta_k|^2\le\exp(-(2B+1)rm)@@`，与转移递归保留下界 `@@M@@|\eta_k|^2\ge\exp(-2Brm)@@` 矛盾。转移深度 `@@M@@k@@` 先固定得足够大，再让尺度 `@@M@@L\to\infty@@`。全程不需要 Green–Harper 的一般逆筛分类。

## 可信度与备注

本文暂无 Lean 形式化证明，请以社区核验为准；证明自含于九个章节，所引外部工具（Montgomery–Vaughan 大筛法、Gallagher 更大筛、Landau–Page 定理、Montgomery 零点密度定理与显式公式）均为解析数论经典结果。文中备注提到同批姊妹篇的零自由定理（非平凡零点实部至多 `@@M@@7/8@@`）可简化供应一节，但正文只依赖上述经典估计。按 OpenAI 官方声明，未经形式化的结果可能有问题，读者宜以社区核验与后续形式化为最终判据。

---

# 深入追问 | The additive indecomposability of the primes

## 深入探讨：像审稿人一样追问 🔍

**问 1：证明中最关键、最脆弱的一步是什么？**

（答：终局的二叉树转移与置换平均（第 6–9 节）：正统计量的振幅经逐层转移保有下界 |η_k|²≥exp(-2Brm)，而坏排列对占比 exp(-¾rm·log r)、连同中国剩余与素数等差估计给出的范数界，把上界压到 |η_k|²≤exp(-(2B+1)rm)。矛盾全靠 2B+1 对 2B 这一层指数差撑开——指数算错一位，反证即塌。）

**问 2：|A|,|B|≥2 这个假设能去掉吗？**

（答：不能，且定理在此意义下最优：若 A={a} 是单点，取 B=P-a（平移）就有 A+B=P。二元条件正是排除平移这种平凡分解；Laffer–Mann 定理（论文引理 lem:finite-factor 给出简证）把一般情形约化为两个无穷加数，之后的技术核心全部针对无穷情形。）

**问 3：与 Green–Harper 的条件路线相比，真正新意是什么？**

（答：Green–Harper 证明合适的逆筛猜想（平方根界附近集合的二次分类）可推出 Ostmann 猜想，Croot–Mao–Pohoata–Yip 的二次像交集只是必要条件且达不到近包含。本文明确"不要求、也不主张任何此类分类定理"，改用逐素数剩余约束与素数覆盖直接矛盾——这是路线层面的新意。）

**问 4：覆盖与排除两条要求为什么都不能换成密度条件？**

（答：引言直说"The conclusion concerns both eventual coverage… Neither requirement is replaced by a density condition"：对称差有限是逐点要求，密度陈述无法区分"漏掉稀疏无穷素数"这类情形。等价形式（覆盖全部大素数则必含无穷合数）也只在逐点意义下成立。）

**问 5：这类 AI 长证明最可能在哪里出错？**

（答：高危点集中在三处：碰撞稳定性引理是 Gallagher 更大筛的加权形式，按 log p/p 平均的"近似均匀、规模减半"若量级有误则后续剩余划分失稳；供应命题把 Landau–Page 与 Montgomery 零点密度经显式公式比较上下界，例外实特征（可能的 Siegel 零点）在第 8 节的算术分离中处理，此处最易藏漏洞；终局指数 2B+1 与 2B 之间仅差常数，属于典型的"差一点就反"结构。）

**问 6：谁会用到这个结果？**

（答：加法数论中研究素数中和集（thin sumsets in primes）与逆筛问题的人群：本文结束了一个七十年的悬案，且其剩余约束加覆盖的矛盾机制为其他"集合方程 X=A+B"型问题提供了不依赖分类定理的新模板。论文本身未展开更多下游推论。）

**总评**

不借任何未证分类猜想、正面解决 Ostmann 逆 Goldbach 猜想，这是结实的分量；最大风险在终局指数矛盾的薄边际与零点密度环节的常数纪律，是需要逐节核验的典型 AI 手稿。

{% endraw %}
