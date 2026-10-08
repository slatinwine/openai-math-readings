---
layout: default
title: "No bigeodesics in planar first-passage percolation"
family: "212"
discipline: "Probability and statistical mechanics"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | No bigeodesics in planar first-passage percolation

> 结果族 212：Planar first-passage geometry and the absence of bigeodesics　·　学科：Probability and statistical mechanics　·　验证状态：暂无形式化证明，请以社区核验为准

## 入门导读 🐣

把一座城市每条道路的拥堵程度随机指定，司机自然想知道任意两点之间哪条路最快。这篇论文研究一个更刁钻的问题：会不会存在一条两头都无限延伸的"永远最快"之路——它途经的每一段，都是那段起止点间的最快选择？结论是：在平面方格路网上，这样的路几乎必然不存在。

**关键词卡片**

- 首达渗流（first-passage percolation）：给方格网每条边独立赋予随机"通行时间"的经典模型。
- 测地线（geodesic）：连接两点、总通行时间最小的路径。
- 双无穷测地线（bigeodesic）：向两头无限延伸，且任意有限段都是测地线的路径。
- 极限形状（limit shape）：时间放长后"可达区域"趋近的确定性轮廓。

**看个具体例子**

<div>

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 560 280">
  <text x="280" y="40" font-size="13" text-anchor="middle" fill="#222">每条边有随机『通行时间』，红色是起点 0 到终点 A 的最快路线</text>
  <line x1="90" y1="80" x2="410" y2="80" stroke="#bbb" stroke-width="1.5"/>
  <line x1="90" y1="125" x2="410" y2="125" stroke="#bbb" stroke-width="1.5"/>
  <line x1="90" y1="170" x2="410" y2="170" stroke="#bbb" stroke-width="1.5"/>
  <line x1="90" y1="215" x2="410" y2="215" stroke="#bbb" stroke-width="1.5"/>
  <line x1="90" y1="80" x2="90" y2="215" stroke="#bbb" stroke-width="1.5"/>
  <line x1="170" y1="80" x2="170" y2="215" stroke="#bbb" stroke-width="1.5"/>
  <line x1="250" y1="80" x2="250" y2="215" stroke="#bbb" stroke-width="1.5"/>
  <line x1="330" y1="80" x2="330" y2="215" stroke="#bbb" stroke-width="1.5"/>
  <line x1="410" y1="80" x2="410" y2="215" stroke="#bbb" stroke-width="1.5"/>
  <text x="128" y="74" font-size="11" fill="#888">7</text>
  <text x="208" y="74" font-size="11" fill="#888">9</text>
  <text x="288" y="74" font-size="11" fill="#888">8</text>
  <text x="368" y="74" font-size="11" fill="#888">5</text>
  <text x="208" y="119" font-size="11" fill="#888">8</text>
  <text x="288" y="119" font-size="11" fill="#888">6</text>
  <text x="368" y="119" font-size="11" fill="#888">9</text>
  <text x="98" y="152" font-size="11" fill="#888">9</text>
  <text x="256" y="152" font-size="11" fill="#888">6</text>
  <text x="416" y="152" font-size="11" fill="#888">7</text>
  <path d="M 90 125 L 170 125 L 170 170 L 250 170 L 330 170 L 330 215 L 410 215" fill="none" stroke="#c0392b" stroke-width="4.5"/>
  <text x="126" y="118" font-size="12" fill="#c0392b">2</text>
  <text x="178" y="152" font-size="12" fill="#c0392b">1</text>
  <text x="206" y="163" font-size="12" fill="#c0392b">3</text>
  <text x="286" y="163" font-size="12" fill="#c0392b">1</text>
  <text x="338" y="196" font-size="12" fill="#c0392b">2</text>
  <text x="366" y="209" font-size="12" fill="#c0392b">1</text>
  <circle cx="90" cy="80" r="3" fill="#777"/>
  <circle cx="170" cy="80" r="3" fill="#777"/>
  <circle cx="250" cy="80" r="3" fill="#777"/>
  <circle cx="330" cy="80" r="3" fill="#777"/>
  <circle cx="410" cy="80" r="3" fill="#777"/>
  <circle cx="250" cy="125" r="3" fill="#777"/>
  <circle cx="330" cy="125" r="3" fill="#777"/>
  <circle cx="410" cy="125" r="3" fill="#777"/>
  <circle cx="90" cy="170" r="3" fill="#777"/>
  <circle cx="170" cy="170" r="3" fill="#777"/>
  <circle cx="250" cy="170" r="3" fill="#777"/>
  <circle cx="330" cy="170" r="3" fill="#777"/>
  <circle cx="410" cy="170" r="3" fill="#777"/>
  <circle cx="90" cy="215" r="3" fill="#777"/>
  <circle cx="170" cy="215" r="3" fill="#777"/>
  <circle cx="250" cy="215" r="3" fill="#777"/>
  <circle cx="330" cy="215" r="3" fill="#777"/>
  <circle cx="90" cy="125" r="5.5" fill="#c0392b"/>
  <circle cx="410" cy="215" r="5.5" fill="#c0392b"/>
  <text x="90" y="108" font-size="11" text-anchor="middle" fill="#c0392b">起点 0</text>
  <text x="410" y="240" font-size="11" text-anchor="middle" fill="#c0392b">终点 A</text>
  <text x="280" y="268" font-size="12.5" text-anchor="middle" fill="#222">红色路线总耗时 10；两头无限延伸且每段都最快的路线（bigeodesic）几乎必然不存在</text>
