---
layout: default
title: "Equidistribution of primitive quartic torus packets for arbitrary orders"
family: "015"
discipline: "Number theory"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | Equidistribution of primitive quartic torus packets for arbitrary orders

> 结果族 015：Torus-packet equidistribution in prime, quartic, and sextic degrees　·　学科：Number theory　·　验证状态：暂无形式化证明，请以社区核验为准

## 入门导读 🐣

数域里除了"最完整的环"（极大序，全部整数的家），还有各种"缩水的环"（阶）。此前的高维 Duke 型定理大多只对完整环造出的轨道束成立。这篇论文证明：四次全实域中，缩水环造出的轨道束同样会被搅得均匀——缩得多厉害都行，哪怕域本身不变、只让环不断缩水。

**关键词卡片**

- 阶 (order)：数域中含 1 的全秩子环；比极大序小，在整除指标的素数处结构可能失控
- 极大序 (maximal order)：数域中最大的整数环，此前结果的主场
- 本原四次域 (primitive quartic field)：不含任何中间域的四次全实域
- 三次预解域 (cubic resolvent)：把四次域的信息编码进一个三次域的辅助结构，用来排除危险退化
- 无质量逃逸 (no escape of mass)：概率不溜向无穷远

**看个具体例子**

数字版定理：固定本原四次域 `@@M@@K@@`，记 `@@M@@D=|\mathrm{Disc}(K)|@@`、指标 `@@M@@q=[\mathcal O_K:\mathcal O]@@`。允许 `@@M@@q@@` 任意增长，此时 `@@M@@|\mathrm{Disc}(\mathcal O)|=q^2D\to\infty@@`，而结论依然成立：`@@M@@\mu_{\mathcal O,\sigma}\to m_4@@`（Haar 测度），且无质量逃逸。具体代入：`@@M@@q=10@@` 时判别式是 `@@M@@100D@@`，`@@M@@q=1000@@` 时是 `@@M@@10^6D@@`——相差一万倍的"缩水程度"，搅匀的结局一模一样。而且所有常数对 `@@M@@K@@`、`@@M@@\mathcal O@@` 与嵌入排序 `@@M@@\sigma@@` 一致，束内还包含全部十六个坐标符号平移的轨道。

**为什么值得关心**

"任意阶"意味着素数处的局部结构可以完全失控，这是四次情形自 ELMV 以来最大的缺口；论文新造的外平方格二次计数与筛法，也为处理其他"非极大"对象提供了模板。

> 暂无形式化证明（AI 结果待核验）

## 一句话结论

本文证明：在没有真中间子域的全实四次域中，任意阶 `@@M@@\mathcal{O}@@` 的可逆理想类所给体积加权环面轨道丛（torus packet）当 `@@M@@|\mathrm{Disc}(\mathcal{O})|\to\infty@@` 时在格空间 `@@M@@X_4@@` 上均匀分布到 Haar 测度，且无质量逃逸；即使域固定、仅阶指数增长也成立。

## 问题背景

这是高维 Duke 均匀分布问题（higher-dimensional Duke equidistribution）在"任意阶"层面的推进。实二次域的理想类对应模曲面上的闭测地线：Linnik 的遍历方法与 Skubenko 在附加分裂条件下开创了方向，Duke（1988）借 Iwaniec 的半整权形式估计去掉分裂限制，Einsiedler–Lindenstrauss–Michel–Venkatesh（ELMV）再用熵方法把立方情形推广到非极大序。四次情形此前只有 Khayutin 对伽罗瓦群为 `@@M@@\mathfrak{A}_4@@` 或 `@@M@@S_4@@` 的极大序丛、以及 Wieser–Yang 对含二次子域情形的结果。任意序的困难有二：整除阶指数的素数处局部结构失控；四次数中正熵分量还可能是真齐性极限，须既证紧性与正熵、又逐一排除它们。

## 主要结果

设 `@@M@@X_4=\mathrm{SL}_4(\mathbb{Z})\backslash\mathrm{SL}_4(\mathbb{R})@@` 为协体积一的行格空间，`@@M@@A_4@@` 为其中行列式为一的正对角群。称四次域 `@@M@@K@@` 本原（primitive），若不存在中间域 `@@M@@\mathbb{Q}\subsetneq E\subsetneq K@@`。取本原全实四次域 `@@M@@K@@`、任意阶 `@@M@@\mathcal{O}\subseteq\mathcal{O}_K@@`（含 `@@M@@1@@` 的全秩子环）及实嵌入排序 `@@M@@\sigma@@`；对每个可逆 `@@M@@\mathcal{O}@@`-理想类以 `@@M@@\Lambda_{I,\sigma}=\covol(\sigma(I))^{-1/4}\sigma(I)@@` 规范化，再取全部十六个坐标符号矩阵 `@@M@@w\in W_{\mathrm{all}}@@` 平移，得到紧 `@@M@@A_4@@`-轨道的有限集 `@@M@@\mathcal{P}_{\mathcal{O},\sigma}@@`（紧性由单位定理保证）。以轨道体积加权的概率测度记作 `@@M@@\mu_{\mathcal{O},\sigma}@@`。主定理：若 `@@M@@|\mathrm{Disc}(\mathcal{O}_i)|\to\infty@@`，则对一切 `@@M@@f\in C_c(X_4)@@` 有 `@@M@@\int f\,d\mu_{\mathcal{O}_i,\sigma_i}\to\int f\,dm_4@@`，且无质量逃逸（no escape of mass）：任意 `@@M@@\varepsilon>0@@` 存在紧集 `@@M@@\mathcal{K}@@` 使 `@@M@@\mu_{\mathcal{O}_i,\sigma_i}(\mathcal{K})\ge1-\varepsilon@@` 对充分大 `@@M@@i@@` 成立。由 `@@M@@|\mathrm{Disc}(\mathcal{O})|=q^2D@@`（`@@M@@q=[\mathcal{O}_K:\mathcal{O}]@@`，`@@M@@D=|\mathrm{Disc}(K)|@@`），允许 `@@M@@K@@` 固定而 `@@M@@q\to\infty@@`，这正是"任意阶"的实质。

