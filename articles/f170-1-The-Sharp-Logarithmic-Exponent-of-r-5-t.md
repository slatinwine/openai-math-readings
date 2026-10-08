---
layout: default
title: "The sharp logarithmic exponent of r(5,t)"
family: "170"
discipline: "Combinatorics"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | The sharp logarithmic exponent of r(5,t)

> 结果族 170：Sharp logarithmic exponents for off-diagonal Ramsey numbers　·　学科：Combinatorics　·　验证状态：暂无形式化证明，请以社区核验为准

## 入门导读 🐣

办一场巨型派对：宾客中要么冒出 5 个人彼此全认识，要么冒出 `@@M@@t@@` 个人彼此全陌生。要保证二者必居其一，最少得请多少人？这就是拉姆齐数 `@@M@@r(5,t)@@`。答案像一座分式：分子 `@@M@@t^4@@` 已知，卡了四十年的是分母上"对数的幂"；本文把它精确锁定为 3。

**关键词卡片**

- 拉姆齐数（Ramsey number）`@@M@@r(s,t)@@`：保证"`@@M@@s@@` 人全相识或 `@@M@@t@@` 人全陌生"的最小宾客数
- 团与独立集（clique / independent set）：互相全连边 / 互相全不连边的顶点集
- 非对角（off-diagonal）：`@@M@@s@@` 固定而 `@@M@@t\to\infty@@` 的极端设定
- 对数指数（logarithmic exponent）：答案分母中 `@@M@@(\log t)@@` 的幂次，本文证得恰为 3
- 随机旗（random flag）：射影空间中"点落在超平面上"的入射对，反例图的建筑砖块

**看个具体例子**

把定理代入 `@@M@@t=10^6@@`（自然对数 `@@M@@\log t\approx 13.8@@`）的数字版：

`@@M@@r(5,10^6)\approx \dfrac{10^{24}}{(13.8)^3}\approx 4\times 10^{20}@@`

即请约 `@@M@@4\times10^{20}@@` 位客人（允许常数倍出入），必现 5 人小团体或百万人互不相识；常数因子具体是多少，论文留作公开问题。完整定理是夹逼：`@@M@@\dfrac{t^4}{(\log t)^{3+\varepsilon}}\le r(5,t)\le C\,\dfrac{t^4}{(\log t)^3}@@`，上下界只差 `@@M@@o(1)@@` 的幂。

**为什么值得关心**

上界 1980 年就由 Ajtai–Komlós–Szemerédi 建立，本文只给它一个初等重证；真正的突破全在下界——此前下界的对数幂落后一倍（`@@M@@6@@` 对 `@@M@@3@@`），本文用射影空间里的随机旗构造加熵压缩把缺口完全闭合。

> 暂无形式化证明（AI 结果待核验）

## 一句话结论

本文证明了 `@@M@@r(5,t)=t^4/(\log t)^{3+o(1)}@@`：非对角拉姆齐数（off-diagonal Ramsey number）在 `@@M@@s=5@@` 时的对数指数被精确确定为 `@@M@@3@@`，下界终于追平 Ajtai–Komlós–Szemerédi 的经典上界，只差 `@@M@@o(1)@@` 的幂。

## 问题背景

拉姆齐数 `@@M@@r(s,t)@@` 是最小的 `@@M@@n@@`，使得任意 `@@M@@n@@` 个顶点的图中必出现 `@@M@@s@@` 团（clique `@@M@@K_s@@`）或 `@@M@@t@@` 个顶点的独立集（independent set）。固定 `@@M@@s@@`、让 `@@M@@t\to\infty@@` 的非对角情形是极值图论最古老的定量问题之一。上界一侧早已定型：Erdős–Szekeres（1935）的二项式界被 Ajtai–Komlós–Szemerédi（1980）改进为 `@@M@@O(t^{s-1}/(\log t)^{s-2})@@`，Li–Rousseau–Zang（2001）又把主导常数做到 `@@M@@1+o(1)@@`。下界一侧却步履蹒跚：Kim（1995）只解决了 `@@M@@s=3@@`；对 `@@M@@s=5@@`，Spencer（1977）的局部引理方法与 Bohman–Keevash（2010）对随机无团过程的最好分析给出的都只有 `@@M@@t^3@@` 的量级，连上界中 `@@M@@t@@` 的四次幂都够不着。有限几何带来转机：Mattheus–Verstraëte（2024）用 Hermitian unital 构造证得 `@@M@@r(4,t)\ge ct^3/(\log t)^4@@`，Bradač（2026）把射影构造推广到 `@@M@@r(s,t)\ge c_s t^{s-1}/(\log t)^{2s-4}@@`——多项式指数就此确定，但对数幂仍差一倍（`@@M@@s=5@@` 时是 `@@M@@6@@` 对 `@@M@@3@@`）。本文把这一缺口完全闭合。

## 主要结果

主定理：存在绝对常数 `@@M@@C>0@@`，使得对任意 `@@M@@\varepsilon>0@@` 与一切充分大的 `@@M@@t@@`，

