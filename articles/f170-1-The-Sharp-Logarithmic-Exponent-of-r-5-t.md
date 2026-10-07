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

## 一句话结论

本文证明了 \(r(5,t)=t^4/(\log t)^{3+o(1)}\)：非对角拉姆齐数（off-diagonal Ramsey number）在 \(s=5\) 时的对数指数被精确确定为 \(3\)，下界终于追平 Ajtai–Komlós–Szemerédi 的经典上界，只差 \(o(1)\) 的幂。

## 问题背景

拉姆齐数 \(r(s,t)\) 是最小的 \(n\)，使得任意 \(n\) 个顶点的图中必出现 \(s\) 团（clique \(K_s\)）或 \(t\) 个顶点的独立集（independent set）。固定 \(s\)、让 \(t\to\infty\) 的非对角情形是极值图论最古老的定量问题之一。上界一侧早已定型：Erdős–Szekeres（1935）的二项式界被 Ajtai–Komlós–Szemerédi（1980）改进为 \(O(t^{s-1}/(\log t)^{s-2})\)，Li–Rousseau–Zang（2001）又把主导常数做到 \(1+o(1)\)。下界一侧却步履蹒跚：Kim（1995）只解决了 \(s=3\)；对 \(s=5\)，Spencer（1977）的局部引理方法与 Bohman–Keevash（2010）对随机无团过程的最好分析给出的都只有 \(t^3\) 的量级，连上界中 \(t\) 的四次幂都够不着。有限几何带来转机：Mattheus–Verstraëte（2024）用 Hermitian unital 构造证得 \(r(4,t)\ge ct^3/(\log t)^4\)，Bradač（2026）把射影构造推广到 \(r(s,t)\ge c_s t^{s-1}/(\log t)^{2s-4}\)——多项式指数就此确定，但对数幂仍差一倍（\(s=5\) 时是 \(6\) 对 \(3\)）。本文把这一缺口完全闭合。

## 主要结果

主定理：存在绝对常数 \(C>0\)，使得对任意 \(\varepsilon>0\) 与一切充分大的 \(t\)，

\[\frac{t^4}{(\log t)^{3+\varepsilon}}\ \le\ r(5,t)\ \le\ C\,\frac{t^4}{(\log t)^3}.\]

等价地，\(\lim_{t\to\infty}\frac{4\log t-\log r(5,t)}{\log\log t}=3\)。上界是经典结果的初等重证，作者用 Alon 的一致独立集（uniform independent set）方法加随机抽样给出自足证明；真正的突破在下界：对每个 \(0<\eta<1/10\) 与充分大的素数 \(q\)，构造出 \(\lfloor q^4\log q\rfloor\) 个顶点、无 \(K_5\) 且独立数小于 \(q(\log q)^{1+\eta}\) 的图。定理并未确定 \(t^4/(\log t)^3\) 的常数因子，作者明确将其留作公开问题。

## 证明思路

先看构造。在四维射影空间 \(\PG(4,q)\) 上，一个"旗"（flag）是入射对 \((a,b)\)：点 \(a\) 落在超平面 \(b\) 上。独立均匀地抽取 \(N=\lfloor q^4\log q\rfloor\) 面组成随机流，流的位置即顶点；\(i<j\) 时连边当且仅当 \(a_i\perp b_j\) 且 \(a_j\not\perp b_i\)。线性代数立刻排除 \(K_5\)：团中的五个点会被逼成线性无关，却又要同落在一个超平面内。而独立集恰好对应"一致序列"（consistent tuple）：\(i<j\) 且 \(a_i\perp b_j\) 时必有 \(a_j\perp b_i\)。

再设熵的障碍。反设每个流都含长为 \(k=\lfloor q(\log q)^{1+\eta}\rfloor\) 的一致序列并按某规则选出一个：无论选取规则造成多大的偏倚，固定的元组总得出现在原流的某组位置上，联合界即得熵下界 \(H(F)\ge 4\sigma\ell+\eta\ell\log\sigma-O(k)\)（\(\sigma=\log q\)，\(\ell=\Theta(k)\)）。必须设法压掉盈余 \(\eta\ell\log\sigma\)。Bradač 式直接计数要为昂贵位置支付 \(O(q\sigma^2)\)，尺度太粗，于是改为迭代压缩：每一轮的解码器只读新消息，不携带旧上下文。

压缩的几何引擎是"稀疏对描述定理"（sparse-pair description）：若对径空间中的点集 \(S,T\) 的关联密度远低于环境密度 \(1/q\)，则谱关联混合（incidence mixing）先逼出 \(|S||T|\le Cq^{d+1}\)；随后一条短消息——公共随机表（public table）中的样本行加几何数据、由若干独立泊松（Poisson）批次算出的得分——就能描述一个捕获较小集固定比例的集合 \(W\)。标记扫描与条件熵论证表明一致序列的大多数代表对几乎无单向关联，残余碰撞被流上的矩形占位界（rectangle occupancy）用 Chernoff 界控制，于是定理可用。代表对按时间顺序挂上平衡二叉树，每个节点的新鲜关联测试只收缩子节点一端的定义域，且所有测试都在检查后代存亡之前完成验证，一个可加位势函数汇总消息总长。

最后是迭代与换算。阶段参数满足递推 \(D_{\rm new}\le\sigma^{2\beta}+D\sigma^{-\eta/4}\)（\(\beta=\eta/10^7\)），\(O(1/\eta)\) 轮后 \(D\le 2\sigma^{2\beta}\)；再压缩一轮即得 \(H(F)\le 4\sigma\ell+O(k)\)，与熵下界矛盾，故存在无长一致序列的流。收尾用 Bertrand 公设取素数 \(q\approx t/(4(\log t)^{1+\eta})\)，得 \(r(5,t)>t^4/(512(\log t)^{3+4\eta})\)，令 \(\eta=\varepsilon/8\) 便完成主定理。

## 可信度与备注

本文主结果暂无 Lean 形式化证明，OpenAI 官方声明"未经形式化的结果可能有问题"，请以社区核验为准。上界一侧是四十年已知的经典结果，作者仅给出初等重证，风险很低；下界的熵压缩论证链条长、参数极细（如 \(\beta=\eta/10^7\) 量级的缝隙需逐一对账），是最需要专家逐行核验的部分。姊妹篇把同一框架推广到所有 \(s\ge6\) 并复用本文的选择律熵界与低维稀疏对框架，两文互为印证：若此处框架有误，推广亦随之失效。

{% endraw %}
