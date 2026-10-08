---
layout: default
title: "Exact Uniform Sampling of Contingency Tables with Arbitrary Margins"
family: "115"
discipline: "Theoretical computer science"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | Exact Uniform Sampling of Contingency Tables with Arbitrary Margins

> 结果族 115：Sampling and counting contingency tables with arbitrary margins　·　学科：Theoretical computer science　·　验证状态：暂无形式化证明，请以社区核验为准

## 入门导读 🐣

填一张表格，让每行合计、每列合计都等于事先给定的数——像把全年预算摊给各部门与各季度：每个部门的总额、每个季度的总额都被钉死。这样的填法往往多到天文数字，如何"完全等概率"地随机抽出一张？精确均匀采样此前只在零散特例下可行；本文给出首个对任意行和、列和都成立的算法，期望时间多项式。

**关键词卡片**

- 列联表（contingency table）：满足给定行和与列和的非负整数矩阵。
- 均匀采样（uniform sampling）：每张合法表被抽中的概率严格相等。
- 精确与近似（exact / approximate）：精确版输出分布分毫不差；近似版允许 `@@M@@2^{-k}@@` 的总变差误差。
- 二进制边际（binary-encoded margins）：总额可写成编码长度的指数倍，因此按数值算多项式不算多项式。
- 马尔可夫链混合（Markov chain mixing）：随机游走要走多久才忘掉起点、接近目标分布。

**看个具体例子**

行和 (3,2)、列和 (2,3) 的 2×2 表恰好有 2 张：表 A 第一行是 (1,2)、第二行是 (1,1)；表 B 第一行是 (2,1)、第二行是 (0,2)。均匀采样器必须以 1/2、1/2 输出两者；本文的近似版输出分布与理想分布的总变差 `@@M@@\le 2^{-k}@@`（每次运行多项式时间），精确版则分毫不差地均匀（期望多项式时间）。维数与边际再大，界都一致成立。

<div>

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 560 280">
  <text x="280" y="26" text-anchor="middle" font-size="15" fill="#333333">行和 (3,2)、列和 (2,3)：合法的 2×2 表恰好两张</text>
  <rect x="60" y="70" width="60" height="60" fill="#eef4fb" stroke="#666666" stroke-width="2"/>
  <rect x="120" y="70" width="60" height="60" fill="#eef4fb" stroke="#666666" stroke-width="2"/>
  <rect x="60" y="130" width="60" height="60" fill="#eef4fb" stroke="#666666" stroke-width="2"/>
  <rect x="120" y="130" width="60" height="60" fill="#eef4fb" stroke="#666666" stroke-width="2"/>
  <text x="90" y="106" text-anchor="middle" font-size="16" fill="#333333">?</text>
  <text x="150" y="106" text-anchor="middle" font-size="16" fill="#333333">?</text>
  <text x="90" y="166" text-anchor="middle" font-size="16" fill="#333333">?</text>
  <text x="150" y="166" text-anchor="middle" font-size="16" fill="#333333">?</text>
  <text x="52" y="106" text-anchor="end" font-size="13" fill="#555555">行1</text>
  <text x="52" y="166" text-anchor="end" font-size="13" fill="#555555">行2</text>
  <text x="90" y="62" text-anchor="middle" font-size="13" fill="#555555">列1</text>
  <text x="150" y="62" text-anchor="middle" font-size="13" fill="#555555">列2</text>
  <text x="192" y="106" font-size="13" fill="#2e8b57">合计 3</text>
  <text x="192" y="166" font-size="13" fill="#2e8b57">合计 2</text>
  <text x="90" y="210" text-anchor="middle" font-size="13" fill="#2e8b57">合计 2</text>
  <text x="150" y="210" text-anchor="middle" font-size="13" fill="#2e8b57">合计 3</text>
  <text x="340" y="88" text-anchor="middle" font-size="14" fill="#333333">表 A</text>
  <rect x="300" y="98" width="40" height="40" fill="#ffffff" stroke="#3b82c4" stroke-width="2"/>
  <rect x="340" y="98" width="40" height="40" fill="#ffffff" stroke="#3b82c4" stroke-width="2"/>
  <rect x="300" y="138" width="40" height="40" fill="#ffffff" stroke="#3b82c4" stroke-width="2"/>
  <rect x="340" y="138" width="40" height="40" fill="#ffffff" stroke="#3b82c4" stroke-width="2"/>
  <text x="320" y="124" text-anchor="middle" font-size="15" fill="#333333">1</text>
  <text x="360" y="124" text-anchor="middle" font-size="15" fill="#333333">2</text>
  <text x="320" y="164" text-anchor="middle" font-size="15" fill="#333333">1</text>
  <text x="360" y="164" text-anchor="middle" font-size="15" fill="#333333">1</text>
  <text x="340" y="196" text-anchor="middle" font-size="13" fill="#2e8b57">概率 1/2</text>
  <text x="490" y="88" text-anchor="middle" font-size="14" fill="#333333">表 B</text>
  <rect x="450" y="98" width="40" height="40" fill="#ffffff" stroke="#3b82c4" stroke-width="2"/>
  <rect x="490" y="98" width="40" height="40" fill="#ffffff" stroke="#3b82c4" stroke-width="2"/>
  <rect x="450" y="138" width="40" height="40" fill="#ffffff" stroke="#3b82c4" stroke-width="2"/>
  <rect x="490" y="138" width="40" height="40" fill="#ffffff" stroke="#3b82c4" stroke-width="2"/>
  <text x="470" y="124" text-anchor="middle" font-size="15" fill="#333333">2</text>
  <text x="510" y="124" text-anchor="middle" font-size="15" fill="#333333">1</text>
  <text x="470" y="164" text-anchor="middle" font-size="15" fill="#333333">0</text>
  <text x="510" y="164" text-anchor="middle" font-size="15" fill="#333333">2</text>
  <text x="490" y="196" text-anchor="middle" font-size="13" fill="#2e8b57">概率 1/2</text>
  <text x="280" y="248" text-anchor="middle" font-size="13" fill="#555555">均匀采样＝各以 1/2 抽 A 或 B；维数与边际任意，期望时间仍多项式</text>
