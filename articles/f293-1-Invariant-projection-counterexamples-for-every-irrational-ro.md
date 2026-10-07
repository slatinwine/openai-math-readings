---
layout: default
title: "Invariant-projection counterexamples for every irrational rotation"
family: "293"
discipline: "Operator algebras"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | Invariant-projection counterexamples for every irrational rotation

> 结果族 293：Invariant projections, hyperinvariant subspaces, and transitive algebras　·　学科：Operator algebras　·　验证状态：暂无形式化证明，请以社区核验为准

## 一句话结论

对任意事先指定的无理角 `@@M@@\theta@@`，本文构造了仅在一点为零、对数积分为 `@@M@@-\infty@@` 的连续圆权 `@@M@@f@@`，使超有限 `@@M@@\mathrm{II}_1@@` 因子中的加权旋转 `@@M@@T_f=Uf(V)@@` 没有任何非平凡不变投影，否定回答了 Zhu–Fang–Shi 的公开问题。

## 问题背景

设 `@@M@@\theta\in(0,1)@@` 无理。满足 `@@M@@VU=e^{2\pi i\theta}UV@@` 的酉算子 `@@M@@U,V@@` 生成的冯·诺依曼代数 `@@M@@R_\theta@@`，即无理旋转的群测度空间构造——超有限 `@@M@@\mathrm{II}_1@@` 因子（hyperfinite factor of type `@@M@@\mathrm{II}_1@@`）。对圆周 `@@M@@\T@@` 上连续函数 `@@M@@f@@` 记 `@@M@@T_f=Uf(V)@@`；闭不变子空间称为隶属（affiliated）于 `@@M@@R_\theta@@`，若其正交投影 `@@M@@p@@` 属于 `@@M@@R_\theta@@`，此时不变性等价于 `@@M@@(1-p)T_fp=0@@` 且 `@@M@@0<\tau(p)<1@@`。Fuglede–Kadison 判别式（determinant）`@@M@@\Delta(f(V))=\exp(\int_\T\log|f|\,dm)@@` 是主要工具：Haagerup–Schultz 理论为 Brown 谱测度（Brown measure）非点质量的算子配上非平凡投影，判别式为零时该测度塌缩为点质量，此路只剩平凡投影。Zhu、Fang、Shi 已造出单零点、零判别式的连续权，却无法排除投影，于是问：若 `@@M@@f@@` 几乎处处非零、`@@M@@|f|@@` 非常值且判别式为零，`@@M@@T_f@@` 是否必有非平凡的隶属不变子空间？本文对每个无理角给出否定答案。

## 主要结果

主定理：对每个无理 `@@M@@\theta\in(0,1)@@`，存在连续函数 `@@M@@f:\T\to[0,1]@@`，满足 `@@M@@f^{-1}(\{0\})=\{1\}@@`、`@@M@@\int_\T\log f\,dm=-\infty@@`，且任意满足 `@@M@@(1-p)Uf(V)p=0@@` 的投影 `@@M@@p\in R_\theta@@` 必为 `@@M@@0@@` 或 `@@M@@1@@`。角度先固定、后构造，不加任何丢番图（Diophantine）条件；结论限于因子 `@@M@@R_\theta@@` 内的投影，一般不变子空间的投影未必落在该因子内。推论：所得 `@@M@@T_f@@` 非零且范数拟幂零（norm-quasinilpotent），即 `@@M@@\|T_f^n\|^{1/n}\to0@@`。再由"超不变子空间的投影必属于包含算子的因子"即得：每个可分无穷维复 Hilbert 空间上都有非零、范数拟幂零、无超不变子空间的有界算子，其交换子代数是传递（transitive）代数。

## 证明思路

第一步造可测障碍。取整除列 `@@M@@q_0\mid q_1\mid\cdots@@` 与代价 `@@M@@c_i@@`，令 `@@M@@g_*(x)=\sum_{i\ge1}c_i\lfloor\{q_ix\}+\{q_i\theta\}\rfloor@@`、`@@M@@f_*=e^{-g_*}@@`：级数几乎处处有限而积分发散。反设存在非平凡不变投影，它在移位表示下化为投影场；有限迹与遍历性迫使对角元 `@@M@@r(x)@@` 几乎处处落于 `@@M@@(0,1)@@`，故投影与其补各有一个中心坐标非零的向量，不变性在其上给出精确的加权正交（卷积）恒等式：先沿旋转轨道，再传到耦合点对。

第二步是卷积障碍。把恒等式截断到窗口 `@@M@@|v|\le K_j@@`：截断部分是两个 Laurent 多项式之积的系数，多项式系数引理保证其在某个概率不小于 `@@M@@c_*@@` 的事件上总和不小于 `@@M@@\varepsilon_j>0@@`——有限块不可能太小。无穷尾则须小到无法抵消：权的下落稀疏到不扰动所选窗口，又陡峭到压制窗外贡献。关键是对两个端点分别作条件概率估计，使无穷尾部无需并集界即可求和，最终得 `@@M@@c_*\varepsilon_j\le(2K_j+1)(e^{-L_j}+2e^{-L_j/800})\le\varepsilon_j/j@@`，矛盾。圆周特征彼此相关，故用混合进制（mixed-radix）展开提取独立数字，据 Strassen–Edwards 耦合理论造出边缘密度一致平方可积的耦合。

第三步换成连续权：把锯齿下落磨光、用单位分割把支撑搬进缩向零点的弧段、再补上在零点发散的背景代价，全部修正恰为常数 `@@M@@1@@` 加可测上边缘（coboundary）`@@M@@b\circ\sigma-b@@`。乘子 `@@M@@H_b@@`（第 `@@M@@k@@` 坐标乘 `@@M@@e^{b(\sigma^kx)}@@`）正、单射且隶属于因子，满足 `@@M@@H_bT_f=e^{-1}T_*H_b@@`；谱截断与极分解的迹守恒论证表明，`@@M@@T_f@@` 的不变投影都被传送为 `@@M@@e^{-1}T_*@@` 的同迹不变投影——后者已被排除，障碍遂转移至连续权。

第四步证拟幂零：无理旋转对连续函数的平均一致收敛于其积分，而 `@@M@@\|T_f^n\|@@` 等于轨道乘积的上确界，故被 `@@M@@e^{-an}@@` 指数压制，谱半径为零。

## 可信度与备注

本篇暂无形式化证明。姊妹篇 Backward intertwiners and a transitive commutant 用 2-adic 模型以不同的构造独立证得同族的存在性结论，其主结果已有 Lean 形式化；两文相互独立、互为印证。文中并指出结果与 Cho–Ko–Lee 推论 2.8 在 `@@M@@\mu=1@@` 处的论断冲突。按 OpenAI 官方声明，未经形式化的结果可能有问题，请以社区核验为准。

{% endraw %}
