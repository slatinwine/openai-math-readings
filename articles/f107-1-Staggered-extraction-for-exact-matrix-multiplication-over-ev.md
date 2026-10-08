---
layout: default
title: "Staggered extraction for exact matrix multiplication over every field"
family: "107"
discipline: "Theoretical computer science"
formalized: true
source: null
pdfname: ""
---

{% raw %}
# 解读 | Staggered extraction for exact matrix multiplication over every field

> 结果族 107：Matrix multiplication with exponent at most 9/4　·　学科：Theoretical computer science　·　验证状态：主结果已 Lean 形式化

## 入门导读 🐣

同门的旗舰结果在复数域上把矩阵乘法纪录砍到 2.25，但那套证法用到了复数独有的便利。这篇论文把同类思想重造成一台"全地形"机器：不做除法、不玩插值，逐系数算得精确，于是在任何数域——包括 `@@M@@1+1=0@@` 这类正特征世界——都成立，并微弱刷新纪录到 2.371054886…。秘诀之一像工厂错峰排班：让不同批次错时开工，三道工序互不空转。

**关键词卡片**

- 域（field）：能做加减乘除的数系；"特征"指多少个 1 相加会归零
- 正特征（positive characteristic）：如模 2 算术，`@@M@@1+1=0@@`；插值、除法技巧在此常失效
- 精确算法（exact algorithm）：不用近似与极限，每个系数一次算对
- 联合抽取（joint extraction）：把不同阶段的分离操作并成一次，短缺与富余互补
- 错峰调度（staggering）：批次错开启动，让各阶段容量互相补齐、损耗在指数尺度相消

**看个具体例子**

一批张量要连续三次对半分裂（`@@M@@8\to4\to2\to1@@`）；多批错峰启动后，稳定时段每道工序都有活干。

<div>

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 560 280">
<text x="270" y="30" text-anchor="middle" font-size="14">错峰调度：三批工件先后流过 A→B→C 三道工序</text>
<rect x="60" y="48" width="88" height="34" fill="#e8eef8" stroke="#345" stroke-width="2"/>
<text x="104" y="69" text-anchor="middle" font-size="13">A：8→4</text>
<rect x="152" y="48" width="88" height="34" fill="#e8f8e8" stroke="#383" stroke-width="2"/>
<text x="196" y="69" text-anchor="middle" font-size="13">B：4→2</text>
<rect x="244" y="48" width="88" height="34" fill="#f8e8d8" stroke="#a73" stroke-width="2"/>
<text x="288" y="69" text-anchor="middle" font-size="13">C：2→1</text>
<rect x="152" y="102" width="88" height="34" fill="#e8eef8" stroke="#345" stroke-width="2"/>
<text x="196" y="123" text-anchor="middle" font-size="13">A：8→4</text>
<rect x="244" y="102" width="88" height="34" fill="#e8f8e8" stroke="#383" stroke-width="2"/>
<text x="288" y="123" text-anchor="middle" font-size="13">B：4→2</text>
<rect x="336" y="102" width="88" height="34" fill="#f8e8d8" stroke="#a73" stroke-width="2"/>
<text x="380" y="123" text-anchor="middle" font-size="13">C：2→1</text>
<rect x="244" y="156" width="88" height="34" fill="#e8eef8" stroke="#345" stroke-width="2"/>
<text x="288" y="177" text-anchor="middle" font-size="13">A：8→4</text>
<rect x="336" y="156" width="88" height="34" fill="#e8f8e8" stroke="#383" stroke-width="2"/>
<text x="380" y="177" text-anchor="middle" font-size="13">B：4→2</text>
<rect x="428" y="156" width="88" height="34" fill="#f8e8d8" stroke="#a73" stroke-width="2"/>
<text x="472" y="177" text-anchor="middle" font-size="13">C：2→1</text>
<text x="32" y="69" text-anchor="middle" font-size="12" fill="#567">批1</text>
<text x="32" y="123" text-anchor="middle" font-size="12" fill="#567">批2</text>
<text x="32" y="177" text-anchor="middle" font-size="12" fill="#567">批3</text>
<line x1="332" y1="40" x2="332" y2="200" stroke="#c33" stroke-width="1.5" stroke-dasharray="5,4"/>
<text x="332" y="218" text-anchor="middle" font-size="12" fill="#c33">此刻：批1 在 C、批2 在 B、批3 在 A</text>
<text x="270" y="248" text-anchor="middle" font-size="12" fill="#567">三道工序互不空转，容量互补，指数记账时损耗相消</text>
</svg>

</div>

数字版结论：对每个固定域 `@@M@@\mathbb F@@`，`@@M@@\omega_{\mathbb F}<2.371054886006746<2.371177@@`（此前的世界纪录），且算法在原域上逐系数精确。

**为什么值得关心**

现代纪录首次覆盖包括正特征在内的一切固定域，并附有理区间证书，可复现核验。

> 已 Lean 形式化

## 一句话结论
本文证明对每个固定域 `@@M@@\mathbb F@@`——包括所有正特征域——方阵乘法的算术指数满足 `@@M@@\omega_{\mathbb F}<2.371054886006746@@`，小幅超越 Dupont 等人 2026 年的 2.371177；算法逐系数精确、全程在原域上进行，不依赖插值或除法。

