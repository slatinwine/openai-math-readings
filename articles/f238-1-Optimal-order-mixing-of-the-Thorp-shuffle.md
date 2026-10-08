---
layout: default
title: "Optimal-order mixing of the Thorp shuffle"
family: "238"
discipline: "Probability and statistical mechanics"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | Optimal-order mixing of the Thorp shuffle

> 结果族 238：Optimal logarithmic mixing of the Thorp shuffle　·　学科：Probability and statistical mechanics　·　验证状态：暂无形式化证明，请以社区核验为准

## 入门导读 🐣

一台老式洗牌机：把 `@@M@@2^d@@` 张牌对半分开、前后对齐配成对，每一对掷一枚公平硬币——正面就交换、反面就不动——再交错合拢。单张牌很快就洗匀了，但所有牌共用同一批硬币，整副牌的"秩序"顽固得多。这篇论文给出最终答案：恰好 `@@M@@\Theta(d)@@` 次完整洗牌，不多不少（就数量级而言）。

**关键词卡片**

- Thorp 洗牌（Thorp shuffle）：上述"配对掷硬币"式洗牌，1973 年为分析 Faro 牌技而提出。
- 混合时间（mixing time）：牌序分布与均匀分布的距离首次降到 `@@M@@1/4@@` 以下所需的洗牌次数。
- 总变差（total variation）：衡量两个分布相差多远的量，`@@M@@\|\mu-\nu\|_{\mathrm{TV}}=\frac12\sum_g|\mu(g)-\nu(g)|@@`。
- 支撑计数（support counting）：下界论证——`@@M@@t@@` 次洗牌至多产生 `@@M@@2^{tn/2}@@` 种硬币结果，远少于 `@@M@@n!@@` 种排列。

**看个具体例子**

取 `@@M@@n=2^{10}=1024@@` 张牌：每次洗牌只消耗 `@@M@@n/2=512@@` 个随机比特，硬币结果的总数远不够区分 `@@M@@n!@@` 种排列，故 `@@M@@t\ge 2d-O(1)\approx 20@@` 次；另一端，数字版定理给出 `@@M@@\|q_d^{*(1600d)}-U_n\|_{\mathrm{TV}}=\|q^{*16000}-U\|_{\mathrm{TV}}\to 0@@`，即一万六千次后任何初始牌序都被洗匀。

<div>

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 560 280">
  <rect x="90" y="88" width="60" height="36" fill="none" stroke="#555" stroke-width="1.5"/>
  <rect x="190" y="88" width="60" height="36" fill="none" stroke="#555" stroke-width="1.5"/>
  <rect x="290" y="88" width="60" height="36" fill="none" stroke="#555" stroke-width="1.5"/>
  <rect x="390" y="88" width="60" height="36" fill="none" stroke="#555" stroke-width="1.5"/>
  <rect x="90" y="176" width="60" height="36" fill="none" stroke="#555" stroke-width="1.5"/>
  <rect x="190" y="176" width="60" height="36" fill="none" stroke="#555" stroke-width="1.5"/>
  <rect x="290" y="176" width="60" height="36" fill="none" stroke="#555" stroke-width="1.5"/>
  <rect x="390" y="176" width="60" height="36" fill="none" stroke="#555" stroke-width="1.5"/>
  <path d="M103 128 L137 172" fill="none" stroke="#c0392b" stroke-width="2"/>
  <path d="M137 128 L103 172" fill="none" stroke="#c0392b" stroke-width="2"/>
  <line x1="220" y1="124" x2="220" y2="176" stroke="#ccc" stroke-width="1.5" stroke-dasharray="4 3"/>
  <line x1="320" y1="124" x2="320" y2="176" stroke="#ccc" stroke-width="1.5" stroke-dasharray="4 3"/>
  <line x1="420" y1="124" x2="420" y2="176" stroke="#ccc" stroke-width="1.5" stroke-dasharray="4 3"/>
  <circle cx="220" cy="150" r="10" fill="none" stroke="#666" stroke-width="1.5"/>
  <circle cx="320" cy="150" r="10" fill="none" stroke="#666" stroke-width="1.5"/>
  <circle cx="420" cy="150" r="10" fill="none" stroke="#666" stroke-width="1.5"/>
  <text x="34" y="110" font-size="14" fill="#333">上半副</text>
  <text x="34" y="200" font-size="14" fill="#333">下半副</text>
  <text x="150" y="155" font-size="13" fill="#c0392b">交换</text>
  <text x="446" y="155" font-size="13" fill="#666">掷硬币</text>
  <text x="46" y="252" font-size="13" fill="#333">每对独立掷公平硬币：正=交换（红），反=保持</text>
  <text x="46" y="270" font-size="13" fill="#333">之后交错合拢，完成一次完整洗牌</text>
