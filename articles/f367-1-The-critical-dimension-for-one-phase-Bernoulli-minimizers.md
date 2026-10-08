---
layout: default
title: "The critical dimension for one-phase Bernoulli minimizers"
family: "367"
discipline: "Partial differential equations"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | The critical dimension for one-phase Bernoulli minimizers

> 结果族 367：The critical dimension for the one-phase Bernoulli problem　·　学科：Partial differential equations　·　验证状态：暂无形式化证明，请以社区核验为准

## 入门导读 🐣

在一片空地里圈一块"最优地盘"：圈内要分布得平缓，而占地本身要按体积付租金，围栏的位置还是待求的。论文问：这种省钱又平缓的最优地盘，围栏最晚会从第几维空间开始长出"尖角"？答案是七维——六维及以下围栏必然光滑，七维起才第一次出现不平整的最优形状。

**关键词卡片**

- 一相 Bernoulli 问题（one-phase Bernoulli problem）：极小化 `@@M@@\int(|\nabla v|^2+\mathbf 1_{\{v>0\}})@@` 的形状优化问题。
- 自由边界（free boundary）：正相位与零相位的界面，位置本身未知。
- 平坦解（flat solution）：半空间形状 `@@M@@u(x)=(x\cdot e)_+@@`，边界面是一张平面。
- 一次齐次整体极小化子（one-homogeneous global minimizer）：从原点看完全成比例的最优形状，即"锥"。
- 临界维度（critical dimension）：第一个非平坦锥出现的维度，本文证明恰为 7。

**看个具体例子**

维度阶梯：`@@M@@d\le6@@` 时所有锥都平坦，自由边界光滑；`@@M@@d=7@@` 出现非平坦锥。对 `@@M@@n@@` 维局部极小化子，奇点集满足 `@@M@@\dim_H\operatorname{Sing}\le n-7@@`：`@@M@@n=7@@` 时奇点至多有限个，`@@M@@n=10@@` 时奇点集维数至多 3；用 7 维锥与 `@@M@@\R^{n-7}@@` 作乘积可造出达到上界的例子，估计最优。

<div>

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 560 280">
  <text x="280" y="30" text-anchor="middle" font-size="16" fill="#333">一相 Bernoulli 问题的维度阶梯：分水岭在 7</text>
  <line x1="45" y1="180" x2="515" y2="180" stroke="#333" stroke-width="2"/>
  <line x1="60" y1="173" x2="60" y2="187" stroke="#333" stroke-width="2"/>
  <line x1="125" y1="173" x2="125" y2="187" stroke="#333" stroke-width="2"/>
  <line x1="190" y1="173" x2="190" y2="187" stroke="#333" stroke-width="2"/>
  <line x1="255" y1="173" x2="255" y2="187" stroke="#333" stroke-width="2"/>
  <line x1="320" y1="173" x2="320" y2="187" stroke="#333" stroke-width="2"/>
  <line x1="385" y1="173" x2="385" y2="187" stroke="#333" stroke-width="2"/>
  <line x1="450" y1="173" x2="450" y2="187" stroke="#333" stroke-width="2"/>
  <line x1="500" y1="173" x2="500" y2="187" stroke="#333" stroke-width="2"/>
  <text x="60" y="207" text-anchor="middle" font-size="13" fill="#333">d=1</text>
  <text x="125" y="207" text-anchor="middle" font-size="13" fill="#333">2</text>
  <text x="190" y="207" text-anchor="middle" font-size="13" fill="#333">3</text>
  <text x="255" y="207" text-anchor="middle" font-size="13" fill="#333">4</text>
  <text x="320" y="207" text-anchor="middle" font-size="13" fill="#333">5</text>
  <text x="385" y="207" text-anchor="middle" font-size="13" fill="#333">6</text>
  <text x="450" y="207" text-anchor="middle" font-size="13" fill="#333">7</text>
  <text x="500" y="207" text-anchor="middle" font-size="13" fill="#333">8…</text>
  <rect x="46" y="120" width="349" height="26" fill="none" stroke="#2e7d32" stroke-width="1.5"/>
  <text x="220" y="112" text-anchor="middle" font-size="13" fill="#2e7d32">d ≤ 6：所有锥都是平坦半空间，自由边界光滑</text>
  <circle cx="450" cy="180" r="7" fill="none" stroke="#c0392b" stroke-width="2.5"/>
  <text x="420" y="158" text-anchor="middle" font-size="13" fill="#c0392b">d=7：非平坦锥出现</text>
  <text x="280" y="245" text-anchor="middle" font-size="13" fill="#666">n 维局部极小化子：奇点集维数 ≤ n−7，且该上界可以取到</text>
  <text x="280" y="267" text-anchor="middle" font-size="13" fill="#666">n=7 时奇点至多有限个；n=10 时奇点集维数至多 3</text>
