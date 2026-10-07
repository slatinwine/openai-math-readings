---
layout: default
title: "Positive eigenvalues of the relative SU(2) BFSS Hamiltonian"
family: "270"
discipline: "Mathematical physics"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | Positive eigenvalues of the relative SU(2) BFSS Hamiltonian

> 结果族 270：Threshold and positive-energy bound states of the BFSS matrix model　·　学科：Mathematical physics　·　验证状态：暂无形式化证明，请以社区核验为准

## 一句话结论

证明由规范不变超荷形式的闭包定义的相对 \(\mathrm{SU}(2)\) BFSS 哈密顿量有无穷多个趋于无穷、带平方可积特征向量的正特征值，从而在 \(N=2\) 处推翻了 BFSS 原文"除零能阈值态外无其他可归一化束缚态"的断言。

## 问题背景

BFSS 矩阵模型由十维超对称杨–米尔斯理论约化到一个时间维度而来；对 \(\mathrm{SU}(2)\)，去掉自由质心后剩下 27 个玻色坐标 \(x=(x^1,x^2,x^3)\in(\mathbb R^9)^3\) 与由 \(\theta_\alpha^a\)（\(\alpha=1,\dots,16\)，\(a=1,2,3\)）生成的有限维克利福德模 (Clifford module)。四次位势 \(V=\sum_{a<b}|x^a\wedge x^b|^2\) 在三个空间向量共线时取零，经典逃逸方向无界。de Wit–Lüscher–Nicolai（1989）证明其谱集为 \([0,\infty)\)，却明确留下谱集内是否嵌有可归一化态的问题；BFSS 原文（1997，式 (5.4) 之后）更断言除零能阈值态外"不可能有其他可归一化束缚态"。此前 Danielsson–Ferretti–Sundborg 只在 Born–Oppenheimer 近似下找到预期衰变的亚稳激发态，Smilga 曾在热力学分析中猜想激发态族的存在。困难在于：连续谱覆盖整个正半轴，要证明嵌入特征值 (embedded eigenvalue) 存在，必须有机制制服平坦方向上的逃逸。

## 主要结果

论文在物理希尔伯特空间 \(\mathcal H=[L^2(\mathbb R^{27};\mathcal F)]^{\mathrm{SU}(2)}\)（规范不变部分）上，取规范不变紧支撑光滑函数核 \(\mathcal C\)，定义超荷形式 \(q(\Psi)=\frac1{16}\sum_{\alpha=1}^{16}\|Q_\alpha\Psi\|^2\)；其闭包对应非负自伴算子 \(H\)，即相对 \(\mathrm{SU}(2)\) BFSS 哈密顿量的精确定义。

**主定理**：存在规范正交序列 \(\Psi_j\in\mathrm{Dom}(H)\) 与实数 \(E_j>0\)、\(E_j\to\infty\)，使 \(H\Psi_j=E_j\Psi_j\)；特别地，点谱 \(\sigma_{\mathrm p}(H)\cap(0,\infty)\) 无穷。

这些特征值嵌在连续谱 \([0,\infty)\) 之内却拥有 \(L^2\) 特征向量，是货真价实的束缚态，而不仅是谱集的一部分。

## 证明思路

证明分三层：先给出形式的显式展开；再借旋转对称性切入高权扇区并证明横向囚禁；最后构造无穷维的物理扇区。

先把 \(q\) 平方开：\(q(\Psi)=\frac12\|\nabla\Psi\|^2+\int V|\Psi|^2+\int\langle\Psi,B(x)\Psi\rangle\)，其中费米乘项 \(B(x)\) 厄米、关于 \(x\) 线性且 \(\|B(x)\|\le C|x|\)——它可正可负，是主要障碍。\(\mathrm{Spin}(9)\) 旋转与规范作用对易，故同型分解 (isotypic decomposition) \(\mathcal H=\bigoplus_\lambda\mathcal H_\lambda\) 约化 \(H\)，可按最高权 (highest weight) \(\lambda=(\lambda_1,\lambda_2,\lambda_3,\lambda_4)\) 逐扇区处理。

核心机制是"横向振子＋表示论排除低能级"。固定一个颜色向量 \(u\ne0\)，把另两个颜色向量分解为平行于 \(u\) 的纵向分量与 16 维横向分量 \(z\in(u^\perp)^2\)。切片上位势满足 \(V\ge|u|^2|z|^2\)，连同横向动能给出频率正比于 \(|u|\) 的谐振子，第 \(n\) 能级能量为 \(|u|(n+8)\)。哪些能级可用由对称性裁决：\(u\) 在 \(\mathrm{Spin}(9)\) 中的稳定化子共轭于 \(\mathrm{Spin}(8)\)；由正交群限制的交错规则 (interlacing rule)，\(\mathrm{Spin}(9)\) 类型 \(\lambda\) 限制到稳定化子后，一切组分类型 \(\nu\) 满足 \(\nu_1\ge\lambda_2\)；而第 \(n\) 能级与费米子（权的第一坐标至多 \(M\)）的张量积中类型满足 \(\nu_1\le n+M\)。于是当 \(\lambda_2>m+M\) 时，低于 \(m\) 的振子能级被对称性完全禁空，横向能量至少 \((m+9)|u|\)。

最后拼装：对三个颜色取平均并利用 \(\sum_a|x^a|\ge|x|\)，取 \(m\) 使 \(c_m=(m+9)/3-C>0\)，得 \(q(\Psi)\ge\frac14\|\nabla\Psi\|^2+c_m\int|x|\,|\Psi|^2\,dx\)——线性增长的正位势压倒费米项，尾部估计加 Rellich 紧性给出该扇区算子的紧预解式 (compact resolvent)，且核平凡。构造侧：费米福克真空给出非零规范不变向量；规范不变多项式 \(P(x)=\sum_{a<b}(\zeta_a\eta_b-\zeta_b\eta_a)^2\) 是权 \(2(\epsilon_1+\epsilon_2)\) 的最高权向量，其 \(k\) 次幂使 \(\lambda_2=2k+\mu_2\) 任意大；再用互不相交的径向支集截断得到无穷多线性无关向量，故扇区无穷维。无穷维空间上带紧预解式的非负算子给出特征基 \(E_j\to\infty\)，核平凡故全为正。

## 可信度与备注

本文暂无形式化证明，请以社区核验为准；OpenAI 官方声明"未经形式化的结果可能有问题"。姊妹篇证明了 \(\mathrm{SU}(N)\) 模零能阈值态唯一（\(N=2\) 时恰一个零能态），本文则补充正能量一侧；两篇合看，\(N=2\) 的束缚态图像是"唯一阈值态＋无穷嵌入正能级"，与 BFSS 原文的排除性断言相抵触。论文亦明言：这一反驳只针对 \(N=2\) 的相对算子，大 \(N\) 的矩阵理论猜想是另一回事。

{% endraw %}
