---
layout: default
title: "Integral points on character varieties of curves"
family: "027"
discipline: "Number theory"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | Integral points on character varieties of curves

> 结果族 027：Potential integral density on curve character varieties　·　学科：Number theory　·　验证状态：暂无形式化证明，请以社区核验为准

## 入门导读 🐣

给一个"带洞的曲面"（比如扎了孔的甜甜圈皮）编一本完整的对称性花名册，数学家把这本花名册本身看成一个几何空间，叫特征簇。论文问：花名册里的"整点"——坐标全是整数的条目——多不多？结论：换一个稍大的数系后，整点在花名册里到处都是，洞口还能贴上事先指定的标签。

**关键词卡片**

- 特征簇（character variety）：把曲面上圈的"矩阵对称性"打包参数化得到的空间。
- 整点（integral point）：坐标属于整数环的点，是算术上最干净的点。
- Zariski 稠密（Zariski dense）：一种严格的"到处都是"：不挤在任何低维曲面上，能撑满整个空间。
- 拟幺幂（quasi-unipotent）：特征值全是单位根的矩阵，描述绕洞一圈的边界行为。
- 潜在（potential）：允许先把系数域扩大一次，结论才成立。

**看个具体例子**

整点稠密并不寻常：单位圆 x² + y² = 1 上只有 (±1,0)、(0,±1) 四个整点，稀稀拉拉。本文证明：任何光滑复曲线的 SL_r-特征簇，在某个有限扩域的整数环上整点必然 Zariski 稠密，且在每个不可约分支里都稠密——洞口的共轭类还可指定为单位根型。

<div>

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 560 280"><line x1="70" y1="40" x2="70" y2="240" stroke="#ddd" stroke-width="1"/><line x1="110" y1="40" x2="110" y2="240" stroke="#ddd" stroke-width="1"/><line x1="150" y1="40" x2="150" y2="240" stroke="#ddd" stroke-width="1"/><line x1="190" y1="40" x2="190" y2="240" stroke="#ddd" stroke-width="1"/><line x1="230" y1="40" x2="230" y2="240" stroke="#ddd" stroke-width="1"/><line x1="50" y1="60" x2="250" y2="60" stroke="#ddd" stroke-width="1"/><line x1="50" y1="100" x2="250" y2="100" stroke="#ddd" stroke-width="1"/><line x1="50" y1="140" x2="250" y2="140" stroke="#ddd" stroke-width="1"/><line x1="50" y1="180" x2="250" y2="180" stroke="#ddd" stroke-width="1"/><line x1="50" y1="220" x2="250" y2="220" stroke="#ddd" stroke-width="1"/><circle cx="150" cy="140" r="80" fill="none" stroke="#1e8449" stroke-width="3"/><circle cx="70" cy="140" r="6" fill="#c0392b"/><circle cx="230" cy="140" r="6" fill="#c0392b"/><circle cx="150" cy="60" r="6" fill="#c0392b"/><circle cx="150" cy="220" r="6" fill="#c0392b"/><line x1="285" y1="30" x2="285" y2="250" stroke="#ddd" stroke-width="1" stroke-dasharray="5 4"/><ellipse cx="430" cy="140" rx="90" ry="80" fill="none" stroke="#1e8449" stroke-width="3"/><circle cx="358" cy="140" r="3" fill="#c0392b"/><circle cx="382" cy="140" r="3" fill="#c0392b"/><circle cx="406" cy="140" r="3" fill="#c0392b"/><circle cx="430" cy="140" r="3" fill="#c0392b"/><circle cx="454" cy="140" r="3" fill="#c0392b"/><circle cx="478" cy="140" r="3" fill="#c0392b"/><circle cx="502" cy="140" r="3" fill="#c0392b"/><circle cx="370" cy="116" r="3" fill="#c0392b"/><circle cx="394" cy="116" r="3" fill="#c0392b"/><circle cx="418" cy="116" r="3" fill="#c0392b"/><circle cx="442" cy="116" r="3" fill="#c0392b"/><circle cx="466" cy="116" r="3" fill="#c0392b"/><circle cx="490" cy="116" r="3" fill="#c0392b"/><circle cx="370" cy="164" r="3" fill="#c0392b"/><circle cx="394" cy="164" r="3" fill="#c0392b"/><circle cx="418" cy="164" r="3" fill="#c0392b"/><circle cx="442" cy="164" r="3" fill="#c0392b"/><circle cx="466" cy="164" r="3" fill="#c0392b"/><circle cx="490" cy="164" r="3" fill="#c0392b"/><circle cx="376" cy="92" r="3" fill="#c0392b"/><circle cx="400" cy="92" r="3" fill="#c0392b"/><circle cx="424" cy="92" r="3" fill="#c0392b"/><circle cx="448" cy="92" r="3" fill="#c0392b"/><circle cx="472" cy="92" r="3" fill="#c0392b"/><circle cx="376" cy="188" r="3" fill="#c0392b"/><circle cx="400" cy="188" r="3" fill="#c0392b"/><circle cx="424" cy="188" r="3" fill="#c0392b"/><circle cx="448" cy="188" r="3" fill="#c0392b"/><circle cx="472" cy="188" r="3" fill="#c0392b"/><circle cx="382" cy="68" r="3" fill="#c0392b"/><circle cx="406" cy="68" r="3" fill="#c0392b"/><circle cx="430" cy="68" r="3" fill="#c0392b"/><circle cx="454" cy="68" r="3" fill="#c0392b"/><circle cx="478" cy="68" r="3" fill="#c0392b"/><circle cx="382" cy="212" r="3" fill="#c0392b"/><circle cx="406" cy="212" r="3" fill="#c0392b"/><circle cx="430" cy="212" r="3" fill="#c0392b"/><circle cx="454" cy="212" r="3" fill="#c0392b"/><circle cx="478" cy="212" r="3" fill="#c0392b"/><text x="150" y="264" font-size="14" text-anchor="middle" fill="#333">圆：整点只有 4 个（稀疏）</text><text x="430" y="264" font-size="14" text-anchor="middle" fill="#333">特征簇：整点稠密（扩域后）</text></svg>

