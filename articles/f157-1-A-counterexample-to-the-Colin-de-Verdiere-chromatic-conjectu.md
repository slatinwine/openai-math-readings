---
layout: default
title: "A counterexample to the Colin de Verdière chromatic conjecture"
family: "157"
discipline: "Combinatorics"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | A counterexample to the Colin de Verdière chromatic conjecture

> 结果族 157：Graph coloring, clique minors, and Colin de Verdière invariants　·　学科：Combinatorics　·　验证状态：暂无形式化证明，请以社区核验为准

## 一句话结论
构造出独立数至多 2、且其上任何"良符号、恰一个负特征值"的实对称矩阵秩都超过 `@@M@@m/2+1@@` 的任意大图，从而 `@@M@@\mu(G)+1<m/2\le\chi(G)@@`：Colin de Verdière 染色猜想 `@@M@@\chi(G)\le\mu(G)+1@@` 及其分数版本被否定。

## 问题背景
Colin de Verdière 不变量 `@@M@@\mu(G)@@` 源自 1990 年前后对图上薛定谔算子的谱研究。称实对称矩阵 `@@M@@M@@` 对图 `@@M@@G@@` 良符号（well-signed），若 `@@M@@M_{uv}<0@@` 当且仅当 `@@M@@uv\in E@@`（非边则取 0），对角元任意；若 `@@M@@M@@` 还恰有一个负特征值并满足强 Arnold 性质（Strong Arnold Property，来自谱横截性条件），则这些矩阵核维数的最大值就是 `@@M@@\mu(G)@@`。该不变量的小值有几何意义：`@@M@@\mu\le2@@` 刻画外可平面图，`@@M@@\mu\le3@@` 刻画可平面图，`@@M@@\mu\le4@@` 刻画无链嵌入（linklessly embeddable）图；且在 `@@M@@\mu\le4@@` 范围内染色界 `@@M@@\chi\le\mu+1@@` 成立。由 `@@M@@\mu@@` 的子式单调性与 `@@M@@\mu(K_t)=t-1@@`（取矩阵 `@@M@@-J_t@@` 即可）可得 `@@M@@h(G)\le\mu(G)+1@@`，故 Hadwiger 猜想蕴含 Colin de Verdière 染色猜想。这一谱不变量究竟能保留多少染色信息，是悬置多年的试金石问题；本文给出否定回答。

## 主要结果
定理 1.2：存在任意大的图 `@@M@@G@@` 满足
`@@M@@D\alpha(G)\le2,\qquad \mu(G)+1<\frac{|V(G)|}{2}\le\chi(G).@@`
证明实际建立了更强的矩阵障碍：在这些图上，任何良符号、恰一个负特征值的矩阵——不要求强 Arnold 性质——秩都严格大于 `@@M@@|V(G)|/2+1@@`；由秩–零化度关系，核维数小于 `@@M@@m/2-1@@`。这同时对 Lovász–Schrijver 考虑的更大参数 `@@M@@\kappa@@`（该类矩阵的最大余核）给出 `@@M@@\kappa(G)+1<m/2@@`。推论 1.5 给出分数染色链
`@@M@@D\chi_f(G)\ge\frac{|V(G)|}{\alpha(G)}\ge\frac m2>\kappa(G)+1\ge\mu(G)+1\ge h(G),@@`
故分数 Colin de Verdière 染色界与 Reed–Seymour 的分数 Hadwiger 弱化一并失效；结合姊妹篇的 `@@M@@\chi_{\mathrm{list}}(G)\le Ch(G)@@` 还得到 `@@M@@\chi_{\mathrm{list}}(G)\le C(\mu(G)+1)@@`。

## 证明思路
构造分两大块。第一大块是基础图（base graph），沿用姊妹篇的帧/洞机器：顶点是二元域 `@@M@@\mathbb F_2@@` 上的单射帧，洞（hole）由共享张量加两条相容的仿射梯度方程加一个奇偶条件认证，沿三角形对方程求和即得矛盾，故洞关系无三角形、补图独立数至多 2。相对姊妹篇的新概率部件是信道稀疏化（channel thinning）：把原始律 `@@M@@\rawlaw@@` 的条件信道律换成稀疏律 `@@M@@\pi@@`，精确保持原帧边际，同时惩罚信道组合的指定非零平移，把困难的相位二择一转化为具有固定正测度相容点对的情形。由此得到区分颜色的冲突超饱和：定理（基础图）之 (G1) 说，大小至少 `@@M@@m/20@@` 的匹配分成大小至多 `@@M@@am@@` 的类后，不同类中必有冲突边对；(G2) 是非对称的边–点版本，`@@M@@\beta m@@` 规模的匹配与 `@@M@@\beta m@@` 规模的点集之间必存在冲突的边–点对；(G3) 说任意两个 `@@M@@\beta m@@` 点集之间必有交叉洞。把两个分布测试经熵指纹论证（Kleitman–Winston 程序、以 Csiszár 约束熵最小为势能、能量增量弱正则化）搬到有限样本，即得基础图，图阶 `@@M@@m=2^{C_0gN}@@`。

第二大块是团膨胀（clique blow-up）`@@M@@H[s]@@` 上的矩阵判据：把 `@@M@@H@@` 的每个点换成 `@@M@@s@@` 点团，独立数至多 2 保持，`@@M@@\chi\ge ms/2@@`。关键在于先固定基础图、再让 `@@M@@s\to\infty@@`。矩阵论证用超平坦面的有限树表示找到可同时规范化的大块族：第一次谱规范化产生坐标的近似完美匹配，第二次规范化从选出的配对块中提取额外的正方向，由此得到的秩增益与"核约占总维数一半"矛盾，于是性质 (G1)–(G3) 迫使 `@@M@@H[s]@@` 上任何良符号单负矩阵的秩大于 `@@M@@ms/2+1@@`。该判据只依赖所列图性质，可独立于张量构造使用；其内部谱规范化计算技术性较强，此处从略。最后由秩–零化度关系得 `@@M@@\mu(G)+1<ms/2\le\chi(G)@@`。

## 可信度与备注
主结果暂无 Lean 形式化证明；OpenAI 官方声明"未经形式化的结果可能有问题"，请以社区核验为准。本文与 Hadwiger 反例篇共享帧/洞与矩构造，但矩阵秩障碍是直接证明的，并不由团子式障碍推出；列表染色篇从正面补上线性界。三篇合观：`@@M@@\chi\le h\le\mu+1@@` 的系数 1 断言失败，而线性松弛 `@@M@@\chi_{\mathrm{list}}\le Ch\le C(\mu+1)@@` 成立。

{% endraw %}
