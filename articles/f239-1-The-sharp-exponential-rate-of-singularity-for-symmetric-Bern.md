---
layout: default
title: "The sharp exponential rate of singularity for symmetric Bernoulli matrices"
family: "239"
discipline: "Probability and statistical mechanics"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | The sharp exponential rate of singularity for symmetric Bernoulli matrices

> 结果族 239：Sharp singularity rates for symmetric random sign matrices　·　学科：Probability and statistical mechanics　·　验证状态：暂无形式化证明，请以社区核验为准

## 入门导读 🐣

用掷硬币填满一面"镜子"方阵：第 `@@M@@i@@` 行 `@@M@@j@@` 列与第 `@@M@@j@@` 行 `@@M@@i@@` 列永远相同。这面随机镜子有多大机会不可逆？论文给出精确答案：概率是 `@@M@@(1/2)^n@@` 量级，而且几乎全部"罪责"来自最笨的一种情形——两行长得一模一样。

**关键词卡片**

- 对称随机矩阵（symmetric random matrix）：满足 `@@M@@a_{ij}=a_{ji}@@` 的随机方阵，像沿对角线立了一面镜子
- 奇异（singular）：行列式为 0，线性方程组失去唯一解
- 两行相等（two equal rows）：最朴素的奇异原因，概率恰为 `@@M@@2^{-n}@@`；本文证明其他机制合起来也不超过它
- 判别群（discriminant group）：由矩阵派生的有限交换群，论文用它给"退化风险"记一本算术账
- 主子式（principal minor）：删去同号行列后剩下的子矩阵，证明沿它逐级推进

**看个具体例子**

定理：`@@M@@\Pr(\det A_n=0)=\left(\tfrac12+o(1)\right)^n@@`。下界：指定两行相等的概率恰为 `@@M@@2^{-n}@@`（两行交点之外的位置独立配合）；上界：整数核向量、近似核向量等其余机制合计不超过同一指数。`@@M@@n=100@@` 时约 `@@M@@2^{-100}\approx8\times10^{-31}@@`。下图是一个 `@@M@@n=3@@` 的退化样本：前两行完全相同，行列式必为 0；这个小样本里"前两行相同"的概率是 `@@M@@2^{-3}=1/8@@`，正是定理公式的缩影。

<div>

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 560 280">
  <text x="280" y="28" text-anchor="middle" font-size="15">镜子矩阵退化的头号原因：两行一模一样</text>
  <rect x="121" y="56" width="208" height="138" fill="#ffe8d9"/>
  <line x1="120" y1="55" x2="120" y2="265" stroke="#333" stroke-width="1.5"/>
  <line x1="190" y1="55" x2="190" y2="265" stroke="#333" stroke-width="1.5"/>
  <line x1="260" y1="55" x2="260" y2="265" stroke="#333" stroke-width="1.5"/>
  <line x1="330" y1="55" x2="330" y2="265" stroke="#333" stroke-width="1.5"/>
  <line x1="120" y1="55" x2="330" y2="55" stroke="#333" stroke-width="1.5"/>
  <line x1="120" y1="125" x2="330" y2="125" stroke="#333" stroke-width="1.5"/>
  <line x1="120" y1="195" x2="330" y2="195" stroke="#333" stroke-width="1.5"/>
  <line x1="120" y1="265" x2="330" y2="265" stroke="#333" stroke-width="1.5"/>
  <text x="155" y="97" text-anchor="middle" font-size="20">1</text>
  <text x="225" y="97" text-anchor="middle" font-size="20">1</text>
  <text x="295" y="97" text-anchor="middle" font-size="20">−1</text>
  <text x="155" y="167" text-anchor="middle" font-size="20">1</text>
  <text x="225" y="167" text-anchor="middle" font-size="20">1</text>
  <text x="295" y="167" text-anchor="middle" font-size="20">−1</text>
  <text x="155" y="237" text-anchor="middle" font-size="20">−1</text>
  <text x="225" y="237" text-anchor="middle" font-size="20">−1</text>
  <text x="295" y="237" text-anchor="middle" font-size="20">−1</text>
  <text x="350" y="90" font-size="14">第 1 行</text>
  <text x="350" y="160" font-size="14">第 2 行＝第 1 行</text>
  <text x="350" y="125" font-size="15" fill="#d62728">⇒ det A = 0</text>
  <text x="350" y="205" font-size="13" fill="#555">P(指定两行相同)=2^(−n)</text>
  <text x="350" y="230" font-size="13" fill="#555">n=100 时约 8×10^(−31)</text>
</svg>

</div>

**为什么值得关心**

对称随机矩阵是自旋玻璃等物理模型的基本对象，奇异性率是它的"体质指标"；非对称情形早有精确答案，本文补上了对称这块拼图。

> 暂无形式化证明（AI 结果待核验）

## 一句话结论

证明了对角线及以上元素独立、均匀取 `@@M@@\pm1@@` 的对称随机矩阵满足 `@@M@@\Pr(\det A_n=0)=(1/2+o(1))^n@@`：最朴素的"两行相等"机制就是奇异的全部指数级来源，对称模型悬置的精确奇异率由此确定。

## 问题背景

离散随机矩阵何时奇异（singularity）是自 Komlós 以来的经典难题。独立条目模型已完全理解：Komlós 证明独立均匀 `@@M@@0/1@@` 矩阵以趋于 1 的概率非奇异，Tikhomirov 进一步证明独立均匀符号矩阵的奇异概率恰为 `@@M@@(1/2+o(1))^n@@`。但对称（symmetric）模型中揭示一行等于同时揭示所有后续行的一列，行与行不再独立，基于独立行的利特尔伍德–奥福德（Littlewood–Offord）反集中论证全部失效。Costello–Tao–Vu 发展二次利特尔伍德–奥福德理论，首次证明对称伯努利矩阵渐近非奇异，界为 `@@M@@O(n^{-1/8+\delta})@@`；此后 Nguyen 改进到任意多项式衰减，Vershynin 与一系列后续工作（最优达 `@@M@@\exp(-c\sqrt{n\log n})@@`）逐步推进，Campos–Jenssen–Michelen–Sahasrabudhe 终于得到指数界 `@@M@@\exp(-cn)@@`。但指数常数是否最优——即奇异率是否恰为 `@@M@@(1/2)^n@@`——此前未知，本文给出肯定回答。

