---
layout: default
title: "Removable Boundaries and Rigidity of Circle Domains"
family: "071"
discipline: "Real and complex analysis"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | Removable Boundaries and Rigidity of Circle Domains

> 结果族 071：Koebe's circle-domain conjecture　·　学科：Real and complex analysis　·　验证状态：暂无形式化证明，请以社区核验为准

## 入门导读 🐣

一块边缘碎成粉尘的拼图：粉尘细到撕掉也不改变整块拼图的弹性（"可去"），定理说这样的拼图反而极"硬"——任何把圆洞仍然变成圆洞的形变，都只能是球面的刚体运动，不许拉伸、不许扭转。这就是 He–Schramm 猜想剩下的、确实成立的那一半：可去推出刚性。

**关键词卡片**

- 圆域（circle domain）：补集每个分支都是闭圆盘或单点的区域，平面区域的"标准件"。
- 共形映射（conformal map）：保持角度的复函数，无撕裂、无挤压的理想形变。
- 可去边界（removable boundary）：边界粉尘小到有界共形函数能直接无视它延拓过去。
- 刚性（rigid）：到其他圆域的共形等价必是 Möbius 变换的限制。
- Möbius 变换（Möbius transformation）：球面到自身的"刚体式"共形变换，只有 6 个实参数，由三点的像完全决定。

**看个具体例子**

设 `@@M@@\Omega,\Omega'@@` 都是圆域、`@@M@@\partial\Omega@@` 可去、`@@M@@f:\Omega\to\Omega'@@` 共形：

<div>

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 560 280">
  <circle cx="115" cy="135" r="78" fill="#e8f1fa" stroke="#4a7dbd" stroke-width="2" stroke-dasharray="5,5"/>
  <circle cx="95" cy="110" r="20" fill="#fff" stroke="#333" stroke-width="2"/>
  <circle cx="140" cy="165" r="13" fill="#fff" stroke="#333" stroke-width="2"/>
  <circle cx="120" cy="140" r="2.5" fill="#333"/>
  <circle cx="135" cy="120" r="2.5" fill="#333"/>
  <circle cx="105" cy="160" r="2.5" fill="#333"/>
  <text x="48" y="245" font-size="14" fill="#333">圆域 Ω：边界是可去粉尘</text>
  <line x1="235" y1="135" x2="325" y2="135" stroke="#333" stroke-width="2"/>
  <polygon points="325,129 325,141 337,135" fill="#333"/>
  <text x="248" y="118" font-size="15" fill="#333">共形等价 f</text>
  <circle cx="445" cy="135" r="78" fill="#f5edf7" stroke="#7a5ba8" stroke-width="2"/>
  <circle cx="425" cy="110" r="20" fill="#fff" stroke="#333" stroke-width="2"/>
  <circle cx="470" cy="165" r="13" fill="#fff" stroke="#333" stroke-width="2"/>
  <circle cx="450" cy="140" r="2.5" fill="#333"/>
  <circle cx="465" cy="120" r="2.5" fill="#333"/>
  <circle cx="435" cy="160" r="2.5" fill="#333"/>
  <text x="378" y="245" font-size="14" fill="#333">圆域 Ω′（洞：圆盘或点）</text>
  <text x="128" y="272" font-size="15" fill="#a33">结论：f 必是 Möbius 变换的限制</text>
</svg>

</div>

自由度盘点：共形等价先验上可以极其任意，结论却把它钉死在只有 6 个实参数、由三点像决定的 Möbius 群里——可去性把无穷压到 6。补分支数目不限（可为不可数）；此前所有部分结果都附加边界几何条件，这里全部撤掉。

**为什么值得关心**

与姊妹篇（Koebe 圆域猜想）合读，存在性与刚性互相成就，是平面共形几何百年故事的收尾两章。

> 验证状态：暂无形式化证明（AI 结果待核验）

## 一句话结论

证明了边界共形可去（conformally removable）的圆域必共形刚性（rigid）：它与任何圆域之间的共形等价都是 Möbius 变换的限制，且对补分支数目（可为不可数）毫无限制。这确立了 He–Schramm 猜想中"可去⟹刚性"的方向。

## 问题背景

圆域（circle domain）是黎曼球面 `@@M@@\Chat=\C\cup\{\infty\}@@` 中补分支全为闭圆盘或单点的区域，是平面区域最直观的共形模型。它的价值取决于两个问题：这样的模型是否存在（即 Koebe 圆域猜想），以及其共形结构是否在相差一个 Möbius 变换（Möbius transformation）的意义下确定位置——后者称为刚性（rigidity）。He 与 Schramm 在 1993 年证明了可数连通圆域的均匀化与刚性，随后又把刚性推广到边界具 `@@M@@\sigma@@`-有限线性测度的情形，并猜想：圆域刚性当且仅当其边界共形可去。2025 年 Rajala 构造出刚性但边界不可去的圆域，说明"刚性⟹可去"不成立；本文证明剩下成立的"可去⟹刚性"方向。此前的部分结果——Ntalampekos–Younsi 的拟双曲距离平方可积条件、Ntalampekos 的 CNED 条件等——都对边界几何附加限制，本文将其全部去除。