</svg>

</div>

图中从起点 0 到终点 A，红色路径总耗时 2+1+3+1+2+1=10，是所有走法中最省的，它就是一条测地线。定理说的是更强的"全场否定"：几乎必然不存在任何一条向两头无限延伸、且每一段都拿到这种"最快认证"的路线——连例外方向也不许依赖随机路况。证明的卡点正在于量词交换：对每个固定方向成立，不等于对所有随机可选的方向同时成立。

**为什么值得关心**

这是 Furstenberg 时代遗留、由 Damron–Hanson 表述的平面无测地线猜想，在四条独立边权最小值二阶矩有限这一温和条件下的完全解决，且不需要对极限形状作任何正则性假设。

> 暂无形式化证明（AI 结果待核验）

## 一句话结论
在边权独立同分布、非负、无原子且四条独立边权最小值二阶矩有限的条件下，证明了平面首达渗流几乎必然不存在任何双无穷测地线，一举解决该条件下的平面无测地线猜想，且完全不需要极限形状的正则性假设。

## 问题背景
首达渗流（first-passage percolation）由 Hammersley 与 Welsh 于 1965 年引入：给 `@@M@@\Z^2@@` 的每条最近邻边独立赋非负通行时间，两点间通行时间 `@@M@@T(x,y)@@` 取一切路径成本的下确界。实现下确界的路径叫测地线（geodesic）；两头无限延伸且任意有限段均测地的路径叫双无穷测地线（bigeodesic）。随机度量中是否含双无穷测地线，是 Furstenberg 提出、由 Kesten 转述的老问题，Damron–Hanson 将其表述为平面猜想：连续边权下它几乎必然不存在。此前进展各有代价：Licea–Newman 的方向聚合只排除满测度确定性集合指定的端方向；Newman、Damron–Hanson、Alexander 等的结果需要曲率、可微性或涨落估计。真正的卡点是量词交换：对每个固定方向几乎必然成立，不等于对环境依赖的例外方向同时成立，而双无穷测地线恰恰可能选中这种随机方向。

