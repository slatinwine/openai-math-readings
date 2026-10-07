---
layout: default
title: "Ambiently homeomorphic isolated hypersurfaces of multiplicities two and three"
family: "059"
discipline: "Algebraic and complex geometry"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | Ambiently homeomorphic isolated hypersurfaces of multiplicities two and three

> 结果族 059：Counterexamples to Zariski's multiplicity conjecture　·　学科：Algebraic and complex geometry　·　验证状态：暂无形式化证明，请以社区核验为准

## 一句话结论

构造出两个约化、加权齐次、带孤立临界点的超曲面芽，可由环境空间（ambient space）的同胚相互变换，重数却是 2 与 3——这否定了 Zariski 重数猜想的嵌入拓扑版本，并连带否定 Arnold 余秩问题与拓扑右等价重数猜想。

## 问题背景

Zariski 在 1971 年提出重数问题：若 `@@M@@\C^N@@` 中两个约化超曲面芽（hypersurface germ）`@@M@@V(f)@@`、`@@M@@V(g)@@` 能被原点邻域的同胚互变（嵌入拓扑等价），它们的重数（multiplicity，即定义函数最低次项的次数）是否必相等？对平面曲线，经典的分支特征数据理论给出肯定答案；A'Campo–Lê 定理说明与光滑芽等价的芽自身光滑，排除重数 1 参与不等对；Greuel–O'Shea 与 Bobadilla–Pełka 在 `@@M@@\mu@@` 常值形变框架下证明了等重性，Yau、Fernandes–Jelonek–Sampaio 等则在低维或双 Lipschitz 度量假设下有正面结果。卡点在于：拓扑不变量（Milnor 纤维化、单项性算子、Seifert 形式）与从方程最低次项读出的重数分属两个世界，此前无法把它们彻底"解耦"。

## 主要结果

定理：存在 8 的倍数的有限维数 `@@M@@N>3@@` 与实系数、约化、正有理权重的加权齐次多项式 `@@M@@f_1,f_2\in\R[z_1,\dots,z_N]@@`，使得三者同时成立：各以原点为唯一临界点（isolated critical point）；`@@M@@\ord_0 f_1=2@@` 而 `@@M@@\ord_0 f_2=3@@`；存在环境对芽的同胚 `@@M@@(\C^N,V(f_1),0)\cong(\C^N,V(f_2),0)@@`。推论进一步给出：存在同胚芽 `@@M@@\varphi@@` 使 `@@M@@f_1=f_2\circ\varphi@@`（拓扑右等价，topological right equivalence），故重数及其模 2 奇偶性都不是右拓扑不变量；两芽的 Hessian 余秩（corank）分别为 `@@M@@N-16E@@` 与 `@@M@@N@@`，否定 Arnold 余秩问题；各加一个平方 `@@M@@t^2@@` 后，初始形式的 Milnor 纤维零维整同调分别为 `@@M@@\Z@@` 与 `@@M@@\Z^2@@`，否定 Budur–Fernández de Bobadilla–Lê–Nguyen 的初始形式纤维同伦猜想。

## 证明思路

证明分四步，核心困难是让整 Seifert 形式完全相同而普通次数不同。先做算术种子：取 `@@M@@d=3^{11}@@`，对与 3 互素的 `@@M@@b@@` 定义有理数 `@@M@@A_b,R_b@@`；素数赋值矩阵经模 1009 消元得到可机器复算的秩证书，从而有整数关系 `@@M@@e_b@@`（总和 `@@M@@E>0@@`）使 `@@M@@\prod A_b^{e_b}=\prod R_b^{e_b}=1@@`。再用辗转相除把每个权重 `@@M@@c/D@@` 补成链多项式（chain）`@@M@@x_1^{a_1}x_2+\cdots+x_\ell^{a_\ell}@@`，按带符号权重表分配变量：第二侧多出 `@@M@@4E@@` 个变量，第一侧补 `@@M@@4E@@` 个平方，于是两侧重数分别为 2 与 3。借助傅里叶反演与三倍角余切恒等式验证两组谱（spectrum）模 2 相等，再用 Steenbrink–Némethi 的谱对分类得实 Seifert 形式同构，用 Orlik–Randell–Hertling–Mase 关于链奇点的定理得整单项性（monodromy）模同构——但这两个同构互不兼容。其次做张量方与局部–整体下降：加上 `@@M@@x^5+y^7@@` 使单项性阶奇且无特征值 1，对称化 `@@M@@B=ST^r@@`（`@@M@@2r\equiv1@@`）后取第一次张量方；奇素数处用有限算子代数里的平方根与二平方和构造等距，素数 2 处用非分歧 hermitian 模按秩唯一性，得到每个 `@@M@@\Z_\ell@@` 上的等变等距，再由 Hasse–Minkowski 得有理等距。接着取第二次张量方：实系数给出反转单项性的整对合（复共轭），一个精确的行列式恒等式把局部图与有理图的偏差在每个特征空间上消为 1；另加六个三次幂使各特征空间上的 hermitian 形不定，加 `@@M@@z^{11}+y^{13}@@` 排除实特征值，于是等距群成为特殊酉群之积——连通、单连通、实位置非紧，Platonov 强逼近定理便给出同时满足所有局部格条件的 rational 点，合成出一个整的等变 Seifert 形式等距。最后回到几何：取 `@@M@@f_j@@` 为四份 `@@M@@q_j@@` 副本、六个三次幂与 `@@M@@x^{11}+y^{13}@@` 之和（变量互不相交，`@@M@@N=4s_0+16\equiv0\pmod 8@@`），Thom–Sebastiani–Sakamoto 定理保证其 Seifert 数据恰为上述张量数据；由于每个分圆指标都含两个不同素因子，`@@M@@\det(1-T)=1@@`，Wang 序列与 Alexander 对偶表明链环（link）是同伦球面、结点为简单结（simple knot），Levine 的高维纽结分类把整 Seifert 同余转化为链环的环境同痕，加权锥坐标再把它扩展成原点邻域上的环境同胚。

## 可信度与备注

本结果未经 Lean 形式化；OpenAI 官方声明"未经形式化的结果可能有问题"，请以社区核验为准。算术核心附带一份只用整数运算与模 1009 消元的有限证书程序，可独立复算；其余构造与行列式计算均在文中完整证明，所引经典定理（Milnor、Steenbrink、Levine、Platonov 等）均先核对了假设。同族姊妹篇把反例推进到 `@@M@@\C^4@@` 中重数 4 与 5、且为收敛全纯芽，与本篇的高维反例互相印证，两篇合计覆盖嵌入同胚、拓扑右等价与初始形式纤维三类问题。

{% endraw %}