</svg>

</div>

**为什么值得关心**

它摘掉了正性、稀疏、平衡、固定维数等全部旧假设，把"均匀生成一张列联表"在最一般意义上变成多项式时间任务——这类表是统计、物理与隐私数据发布中的基本随机对象。

> 暂无形式化证明（AI 结果待核验）

## 一句话结论
对任意行和、列和的非负整数列联表，本文构造出首个精确均匀采样算法，期望比特时间在维数与边际二进制长度上多项式；并给出每次运行都有最坏情形多项式界、误差 `@@M@@2^{-k}@@` 的近似均匀采样器，取消了正性、稀疏、平衡、固定维数等全部旧假设。

## 问题背景
给定非负整数行和 `@@M@@r@@` 与列和 `@@M@@c@@`（总量相同），满足这些边际的非负整数矩阵称为列联表（contingency table），记作 `@@M@@\Omega(r,c)@@`；均匀生成其中一张表，是计数与随机结构生成领域的基准问题，与统计物理、网络流和隐私数据发布都相关。真正的困难在编码方式：当边际以二进制给出时，总量 `@@M@@N@@` 可以是输入长度的指数倍，任何 `@@M@@\mathrm{poly}(N)@@` 的算法都不算多项式时间。此前只有碎片化结果：两行情形的热浴链（Dyer–Greenhill，2000）；固定行数时 `@@M@@2\times 2@@` 热浴链的多项式混合（Cryan–Dyer–Goldberg–Jerrum–Martin，2006）；大边际稠密情形的几何方法（Dyer–Kannan–Mount 1997、Morris 2002）；稀疏情形 `@@M@@5\Delta^4<N@@` 下的精确生成（Arman–Gao–Wormald，2021）。DeSalvo–Zhao（2016）的分治精确采样则依赖一个未证明的计数猜想。Arman 等人 2021 年的综述明确指出：任意边际的多项式时间近似均匀采样器当时并不存在。