</div>

**为什么值得关心**

它肯定回答了 Litt 的潜在整密度问题在曲线情形的版本，并把此前只对秩 2（SL_2）成立的结论推广到任意秩 r 的 SL_r。

> 暂无形式化证明（AI 结果待核验）

## 一句话结论

论文证明：对任何光滑连通复代数曲线与任意秩 `@@M@@r@@`，其 `@@M@@\SL_r@@`-特征簇的整点在某个数域的全整数环上必然 Zariski 稠密，且允许在穿孔处指定任意拟幺幂边界共轭类（含非半单类），并在每一分支上成立——肯定回答了 Litt 整密度问题的曲线、行列式一情形。

## 问题背景

设 `@@M@@X@@` 为光滑连通复代数曲线，其 `@@M@@\SL_r@@`-特征簇（character variety）`@@M@@M_r(X)@@` 参数化 `@@M@@\pi_1(X)@@` 的半单表示（semisimple representation）的同构类。虽然 `@@M@@X@@` 未必定义在数域上，但用 `@@M@@\pi_1(X)@@` 的有限表示可在 `@@M@@\mathbb{Z}@@` 上写出表示概形，取其共轭不变量环的谱，即得 `@@M@@M_r(X)@@` 的自然整模型（integral model），于是能问算术问题：整点何时 Zariski 稠密？扩一次基域是否就够？这正是 Litt 的潜在整密度问题（其综述中的 Question 5.4.3(2)），Coccia–Litt 又给出带边界数据的猜想版本。此前结果各有缺口：Simpson 猜想与 Esnault–Groechenig 一线需要刚性假设，de Jong–Esnault 只给出逐素存在的 `@@M@@\ell@@`-adic 局部系统，Coccia–Litt 仅处理秩二的 `@@M@@\SL_2@@` 与 `@@M@@\mathrm{PGL}_2@@`。真正的拦路虎是曲面关系 `@@M@@\prod_j[A_j,B_j]=\cdots@@` 把所有柄矩阵耦合在一起，而允许非半单、非正则的边界类，以及非一般位置的分支，使得纯几何的参数化方法失效。

## 主要结果

主定理（文中定理 1.1）：设 `@@M@@X@@` 光滑连通，`@@M@@r\geq1@@`，在每个穿孔处指定拟幺幂（quasi-unipotent，即全部特征值都是单位根）共轭类 `@@M@@C_1,\dots,C_s\subset\SL_r(\mathbb{C})@@`，`@@M@@K@@` 为包含其特征值的数域。则存在有限扩张 `@@M@@L/K@@`，使得 `@@M@@M_r(X)(\cO_L)\cap Y(\mathbb{C})@@` 在边界轨迹 `@@M@@Y@@` 中 Zariski 稠密，从而在 `@@M@@Y@@` 的每个不可约分支（irreducible component）中都稠密；`@@M@@Y@@` 由半单表示的边界单值 `@@M@@\rho(\gamma_i)@@` 恰好落在指定类中刻画。整性采用"环境整性"（ambient integrality）：点须延拓到 `@@M@@M_r(X)@@` 在全整数环 `@@M@@\cO_L@@` 上的模型，而精确边界条件施加于复表示一侧，不要求在每个有限素处避开更小的 Jordan 类。只指定特征多项式（根全为单位根）的版本、以及不带边界条件的整簇（此时可取 `@@M@@K=\mathbb{Q}@@`）同样成立。扩张还可显式统一给出：取相异素数 `@@M@@p,q>r@@`，令 `@@M@@F=K(\sqrt2,\zeta_{pq})@@`、`@@M@@L=F\bigl(\zeta_r,\{u^{1/r}:u\in\cO_F^\times\}\bigr)@@`，由 Dirichlet 单位定理它是有限扩张，且对整个轨迹、所有分支固定不变。若 `@@M@@X@@` 非射影且不加边界条件，则 `@@M@@\pi_1(X)@@` 是自由群、`@@M@@\SL_r(\mathbb{Z})@@` 已在 `@@M@@\SL_r(\mathbb{C})@@` 中稠密，结论平凡。

