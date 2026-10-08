---
layout: default
title: "Minimal models and Mori fibre spaces for generalized log canonical Q-pairs"
family: "036"
discipline: "Algebraic and complex geometry"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | Minimal models and Mori fibre spaces for generalized log canonical Q-pairs

> 结果族 036：Numerical semiampleness and generalized minimal models　·　学科：Algebraic and complex geometry　·　验证状态：暂无形式化证明，请以社区核验为准

## 入门导读 🐣

整理房间只有两种好结局：要么把所有东西摆到互不冲突的稳定状态，要么发现房间本质上是一排锥形抽屉柜，每格抽屉都是简单形状。论文证明：连"带隐形行李"的广义 log canonical 形状——数据里额外揣着一件高阶模型上的 nef 部分 `@@M@@M@@`——也一定抵达其中一种结局，而且行李全程不丢。

**关键词卡片**

- 极小模型（minimal model）：伴随除子 `@@M@@K_X+B+M@@` 变 nef 的终点模型
- Mori 纤维空间（Mori fibre space）：整体呈一束简单纤维、负伴随除子在纤维上丰富的结构
- 伪有效（pseudo-effective）："总量不为负"，是走哪条岔路的判据
- 广义对（generalized pair）：额外携带 nef 数据 `@@M@@M@@` 的形状记账方式，`@@M@@M@@` 来自纤维化的模项
- log 差异（log discrepancy）：给奇点温和度打分的量，程序运行中只升不降

**看个具体例子**

<div>

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 560 280"><rect x="185" y="20" width="190" height="46" rx="10" fill="#e8eef7" stroke="#4a6fa5" stroke-width="2"/><text x="205" y="49" font-size="15" fill="#333">广义 lc 对 (X, B+M)</text><path d="M280 66 C280 100 150 95 150 130" fill="none" stroke="#333333" stroke-width="2"/><path d="M280 66 C280 100 410 95 410 130" fill="none" stroke="#333333" stroke-width="2"/><polygon points="144,128 156,128 150,142" fill="#333333"/><polygon points="404,128 416,128 410,142" fill="#333333"/><rect x="40" y="146" width="220" height="66" rx="10" fill="#e9f5ec" stroke="#3d8b57" stroke-width="2"/><text x="58" y="172" font-size="15" fill="#3d8b57">K+B+M 伪有效：</text><text x="62" y="196" font-size="15" fill="#3d8b57">极小模型（nef 终点）</text><rect x="310" y="146" width="220" height="66" rx="10" fill="#fdf1e3" stroke="#d98c3f" stroke-width="2"/><text x="345" y="172" font-size="15" fill="#d98c3f">非伪有效：</text><text x="322" y="196" font-size="15" fill="#d98c3f">Mori 纤维空间（锥束）</text><text x="120" y="248" font-size="15" fill="#666666">两种结局必居其一，nef 行李 M 全程固定</text></svg>

</div>

岔路的判据是纯数值的：`@@M@@K_X+B+M@@` 伪有效就走上路，得 nef 终点；否则走下路，得 Picard 数为 1 的收缩，负伴随除子在底上丰富。取 `@@M@@M=0@@` 即回到普通 log canonical 对的经典结论。

**为什么值得关心**

广义 log canonical 对上极小模型猜想的存在性形式由此解决（特征零），是整个纲领的地基；注意结论只保证"某个"程序终止，且 nef 终点尚不含半丰富——那要靠姊妹篇的丰度定理补齐。

> 暂无形式化证明（AI 结果待核验）

## 一句话结论
论文解决了广义 log canonical 对上极小模型猜想的存在性形式：伴随除子 `@@M@@K_X+B+M@@` 伪有效时存在极小模型（nef 终点），否则得 Mori 纤维空间，且全程固定 nef b-除子数据。取 `@@M@@M=0@@` 即恢复普通 log canonical 对的相应定理。

## 问题背景
极小模型纲领（minimal model program, MMP）要在双有理等价类中找典范除子符号确定的模型：要么 nef（极小模型），要么沿纤维为负（Mori 纤维空间）。Birkar–Cascini–Hacon–McKernan 在 big 的 klt 情形建立了存在性，但伪有效而非大的情形始终是难点。广义对（generalized pair，Birkar–Zhang 形式体系）在数据里额外保留高阶双有理模型上的 nef 除子 `@@M@@M@@`——它来自 Ambro 典范丛公式中的模项——因此存在性问题要求在固定这组 nef 数据下找模型。此前 Birkar、Han–Li、Lazić–Tsakanikas、Tsakanikas–Xie 等把 lc 情形约化到光滑相对问题或需附加终止性假设，光滑输入本身一直悬而未决。