</svg>

</div>

**为什么值得关心**

此前最好结果是 `@@M@@O(d^3)@@`，对数阶是悬置多年的目标；本文首次达到并配上同阶下界。常数 `@@M@@1600@@` 是证明里的显式选择而非最优值，更小的领先常数与切断现象留作公开问题。顺带还得到：用 `@@M@@O(n\log n)@@` 个公平比特即可生成近似均匀的随机排列，且这个比特数已是必需。

> 暂无形式化证明（AI 结果待核验）

## 一句话结论

证明 `@@M@@2^d@@` 张牌的 Thorp 洗牌经 `@@M@@1600d@@` 次完整洗牌后，整副牌的排列律在总变差（total variation）意义下收敛到均匀分布，而支撑计数给出 `@@M@@2d-O(1)@@` 的下界，从而把该洗牌的最优混合阶确定为 `@@M@@\Theta(d)=\Theta(\log N)@@`。

## 问题背景

Thorp 洗牌由 Thorp 于 1973 年研究非随机洗牌对 Faro 纸牌游戏的影响时提出：把 `@@M@@2^d@@` 张牌等分成两半，配对处于对应位置的牌，每对内部次序由一枚独立公平硬币决定，再交错合并。其微妙之处在于：`@@M@@d@@` 次洗牌后每张牌的位置已单独均匀，但所有牌共用同一组硬币，轨迹高度相关，整副牌的联合排列远未随机。整副牌到底需要多少次洗牌，悬置多年：Morris 用演化集（evolving set）方法首先给出多项式界 `@@M@@O(d^{44})@@`，Montenegro 与 Tetali 改进到 `@@M@@O(d^{29})@@`，Morris 又用相对熵方法得到一般偶数牌数的 `@@M@@O((\log n)^4)@@` 与二进制牌数的 `@@M@@O(d^3)@@`；对数阶正是 Jonasson 笔记中讨论的目标。本文首次达到这一最优阶。

## 主要结果

记 `@@M@@q_d@@` 为一次完整洗牌作为位置置换的分布，`@@M@@U_n@@` 为对称群（symmetric group）`@@M@@S_n@@`上的均匀分布，距离取总变差 `@@M@@\|\mu-\nu\|_{\mathrm{TV}}=\frac12\sum_g|\mu(g)-\nu(g)|@@`，混合时间（mixing time）`@@M@@t_{\mathrm{mix}}(d)@@` 是距离首次不超过 `@@M@@1/4@@` 的时刻。主定理分两半：上半是当 `@@M@@d\to\infty@@` 时 `@@M@@\|q_d^{*(1600d)}-U_n\|_{\mathrm{TV}}\to0@@`，且对任意确定性初始牌序一致成立；下半是支撑下界——`@@M@@t@@` 次洗牌至多产生 `@@M@@2^{tn/2}@@` 种硬币串，故 `@@M@@\|q_d^{*t}-U_n\|_{\mathrm{TV}}\ge1-2^{tn/2}/n!@@`，距离不超过 `@@M@@1/4@@` 就迫使 `@@M@@t\ge\lceil\frac2n\log_2\frac{3n!}{4}\rceil=2d-O(1)@@`。合并得 `@@M@@t_{\mathrm{mix}}(d)=\Theta(d)@@`。常数 `@@M@@1600@@` 是证明中的显式选择而非最优值，领先常数与切断现象（cutoff）留作公开问题。附带推论：该洗牌以 `@@M@@O(n\log n)@@` 个公平比特生成近似均匀的随机排列，而支撑论证表明同阶比特数是必要的。