## 主要结果

**定理 1.1**　设 `@@M@@A_n@@` 为对称 `@@M@@n\times n@@` 随机矩阵，其对角线及以上元素独立且均匀分布于 `@@M@@\{-1,1\}@@`，则
`@@M@@D\Pr(\det A_n=0)=\left(\frac12+o(1)\right)^n=2^{-n+o(n)}.@@`

下界显而易见：指定两行相等的概率恰为 `@@M@@2^{-n}@@`——两行交点之外有 `@@M@@n-2@@` 个坐标相等比较，加上两个对角位置条件，它们相互独立。定理的实质是上界：整数核向量、近似核向量等所有其他奇异机制合起来，在指数尺度上也不超过"两行相等"。

## 证明思路

全文沿"归约—位势—静态计数—动态控制"展开。

先做两次精确归约。将 `@@M@@A_n@@` 乘以 `@@M@@(A_n)_{11}@@` 并作对角合同变换，可使第一行全为 1，其 Schur 补（Schur complement）等于 `@@M@@-2@@` 乘一个比特对称矩阵，故 `@@M@@\Pr(\det A_n=0)=\Pr(\det\mathbf B_{n-1}=0)@@`，而比特模型的上三角元素独立均匀。再翻转 `@@M@@k-1@@` 个对角比特（`@@M@@k\le N^{3/5}@@`）可把余秩（corank）`@@M@@k@@` 化为 1，每个像至多 `@@M@@2^{o(N)}@@` 个原像；更高余秩的概率不超过 `@@M@@2^{-\Omega(N^{6/5})}@@`，可以忽略。余秩一又化为加列问题：删去核向量绝对值最大的坐标得非奇异主子式（principal minor）`@@M@@B@@`，被删列 `@@M@@z@@` 必属于容许列集 `@@M@@\mathcal S(B)=\{z\in\{0,1\}^m:z^{\mathsf T}B^{-1}z\in\{0,1\},\ \|B^{-1}z\|_\infty\le1\}@@`，且 `@@M@@\Pr(\mathrm{corank}=1)\le N2^{-N}\E|\mathcal S(\mathbf B_{N-1})|@@`。于是全部问题化为证明 `@@M@@\E|\mathcal S(\mathbf B_{N-1})|\le2^{o(N)}@@`。

再在判别群（discriminant group）`@@M@@G_B=\Z^m/B\Z^m@@` 上定义算术位势（potential）`@@M@@\Psi@@`：以 `@@M@@k_B(p,e)@@` 记各素数幂层的层高、`@@M@@\nu_p=\log_Np/N@@` 记权，令 `@@M@@\Psi(B)=\sum\nu_p\,\phi(k_B(p,e))@@`（`@@M@@\phi(1)=0@@`，`@@M@@\phi(2)=7/5@@`，`@@M@@\phi(k)=2k@@`）。两个支柱命题：典型地（即除概率 `@@M@@2^{-Nf(N)}@@`、`@@M@@f\to\infty@@` 的例外集外）`@@M@@|\mathcal S(B)|\le2^{N(\Psi+\ell^{-A})}@@`；以及 `@@M@@\E\,2^{N\Psi(\mathbf B_{N-1})}\le2^{o(N)}@@`。前者把容许列数押在 `@@M@@B@@` 的算术结构上，后者说明这种结构典型地便宜，相乘即得目标。

静态一半（第六节）用判别配对 `@@M@@\lambda_B(\bar x,\bar y)=x^{\mathsf T}B^{-1}y\pmod{\Z}@@`：它是完美（perfect）配对，且容许列的类必迷向（isotropic）。对迷向元作正交块分解并染色，使同色元素之差的配对值阶可控；大色块经鲁棒子集构造出 `@@M@@B^{-1}@@` 图像上协体积（covolume）可控的格。由低高度有理子空间覆盖（low-height cover）使秩估计对所有子空间同时成立，从而让配对给出的行列式下界与典型秩及谱性质的上界相矛盾——后者由半圆律矩估计加 Talagrand 凸集中不等式推出，说明近零特征值稀少；格部分对删去极小子格后的正交商调用 Regev–Stephens-Davidowitz 的逆向 Minkowski 定理（Reverse Minkowski）。

动态一半（第七至十一节）沿主子式路径推进：门控删除引理保证任何非奇异矩阵都可经宽度 1 或 2 的非奇异主子式步到达，宽度二步满足"两新列均容许"的门、其概率由静态列估计直接支付；宽度一步的位势增长由"证书定价"在条件指数矩中结清。高层尾部由"对所有素数的余秩一致不超过 `@@M@@N^{3/5}@@`"与尾递归排除。最后在短终端窗口上二选一：某节点位势已小则局部估计直接收官；否则一个有界辅助统计量持续下降，迫使出现大量条件概率极小的步骤，总概率可以忽略。

## 可信度与备注

主结果尚无 Lean 形式化证明。姊妹篇（偏置对称情形）直接沿用本文的主子式路径、判别群配对与格工具，并将其立方交估计加强为同时版本，两文互相支撑、共同构成族 239。按 OpenAI 官方声明，未经形式化的结果可能存在问题，请以社区核验为准。

{% endraw %}