## 主要结果
论文主定理断言，在只使用独立无偏随机比特与比特运算的模型中，对任意具有相同总量的非负整数边际：(i) 给定整数 `@@M@@k\ge 1@@`，存在算法输出 `@@M@@\Omega(r,c)@@` 中一张表，其分布与均匀分布的总变差距离（total variation distance）不超过 `@@M@@2^{-k}@@`，运行时间以 `@@M@@m,n,\log(N+1),k@@` 的多项式为界；(ii) 存在输出精确均匀表格的算法，它几乎必然终止，期望运行时间是 `@@M@@m,n,\log(N+1)@@` 的多项式。两个多项式对一切边际向量一致成立。注意 (i) 的时间界在每次执行中都成立；(ii) 的多项式界是期望意义的——一条概率极小的修正分支需要做穷举计算。

## 证明思路
证明分三步组装。先做大小分解并构造状态图：与低于阈值 `@@M@@U=d^{20}@@` 的边际相邻的格子称为小格，其余格子构成大格矩形块；给大格边际统一加上填充量 `@@M@@L=d^{12}@@`，使每个条件完成问题都变"稠密"。每个小格配行视角 `@@M@@x_s@@`、列视角 `@@M@@q_s@@` 两个坐标，二者相等的状态叫横截面（transversal），另允许恰有一处 `@@M@@+1@@`、一处 `@@M@@-1@@` 偏差的缺陷态（defect）；状态权重 `@@M@@f(X)@@` 定义为该块填充后的完成表数目。从稳态 `@@M@@\pi\propto f@@` 抽状态、再抽均匀完成表，则每个（状态，完成表）对等概率，只接受"横截面且所有大格条目均不低于 `@@M@@L@@`"并减去填充，即得均匀原始表；接受概率下界依赖修复映射（repair map）：它把每个缺陷态连同其完成表单射入某个横截面，故缺陷总质量至多是横截面质量的 `@@M@@d^2@@` 倍。

第二步证链快速混合，这是技术核心。链从不显式计算 `@@M@@f@@`：理想转移用一次均匀完成抽样来检验提案是否可接受，拒绝概率由"小条目引理"（对 `@@M@@2\times 2@@` 搬运做双重计数）控制。分析按行优先顺序逐格暴露小格取值，比较相邻条件纤维上任意函数的均值差；为此引入软化权重 `@@M@@\eta^{D(\xi)}@@`，证明"双移除矩阵"的二次型签名（quadratic signature）——它至多有一个正特征值，且在逐格求和下封闭。这正对应 Brändén–Huh 的 Lorentzian 多项式视角，但所需的离散封闭性由层叠（laminar）分解与加权伸缩恒等式直接证明。再用递归构造的符号流（signed flow）估计纤维间能量，配条件方差分解与修复映射，得到图上的 Poincaré 不等式，给出 `@@M@@d^{160}@@` 级的混合时间界。

第三步实现与精确化。稠密完成抽样把整数表按缩放坐标分箱，箱权重由对数凹密度软化，拒绝成功率至少 `@@M@@1/64@@`，箱上 Metropolis 链的导热率（conductance）由 Prékopa–Leindler 型积分插值不等式控制，全部用有理数与二元随机比特实现。最后把实现算法的输出分布精确制表（带公共二元分母），套用 Göbel–Liu–Manurangsi–Pappik 的残差混合（residual mixture）构造：以概率 `@@M@@1-\delta@@` 走近似分支、以 `@@M@@\delta=2^{-D}@@` 走穷举分支精确抽取剩余质量，两者混合恰为均匀分布，而穷举成本被指数小的 `@@M@@\delta@@` 抵消成多项式期望。

## 可信度与备注
本结果与同族姊妹篇《An FPRAS for Cell-Bounded Contingency Tables》共享"二次签名＋符号流传输"的分析骨架，后者把同一技术推广到带逐格上界的计数侧，两文互相印证核心引理的稳健性。两篇均未提供 Lean 形式化证明，请以社区核验为准；OpenAI 官方声明"未经形式化的结果可能有问题"。另外文中多项式指数刻意取得很大（如混合时间 `@@M@@d^{160}@@`、制表成本 `@@M@@2^{500db}@@`），作者自陈这是统一的复杂度保证而非实用运行时间估计。

{% endraw %}