## 证明思路

先把位置等同于 `@@M@@\mathbb F_2^d@@` 的顶点：一次物理洗牌是确定性坐标循环 `@@M@@R@@` 与沿方向 `@@M@@e_1@@` 的随机开关 `@@M@@S@@` 之复合；撤销旋转后，相继洗牌变成沿相继坐标方向的独立开关层，扫完 `@@M@@d@@` 个方向恰花 `@@M@@d@@` 次洗牌，单牌均匀性由此立得。

上界分两阶段。第一阶段控制"大部分牌"的联合位置：先均匀随机选取 `@@M@@7n/8@@` 张牌的有序表并逐张暴露轨迹，考察下一张被追踪牌在剩余位置上的条件分布与均匀分布之差，即中心化流 `@@M@@w_s@@`。两个位置都空闲的开关把两份质量平均，平方范数不增；只剩一个空闲位置的开关被迫沿已暴露路径输运质量，恰好产生条件均值为零的噪声，写成 `@@M@@w_{s+1}=A_{i_s}w_s+\xi_s@@`。由于 `@@M@@d@@` 个坐标平均算子的乘积把任何均值为零的向量映为其整体均值，能量恒等式断言当前能量恰是上一扫各时刻噪声的加权和。为控制噪声，向前回看 `@@M@@d-1@@` 个方向：这些更新在两个对半内部独立进行，故一半内的流值与另一半伙伴位置是否空闲条件独立；配合随机表以高概率（Azuma–Hoeffding 集中）在两半各留固定比例空位，得标量递推，能量几何衰减为 `@@M@@(31/32)^{t-2d}@@` 加指数小项。最后用逐张序列比较引理与 Cauchy–Schwarz 不等式，得 `@@M@@200d@@` 次后随机表联合位置平均以 `@@M@@O(n^{-5/2})@@` 接近均匀注入分布。

第二阶段把缺掉的八分之一的依赖关系补回全群。把标签分成八块，由平均值论证可选定一个确定性划分，使八个补集边际——等价于相应块子群左陪集（coset）的分布——总误差 `@@M@@o(1)@@`；删去超重陪集得到公共的邻近律 `@@M@@\nu@@`，其八个陪集系质量都被均匀值的四倍封顶。再把 `@@M@@S_n@@` 的不可约表示 `@@M@@\rho@@`（维数 `@@M@@D@@`）限制到八个块子群之积上：每个张量分量必有某因子维数不超过 `@@M@@D^{1/8}@@`，而单个向量在该块子群轨道下张成的空间维数不超过小因子维数的平方之和——关键在于多重性不放大轨道维数，因为群作用经由一个维数 `@@M@@a^2@@` 的矩阵空间实现；再用钩长公式（hook-length formula）初等证明的互逆维数和 `@@M@@\sum_\lambda(f^\lambda)^{-1}\le C_1@@` 控制，得 Fourier 算子范数 `@@M@@\|\widehat\nu(\rho)\|_{\mathrm{op}}\le AD^{-5/16}@@`。收尾用 Diaconis–Shahshahani 的 Plancherel 上界：八个因子的非平凡、非符号贡献以 `@@M@@\sum D^{-3}@@` 计趋于零；符号表示单独处理——固定最后一步洗牌的其余硬币，翻动最后一枚等价于复合对换（transposition），故符号均值为零。把八个独立的 `@@M@@200d@@` 时间块换回原律即得 `@@M@@q_d^{*(1600d)}@@` 的收敛。

## 可信度与备注

本文是 OpenAI 手稿，主结果尚未形式化；按 OpenAI 官方声明"未经形式化的结果可能有问题"，请以社区核验为准。本篇证明自包含：坐标收缩与八块传递均在内文完成，未引用任何姊妹篇；姊妹篇"随机坐标架"用随机方向序列独立证得 `@@M@@32800d@@` 的收敛，"Fourier 传递"篇则把第二阶段的表示论提升抽象为一般定理，三者在 `@@M@@\Theta(d)@@` 这一结论上互相印证。下界 `@@M@@2d-O(1)@@` 是初等支撑计数，各篇独立推导一致。

{% endraw %}