</svg>

</div>

**为什么值得关心**

它与极小曲面里 Simons 锥的七维分界遥相呼应，补上了悬置多年的 5、6 维最后缺口。

> 暂无形式化证明（AI 结果待核验）

## 一句话结论
证明了一相 Bernoulli 问题的临界维度是 7：一至六维中所有一次齐次整体极小化子都是平坦半空间解，第七维起才存在非平坦极小化锥；因此自由边界在六维及以下光滑，更高维奇点集维数至多 `@@M@@n-7@@` 且该界可达。

## 问题背景
一相 Bernoulli 问题（one-phase Bernoulli problem）研究能量 `@@M@@J(v;B)=\int_B(|\nabla v|^2+\mathbf 1_{\{v>0\}})\,dx@@` 的极小化：函数在正相位内调和，但正相位要付出体积代价，于是正相位与零相位之间的自由边界（free boundary）本身成为未知对象。Alt 与 Caffarelli（1981）奠定了存在性与正则性理论，Weiss（1999）的单调性公式与维度约化进一步把一般极小化子的奇点研究归结为一次齐次（one-homogeneous）整体极小化子的分类：第一个非平坦（nonflat）极小化锥出现的维度 `@@M@@d_*@@` 恰好决定自由边界从哪个维度起出现奇点。Caffarelli–Jerison–Kenig（2004）与 Jerison–Savin（2015）证明截面光滑的稳定齐次解在四维及以下皆平坦，给出 `@@M@@d_*\ge 5@@`；De Silva–Jerison（2009）在七维构造出非平坦极小化锥，给出 `@@M@@d_*\le 7@@`。缺口正落在 5、6 两维——Jerison–Savin 指出用 Hessian 范数的幂作测试在这两维无法给出一致的稳定性判据——本文以新的配对构造补上了这最后一环。

## 主要结果
主定理：在 `@@M@@\mathbb R^d@@`、`@@M@@1\le d\le 6@@` 中，每个非零一次齐次整体极小化子（global minimizer）都是平坦（flat）的，即 `@@M@@u(x)=(x\cdot e)_+@@`，`@@M@@|e|=1@@`；而 `@@M@@\mathbb R^7@@` 中存在非平坦的一次齐次整体极小化子（即 De Silva–Jerison 锥）。因此临界维度 `@@M@@d_*=7@@`。

推论（奇点集的最优维数界）：对开集 `@@M@@D\subset\mathbb R^n@@` 中的非负局部极小化子，其内部自由边界在正则点附近光滑；奇点集 `@@M@@\operatorname{Sing}(u)@@` 在 `@@M@@n\le 6@@` 为空集，`@@M@@n=7@@` 时局部有限，`@@M@@n\ge 7@@` 时其 Hausdorff 维数（Hausdorff dimension）不超过 `@@M@@n-7@@`。将 De Silva–Jerison 锥与 `@@M@@\mathbb R^{n-7}@@` 作笛卡尔积（悬垂）可得达到该维数的整体极小化子，故估计是最优的。这与极小超曲面理论中 Simons 关于极小锥的著名论证遥相呼应。

