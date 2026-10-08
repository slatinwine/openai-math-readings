---
layout: default
title: "Marked polygon correlations and one-arc bounds"
family: "237"
discipline: "Probability and statistical mechanics"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | Marked polygon correlations and one-arc bounds

> 结果族 237：The three-quarter exponent for honeycomb self-avoiding walk　·　学科：Probability and statistical mechanics　·　验证状态：暂无形式化证明，请以社区核验为准

## 入门导读 🐣

数橡皮筋也有陷阱：一根蜷在小盒子里的橡皮筋可以绕极多圈，单看"根数"根本压不住它。所以想证明"长链条终会摊开"，得先回答：直径不超过 `@@M@@H@@` 的橡皮筋，按"长度的平方"打分，总分最多多大？这篇论文给出天花板：`@@M@@H^{2/3}@@`。

**关键词卡片**

- 简单多边形（simple polygon）：蜂窝格点上首尾相接、全程不自交的闭合圈。
- 平移类（translation class）：整体平移后重合的圈只算一次，避免无限重复计数。
- 临界顶点活性（critical vertex activity）`@@M@@\rho_{\rm v}@@`：每个顶点乘以 `@@M@@(2+\sqrt2)^{-1/2}@@`，恰好处于收敛与发散的分界点。
- 平方长度权重 `@@M@@|P|^2@@`：在圈上同时标两个"检查点"，每个圈恰被数 `@@M@@|P|^2@@` 次——用两点相关恢复出长度平方。
- 单弧界（one-arc bound）：对只含一段弧的构型的多项式上界，且两墙周期可任意悬殊时仍一致成立。

**看个具体例子**

<div>

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 560 280"><rect x="60" y="70" width="150" height="150" fill="#f7f4ec" stroke="#889" stroke-width="2"/><ellipse cx="135" cy="145" rx="58" ry="58" fill="none" stroke="#7dc7a3" stroke-width="1.6"/><ellipse cx="135" cy="145" rx="40" ry="46" fill="none" stroke="#7dc7a3" stroke-width="1.6"/><ellipse cx="135" cy="145" rx="24" ry="32" fill="none" stroke="#7dc7a3" stroke-width="1.6"/><ellipse cx="135" cy="145" rx="12" ry="18" fill="none" stroke="#7dc7a3" stroke-width="1.6"/><text x="62" y="60" font-size="13" fill="#333">直径 ≤ H 的小盒子</text><text x="72" y="245" font-size="13" fill="#1a7a4a">长而蜷的圈藏在里面</text><line x1="230" y1="145" x2="270" y2="145" stroke="#666" stroke-width="2"/><text x="285" y="120" font-size="14" fill="#333" font-weight="bold">总分（按 |P|² 打分）</text><text x="285" y="148" font-size="15" fill="#c0392b" font-weight="bold">≤ H^(2/3+η)</text><text x="285" y="180" font-size="13" fill="#555">直径放大 1000 倍，总分至多放大 100 倍</text><text x="90" y="272" font-size="12" fill="#666">"小而肥"的蜷缩圈在临界权下翻不了天</text></svg>

</div>

数字版定理：`@@M@@\sum_{\operatorname{diam}P\le H}\rho_{\rm v}^{|P|}\,|P|^2\le C_\eta H^{2/3+\eta}@@`。代入比较：直径从 `@@M@@10^3@@` 放大到 `@@M@@10^6@@`（1000 倍），上界只放大 `@@M@@1000^{2/3}=100@@` 倍——无论圈怎么蜷，其平方长度加权的总质量都被压在很低的增长速度下。

**为什么值得关心**

它是 3/4 直径定理的守门员：没有这道天花板，"行走极长却缩成一团"的怪物构型就无法排除，Nienhuis 指数的严格化就会卡壳。

> 暂无形式化证明（AI 结果待核验）

## 一句话结论

在蜂窝点阵 (honeycomb lattice) 临界顶点活性下，直径不超过 `@@M@@H@@` 的简单多边形 (simple polygon) 按平移类计数、以长度平方加权，总质量至多 `@@M@@H^{2/3+o(1)}@@`；配套的双标记圆柱估计与单弧多项式界，是证明自回避行走直径指数 `@@M@@3/4@@` 时控制"大质量多边形"的关键输入。

## 问题背景

Nienhuis 1982 年借稀稀释 `@@M@@O(n)@@` 模型 (dilute `@@M@@O(n)@@` model) 预言了蜂窝点阵自回避行走 (self-avoiding walk) 的临界点与临界指数；Duminil-Copin 与 Smirnov 随后用局部抛物费米恒等式 (parafermionic identity) 证明了连接常数 (connective constant) 的精确值。但要严格确立"`@@M@@n@@` 步行走直径为 `@@M@@n^{3/4+o(1)}@@`"，必须排除行走很长却蜷缩在小区域内的情形。只数多边形个数并不够：一个多边形可以有极多顶点而直径很小。正确的观测量是同时记录多边形上的两个被访问端口 (port)，对它们的相关 (correlation) 求和，每个多边形恰被计数 `@@M@@|P|^2@@` 次，从而恢复平方长度。本文的任务就是把这个带平方长度权重的多边形总质量在直径 `@@M@@H@@` 内压到 `@@M@@H^{2/3+o(1)}@@`。

## 主要结果

主定理（平方长度多边形质量）：对每个 `@@M@@\eta>0@@` 存在 `@@M@@C_\eta<\infty@@`，使得