## 主要结果
主定理：设边权法律 `@@M@@G@@` 无原子，且独立样本满足 `@@M@@\EE[\min\{X_1,X_2,X_3,X_4\}^2]<\infty@@`，则几乎必然不存在成对相异的顶点序列 `@@M@@(v_i)_{i\in\Z}@@`，使对一切 `@@M@@i<j@@` 都有 `@@M@@\sum_{k=i}^{j-1}t_{\{v_k,v_{k+1}\}}=T(v_i,v_j)@@`。即在一个概率一的事件上同时排除全部双无穷测地线，端方向可以依赖环境。结论对 `@@M@@G@@` 十分宽容：允许奇异连续分布、有界支撑，甚至 `@@M@@\EE t_e=\infty@@`；对极限形状（limit shape）不作可微、严格凸或曲率假设。作者明言这是该矩条件下的正面解答，不涵盖完全无矩的表述。

## 证明思路
先立结构：每条射线（ray）`@@M@@p@@` 都有 Busemann 函数 `@@M@@B_p(x,y)=\lim_{j\to\infty}(T(x,p_j)-T(y,p_j))@@`，且带线性渐近泛函 `@@M@@\rho_p@@`，称为标签（label）；双无穷测地线两端标签相反。以 Ahlberg–Hoffman 结构理论为输入：固定标签的射线族唯一、聚合且向后有限，由此先排除一切确定性标签。经可数归约，只需处理上标签落在对偶单位圆一个紧扇区内的情形，用水平坐标 `@@M@@r@@` 排序，记扇区宽度为 `@@M@@W@@`。

核心是一个"标签预算"矛盾。在间距 `@@M@@l@@` 的水平网格上标记格点：若被选中的双无穷测地线在有限加重的环境中获得至少 `@@M@@M@@` 的额外成本，且相邻标记的标签同落一个小区间，则与区间端点标签处的基准射线比较，Busemann 增量沿直线望远镜式相消，得 `@@M@@Mq\le lW@@`，`@@M@@q@@` 为单点标记概率。该论证只用到各点边际概率相等，完全不需要标记间独立。

要引爆矛盾，需构造 `@@M@@q@@` 有正下界、`@@M@@l@@` 固定而 `@@M@@M@@` 任意大的标记，难点有二。其一，抬高边权后如何保住标记：在每点周围加宽区域内抬高有限条边，替换尺度取 `@@M@@\delta_h=\eta/((h+2)\log(h+2))@@`，使 `@@M@@\sum h\delta_h^2@@` 收敛（换律总误差一致小，即 Bates–Chatterjee 的有界密度扰动技巧），而 `@@M@@\sum\delta_j@@` 发散保证路径增益可任意大；路径须从加重后的环境中选出，条件化后隐藏抬升呈显式乘积律，由此 `@@M@@q\ge p/8@@`。其二，如何不加大间距就分开标签：关键断言是同标签的双无穷测地线共享同一对 Busemann 函数。例外标签在每个环境至多可数；独立重采样互补半平面，把射线平移过远处切口而保持标签与例外见证，可数性与独立性迫使例外标签在另一端聚合，再以一边重采样版预算加有限树计数排除分叉。随后让所有格点共享同一组抬升样本，取两个个体环境的并：若两标记点标签相同，其公共 Busemann 对会在并度量中造出一条额外成本任意小的绕行，回到另一个体度量后严格便宜于所选测地线，矛盾；故不同标记点标签必不同。最后细化标签分割以分开相邻标记，损失概率随加细趋于零；此后才令 `@@M@@M@@` 增大，与预算 `@@M@@Mq\le lW@@` 矛盾。

## 可信度与备注
本文主结果暂无形式化证明，请以社区核验为准；结构输入取自 Ahlberg–Hoffman 已发表理论，附录中的边界比较取代了原本需要额外可积性的期望步骤。姊妹篇证明指数权极限形状严格凸且 `@@M@@C^1@@`、Gamma 权时间常数范数可微，与本文互补：那篇把方向固定的测地线结构收缩到单一方向，本文则不依赖任何形状正则性而同时排除所有双无穷测地线。按 OpenAI 官方声明，未经形式化的结果可能有问题，本文结论宜以社区核验为准。

{% endraw %}