`@@M@@D\frac{t^4}{(\log t)^{3+\varepsilon}}\ \le\ r(5,t)\ \le\ C\,\frac{t^4}{(\log t)^3}.@@`

等价地，`@@M@@\lim_{t\to\infty}\frac{4\log t-\log r(5,t)}{\log\log t}=3@@`。上界是经典结果的初等重证，作者用 Alon 的一致独立集（uniform independent set）方法加随机抽样给出自足证明；真正的突破在下界：对每个 `@@M@@0<\eta<1/10@@` 与充分大的素数 `@@M@@q@@`，构造出 `@@M@@\lfloor q^4\log q\rfloor@@` 个顶点、无 `@@M@@K_5@@` 且独立数小于 `@@M@@q(\log q)^{1+\eta}@@` 的图。定理并未确定 `@@M@@t^4/(\log t)^3@@` 的常数因子，作者明确将其留作公开问题。

## 证明思路

先看构造。在四维射影空间 `@@M@@\PG(4,q)@@` 上，一个"旗"（flag）是入射对 `@@M@@(a,b)@@`：点 `@@M@@a@@` 落在超平面 `@@M@@b@@` 上。独立均匀地抽取 `@@M@@N=\lfloor q^4\log q\rfloor@@` 面组成随机流，流的位置即顶点；`@@M@@i<j@@` 时连边当且仅当 `@@M@@a_i\perp b_j@@` 且 `@@M@@a_j\not\perp b_i@@`。线性代数立刻排除 `@@M@@K_5@@`：团中的五个点会被逼成线性无关，却又要同落在一个超平面内。而独立集恰好对应"一致序列"（consistent tuple）：`@@M@@i<j@@` 且 `@@M@@a_i\perp b_j@@` 时必有 `@@M@@a_j\perp b_i@@`。

再设熵的障碍。反设每个流都含长为 `@@M@@k=\lfloor q(\log q)^{1+\eta}\rfloor@@` 的一致序列并按某规则选出一个：无论选取规则造成多大的偏倚，固定的元组总得出现在原流的某组位置上，联合界即得熵下界 `@@M@@H(F)\ge 4\sigma\ell+\eta\ell\log\sigma-O(k)@@`（`@@M@@\sigma=\log q@@`，`@@M@@\ell=\Theta(k)@@`）。必须设法压掉盈余 `@@M@@\eta\ell\log\sigma@@`。Bradač 式直接计数要为昂贵位置支付 `@@M@@O(q\sigma^2)@@`，尺度太粗，于是改为迭代压缩：每一轮的解码器只读新消息，不携带旧上下文。

压缩的几何引擎是"稀疏对描述定理"（sparse-pair description）：若对径空间中的点集 `@@M@@S,T@@` 的关联密度远低于环境密度 `@@M@@1/q@@`，则谱关联混合（incidence mixing）先逼出 `@@M@@|S||T|\le Cq^{d+1}@@`；随后一条短消息——公共随机表（public table）中的样本行加几何数据、由若干独立泊松（Poisson）批次算出的得分——就能描述一个捕获较小集固定比例的集合 `@@M@@W@@`。标记扫描与条件熵论证表明一致序列的大多数代表对几乎无单向关联，残余碰撞被流上的矩形占位界（rectangle occupancy）用 Chernoff 界控制，于是定理可用。代表对按时间顺序挂上平衡二叉树，每个节点的新鲜关联测试只收缩子节点一端的定义域，且所有测试都在检查后代存亡之前完成验证，一个可加位势函数汇总消息总长。

最后是迭代与换算。阶段参数满足递推 `@@M@@D_{\rm new}\le\sigma^{2\beta}+D\sigma^{-\eta/4}@@`（`@@M@@\beta=\eta/10^7@@`），`@@M@@O(1/\eta)@@` 轮后 `@@M@@D\le 2\sigma^{2\beta}@@`；再压缩一轮即得 `@@M@@H(F)\le 4\sigma\ell+O(k)@@`，与熵下界矛盾，故存在无长一致序列的流。收尾用 Bertrand 公设取素数 `@@M@@q\approx t/(4(\log t)^{1+\eta})@@`，得 `@@M@@r(5,t)>t^4/(512(\log t)^{3+4\eta})@@`，令 `@@M@@\eta=\varepsilon/8@@` 便完成主定理。

## 可信度与备注

本文主结果暂无 Lean 形式化证明，OpenAI 官方声明"未经形式化的结果可能有问题"，请以社区核验为准。上界一侧是四十年已知的经典结果，作者仅给出初等重证，风险很低；下界的熵压缩论证链条长、参数极细（如 `@@M@@\beta=\eta/10^7@@` 量级的缝隙需逐一对账），是最需要专家逐行核验的部分。姊妹篇把同一框架推广到所有 `@@M@@s\ge6@@` 并复用本文的选择律熵界与低维稀疏对框架，两文互为印证：若此处框架有误，推广亦随之失效。

{% endraw %}