## 主要结果

主定理：设 `@@M@@\Omega,\Omega'\subset\Chat@@` 为圆域，`@@M@@\partial\Omega@@` 共形可去，`@@M@@f\colon\Omega\to\Omega'@@` 为共形等价，则存在 Möbius 变换 `@@M@@M@@` 使 `@@M@@f=M|_\Omega@@`。定理对补分支基数不作任何限制，也不假设 `@@M@@f@@` 预先延拓到边界——边界控制是论证的产物而非前提。

关键的中间结果是跨越可去"尘埃"的连续 Sobolev 延拓定理：若紧全不连通集 `@@M@@B\subset\C@@` 共形可去，则每个在球面上连续、在 `@@M@@G=\Chat\setminus B@@` 上属于 `@@M@@W^{1,2}(G)@@` 的实函数自动属于 `@@M@@W^{1,2}(\Chat)@@`。它是把可去性转化为 Sobolev 信息的枢纽，亦独立有意义。

## 证明思路

证明分四步，总策略是"先用掉可去性，再回到 `@@M@@f@@`"。

第一步，对补集为紧全不连通集 `@@M@@B@@` 的情形建立"保留测试的模型"。从姊妹篇（Koebe 猜想一文）输入数量化的保留测试转移定理：有限个标量测试在穷竭核心上被精确保留，尾部能量与边界振荡平方和同时趋于零。填掉有限多个圆洞并取弱极限，得到模型 `@@M@@h@@`，使 `@@M@@u_i\circ\pi_h@@`（`@@M@@\pi_h@@` 为塌缩映射）成为全球 Sobolev 函数，且在省略集上梯度为零；再用围道论证逐一确定函数在省略分量上的取值，即便点分量之并可具正面积。

第二步，变动模型以制造屏障。在保留固定有限测试列表的映射中，逼近无穷远处第一 Laurent 系数实部的上确界；借助经经典 Beltrami 方程构造的电导率形变，得到与普通纵坐标误差任意小的高度函数，水平集论证保证其与保留测试相容；压平非点洞对应的可数多个取值后，再补上横坐标。两坐标合成围绕所有源端点、能量任意小的屏障。

第三步，保存屏障并不断扩充测试列表。若极限模型的某省略分量不是点，其某条轴投影含正长度区间 `@@M@@J@@`，则每条相应横截线都迫使某个保存下来的屏障从 1 降到 0，由 Cauchy–Schwarz 其能量至少为 `@@M@@|J|/(2L)@@`，与"能量可任意小"矛盾。故所有省略分量都是点；分量对应把极限模型延拓为球面同胚，`@@M@@B@@` 的可去性使规范化极限为恒等映射，弱紧致性随即给出上述 Sobolev 延拓定理。

第四步，回到一般的 `@@M@@f\colon\Omega\to\Omega'@@`。点分量可能与圆盘对应，坐标延拓不必连续，于是先对可数个含盘配对施加遮罩（mask），剩余公共点分量构成紧、全不连通且可去的残余集，可套用第三步的定理；遮罩分析（基于 Hardy–Littlewood 极大函数的"球综合"引理）表明这些迹在几乎每条线上的轴向投影零测。最后是通量—面积论证：用 `@@M@@f@@`、目标圆盘圆心与公共点对应定义有界可测场，对线估计沿两个方向积分得 `@@M@@2\pi R^2\le 2\int_{\Omega\cap D_R}|f'|\,\dd A+2\pi\sum_j r_js_j@@`；与源、目标两侧面积不等式 `@@M@@\int 1+\pi\sum r_j^2\le\pi R^2@@`、`@@M@@\int|f'|^2+\pi\sum s_j^2\le\pi R^2@@` 相加化简，得 `@@M@@\int_{\Omega\cap D_R}(|f'|-1)^2\,\dd A+\pi\sum_j(r_j-s_j)^2\le0@@`。两项均非负，故 `@@M@@|f'|\equiv1@@`，开映射定理与恒等定理迫使 `@@M@@f@@` 仿射，再由 `@@M@@f(z)=z+O(1/z)@@` 的规范化知其为恒等，即原等价是 Möbius 变换的限制。

## 可信度与备注

本文主结果暂无 Lean 形式化证明，属 OpenAI 批量产出的手稿之一；按其官方声明，未经形式化的结果可能存在问题，请以社区核验为准。本文与姊妹篇《Koebe's Circle-Domain Conjecture》相互咬合：刚性论证依赖姊妹篇提供的数量化保留测试定理，而该定理正是姊妹篇均匀化构造的定量加强。两篇合读，可见 Koebe 存在性问题与 He–Schramm 刚性问题如何互相成就。

{% endraw %}