## 证明思路
证明采用排除法：反设第一个非平坦极小化锥出现在 `@@M@@d\in\{5,6\}@@`。先做归约：在锥的非零自由边界点处作爆破（blowup），其极限沿该点方向平移不变，且其因子是低一维的整体极小化子，由 `@@M@@d_*@@` 的极小性必平坦，故这些点全为正则点。正则性理论进而使球面正集 `@@M@@\{g>0\}\subset S^{d-1}@@` 的每个连通分量为光滑紧区域；且必有一个分量上 `@@M@@T=\nabla^2g+g\,\Id@@` 不恒为零，否则逐分量论证可推出 `@@M@@u@@` 就是半空间，与非平坦矛盾。五维情形再把锥悬垂（suspension）成六维极小化子，其球面分量除光滑侧边界外恰有两个奇异尖端。于是一律归结为 `@@M@@S^5@@` 上的光滑区域 `@@M@@\Omega@@`（至多附加两个尖端），`@@M@@g@@` 满足 `@@M@@\Delta g=-5g@@`、边界上 `@@M@@g=0@@`、`@@M@@\nabla g=N@@`。接着从极小性直接推导第二变分的稳定性不等式：经过对自由边界层的细致展开，得 `@@M@@\int_{\partial\Omega}Hv^2\le\int_\Omega(|\nabla v|^2+4v^2)@@`，其中常数 4 来自最优径向 Hardy 阈值 `@@M@@\beta^2@@`，`@@M@@\beta=(m-1)/2@@`、`@@M@@m=5@@`。最后是代数核心：在 `@@M@@w=|T|>0@@` 处用 Hessian 的归一化形状 `@@M@@A=T/w@@` 同时构造标量测试 `@@M@@h=w^a\sqrt f@@`（`@@M@@a=29/50@@`）与向量场 `@@M@@Z@@`，目标是逐点不等式 `@@M@@\operatorname{div}Z\ge 4h^2+|\nabla h|^2+\epsilon_*w^{2a}@@` 与边界符号条件 `@@M@@N\cdot Z+Hh^2\ge\delta_*w^{2a+1}>0@@`。两组消去使这一构造成为可能：其一是 Laplace 收缩配合恒等式 `@@M@@\Delta T=5T@@`、反对称收缩配合球面曲率交换子，把 `@@M@@g@@` 的全部不定的四阶导数从 `@@M@@\operatorname{div}Z@@` 中清除；其二是边界上利用系数多项式关于 `@@M@@p@@` 的偶性与正交等变性，经法向反射把边界条件未能确定的偶法向分量全部清零。剩下的不等式只涉及有限多个归一化张量，论文以带权张量平方和与精确有理余项完成验证，全部系数列于附录表格。将两个不等式在 `@@M@@\Omega_+@@` 上积分，并与取 `@@M@@v=h@@` 的稳定性不等式比较，多出的严格正质量 `@@M@@\epsilon_*\int w^{2a}@@` 即给出矛盾。归一化数据在 `@@M@@w=0@@` 处与两个尖端处无定义，不能直接丢弃：正则化 Bochner 恒等式在 Hessian 零点附近给出可积权，悬垂的显式公式在尖端给出距离参数的可积幂，光滑乘积截断由此移除两处障碍并使所有误差项消失。

## 可信度与备注
本文是 OpenAI 的研究手稿，主结果暂无 Lean 形式化证明，验证状态以社区核验为准；OpenAI 官方亦声明未经形式化的结果可能存在问题。正文对归约、几何恒等式、稳定性推导与截断均给出完整证明，其中最技术性的代数证书部分以带权张量平方和与精确有理数余项界定成验证，系数全部公开于附录。本批次该结果族仅含此篇，其结论与 Jerison–Savin 的下界 `@@M@@d_*\ge5@@`、De Silva–Jerison 的七维构造首尾相接，共同锁定 `@@M@@d_*=7@@`。

{% endraw %}