## 证明思路

证明按"先换群、再降秩、后下降"三段推进。

第一步从 `@@M@@\SL_n@@` 换到 `@@M@@\GL_n@@`：直和、子空间与商空间从此不受行列式限制。指定 Jordan 型的边界矩阵容许一个不变旗（invariant flag），其逐次商上作用为纯量单位根；据此在每个穿孔外套上若干带纯量单值的穿孔圆盘"帽子"。问题化为"曲面图"（surface diagram）：若干赋秩曲面沿边缝以父—子过滤和已认同的分次商相连。可复用的引擎是图密度定理（diagram density）：任何曲面图的整解在其复解簇中 Zariski 稠密，证明对最大秩作归纳。

非闭的归纳步骤把带边最大秩面切成圆盘。切口两端的旗由"双子旗引理"比较：按交秩数组 `@@M@@(m_{ij})@@` 把两面旗细化为带标签的块，再用相邻交换重新排序，切带被替换为低秩条带；回粘的匹配参数构成局部仿射丛，其整参数稠密。对每个圆盘，取起始边界旗的一个真前缀子空间 `@@M@@U@@`：穿孔单值全是纯量，故 `@@M@@U@@` 平行延拓成子系统，商 `@@M@@Q=V/U@@` 使秩数下降；丢失的扩张信息靠逐次线性映射补回，前缀使起始区间上的提升唯一，绕边界一周不再产生新方程。矩阵交换顶点处则插入纯量单值为 `@@M@@-I@@` 的秩 `@@M@@h@@` 小圆盘，其符号恰使短正合列闭合，避免除以 `@@M@@2@@`。

闭曲面带来簇 `@@M@@\mathcal R_{n,g}(c)=\{\prod_j[A_j,B_j]=cI_n\}@@`。亏格一时可用 clock-and-shift 坐标化为交换矩阵对的密度（Motzkin–Taussky）；亏格至少二时先证不可约性：在有限域上仿 Liebeck–Shalev 做特征标计数得点数 `@@M@@|G|^{2g-1}(1+O_n(q^{-(n-1)}))@@`，结合主理想定理的维数下界与 Lang–Weil 估计得唯一分支。密度分两步：先沿非分离圆切开并固定谱 `@@M@@\alpha_i=\zeta^{i-1}@@`——谱差是单位，谱投影子有整系数，粘合参数是环面 `@@M@@(\Gm)^n@@` 且单位稠密；再用 Dehn 扭转 `@@M@@(A_1,B_1)\mapsto(A_1B_1^{\pm1},B_1)@@`，它保持簇与整点集，在显式检测点借 Baire 纲论证找到乘法无关的谱，使 `@@M@@B_1@@` 的幂在中心化环面中稠密，而全纯扭转族在该点浸没、其像含解析开集，故 Zariski 稠密。

最后下降：构造的整表示各柄行列式都是 `@@M@@\cO_F@@` 单位，一次性添加全部单位的 `@@M@@r@@` 次根得 `@@M@@L@@` 后，标量扭转映射是幂映射 `@@M@@[r]:T\to T@@` 的拉回，有限、平展且开，于是 `@@M@@\SL_r(\cO_L)@@` 表示稠密。精确 Jordan 类最后才在特征商上选取：它是闭秩约束像中的开集 `@@M@@q(C)\setminus q(C_{\mathrm{bad}})@@`，稠密集与之相交即稠密。此次序不可倒置——半单化可能缩小边界 Jordan 块。三个标准输入各就其位：不变量有限生成给出模型，Dirichlet 单位定理给出单一数域（`@@M@@\sqrt2@@` 使 `@@M@@1+\sqrt2@@` 为无限阶单位），Lang–Weil 把计数化为不可约性。

## 可信度与备注

本文为 OpenAI 手稿，暂无 Lean 形式化证明；按官方声明，"未经形式化的结果可能有问题"，请以社区核验为准。行文自含，模型、降秩、闭曲面与动力学、下降四章给出全部关键构造与引理。本批结果族 027 仅此一篇，其外部支撑在于与既有定理的衔接：秩二情形可与 Coccia–Litt 的曲面定理互相推导（文中附比较注记），不可约性沿用 Liebeck–Shalev 的计数方法，亏格一密度化归于 Motzkin–Taussky 型交换对结论，而高维、高秩的 Litt 问题仍在范围之外。

{% endraw %}
