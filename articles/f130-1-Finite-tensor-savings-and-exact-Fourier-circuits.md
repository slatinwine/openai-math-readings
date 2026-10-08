---
layout: default
title: "Finite tensor savings and exact Fourier circuits"
family: "130"
discipline: "Theoretical computer science"
formalized: true
source: null
pdfname: ""
---

{% raw %}
# 解读 | Finite tensor savings and exact Fourier circuits

> 结果族 130：Exact Fourier transforms below `@@M@@n\log n@@`　·　学科：Theoretical computer science　·　验证状态：主结果已 Lean 形式化

## 入门导读 🐣

把一台"乘法机器" `@@M@@A@@` 用到一条 `@@M@@q^b@@` 个坐标的大流水线上，教科书做法是沿 `@@M@@b@@` 个方向各扫一遍，共 `@@M@@b\cdot q^{b-1}@@` 次调用。本文证明：存在聪明的接线路径，配合"免费换线"，让调用次数严格少于这个数；并靠这一点，在完全不限制系数的电路模型里，把"算傅里叶变换必须花 `@@M@@\Omega(n\log n)@@`"的老猜想推翻了。

**关键词卡片**

- 线性电路（linear circuit）：只含加、减、乘预选常数三种门的电路，用来计算矩阵变换。
- 非均匀（nonuniform）：每个规模配一个专门电路，常数随便预置、生成不计费。
- 单项矩阵（monomial matrix）：每行每列恰有一个非零元的矩阵，相当于"换线加缩放"，在此模型里免费。
- 张量幂（tensor power）：`@@M@@A\otimes A\otimes\cdots\otimes A@@`，同一个小变换叠 `@@M@@b@@` 层的大变换。
- 有限张量盈余（finite tensor saving）：某个 `@@M@@A@@` 的 `@@M@@b@@` 层张量幂存在省调用的算法。

**看个具体例子**

<div>

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 560 280"><text x="280" y="26" text-anchor="middle" font-size="16" fill="#333">目标：算 A⊗A⊗⋯⊗A（b 层，共 qᵇ 个坐标）</text><text x="20" y="76" font-size="14" fill="#555">标准逐轴：</text><rect x="105" y="54" width="92" height="32" rx="6" fill="#eef" stroke="#345"/><text x="151" y="75" text-anchor="middle" font-size="13" fill="#123">A × qᵇ⁻¹</text><text x="201" y="75" font-size="14" fill="#345">→</text><rect x="215" y="54" width="92" height="32" rx="6" fill="#eef" stroke="#345"/><text x="261" y="75" text-anchor="middle" font-size="13" fill="#123">A × qᵇ⁻¹</text><text x="311" y="75" font-size="14" fill="#345">→ ⋯（共 b 段）</text><text x="280" y="112" text-anchor="middle" font-size="13" fill="#345">总计 b·qᵇ⁻¹ 次 A 调用</text><text x="20" y="156" font-size="14" fill="#555">论文的赢词：</text><rect x="105" y="134" width="70" height="32" rx="6" fill="#efe" stroke="#253"/><text x="140" y="155" text-anchor="middle" font-size="13" fill="#121">A 一次</text><text x="179" y="155" font-size="14" fill="#253">→</text><rect x="193" y="134" width="92" height="32" rx="6" fill="#fff" stroke="#253" stroke-dasharray="6,4"/><text x="239" y="155" text-anchor="middle" font-size="13" fill="#121">免费换线</text><text x="289" y="155" font-size="14" fill="#253">→</text><rect x="303" y="134" width="70" height="32" rx="6" fill="#efe" stroke="#253"/><text x="338" y="155" text-anchor="middle" font-size="13" fill="#121">A 一次</text><text x="377" y="155" font-size="14" fill="#253">→ ⋯</text><text x="280" y="192" text-anchor="middle" font-size="13" fill="#253">总计严格少于 b·qᵇ⁻¹ 次 A 调用</text><text x="30" y="228" font-size="13" fill="#666">换线 = 可逆单项映射（每行每列恰一个非零元），在这个电路模型里不收费；</text><text x="30" y="254" font-size="13" fill="#666">"有限张量盈余"定理：这样的矩阵 A 与赢词必然存在。</text></svg>