## 问题背景
矩阵乘法指数 `@@M@@\omega@@` 的所有现代上界都源于张量方法：Bini 的近似—精确转换、Schönhage 渐近和不等式、Strassen 激光方法，以及 Coppersmith–Winograd 张量高次幂分析。这条路线的绝大多数论证默认在复数域上进行——边界秩与退化要用参数极限和插值，转移到正特征域历来需要额外的谨慎处理。另一方面，Duan–Wu–Zhou 的非对称哈希压缩了合并损失（combination loss），Vassilevska Williams–Xu–Xu–Zhou 把三边删除的恢复论证推广到受限张量积，Alman 等六作者又引入对三边区别对待的相继相容性测试；Dupont 等 2026 年用现代优化加 AlphaEvolve 把八次幂实例调到 2.371177。本文在同一非对称框架内加入跨深度联合抽取与错峰调度两个新想法，并给出完全避开插值的整数系数构造，从而在所有域上一致越过 2.3711。

## 主要结果
定理：在每个固定域 `@@M@@\mathbb F@@` 上，方阵矩阵乘法的算术指数满足 `@@M@@\omega_{\mathbb F}<2.371054886006746<2.371054887@@`。构造给出精确算术算法，有限选择与输入矩阵无关；论文明确不涉及比特复杂度与实用交叉点估计。

## 证明思路
第一步是域无关的秩界，也是全文能覆盖正特征的关键。利用 Coppersmith–Winograd 的 Laurent 多项式恒等式，把 `@@M@@\mathrm{CW}_q@@` 写成 `@@M@@q+2@@` 个三项 Laurent 线性型之积的组合，再直接读取 `@@M@@m@@` 次张量幂的 `@@M@@t^0@@` 系数——不做插值、不做除法——得到 `@@M@@\mathrm R(\mathrm{CW}_q^{\otimes m})\le(q+2)^m\binom{3m+2}{2}@@` 对每个域成立；取 `@@M@@q=5@@`，每份张量的秩至多 `@@M@@7^m@@` 乘一个多项式因子。

此后进入束（strand）与形状的语言。一条长度 `@@M@@\ell@@` 的束是 `@@M@@\mathrm{CW}_5^{\otimes\ell}@@` 的拷贝，各边指标字按标签权重 `@@M@@0,1,\dots,1,2@@` 求和得到形状；正形状的束继续对半分裂（长度 `@@M@@8\to4\to2\to1@@`），含零坐标的形状立即是矩阵乘法张量。每个深度上的抽取对三条物理边做相继的相容性测试，每个测试给出一个方向容量（directional capacity）——该边能保住的输出数目的对数上界，总保证取三者最小值。

新想法之一是联合抽取：此前的分析只把同一深度内不同规定的总体合并，本文允许把不同深度（阶段）的总体放进同一次抽取，只要它们的优先序在物理边上一致。收益由不等式 `@@M@@\sum_r\min_W v_{r,W}\le\min_W\sum_r v_{r,W}@@` 刻画——某深度在某边的容量短缺可由另一深度的富余弥补。抽取先在第一边按权重和序列把变量分成粗块、每块唯一指派给一个输出，再由相容性决定第二、三边保留哪些变量。随后是恢复定理：被类型条件与竞争指派删除的变量，证明其在每个轨道上至多均匀失去 `@@M@@C/N@@` 比例；独立的对称平移覆盖理想张量，按变量是否出现划分，恰好在原域上把每个系数重建一次，只需次指数多份独立输入拷贝。

新想法之二是错峰调度（staggering）。一批含 `@@M@@N@@` 条长度 8 的束；`@@M@@K@@` 批错峰启动，使内部时刻上分裂阶段 A（`@@M@@8\to4@@`）、B（`@@M@@4\to2@@`）、C（`@@M@@2\to1@@`）各有一批在场。阶段 C 的抽取顺序可自由安排，论文用比例 `@@M@@\lambda_i@@` 调配，使三个阶段的容量向量之和恰为均衡向量 `@@M@@(C_*,C_*,C_*)@@`；六种物理轴序划分全部工作量，每种各做一次联合抽取，六个输出计数相乘；边界时刻的亏损 `@@M@@\beta<1@@`。合计对数产率为 `@@M@@K(H_0+C_*)-\beta@@`。最后由相同加数的直和秩不等式得 `@@M@@\omega_{\mathbb F}\le3(8\log7-H_0-C_*)/S_*@@`，其中 `@@M@@S_*@@` 是终端矩阵体积；论文第 7 节与附录的有理参数表和区间证书证实 `@@M@@S_*>0@@` 且该比值低于定理界。极限顺序为先令 `@@M@@N\to\infty@@` 再令批数增长，使边界损失消失。

## 可信度与备注
主结果已 Lean 形式化，且数值参数附有可复现的验证器与有理—对数区间证书。本文是结果族 107 的第三篇：旗舰篇在复数域证明 `@@M@@\omega\le9/4@@`，姊妹篇给出特征零域的 `@@M@@\omega<2.258@@` 与矩形、对偶纪录，本文则以纯代数构造覆盖包括正特征在内的一切固定域，三者的共性是把分离与恢复的代价逐项记账、在指数尺度上互相抵偿。按 OpenAI 官方声明，未经形式化的结果可能存在问题；本文主定理已形式化。另注：优化参数只要求可行、不保证最优，后续仍有数值改进空间。

{% endraw %}