`@@M@@D\sum_{[P]\,:\,\operatorname{diam}P\le H}\rho_{\rm v}^{|P|}\,|P|^2\le C_\eta\,H^{2/3+\eta},@@`

求和遍历简单无向多边形的平移类 (translation class)，`@@M@@\rho_{\rm v}=(2+\sqrt2)^{-1/2}@@` 为临界顶点活性，`@@M@@|P|@@` 是顶点数，直径取固定嵌入下的欧氏直径。中间结果是蜂窝圆柱上的双标记估计：沿一行端口切出循环顺序 `@@M@@[p,X,p',Y]@@`（`@@M@@s=|X|@@`，`@@M@@b=|Y|@@`），同时访问两标记端口 `@@M@@p,p'@@` 的圆柱多边形质量 `@@M@@\mathcal C(p,p')@@` 满足

`@@M@@D\log\mathcal C(p,p')\le-\tfrac43\log s+\tfrac{617}{1200}\log(b/s)+o(\log b),@@`

在对数墙长 `@@M@@c_1L_Y\le L_X\le L_Y@@`（`@@M@@L_X=\gamma^{-1}\log s@@`，`@@M@@\gamma=4/3@@`）、上位位点占比 `@@M@@t\in[1/2,1]@@` 且指数小的下位少数带余量的范围内一致成立。第三项输出是多项式单弧界 (one-arc bound)：从 `@@M@@p@@` 的西半边出发、到 `@@M@@p'@@` 的东半边终止、其余标记半边空置的简单弧 (arc) 质量 `@@M@@A(p,p')\le b^C@@`，只要 `@@M@@L_Y\ge L_X\ge L_*@@` 且 `@@M@@X@@` 组上位占比至少 `@@M@@1/2-\delta_1@@`；不要求 `@@M@@L_X/L_Y@@` 有正下界，即两墙周期可任意悬殊。

## 证明思路

第一步是精确表示：把 `@@M@@\mathcal C(p,p')@@` 写成半圆柱真空 (vacuum) 态的双线性自旋收缩 (spin contraction)，闭圈权 `@@M@@k^2+k^{-2}=0@@` 使所有未标记圈成对相消，而一段比较切向转向数与东西穿越数的拓扑论证（`@@M@@W=-2\pi F_X@@`）保证标记圈相位为一，于是正的物理量被无遗漏编码。再用一族完备的对偶余向量 (dual covectors)——依赖 Yang–Baxter 辫恒等式与幺正性——把收缩解析成保持精确归一化的有限围道积分 (contour integral) 恒等式。第二步处理分母：真空多项式归一化的下界须对两种位点高度占比任意悬殊的情形一致成立；证明把一个 Pfaffian 比写成关于正概率测度的期望（de Bruijn 行列式–Pfaffian 积分恒等式，加上 Rolle 定理归纳给出的实指数全正性），用 Jensen 不等式放缩，再对参考谱测度做形变并以 Cauchy 插值公式计算首阶对数变分，系数 `@@M@@5/24@@` 恰来自一个显式对数积分 `@@M@@\int_{\R}S=\frac{5\pi^2}{72\beta}@@`。第三步构造"磁性"围道：把主围道弯成虚部原函数的水平集曲线，使中心化测度 `@@M@@\nu_X@@` 实且正；一列 Fourier 符号计算给出平均恒等式，使普通位点点对因子与 `@@M@@\prod H_*(a_i-a_j)^2@@` 精确对消。实能量 `@@M@@B(\xi)=\tfrac12(\xi,\Re H\,\xi)@@` 的强制性 (coercivity) 先在水平边界线上对七个粒子种类验证：把符号按 `@@M@@\cosh(\beta k/8)-1@@` 展开为多项式，低次系数用有理消元逐主元验证正定，高次系数用加权严格对角占优；随后经调和扫除 (balayage) 与 Dirichlet 原理下非负的 Green 能量把估计转到曲围道，常数在曲线贴边时仍一致。第四步用试验场把粒子推离自然区间：虚位移场在公共区间增益 `@@M@@2L_X@@`，`@@M@@L_X@@` 与 `@@M@@L_Y@@` 之间的两肩用另一种平方配凑控制，且活动度求和与归一化都保留而非吸收进尺寸常数；结合非等墙行列式、参考测度归一化与有限秩粒子输运，合成尖锐的双标记估计。最后，平面上每个足够长的多边形有固定比例的有序标记对落入该估计的适用域，据此求和即得主定理——无需对每一对标记都一致。单弧结论精度要求更低：探针留数给出粒子束缚，两个半质量使涨落场中性化，粗糙的实参考比较即可，故论证在两墙任意悬殊的更大参数域上仍然成立。

## 可信度与备注

本文暂无形式化证明，请以社区核验为准。它是结果族 237 的组件：姊妹篇证明桥 (bridge) 平均长 `@@M@@R^{4/3+o(1)}@@` 与分离多边形配分函数估计，处理"路径一侧"；本文的平方长度矩界处理"圈一侧"，共同支撑直径 `@@M@@n^{3/4+o(1)}@@` 主定理；文中源估计与粒子输运还直接改编自圆柱权重伴生文 [Electric] 并逐条验证其正则性假设。按 OpenAI 官方声明，未经形式化的结果可能有问题，读者应以社区核验为准。

{% endraw %}
