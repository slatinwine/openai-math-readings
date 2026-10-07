---
layout: default
title: "A counterexample to Hadwiger's conjecture"
family: "157"
discipline: "Combinatorics"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | A counterexample to Hadwiger's conjecture

> 结果族 157：Graph coloring, clique minors, and Colin de Verdière invariants　·　学科：Combinatorics　·　验证状态：暂无形式化证明，请以社区核验为准

## 一句话结论
构造出独立数至多 2、连通匹配数却不足 \(m/100\) 的任意大图 \(G\)，由此 \(h(G)<26m/75+2/3<m/2\le\chi_f(G)\le\chi(G)\)：1943 年的 Hadwiger 猜想及其分数染色弱化形式被一并推翻。

## 问题背景
Hadwiger 猜想（1943）断言每个有限非空简单图的色数 \(\chi(G)\) 不超过其 Hadwiger 数 \(h(G)\)，即最大团子式（clique minor）\(K_t\) 的阶数 \(t\)。小 \(t\) 情形都是对的：\(t=4\) 由 Hadwiger 与 Dirac 证明，\(t=5\) 经 Wagner 结构定理等价于四色定理，\(t=6\) 由 Robertson、Seymour 与 Thomas 于 1993 年解决。对一般 \(t\)，Kostochka 与 Thomason 的密度界给出 \(O(t\sqrt{\log t})\) 种颜色，此后不断改进，目前最好结果为 \(O(t\log\log\log t)\)（Liu–Luo，2026），离线性仍有对数鸿沟。独立数（independence number）\(\alpha(G)\le2\) 的情形备受关注：Plummer–Stiebitz–Toft 证明此时猜想等价于"\(m\) 个点的图必含 \(K_{\lceil m/2\rceil}\) 子式"。而 Duchet–Meyniel 只证得 \(h(G)\ge m/3\)，Fox 加强到 \(m/3+c\,m^{4/5}(\log m)^{1/5}\)，距 \(m/2\) 一步之遥却久攻不下。本文证明：这一步其实跨不过去。

## 主要结果
定理 1.1：存在任意大的整数 \(m\) 与 \(m\) 点有限简单图 \(G\)，同时满足
\[\alpha(G)\le2,\qquad \mathrm{cm}(G)<\frac{m}{100},\]
其中 \(\mathrm{cm}(G)\) 是连通匹配数（connected matching），即两两接触（touching，共享端点或两端点集之间有边相连）的匹配的最大规模。作者进一步证明计数不等式
\[h(G)\le\frac{|V(G)|+4\,\mathrm{cm}(G)+2}{3}\]
（大的团子式中大量分支集取单点或双边，必然导出大连通匹配）。由于每个色类至多含 \(\alpha(G)\) 个点，对分数染色数 \(\chi_f(G)\)（fractional chromatic number）同样有 \(\chi_f(G)\ge m/\alpha(G)\)，于是推论 1.2 给出：任意大的图满足
\[h(G)<\frac{26m}{75}+\frac23<\frac m2\le\chi_f(G)\le\chi(G).\]
因此 Hadwiger 猜想不真；Reed–Seymour 1998 年讨论的分数弱化——无 \(K_{p+1}\) 子式的图应有分数 \(p\) 染色（他们只证得 \(2p\) 界）——同样被否定。历史章节还指出，Füredi–Gyárfás–Simonyi 的精确连通匹配猜想也随之失效。

## 证明思路
构造分三层。第一层用代数定义"洞"（hole，即缺失的边）。从有限概率空间采样 \(m\) 个位置，两点相邻当且仅当它们之间没有洞。每个元素 \(i\) 带有进入公共二元向量空间的单射线性映射 \(U_i\) 与线性泛函 \(u_i\)；固定泛函 \(a\) 与对称双线性型 \(T\)，规定 \(i,j\) 有洞当且仅当存在 \(\lambda_i,\lambda_j\) 满足 \(U_i\lambda_i=U_j\lambda_j\)、\(u_jU_i=a+T(\lambda_i,\cdot)\)、\(u_iU_j=a+T(\lambda_j,\cdot)\)、\(a(\lambda_i)+a(\lambda_j)=1\)。把三条泛函恒等式沿假想的洞三角形求和：左端因共享向量条件成对抵消，双线性项因 \(T\) 的对称性成对抵消，只剩 \(1+1+1=1\)（特征 2），矛盾。故洞关系无环、无三角形，图即使采样出现重复元素也有 \(\alpha\le2\)、\(\chi\ge m/2\)，分数同理。

第二层阻止大连通匹配。两条不相交边互不接触，恰当四条交叉点对全是洞，称之为冲突。原始超饱和定理断言：任何满足边际与联合密度上界（\(\sigma_1\le M\mu\)、\(\sigma_2\le M\mu\)、\(\sigma\le2^{DN}\mu^2\)）的单位分布 \(\sigma\)，两个独立单位以至少 \(2^{-100gN}\) 的概率冲突；单位（unit）指内部无洞的点对，允许两端点强相依——这正是匹配边所需的自由度。代数部分以布尔点上单项式赋值的秩一矩 \(vv^{\top}\) 为素材：键（key，帧映射像的元组）相等给出共享张量，针（pin）保留有界个系数方向的指定像，低秩矩分解化解交叉收缩方程，碰撞判据把"四洞"化为被接受键分布的重叠。概率部分先把条件于针像的分布分解成叶子并记录小表，相位估计在正测度上给出相容表；再用直方图与乘积比较把查询律送往公共极限，有限维对偶在极限处产生重叠的标量配方；测度极小的分支另用一致性大集估计处理。此段技术性较强，此处从略。

第三层把分布命题搬到有限图：以 Csiszár 信息投影（相对熵最小化）为势能运行 Kleitman–Winston 式指纹算法，超饱和保证每步删去足够大的冲突邻域；当不再有可行律时，用 Ford–Fulkerson 容量割把剩余单位族覆盖成小端点集加小点对集。最后采样 \(m=2^{C_0gN}\) 个位置，以 \(1-\exp(-\Omega(m))\) 的概率同时实现 \(\alpha\le2\) 与 \(\mathrm{cm}<m/100\)，定理得证。

## 可信度与备注
主结果暂无 Lean 形式化证明；OpenAI 官方声明"未经形式化的结果可能有问题"，请以社区核验为准。姊妹篇用同一套帧/洞机器证明 Colin de Verdière 染色猜想 \(\chi\le\mu+1\) 亦不成立，并给出一条独立的矩阵秩路线同样违反 Hadwiger 不等式；另一姊妹篇则证明线性列表染色界 \(\chi_{\mathrm{list}}(G)\le Ch(G)\) 成立。三篇合观：Hadwiger 猜想的失败只在系数 1，线性松弛仍然正确。

{% endraw %}