## 主要结果
设 `@@M@@k@@` 为特征零代数闭域，`@@M@@(X,B+M)@@` 为射影广义 log canonical `@@M@@\mathbb{Q}@@`-对：`@@M@@X@@` 正规整射影，`@@M@@B@@` 有效有理边界，`@@M@@M@@` 是高阶模型上 nef 有理 Cartier 除子的迹，`@@M@@K_X+B+M@@` 为 `@@M@@\mathbb{Q}@@`-Cartier。定理断言存在双有理映射 `@@M@@\phi:X\dashrightarrow Y@@`（逆不收缩除子），使 `@@M@@(Y,B_Y+M_Y)@@` 仍 log canonical，且对所有公共函数域上的素除子 `@@M@@E@@` 有 log 差异（log discrepancy）不等式 `@@M@@A_{X,B+M}(E)\le A_{Y,B_Y+M_Y}(E)@@`，对被 `@@M@@\phi@@` 收缩的除子严格。且二择一由 `@@M@@D=K_X+B+M@@` 决定：`@@M@@D@@` 伪有效时 `@@M@@K_Y+B_Y+M_Y@@` 为 nef；`@@M@@D@@` 非伪有效时 `@@M@@Y@@` 带 Picard 数为 `@@M@@1@@` 的收缩 `@@M@@h:Y\to T@@`，使 `@@M@@-(K_Y+B_Y+M_Y)@@` 在 `@@M@@T@@` 上丰富。注意：结论只给出"某个"终止的程序选择，不断言任意 MMP 终止；nef 终点不含半丰富性。取 `@@M@@M=0@@` 得普通 log canonical 对的推论，此时配合姊妹篇的 log 丰富性定理，`@@M@@K_Y+B_Y@@` 在同一终点半丰富。

## 证明思路
证明从局部推向全局。核心局部命题是"相位定理"：对带循环群作用、具半不变体积形式的一列固定维数 Gorenstein klt 芽，可选出差异（discrepancy）一致有界的除子赋值 `@@M@@w'_i@@` 与固定正整数 `@@M@@\ell@@`，使每个半不变函数 `@@M@@h@@` 满足同余 `@@M@@w'_i(h)\equiv \ell\cdot\mathrm{angle}(\chi(\gamma_i)) \pmod{\mathbb{Z}}@@`。其证明先由稳定退化定理与体积最小化赋值（normalized volume minimizer，Li–Blum–Xu–Zhuang 理论）得到群不变的拟单项赋值及其有限生成分次代数，做等变有理重分次；再经约束赋值优化、对数 Cartier 选择与精确舍入；特征约化只在芽的有限数据固定后进行（用 Deligne–Illusie 型工具），一致性估计由有界表示、trait 计算与 lc 心关联给出，经塔约化与 lifting/mixing 定理得到整数跳跃估计和度数乘积界。全局演绎用反证：若光滑簇上带缩放的典范 MMP 无限，则缩放数趋于零（BCHM 标记丰富模型有限性），渐近乘子理想把累积差异变化控制住，使其在离散测试赋值集上的有限极限可数；相位定理用于循环指标一覆盖，排除典范指标无界——否则任意特征角都会落入可数集。固定公共 Cartier 倍数后，高阶直像消失与有效基点自由迫使某除子既整体生成又在某条收缩曲线上取负值，矛盾，故程序终止并给出弱 Zariski 分解。最后借助 Tsakanikas–Xie 的 NQC 广义 MMP 存在性定理把光滑相对结果转移到广义对，再做域下降，完成主定理。

## 可信度与备注
主结果暂无 Lean 形式化证明。本文与族内另两篇构成闭环：它为数值半丰富性论文提供终止的 MMP 与极小模型终点，而后者的 log 丰富性定理又把本文普通情形的 nef 终点升级为半丰富；证明大量引用 BCHM、Birkar、Tsakanikas–Xie 等既有结果并明确致谢转移步骤。依照 OpenAI 官方声明"未经形式化的结果可能有问题"，上述结论请以社区核验为准。

{% endraw %}
