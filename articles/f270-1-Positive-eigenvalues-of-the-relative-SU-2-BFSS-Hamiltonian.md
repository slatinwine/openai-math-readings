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

## 入门导读 🐣

一个平静的游泳池，水面可以被搅起任意小的涟漪——能量从零到无穷都能被"散射波"带走。直觉说：既然任何正能量都会被带走，就不该有稳稳钉在某个固定能量上的驻波。论文证明恰恰相反：有无穷多个这样的驻波，钉在一路升高的能量上；BFSS 原文当年断言"不可能"，本文在 N=2 处推翻了它。

**关键词卡片**

- 嵌入特征值（embedded eigenvalue）：藏在连续谱内部、却带平方可积波函数的能量级
- 连续谱（continuous spectrum）：可取任意正能量的散射态集合，这里覆盖 [0,∞)
- 相对哈密顿量（relative Hamiltonian）：去掉自由质心后剩下的相互作用部分
- 超荷形式（supercharge form）：把能量定义为 16 个超荷平方和的方式
- 同型分解（isotypic decomposition）：按旋转对称性把态空间切成互不串门的小间

**看个具体例子**

定理：存在规范正交的波函数序列 Ψ₁,Ψ₂,… 与能量 E₁<E₂<…→∞，使 HΨ_j=E_jΨ_j。它们像插进水面的一根根固定桩：能量越来越高、有无穷多根，每一根都是货真价实的束缚态。

<div>

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 560 280">
<line x1="60" y1="170" x2="520" y2="170" stroke="#b8b8b8" stroke-width="12"/>
<text x="70" y="200" font-size="14" fill="#888">连续谱 [0,∞)：任意正能量的散射态</text>
<line x1="110" y1="170" x2="110" y2="125" stroke="#c0392b" stroke-width="3"/>
<line x1="175" y1="170" x2="175" y2="88" stroke="#c0392b" stroke-width="3"/>
<line x1="245" y1="170" x2="245" y2="138" stroke="#c0392b" stroke-width="3"/>
<line x1="320" y1="170" x2="320" y2="62" stroke="#c0392b" stroke-width="3"/>
<line x1="395" y1="170" x2="395" y2="105" stroke="#c0392b" stroke-width="3"/>
<line x1="470" y1="170" x2="470" y2="75" stroke="#c0392b" stroke-width="3"/>
<circle cx="110" cy="125" r="5" fill="#c0392b"/>
<circle cx="175" cy="88" r="5" fill="#c0392b"/>
<circle cx="245" cy="138" r="5" fill="#c0392b"/>
<circle cx="320" cy="62" r="5" fill="#c0392b"/>
<circle cx="395" cy="105" r="5" fill="#c0392b"/>
<circle cx="470" cy="75" r="5" fill="#c0392b"/>
<text x="120" y="45" font-size="14" fill="#c0392b">嵌入特征值 E₁,E₂,E₃,… 趋于无穷</text>
<line x1="60" y1="170" x2="60" y2="60" stroke="#333" stroke-width="2"/>
<text x="30" y="55" font-size="14" fill="#333">0</text>
</svg>

</div>

**为什么值得关心**

它回答了 de Wit–Lüscher–Nicolai 1989 年留下的老问题，并纠正 BFSS 原文的断言：SU(2) 模除一个零能阈值态外，还有无穷多个正能量束缚态。与姊妹篇合起来看，N=2 的完整图像是"唯一阈值态＋无穷嵌入正能级"。

> 暂无形式化证明（AI 结果待核验）

## 一句话结论

证明由规范不变超荷形式的闭包定义的相对 `@@M@@\mathrm{SU}(2)@@` BFSS 哈密顿量有无穷多个趋于无穷、带平方可积特征向量的正特征值，从而在 `@@M@@N=2@@` 处推翻了 BFSS 原文"除零能阈值态外无其他可归一化束缚态"的断言。

## 问题背景

BFSS 矩阵模型由十维超对称杨–米尔斯理论约化到一个时间维度而来；对 `@@M@@\mathrm{SU}(2)@@`，去掉自由质心后剩下 27 个玻色坐标 `@@M@@x=(x^1,x^2,x^3)\in(\mathbb R^9)^3@@` 与由 `@@M@@\theta_\alpha^a@@`（`@@M@@\alpha=1,\dots,16@@`，`@@M@@a=1,2,3@@`）生成的有限维克利福德模 (Clifford module)。四次位势 `@@M@@V=\sum_{a<b}|x^a\wedge x^b|^2@@` 在三个空间向量共线时取零，经典逃逸方向无界。de Wit–Lüscher–Nicolai（1989）证明其谱集为 `@@M@@[0,\infty)@@`，却明确留下谱集内是否嵌有可归一化态的问题；BFSS 原文（1997，式 (5.4) 之后）更断言除零能阈值态外"不可能有其他可归一化束缚态"。此前 Danielsson–Ferretti–Sundborg 只在 Born–Oppenheimer 近似下找到预期衰变的亚稳激发态，Smilga 曾在热力学分析中猜想激发态族的存在。困难在于：连续谱覆盖整个正半轴，要证明嵌入特征值 (embedded eigenvalue) 存在，必须有机制制服平坦方向上的逃逸。

## 主要结果