</div>

把盈余层层放大再"搬运"到傅里叶矩阵上：对任意常数 `@@M@@c>0@@`（比如 `@@M@@c=1/100@@`），都存在无穷增大的长度 `@@M@@n@@`（取互异素数之积），使精确傅里叶电路的规模不足 `@@M@@c\cdot n\log_2 n@@` 个门——即比值 `@@M@@L(n)/(n\log_2 n)@@` 的下极限为 0。

**为什么值得关心**

四十多年来 `@@M@@\Omega(n\log n)@@` 下界在带系数限制的模型里屡试不爽，本文说明在最一般的非均匀复线性电路模型里它就是错的。

> 已 Lean 形式化

## 一句话结论
本文在系数任意、非均匀的复线性电路（linear circuit）模型中，沿一列趋于无穷的长度构造出规模 `@@M@@o(n\log n)@@` 的精确傅里叶电路，推翻了该模型下的 `@@M@@\Omega(n\log n)@@` 下界猜想；核心是一个"有限张量盈余"的存在性证明。

## 问题背景
精确计算 `@@M@@n@@` 点傅里叶矩阵 `@@M@@F_n=(\zeta_n^{jk})@@` 是否必须耗费 `@@M@@\Omega(n\log n)@@` 次运算，是算术复杂度理论的老问题。已知下界均带附加条件：Morgenstern 1973 年的行列式论证要求系数有界；Ailon 的两个结果分别要求恰好 `@@M@@n@@` 个寄存器配酉两坐标门、或对中间变换条件数的控制。在系数无界、允许任意预选常数的非均匀模型里，问题长期开放；上界方面 Alman–Rao 只改进了 2 的幂长度的常数因子。本文证明：在最一般的非均匀意义下，`@@M@@\Omega(n\log n)@@` 下界不成立。

## 主要结果
主定理：在该模型中 `@@M@@\liminf_{n\to\infty}L(n)/(n\log_2 n)=0@@`。等价地说，对任意 `@@M@@c>0@@` 与任意阈值，都存在长度 `@@M@@n@@`（取互异素数之积、构成无界序列）以及规模不足 `@@M@@c\,n\log_2 n@@` 个门的精确电路。模型计费严格：每个加、减、乘预选标量的门各记一次；系数的模、代数次数与描述长度不受限，其生成不计费；深度、存储与消去均无约束。支撑结论的是有限张量盈余（finite win）定理：存在可逆非单项（nonmonomial）矩阵 `@@M@@A\in\GL_q(\mathbb C)@@`、整数 `@@M@@b\ge2@@` 与 `@@M@@q^b@@` 个坐标上的词，用少于 `@@M@@bq^{b-1}@@` 次 `@@M@@A@@` 调用实现 `@@M@@A^{\otimes b}@@`，调用之间可自由插入可逆单项（monomial）映射。`@@M@@bq^{b-1}@@` 正是逐轴标准算法的调用量。

## 证明思路
全文分两半：有限盈余如何放大并传输给傅里叶矩阵，以及它为何必然存在。

