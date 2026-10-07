---
layout: default
title: "Expected amenable subalgebras preserving core commutants"
family: "290"
discipline: "Operator algebras"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | Expected amenable subalgebras preserving core commutants

> 结果族 290：Relative bicentralizers and modular spectral recovery　·　学科：Operator algebras　·　验证状态：暂无形式化证明，请以社区核验为准

## 一句话结论

证明了 Marrakchi 的相对双中心子猜想：对任何预对偶可分、带忠实正规条件期望的包含 `@@M@@N\subset M@@`，都存在含于 `@@M@@N@@` 的可均子代数 `@@M@@P@@`，使 `@@M@@P@@` 与 `@@M@@N@@` 在连续核 `@@M@@c(M)@@` 中的交换子完全相同；并给出 Connes 双中心子猜想的又一证明。

## 问题背景

冯诺依曼代数 (von Neumann algebra) 的分类理论中，III`@@M@@_1@@` 型因子最为棘手。Connes 在内射因子分类纲领里提出双中心子 (bicentralizer) 问题：III`@@M@@_1@@` 因子上忠实正规态的双中心子是否必为标量。Haagerup 1987 年解决可均情形，完成内射 III`@@M@@_1@@` 因子唯一性定理；非可均情形长期开放，直到最近 Houdayer–Marrakchi 才宣布了不带可分性限制的定理。与此平行的是 Kadison 问题：期望包含 `@@M@@N\subset M@@` 中是否有在更大代数里仍极大交换的 MASA。Masuda 及 Ando–Haagerup–Houdayer–Marrakchi 建立了相对双中心子及其流的理论，Marrakchi 进而提出相对双中心子猜想，并证明它与"存在保持核交换子的期望可均子代数"等价。此前的技术卡点是：连续核 `@@M@@c(M)@@` 中还含有实现模作用的酉群，只控制 `@@M@@M@@` 内部的交换子并不够。

## 主要结果

主定理：设 `@@M@@N\subset M@@` 为预对偶可分的酉包含，且存在忠实正规条件期望 (faithful normal conditional expectation) `@@M@@E_N:M\to N@@`。则存在酉可均（即内射，injective）子代数 `@@M@@P\subset N@@` 与忠实正规期望 `@@M@@F:N\to P@@`，使 `@@M@@P'\cap c(M)=N'\cap c(M)@@`，其中 `@@M@@c(M)=M\rtimes_{\sigma^\varphi}\R@@` 是连续核 (continuous core)。这正面解决了相对双中心子猜想，且对任意中心和类型都成立。中间产物是绝对定理：每个预对偶可分的 III`@@M@@_1@@` 型因子 `@@M@@N@@` 与每个忠实正规态 `@@M@@\varphi@@` 满足 `@@M@@\mathrm B(N,\varphi)=\C 1@@`，即 Connes 猜想本身。推论还给出带期望的 MASA (maximal abelian subalgebra) `@@M@@A\subset N@@`，满足 `@@M@@A'\cap c(M)=c(A)\vee(N'\cap c(M))@@`，呼应 Kadison 问题的期望形式。

## 证明思路

证明先绝对、后相对。第一步证绝对定理（反证）：若某 `@@M@@\mathrm B(N,\varphi)\ne\C1@@`，用 Houdayer–Isono 的自双中心化约简，换成非平凡 III`@@M@@_1@@` 因子满足 `@@M@@M=\mathrm B(M,\varphi)@@`、`@@M@@M_\varphi=\C1@@`。取对称平移不变平均 `@@M@@m@@`，把模作用平均后的两种乘法次序做成等距 `@@M@@R,L:H\otimes H\to\mathcal H_m@@`；双正规态恒等式 (binormal state identity) 先在窄谱带上比较 `@@M@@R@@` 与 `@@M@@L@@`，再借平移协方差与谱分划拼接成全局恒等式 `@@M@@R=L\exp(iX\otimes Y)@@`，其中 `@@M@@X=\log\Delta_\varphi@@`、`@@M@@Y@@` 生成双中心子流。反射对合 `@@M@@J_0@@` 对称地给出 `@@M@@L=R\exp(iY\otimes X)@@`，两式联立得 `@@M@@\exp(iY\otimes X)\exp(iX\otimes Y)=1@@`，迫使 `@@M@@(X,Y)@@` 的联合谱满足格点约束 `@@M@@rs'+sr'\in2\pi\Z@@`：只要联合谱含两个线性无关点或张成斜线，它便可数，`@@M@@X@@` 从而有纯点谱；但标量中心化子配合 KMS 条件的初等论证表明模算子只有 `@@M@@\Omega@@` 方向的特征向量，纯点谱被排除，而 `@@M@@X=0@@`、`@@M@@Y=0@@` 又分别与模非平凡性、双中心子流的遍历性矛盾。

第二步转向相对情形。绝对定理立刻给出 `@@M@@E_N|_B=E_B|_N=\varphi(\cdot)1@@`（`@@M@@B@@` 为相对双中心子），于是未平均的乘法映射 `@@M@@R(x\Omega\otimes a\Omega)=xa\Omega@@` 与 `@@M@@L(x\Omega\otimes a\Omega)=ax\Omega@@` 本身就是 `@@M@@H\otimes K@@` 上的等距。剩下只需证压缩 `@@M@@U=L^*R@@` 等于酉算子 `@@M@@D=\exp(iX\otimes Y)@@`。第三步把任意张量长度与流位移组成的"词"打包为一个固定代数 `@@M@@\mathbf B(\mathcal H)@@` 上的完全正 (completely positive) 核 `@@M@@Z@@`，词的系数变成态的值，双正规恒等式一次用尽，给出对长度、位移、能量位置都一致的估计；核可能非正规 (nonnormal)，作者用带限 (bandlimited) 元素与谱截断论证为函数演算辩护。第四步去掉谱带限制：若 `@@M@@U\ne D@@`，取平均 `@@M@@G=(U+D)/2@@`，平行四边形恒等式表明它在差异处损失范数；用相互独立的随机平移反复"捕获"差异，捕获概率之和发散而传播误差被同一概率控制，累计期望损失超过范数预算 `@@M@@1@@`，矛盾，故 `@@M@@U=D@@`。最后看核：`@@M@@U=D@@` 是酉算子使 `@@M@@R=LD@@`，公共值域恰为 `@@M@@L^2(B\vee N)@@`；换坐标后 `@@M@@N@@` 只作用在 `@@M@@H@@` 上，双中心子流的不动点只作用在 `@@M@@K\otimes L^2(\R)@@` 上，二者必须交换，从而核中流的不动点代数等于 `@@M@@N'\cap c(M)@@`。再经弱 Dixmier 性质与 Marrakchi 的特征化定理即得 `@@M@@P@@`；一般包含用中心分解与交换仿射映射的紧凸不动点定理归约。

## 可信度与备注

本篇暂无形式化证明，请以社区核验为准。姊妹篇《Bounded recovery for modular spectral averages》用"有界恢复"路线独立证明同一绝对定理，本篇第 3 节的绝对论证与之互补并相互引用；Houdayer–Marrakchi 的同期宣布亦给出无可分性限制的绝对定理，多方互为印证。按 OpenAI 官方声明，未经形式化的结果可能存在问题，引用前宜保持审慎。

{% endraw %}