论文在物理希尔伯特空间 `@@M@@\mathcal H=[L^2(\mathbb R^{27};\mathcal F)]^{\mathrm{SU}(2)}@@`（规范不变部分）上，取规范不变紧支撑光滑函数核 `@@M@@\mathcal C@@`，定义超荷形式 `@@M@@q(\Psi)=\frac1{16}\sum_{\alpha=1}^{16}\|Q_\alpha\Psi\|^2@@`；其闭包对应非负自伴算子 `@@M@@H@@`，即相对 `@@M@@\mathrm{SU}(2)@@` BFSS 哈密顿量的精确定义。

**主定理**：存在规范正交序列 `@@M@@\Psi_j\in\mathrm{Dom}(H)@@` 与实数 `@@M@@E_j>0@@`、`@@M@@E_j\to\infty@@`，使 `@@M@@H\Psi_j=E_j\Psi_j@@`；特别地，点谱 `@@M@@\sigma_{\mathrm p}(H)\cap(0,\infty)@@` 无穷。

这些特征值嵌在连续谱 `@@M@@[0,\infty)@@` 之内却拥有 `@@M@@L^2@@` 特征向量，是货真价实的束缚态，而不仅是谱集的一部分。

## 证明思路

证明分三层：先给出形式的显式展开；再借旋转对称性切入高权扇区并证明横向囚禁；最后构造无穷维的物理扇区。

先把 `@@M@@q@@` 平方开：`@@M@@q(\Psi)=\frac12\|\nabla\Psi\|^2+\int V|\Psi|^2+\int\langle\Psi,B(x)\Psi\rangle@@`，其中费米乘项 `@@M@@B(x)@@` 厄米、关于 `@@M@@x@@` 线性且 `@@M@@\|B(x)\|\le C|x|@@`——它可正可负，是主要障碍。`@@M@@\mathrm{Spin}(9)@@` 旋转与规范作用对易，故同型分解 (isotypic decomposition) `@@M@@\mathcal H=\bigoplus_\lambda\mathcal H_\lambda@@` 约化 `@@M@@H@@`，可按最高权 (highest weight) `@@M@@\lambda=(\lambda_1,\lambda_2,\lambda_3,\lambda_4)@@` 逐扇区处理。

核心机制是"横向振子＋表示论排除低能级"。固定一个颜色向量 `@@M@@u\ne0@@`，把另两个颜色向量分解为平行于 `@@M@@u@@` 的纵向分量与 16 维横向分量 `@@M@@z\in(u^\perp)^2@@`。切片上位势满足 `@@M@@V\ge|u|^2|z|^2@@`，连同横向动能给出频率正比于 `@@M@@|u|@@` 的谐振子，第 `@@M@@n@@` 能级能量为 `@@M@@|u|(n+8)@@`。哪些能级可用由对称性裁决：`@@M@@u@@` 在 `@@M@@\mathrm{Spin}(9)@@` 中的稳定化子共轭于 `@@M@@\mathrm{Spin}(8)@@`；由正交群限制的交错规则 (interlacing rule)，`@@M@@\mathrm{Spin}(9)@@` 类型 `@@M@@\lambda@@` 限制到稳定化子后，一切组分类型 `@@M@@\nu@@` 满足 `@@M@@\nu_1\ge\lambda_2@@`；而第 `@@M@@n@@` 能级与费米子（权的第一坐标至多 `@@M@@M@@`）的张量积中类型满足 `@@M@@\nu_1\le n+M@@`。于是当 `@@M@@\lambda_2>m+M@@` 时，低于 `@@M@@m@@` 的振子能级被对称性完全禁空，横向能量至少 `@@M@@(m+9)|u|@@`。

最后拼装：对三个颜色取平均并利用 `@@M@@\sum_a|x^a|\ge|x|@@`，取 `@@M@@m@@` 使 `@@M@@c_m=(m+9)/3-C>0@@`，得 `@@M@@q(\Psi)\ge\frac14\|\nabla\Psi\|^2+c_m\int|x|\,|\Psi|^2\,dx@@`——线性增长的正位势压倒费米项，尾部估计加 Rellich 紧性给出该扇区算子的紧预解式 (compact resolvent)，且核平凡。构造侧：费米福克真空给出非零规范不变向量；规范不变多项式 `@@M@@P(x)=\sum_{a<b}(\zeta_a\eta_b-\zeta_b\eta_a)^2@@` 是权 `@@M@@2(\epsilon_1+\epsilon_2)@@` 的最高权向量，其 `@@M@@k@@` 次幂使 `@@M@@\lambda_2=2k+\mu_2@@` 任意大；再用互不相交的径向支集截断得到无穷多线性无关向量，故扇区无穷维。无穷维空间上带紧预解式的非负算子给出特征基 `@@M@@E_j\to\infty@@`，核平凡故全为正。

## 可信度与备注

本文暂无形式化证明，请以社区核验为准；OpenAI 官方声明"未经形式化的结果可能有问题"。姊妹篇证明了 `@@M@@\mathrm{SU}(N)@@` 模零能阈值态唯一（`@@M@@N=2@@` 时恰一个零能态），本文则补充正能量一侧；两篇合看，`@@M@@N=2@@` 的束缚态图像是"唯一阈值态＋无穷嵌入正能级"，与 BFSS 原文的排除性断言相抵触。论文亦明言：这一反驳只针对 `@@M@@N=2@@` 的相对算子，大 `@@M@@N@@` 的矩阵理论猜想是另一回事。

{% endraw %}