## 证明思路

全文是"两次计数夹住测度分类"的流水线，所有常数一致于 `@@M@@K@@`、`@@M@@\mathcal{O}@@` 与 `@@M@@\sigma@@`。

先建立丛模型（第 2 节）：可逆 `@@M@@\mathcal{O}@@`-理想在每个素数处恰是极大序理想中 `@@M@@\mathcal{O}@@` 的单位平移 `@@M@@L_p=\xi_pt_p\mathcal{O}_p@@`，局部标签共 `@@M@@N_{\mathcal{O}}=\prod_{p\mid q}[R_p^\times:\mathcal{O}_p^\times]@@` 个；类数公式给出总轨道体积 `@@M@@N_{\mathcal{O}}\sqrt D\,\kappa@@`（`@@M@@\kappa=\mathrm{Res}_{s=1}\zeta_K(s)@@`），使"对局部标签平均"成为精确操作。

再做第一次计数（第 3 节）：把向量属于理想格的概率对标签平均，恰好展开为极大序 `@@M@@R@@` 的整理想加权和；赋值壳层恒等式给出总质量 `@@M@@Z_q/q@@`，一个 `@@M@@1/8@@` 次矩不等式驯服阶指数；本原性排除二次子域，Stark 的例外零点结果因此给出一致零点自由区域，使残差 `@@M@@\kappa@@` 在理想计数中不丢失；配合 Shiu 型区间估计得 `@@M@@\sum P(\mathfrak{a})\ll\kappa y/q@@`。由此收获两点：短向量计数证明紧性（Mahler 判据），远离坐标超平面的方块计数给出概率极限的球体界 `@@M@@\mu(xB(r))\le C_\Omega r^4@@`。

接着是刚性环节（第 4 节）：按 ELMV 的双侧管判据，长 `@@M@@2t@@` 的流管可被 `@@M@@O(r^{-3})@@` 个球覆盖（`@@M@@r=e^{-\lambda_at}@@`），每个球质量 `@@M@@O(r^4)@@`，故管质量指数衰减；经控制不等式传递，几乎每个 `@@M@@A_4@@`-遍历分量熵 `@@M@@\ge\lambda_a/3@@`。EKL 测度分类使正熵分量成为闭轨道 `@@M@@\Lambda J@@` 上的 Haar 测度，等块引理迫使 `@@M@@J=\mathrm{SL}_4(\mathbb{R})@@` 或两个 `@@M@@2\times2@@` 块。后者即障碍事件 `@@M@@\mathcal{E}_b@@`（`@@M@@b\in\{12|34,13|24,14|23\}@@`）：格外平方（exterior square）`@@M@@\bigwedge^2\Lambda@@` 在坐标平面 `@@M@@V_b@@` 中有向量 `@@M@@w@@` 使 `@@M@@Q(w)=w_{12}w_{34}-w_{13}w_{24}+w_{14}w_{23}@@` 取非零整值。

第二次计数（第 5–8 节）排除它：三个带号积 `@@M@@(w_{12}w_{34},-w_{13}w_{24},w_{14}w_{23})@@` 恰是三次预解域（cubic resolvent）`@@M@@F@@` 中元素 `@@M@@z@@` 的三个实嵌入，固定 `@@M@@Q=\mathrm{Tr}\,z=m@@` 后几何事件对应迹平面上面积 `@@M@@O(r^4)@@` 的矩形；核心计数定理给出一致于 `@@M@@\mathcal{O}@@` 的界 `@@M@@\sum_zM(z)\ll\kappa\sqrt D\cdot\mathrm{area}@@`。难点在 `@@M@@p\mid Dq@@`：局部乘数密度是外平方格上二次积映射对 Haar 测度的推进，须经二次 Fourier 变换、分母理想与稳定子序 `@@M@@C_F@@`（其判别式被 `@@M@@X@@` 的固定幂次上下夹住）控制，Poisson 求和给出剩余类均匀性；未分歧素数处局部均值 `@@M@@1+(a_K(p)-1)/p@@` 由加权 Selberg 筛平均，其中减 `@@M@@1@@` 消去对数因子而留下 `@@M@@\kappa@@`。

最后（第 9 节）沿对角流展开计数函数：每个原始向量的纤维长度为三重对数 `@@M@@\mathcal{L}_{L,r}(z)@@`，二进分解矩形后级数收敛，得 `@@M@@\int N_{m,L,r}\,d\mu\le C_{m,L}r^4@@`；对非零整数 `@@M@@m@@` 与 `@@M@@L@@` 取可数并即 `@@M@@\mu(\mathcal{E}_b)=0@@`，三个障碍全被排除，一切分量为 Haar，故 `@@M@@\mu=m_4@@`；紧性再把子列收敛升级为整列收敛并给出无质量逃逸。

## 可信度与备注

本篇主结果尚无 Lean 形式化证明（任务元数据 formalized=false；族概述虽引用族级文档 lean/docs/015.md，但该篇主定理未被标记为已验证），结论请以社区核验为准，OpenAI 官方亦声明"未经形式化的结果可能有问题"。作为结果族 015 的四次数姊妹篇，它与素数次（任意局部型）与六次数（极大序）两文共享同一丛—熵框架：本文的普通向量方法直接改编自素数次姊妹篇，而外平方计数与筛法是为驯服无界阶指数新造的部件，逻辑上自洽且与前人体裁一致。

{% endraw %}
