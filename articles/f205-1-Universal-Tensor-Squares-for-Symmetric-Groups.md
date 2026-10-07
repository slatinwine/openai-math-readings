---
layout: default
title: "Universal Tensor Squares for Symmetric Groups"
family: "205"
discipline: "Algebra"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | Universal Tensor Squares for Symmetric Groups

> 结果族 205：Saxl's conjecture and universal tensor squares　·　学科：Algebra　·　验证状态：暂无形式化证明，请以社区核验为准

## 一句话结论

本文证明：除 `@@M@@n\in\{2,4,9\}@@` 外，对称群 `@@M@@S_n@@` 都存在一个不可约表示，其张量平方包含该群的全部不可约表示，从而肯定地解决了 Pak–Panova–Vallejo 提出的对称群张量平方猜想（tensor square conjecture）。

## 问题背景

对称群 `@@M@@S_n@@` 的不可约复表示由 `@@M@@n@@` 的分拆（partition）`@@M@@\lambda\vdash n@@` 分类，即 Specht 模 `@@M@@S^\lambda@@`。两个不可约表示的张量积如何分解，其重数由 Kronecker 系数（Kronecker coefficient）`@@M@@g(\lambda,\mu,\nu)=\dim\Hom_{S_n}(S^\nu,S^\lambda\otimes S^\mu)@@` 刻画，这是表示论中著名的老大难问题，至今没有一般的组合公式。2013 年 Pak、Panova 与 Vallejo 提出张量平方猜想：对 `@@M@@n\ge3@@`、`@@M@@n\ne4,9@@`，某个不可约表示的张量平方应包含所有不可约表示。与之相关的 Saxl 猜想（Saxl 于 2012 年 3 月 20 日在 UCLA 组合讨论班上提出）则更具体：在三角度数 `@@M@@N_m=m(m+1)/2@@` 上，阶梯分拆 `@@M@@\rho_m=(m,m-1,\ldots,1)@@` 的张量平方就有这种普适性。此前 Ikenmeyer 证明了与阶梯可比较（dominance order）的分拆都被覆盖，Luo–Sellke 证明了阶梯平方包含"几乎所有"分拆，Harman 与 Ryba 证明了张量立方情形，Bessenrodt、Li 等用自旋特征标方法处理了双钩、三钩目标；但非三角度数下的完全覆盖始终无人攻克，这正是本文补上的缺口。

## 主要结果

**主定理**：对每个正整数 `@@M@@n\notin\{2,4,9\}@@`，存在分拆 `@@M@@\lambda\vdash n@@`，使得对一切 `@@M@@\nu\vdash n@@` 都有 `@@M@@g(\lambda,\lambda,\nu)>0@@`。换言之，一个不可约表示 `@@M@@S^\lambda@@` 的张量平方 `@@M@@S^\lambda\otimes S^\lambda@@`（对角作用）包含 `@@M@@S_n@@` 的每一个不可约表示。关键在于 `@@M@@\lambda@@` 对每个度数是先固定好的，不随目标 `@@M@@\nu@@` 变化。由于符号表示（sign representation）必须出现，而 `@@M@@g(\lambda,\lambda,(1^n))>0@@` 当且仅当 `@@M@@\lambda@@` 自共轭（self-conjugate），构造必须保持自共轭性。文中还给出推论：借助 Letellier 的非负性定理，同样的分拆标签给出一般线性群 `@@M@@\GL_n(\mathbb F_q)@@` 上单幂歧表示（unipotent representation）的普适张量平方：`@@M@@U_q^{\lambda_n}\otimes U_q^{\lambda_n}@@` 对每个素数幂 `@@M@@q@@` 都包含所有 `@@M@@U_q^\nu@@`。

## 证明思路

证明的策略是"先造一个候选、再给两个充分判据、最后用容量计数与精确计算清扫剩余情形"。第一步，对每个度数 `@@M@@n@@` 固定一个自共轭候选 `@@M@@L@@`：取与 `@@M@@n@@` 同奇偶的最大三角数 `@@M@@N_M\le n@@`，把余量 `@@M@@2r@@` 以"转置匹配"的方式加在前两行与前两列，得到列长为 `@@M@@(M+b+s-1,\ M-1+b,\ M-2,\ldots,3,\ 2^{b+1},\ 1^s)@@` 的自共轭图；`@@M@@M\ge9@@` 时该构造有效，否则 `@@M@@n\le64@@` 留待计算处理。第二步不直接计算 Kronecker 系数，而是在张量平方里显式造向量，再用对偶多表元（dual polytabloid）收缩检验非零。带判据（band criterion）在第一因子沿行、第二因子沿列做交错，得到型为 `@@M@@L\otimes L@@` 的循环子模；随后用一个"标记字母"坐标投影，把图形分离成小三角（`@@M@@M-2@@` 阶阶梯）、一条宽二的带和两块附加图。坐标扇区诱导引理表明投影像是完整的诱导模 `@@M@@\Ind_{S_D\times S_F}^{S_B}(W_{M-2}\boxtimes U_F)@@`，而姊妹篇的循环阶梯定理恰好供应 `@@M@@D@@` 上的全部成分，于是由分支法则（branching rule）只需在目标 `@@M@@\lambda@@` 内找一个被支撑的补图 `@@M@@\mu@@`。带是一条奇长度路径，其收缩等于一串 `@@M@@2\times2@@` 矩阵与伴随矩阵（adjugate）乘积的 `@@M@@(1,1)@@` 元：利用恒等式 `@@M@@JY^{\mathsf T}J=-\adj(Y)@@` 与两两反交换的基 `@@M@@\{I,Z,T,J\}@@`，逐段交错后每段都是可逆矩阵，故可取公共基使总收缩非零。两块附加图则用非退化对称型与 Littlewood–Richardson 分裂处理，并刻意把附加柱放在远离路径端点处，使所有混合赋值为零、总收缩因式分解为两个非零因子，从而避开相消。平衡判据（balance test）在整个方格上做列交错，用"数字与和值"双重投影补充覆盖前四行或前四列总和较小的目标。第三步是覆盖论证：若目标在两个方向上都不满足带判据，则其行、列前缀同时被约束，容量引理（一个纯组合的面积估计）迫使图的面积小于 `@@M@@n@@`，矛盾；这纯理论地解决了 `@@M@@M\ge22@@`，而 `@@M@@9\le M\le21@@` 中仅剩 19 对参数 `@@M@@(M,r)@@` 由 Python 程序精确枚举（每个剪枝规则均有可靠性证明）。最后，`@@M@@n\le64@@` 的所有度数用 Murnaghan–Nakayama 递归在素数域 `@@M@@\mathbb F_p@@`（`@@M@@p\in\{1000000007,1000000009\}@@`）中精确计算整个 Kronecker 系数向量——非零剩余即认证正重数，无需重建整数本身。各部分在完成一节合并，得到主定理。

## 可信度与备注

本文主结果暂无 Lean 形式化证明，且证明包含两块计算机辅助验证（Python 容量检查与 C++ 特征标计算）；作者对程序所用的每条测试与剪枝规则给出了数学可靠性论证，并附完整源代码、执行记录与独立复核工具，但结论仍属"未经机器形式化的人写证明+可复现计算"。它与本结果族的姊妹篇《A Cyclic Polytabloid Proof of Saxl's Conjecture》互相支撑：该篇证明的循环形式阶梯定理正是本文从三角度数推广到全部度数的关键输入；那篇主结果已 Lean 形式化，而本文的普适度数结论尚待社区核验。按 OpenAI 官方声明，未经形式化的结果可能有问题，请读者以此为准绳审慎看待。

{% endraw %}