前半从正生成引理开始：若 `@@M@@A@@` 非单项，则 `@@M@@A@@` 对角子空间的共轭撑满全矩阵空间，配合 Jacobi 行列式非零、Zariski 开集像与"两份模式相乘"，得到固定模式 `@@M@@H=M_0AM_1\cdots AM_h@@`，仅靠调节单项因子便能实现一切 `@@M@@H\in\GL_q(\mathbb C)@@`。张量放大引理把赢词自乘 `@@M@@j=\lfloor k/b\rfloor@@` 层，调用槽的 `@@M@@j@@` 重张量幂分解为直和 `@@M@@\bigoplus_r(A^{\otimes r})^{\oplus\binom jr(Q-q)^{j-r}}@@`，归一成本满足 `@@M@@f(k)\le C_0+g\,\mathbb E f(K)@@`，其中 `@@M@@K@@` 服从二项分布；由严格盈余 `@@M@@g\rho<1@@`（`@@M@@\rho=q/(Qb)@@`）与凹性归纳，得 `@@M@@A^{\otimes k}@@` 只需 `@@M@@O(q^k(k+1)^\alpha)@@`、`@@M@@\alpha<1@@`。传输阶段：Newton/Kuznetsov 型分解 `@@M@@F_r=ND_N^{-1}N^{\mathsf T}@@` 把傅里叶阵化为三角 Toeplitz 阵，经位移秩（displacement rank）方法（残差秩至多 3）拆成卷积，再用 Bennett 式"计算—读取—逆算"重放在恰好 `@@M@@r@@` 个坐标上借用脏坐标并复原，得 `@@M@@O(\log^4 r)@@` 层的两坐标层；取 `@@M@@n_m@@` 为前 `@@M@@m@@` 个大于 `@@M@@2q@@` 的素数之积（素数个数由初等组合估计保证），中国剩余定理给出 `@@M@@F_{n_m}=\bigotimes_iF_{r_i}@@`（至差一个置换）；把各轴的两坐标映射一律改写为 `@@M@@A@@` 的固定正词并按时隙同步，每个 `@@M@@A@@` 调用槽按活跃坐标分解为扇区直和，扇区宽度之和恰为 `@@M@@n_m@@`，总规模 `@@M@@O(n_m(1+\log^4 m)(m+1)^\alpha)=o(n_m\log n_m)@@`。

后半反设不存在任何有限盈余，由此构造价格函数 `@@M@@p@@` 推出矛盾：比较打包与紧性论证给出在非单项矩阵上取正值、满足精确张量律与直和律的 `@@M@@p@@`；反馈构造（对新鲜数据反复调用、保留状态）使初始状态的修正费可忽略，证明可逆角块不贵于其宿主矩阵；标量枢轴律允许在两组基仍为基时交换一个输入与一个输出基向量而价格不变。最后的矛盾由反射制造：用 `@@M@@C,Z,X@@` 型符号矩阵构造对合 `@@M@@\Gamma@@`，其价格精确等于 `@@M@@dN/2@@`；在 `@@M@@w=N^2@@` 维取 `@@M@@M=\Gamma\otimes\Gamma@@`，其 `@@M@@+1@@` 特征空间 `@@M@@E@@` 既是对称稀疏阵 `@@M@@A=SL@@` 的核（非对角支持对至多 `@@M@@(d/2+1)w@@` 个），又是某个可逆矩阵的图像。上界：对每个支持对的多项式微扰至多 `@@M@@3/2@@`，经反馈单元与两次代数特化传给 `@@M@@E@@` 上的正交反射 `@@M@@R@@`，得 `@@M@@p(R)\le(\frac{3d}{4}+\frac72)w@@`；下界：由图像表示做枢轴与和差对角化，能以 `@@M@@O(w)@@` 的附加费从 `@@M@@R@@` 复原 `@@M@@M@@` 的价格 `@@M@@dw@@`，即 `@@M@@dw\le p(R)+4w@@`。取 `@@M@@d>30@@` 时两式不相容，矛盾；故有限盈余存在，接上前半段即得主定理。

## 可信度与备注
按任务信息，本文主结果已 Lean 形式化（结果族 130 附有 Lean 文档）。姊妹篇《An explicit power saving for the exact discrete Fourier transform》在同一证书接口上给出对所有长度的量化算法，两文互补：本文证有限盈余必然存在，该文给出显式网络与全长度实现。需注意本结论是非均匀存在性：系数逐电路预选且生成不计费，对数值稳定性与比特复杂度不作承诺；姊妹篇尚未形式化，按 OpenAI 官方声明，未经形式化的结果可能有问题，请以社区核验为准。

{% endraw %}
